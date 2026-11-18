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

### Ai làm gì (CP1–CP3, theo lịch sử commit)

Cột "Theo phân công" lấy từ bảng trên. Cột "Thực tế làm" ghi đúng người đã viết/chạy, kèm commit hoặc mã lần chạy.

| Mốc | Việc | Mục / file | Theo phân công | Thực tế làm | Bằng chứng |
|---|---|---|---|---|---|
| CP1 | Bảng thành viên, chia vai | `TEAM.md` | Trưởng nhóm | Đức, Ngọc, Trân cùng sửa | `e35f49b` (Đức), `9b4c6a7` (Ngọc), `4f7a0da` (Trân) |
| CP2 | Câu 1.1–1.6, Phiếu A A1–A5 | `templates/form-a-criteria.md` | Đức | Đức | `1152571` |
| CP2 | Điền và ký tiêu chí (lệnh 1) | `config/acceptance_criteria.json`, `.lock` | Đức | Đức | `7059dbb` (ký 2026-11-18 15:12:30, đã push `main`) |
| CP2 | Sửa công thức câu 1.3 (lỗi oan so với `fault_causes`) | Phiếu A mục A2 | Đức | Trân (sửa theo review) | `84ccfbe` |
| CP3 | Câu 2.1 lần chạy base + `gate` | Phiếu B B0 dòng 1, B1 | Trân | Trân | `R-base-before-20261118-154100-bde05c` |
| CP3 | Câu 2.2 soát lỗi `T-002@55` | Phiếu B B2 | Trân | Trân | `84ccfbe` |
| CP3 | Câu 2.3 bản đồ dữ liệu, drift | Phiếu B B3 | Đức | Đức (Trân sửa dòng `index_active` của v4) | `1152571`, `84ccfbe` |
| CP3 | Câu 2.4 HAZOP vòng 1, checklist 9 nhóm | Phiếu B B4, B5 | Ngọc | Ngọc (Trân sửa tên trường theo `world.json`, dòng 1 và 4 của B5) | `2ecd269`, `84ccfbe` |
| CP3 | Câu 2.5 pre-mortem bốn lăng kính | Phiếu B B6 | Cả bàn | Trân soạn nháp; **cả bàn cần duyệt** | `0699b71` |
| CP3 | Câu 2.6 ba cổng vòng 1 | `lab10/guards.py`, Phiếu B B7.1 | Trân | Trân | `84ccfbe`, `R-base-after-20261118-154125-84ee27` |
| CP3 | Câu 2.7, 2.8 chống rò rỉ, 2 ticket hiểm | Phiếu B B7.2, B7.3 | Trân | Trân | `84ccfbe` |
| CP3 | Câu 2.9 cổng `business` | `config/operating_gates.json`, Phiếu B B7.4 | Đức | Đức | `1152571` |
| CP3 | Câu 2.10 cổng `operations`, `legal`, runbook 1–3, giờ cao điểm | `config/operating_gates.json`, Phiếu B B7.5, B7.6 | Ngọc | Ngọc (Trân sửa `pii_fields_blocked_to_third_party` và B7.6; Ngọc sửa trùng ở `d61411c`, bản trên `main` giữ bản của Trân) | `2ecd269`, `84ccfbe`, `R-base-after-20261118-155700-ff7de9` |
| CP3 | Lệnh 5 chốt vòng 1, mốc prepared, `gate` | `lab10/guards_round1.py`, `config/operating_gates.round1.json`, `config/round1.lock`, B0 dòng 3 | Trân | Trân | hash `e8c93d4a`, `R-base-prepared-20261118-164140-b5bfcd` |
| CP3 | Quyết định v1 (**Thu hẹp**) | Phiếu B B8 | Đức | Trân soạn theo report; **Đức cần xác nhận và ký** | commit chốt vòng 1 |
| CP3 | Gộp các nhánh, đẩy `main` | `main` | Đức | Trân | commit chốt vòng 1 |

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

- Chạy mốc base, đọc `gate`, điền B0, B1; dò `T-002@55`, điền bảng soát lỗi B2 (thêm lỗi thứ hai: `customer_note` gửi cho hãng mà `pii_leaks` không đếm).
- Viết 3 cổng vòng 1 trong `lab10/guards.py`: (1) `pre_guard` ghim chính sách theo ngày + `issue_refund` tính lại tiền từ tracking DB, chống ghi trùng, chặn fail-open và đổi người trả; (2) `file_carrier_fault` chỉ ghi khi có nguyên nhân lỗi hãng, đúng kiện, chưa chạm trần/ngày; (3) `notify_carrier` chỉ giữ `carrier_notice_fields`.
- Câu 2.7, 2.8 (B7.2, B7.3): 2 ticket hiểm `--adhoc`, cả hai giữ tính chất.
- Gộp phần của Đức và Ngọc, sửa các lỗi review (khoá PII, tên trường B4, câu 1.3), soạn nháp B6 và B8 cho bàn duyệt, chốt vòng 1 (lệnh 5), chạy mốc prepared.
- Dùng trợ lý AI (Claude) để đọc code `lab10/`, gợi ý cách viết cổng, soạn nháp phiếu và kiểm tra hash; mọi số trong phiếu lấy từ lần chạy thật.

### Bằng chứng

- Commit: `4f7a0da`, `84ccfbe`, `36645aa`, `0699b71`, commit chốt vòng 1 trên `main`.
- Lần chạy: `R-base-before-20261118-154100-bde05c` (base), `R-base-after-20261118-154125-84ee27` (cổng vòng 1), `R-base-after-20261118-155700-ff7de9` (sửa khoá PII), `R-base-prepared-20261118-164140-b5bfcd` (prepared).
- Hash chốt vòng 1: `e8c93d4a`. Phiếu B: B0 dòng 1–5, B1, B2, B7.1–B7.3.

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
