### TÀI LIỆU TỔNG HỢP POWERSHELL CƠ BẢN ĐẾN NÂNG CAO (TIẾNG VIỆT)

---

## 1. **Các lệnh cơ bản (Command)**

### 📌 Danh sách lệnh

- `Get-Command` # Liệt kê tất cả lệnh có thể dùng (cmdlet, function, binary...)
- `Get-Command -Module Microsoft*` # Liệt kê lệnh trong các module có tên bắt đầu bằng "Microsoft"
- `Get-Command -Name *item` # Tìm các lệnh có tên chứa "item"
- `Get-Command -CommandType Cmdlet` # Chỉ lấy các lệnh dạng cmdlet
- `Get-Command -CommandType Function` # Lấy các hàm người dùng tự định nghĩa
- `Get-Command -Noun Process` # Các lệnh liên quan đến Process
- `Get-Command -Verb Get` # Các lệnh có động từ Get

### 📌 Trợ giúp (Help)

- `Get-Help` # Hiển thị hệ thống trợ giúp
- `Get-Help -Name Get-Command` # Hướng dẫn chi tiết cho Get-Command
- `Get-Help -Name about_Variables` # Chủ đề nâng cao về biến
- `Get-Help -Parameter *` # Tra cứu các tham số có sẵn
- `Update-Help` # Cập nhật tài liệu trợ giúp từ Microsoft
- `Get-Help Get-Process -Examples` # Xem ví dụ cụ thể

---

## 2. **Toán tử (Operators)**

### 📌 Gán và toán học:

```powershell
$a = 2           # Gán giá trị
$a += 3          # Tăng thêm 3
$a -= 1          # Giảm 1
$a *= 4          # Nhân 4
$a /= 2          # Chia 2
$a %= 3          # Lấy phần dư chia 3
```

### 📌 So sánh:

```powershell
$a -eq 10        # So sánh bằng
$a -ne 5         # So sánh khác
$a -gt 7         # Lớn hơn
$a -lt 100       # Nhỏ hơn
$a -ge 0         # Lớn hơn hoặc bằng
$a -le 9         # Nhỏ hơn hoặc bằng
```

### 📌 Chuỗi:

```powershell
"abc" -like "a*"               # Chuỗi bắt đầu bằng "a"
"abc" -notlike "z*"           # Không bắt đầu bằng "z"
"Hello" -match "^H"           # Bắt đầu bằng H
"value" -in @("a","b","value")  # Có trong danh sách
"value" -notin @("x","y")    # Không có trong danh sách
```

### 📌 Kiểu dữ liệu:

```powershell
5 -is [int32]           # Kiểu số nguyên 32-bit
"5" -isnot [int]        # Không phải số nguyên
$true -is [bool]        # Là boolean
'abc' -is [string]      # Là chuỗi
```

---

## 3. **Biểu thức chính quy (Regex)**

```powershell
"PowerShell" -match '^P.*l$'   # Bắt đầu bằng P và kết thúc bằng l
$matches[0]                     # Lấy kết quả khớp đầu tiên
@("cat", "dog") -match '^d'    # Chỉ chuỗi bắt đầu bằng "d"
$regex = [regex]'\d{3}-\d{2}'  # Pattern cho chuỗi số kiểu 123-45
$regex.Matches('123-45 567-89').Value  # Lấy danh sách các chuỗi khớp
```

---

## 4. **Câu lệnh điều khiển (Flow Control)**

```powershell
if ($a -gt 0) { "Dương" } elseif ($a -lt 0) { "Âm" } else { "Bằng 0" }

while ($true) {
  "Lặp vô hạn"
  break
}

for ($i = 0; $i -lt 3; $i++) {
  Write-Host "Lần $i"
}

foreach ($item in @("a","b")) {
  Write-Output $item
}

switch (3) {
  1 { "Một"; break }
  3 { "Ba"; break }
  default { "Không xác định" }
}
```

---

## 5. **Biến (Variables)**

```powershell
$name = "PowerShell"
[int]$count = 10
New-Variable -Name 'status' -Value 'OK'
Set-Variable -Name 'x' -Value 99
Get-Variable | Where-Object { $_.Name -like '*a*' }
Clear-Variable -Name 'x'
Remove-Variable -Name 'status'
```

---

## 6. **Hàm (Functions)**

```powershell
function Greet {
    [CmdletBinding()]
    param (
        [Parameter(Mandatory=$true)]
        [string]$Name,

        [string]$Language = 'vi'  # Mặc định: tiếng Việt
    )

    switch ($Language.ToLower()) {
        'vi' { return "Xin chào $Name" }
        'en' { return "Hello $Name" }
        'jp' { return "こんにちは $Name さん" }
        'fr' { return "Bonjour $Name" }
        default { return "[!] Ngôn ngữ không hỗ trợ: $Language" }
    }
}

# Ví dụ:
Greet -Name "Thái"
Greet -Name "Thái" -Language "en"

########################

function Multiply {
    [CmdletBinding()]
    param (
        [Parameter(Mandatory=$true)]
        [double]$x,

        [Parameter(Mandatory=$true)]
        [double]$y
    )

    return [math]::Round($x * $y, 2)
}

# Ví dụ:
Multiply 4.5 2        # => 9.0
Multiply -x 5 -y 3.14 # => 15.7

###########################

function Process-List {
    [CmdletBinding()]
    param (
        [Parameter(Mandatory=$true, ValueFromPipeline=$true)]
        [string[]]$Items
    )

    process {
        foreach ($item in $Items) {
            if ($item.Trim()) {
                Write-Output "📦 Mục: $item"
            }
        }
    }
}

# Ví dụ:
Process-List -Items @("Táo", "Nho", "Chuối", "")
# Hoặc dùng pipeline:
"Cam", "Ổi", "Bưởi" | Process-List
```

---

## 7. **Module & Thư viện**

```powershell
Get-Module -All                 # Tất cả module trong session
Get-Module -ListAvailable       # Các module đã cài
Import-Module Az.Accounts       # Nạp module
Remove-Module Az.Accounts       # Gỡ bỏ khỏi session
New-Module -ScriptBlock {
  function Test { "OK" }
} -Name tempmod | Import-Module
```

---

## 8. **Quản lý module từ Gallery**

```powershell
Register-PSRepository -Name MyRepo -SourceLocation "https://example.com"
Find-Module -Tag networking
Install-Module -Name Pester -Scope CurrentUser
Save-Module -Name Az -Path "C:\ps-modules"
Uninstall-Module -Name Pester
```

---

## 9. **Tương tác hệ thống tệp (Filesystem)**

```powershell
New-Item "C:\data" -ItemType Directory
New-Item "C:\data\info.txt" -ItemType File
Set-Content "C:\data\info.txt" -Value "Demo"
Add-Content "C:\data\info.txt" -Value "Thêm dòng"
Get-Content "C:\data\info.txt"
Remove-Item "C:\data\info.txt" -Force
```

---

## 10. **Bảng băm (Hashtable)**

```powershell
$user = @{
  Username = "admin"
  Roles = @("user", "editor")
}
$user.Username
$user["Roles"] += "admin"
$user.Email = "admin@example.com"
```

---

## 11. **Thông tin hệ thống (WMI)**

```powershell
Get-CimInstance Win32_ComputerSystem
Get-CimInstance Win32_LogicalDisk -Filter "DriveType=3"
Get-CimInstance Win32_NetworkAdapter | Where-Object { $_.NetEnabled -eq $true }
```

---

## 12. **Sự kiện bất đồng bộ (Event)**

```powershell
$timer = New-Object Timers.Timer
$timer.Interval = 3000
Register-ObjectEvent -InputObject $timer -EventName Elapsed -Action {
  Write-Host "Đã hết 3 giây"
}
$timer.Start()
```

---

## 13. **Ổ ảo PowerShell (PSDrive)**

```powershell
New-PSDrive -Name X -PSProvider FileSystem -Root "D:\Project" -Persist
Set-Location X:
Get-ChildItem
Remove-PSDrive -Name X
```

---

## 14. **Xử lý dữ liệu**

```powershell
Get-Service | Sort-Object Status
Get-Service | Where-Object { $_.Status -eq 'Running' }
Get-Process | Group-Object -Property Company
```

---

## 15. **Lập trình hướng đối tượng (Class)**

```powershell
class Laptop {
  [string]$Brand
  [int]$RAM
  [string] Specs() { return "$($this.Brand) - $($this.RAM)GB" }
}
$l = [Laptop]::new()
$l.Brand = 'Dell'
$l.RAM = 16
$l.Specs()
```

---

## 16. **Gọi API (REST)**

```powershell
$params = @{
  Uri = 'https://jsonplaceholder.typicode.com/posts/1'
  Method = 'Get'
  Headers = @{ Accept = 'application/json' }
}
Invoke-RestMethod @params
```

---

