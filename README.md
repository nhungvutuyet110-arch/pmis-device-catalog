# Kho danh mục thuộc tính PMIS

Repository công khai này là nguồn dữ liệu chỉ đọc cho PMIS Catalog Viewer.

## Quản trị

- Chỉ chủ repository và người được cấp quyền ghi mới sửa được danh mục.
- Người dùng extension chỉ tải công khai `catalog.json`; họ không có token và không thể ghi dữ liệu.
- Không đưa mã hệ thống, dữ liệu cá nhân, vị trí nhạy cảm hoặc thông tin không được phép công khai vào file.

## Cấu trúc dữ liệu

```json
{
  "version": 1,
  "updatedAt": "2026-07-10",
  "devices": [
    {
      "deviceType": "Tiếp địa 22kV",
      "templates": [
        {
          "id": "tiep-dia-r1c",
          "name": "R1C",
          "attributes": [
            { "name": "Số cọc", "value": "1.00" },
            { "name": "Mã hiệu", "value": "RC2" }
          ]
        }
      ]
    }
  ]
}
```

Thuộc tính không muốn hiển thị thì xóa khỏi mảng `attributes`. Thuộc tính có giá trị trống cũng nên được xóa.

## Xuất lại từ Excel

Chạy script `tools/excel_to_catalog.py` trong gói dự án. Script tạo đồng thời:

- `github-catalog/catalog.json`: tải lên GitHub.
- `pmis-autofill/catalog-data.js`: bản dự phòng đóng gói cùng extension.
