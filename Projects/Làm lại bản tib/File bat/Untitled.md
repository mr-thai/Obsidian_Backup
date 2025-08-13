```
@echo off
title Xoa phan vung Win 11 -> Data
color 0C
echo WARNING: Tat ca du lieu tren phan vung nay se bi XOA!
pause

REM Tạo script cho diskpart
(
echo select disk 0
echo list partition
echo select partition 2
echo delete partition override
echo create partition primary
echo format fs=ntfs quick label="Data"
echo assign letter=E
) > diskpart_script.txt

diskpart /s diskpart_script.txt
del diskpart_script.txt

pause
```
### Giải thích:

- `select disk 0` → Chọn ổ vật lý số 0.
    
- `list partition` → Liệt kê các phân vùng để bạn biết thứ tự (Partition 1 có thể là boot, Partition 2 là Win 11, Partition 3 là Win 10).
    
- `select partition 2` → Chọn phân vùng Win 11 (xác định bằng `list partition`).
    
- `delete partition override` → Xóa phân vùng này, bỏ qua mọi cảnh báo.
    
- `create partition primary` → Tạo phân vùng mới.
    
- `format fs=ntfs quick label="Data"` → Định dạng nhanh NTFS và đặt tên "Data".
    
- `assign letter=E` → Gán ký tự ổ đĩa E cho phân vùng mới.










```
rd /s /q "D:\FolderMuốnXoa"

```