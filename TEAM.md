# Team

## Thông tin nhóm

- Tên nhóm (`TenNhom`, không dấu, không khoảng trắng): NTD
- Lớp: `L3A`
- Repo của bàn: `K5-L3A-DAY10-NTD-PoCtoPilotGate1` (https://github.com/mynameduyjob/K5-L3A-DAY10-NTD-PoCtoPilotGate1)
- Thẻ sự cố đã bốc (S1–S8): (điền ở phút 125)

## Thành viên

Họ tên đầy đủ và MSSV của **mọi** thành viên; thêm dòng nếu cần. Vai: Kỹ sư cổng · Sản phẩm và kinh doanh · Vận hành và pháp lý (README mục 3, phút 0–15).

| STT | Họ và tên | MSSV | Vai | Trưởng nhóm |
| --: | --------- | ---- | --- | :---------: |
|   1 | Phạm Duy Đức | 2A202603611 | Sản phẩm và kinh doanh | ✓ |
|   2 | Nguyễn Trần Tú Trân | 2A202603603 | Kỹ sư cổng | |
|   3 | Phạm Thị Hồng Ngọc | 2A202603602 | Vận hành và pháp lý | |

Ghi `members` trong `submission/submission.json` theo dạng `"HoVaTen-MSSV"`, khớp bảng trên.

### Phân công theo vai

| Vai | Người | Câu của đề · mục phiếu | File phụ trách |
|---|---|---|---|
| Sản phẩm và kinh doanh (trưởng nhóm) | Phạm Duy Đức | 1.1–1.6 (Phiếu A, A1–A5) · 2.3 bản đồ dữ liệu, drift (B3) · 2.9 cổng `business` (B7.4) · quyết định v1 (B8) và v2 (C12) | `config/acceptance_criteria.json` (ký một lần), `config/operating_gates.json` mục `business` |
| Kỹ sư cổng | Nguyễn Trần Tú Trân | 2.1 (B0, B1) · 2.2 soát lỗi `T-002@55` (B2) · 2.6–2.8 cổng code, chống rò rỉ, ticket hiểm `--adhoc` (B7.1–B7.3) · 3.0–3.6 trace thẻ, C2, C5–C9 · lệnh 2–6 | `lab10/guards.py` (`pre_guard`, `write_gate`), `lab10/monitors.py` (`MONITORS`) |
| Vận hành và pháp lý | Phạm Thị Hồng Ngọc | 2.4 HAZOP vòng 1 + checklist 9 nhóm có PIC (B4, B5) · 2.10 cổng `operations`, `legal`, runbook 1–3, giờ cao điểm (B7.5, B7.6) · C3, C4 HAZOP thẻ, C10 risk register, C11 runbook 4–5 · lệnh 7 | `config/operating_gates.json` mục `operations`, `legal`; `submission/submission.json` |
| Cả bàn | Đức · Trân · Ngọc | 2.5 pre-mortem bốn lăng kính (B6) · demo, phản biện | `templates/form-*.md` |

## Cá nhân

Mỗi thành viên tự viết một mục bên dưới (chép mẫu, đổi tiêu đề thành họ tên không dấu và MSSV, ví dụ `## NguyenVanAn-20241234`).

## PhamDuyDuc-2A202603611

### Phần việc phụ trách

Trưởng nhóm · Sản phẩm và kinh doanh. Câu 1.1–1.6 (Phiếu A, A1–A5), câu 2.3 (B3), câu 2.9 (B7.4), quyết định v1 (B8) và v2 (C12). File: `config/acceptance_criteria.json`, `config/operating_gates.json` mục `business`. Đẩy commit ký tiêu chí, chốt vòng 1 và bài nộp lên `origin`.

### Đóng góp cụ thể

...

### Bằng chứng

Mã commit, mã lần chạy (`runs/<mã>`), dòng trong phiếu.

### Exit ticket

Một điều học được, một điều còn chưa chắc.

## NguyenTranTuTran-2A202603603

### Phần việc phụ trách

Kỹ sư cổng. Câu 2.1–2.2 (B0–B2), câu 2.6–2.8 (B7.1–B7.3), câu 3.0–3.6 (C0–C2, C5–C9). File: `lab10/guards.py` (`pre_guard`, `write_gate`), `lab10/monitors.py` (`MONITORS`). Chạy lệnh 2–6.

### Đóng góp cụ thể

...

### Bằng chứng

Mã commit, mã lần chạy (`runs/<mã>`), dòng trong phiếu.

### Exit ticket

Một điều học được, một điều còn chưa chắc.

## PhamThiHongNgoc-2A202603602

### Phần việc phụ trách

Vận hành và pháp lý. Câu 2.4 (B4, B5), câu 2.10 (B7.5, B7.6), C3, C4, C10, C11. File: `config/operating_gates.json` mục `operations`, `legal`; `submission/submission.json`. Chạy lệnh 7.

### Đóng góp cụ thể

...

### Bằng chứng

Mã commit, mã lần chạy (`runs/<mã>`), dòng trong phiếu.

### Exit ticket

Một điều học được, một điều còn chưa chắc.
