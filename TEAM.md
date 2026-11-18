# Team

## Thông tin nhóm

- Tên nhóm (`TenNhom`, không dấu, không khoảng trắng): NTD
- Lớp: `L3A`
- Repo của bàn: `K5-L3A-DAY10-NTD-PoCtoPilotGate1` (https://github.com/mynameduyjob/K5-L3A-DAY10-NTD-PoCtoPilotGate1)
- Thẻ sự cố đã bốc (S1–S8): S7 (Email pháp chế: lộ số điện thoại người nhận quà)

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

### Ai làm gì (CP1–CP5, theo lịch sử commit)

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
| CP4 | Nhận thẻ S7 (repo thẻ, đối chiếu hash MANIFEST), ghi `Thẻ đã bốc: S7` | `incidents/`, Phiếu C dòng đầu, `TEAM.md` | Đức | Trân | `07f5971`, `8b247c8` |
| CP4 | Câu 3.0 `grade --incident S7` trước khi sửa | Phiếu C C0 dòng 1, C1 | Trân | Trân | `R-S7-grade-20261118-165613-b5bfcd` |
| CP4 | Câu 3.1 trace ≥ 2 kiểu lỗi, bảng soát lỗi | Phiếu C C2 | Trân | Trân | `S7-01@11`, `S7-20@11`, `S7-04@11`, `S7-05@11` |
| CP4 | Câu 3.1 phần riêng thẻ S7 (C3.3 hiệu chỉnh lòng tin), HAZOP của thẻ | Phiếu C C3.3, C4 | Ngọc | Trân soạn nháp; **Ngọc đã duyệt** | `05ea3f9` (đối chiếu C3.3, C4 với thẻ S7) |
| CP4 | Câu 3.2, 3.3 specification, giả định môi trường | Phiếu C C5 | Trân | Trân | commit vòng 2 |
| CP4 | Câu 3.4 fault tree trước khi sửa | Phiếu C C6 | Trân | Trân | `R-S7-before-20261118-165613-b5bfcd` |
| CP4 | Câu 3.5 sửa: Cổng 3 ghi sự kiện `notice_fields_stripped`; bảng sửa | `lab10/guards.py`, Phiếu C C7 | Trân | Trân | `R-S7-after-20261118-165913-4cd37f` |
| CP4 | Câu 3.6 ba chỉ số theo dõi mới | `lab10/monitors.py`, Phiếu C C8 | Trân | Trân | `R-S7-after-20261118-170032-5d6948`, grade `R-S7-grade-20261118-170103-5d6948` (`PASS-VISIBLE`) |
| CP4 | Câu 3.7 fault tree sau khi sửa | Phiếu C C9 | Trân | Trân | `R-S7-after-20261118-170103-5d6948` |
| CP4 | Câu 3.7 risk register, checklist, runbook 4–5 | Phiếu C C10, C11 | Ngọc | Trân soạn nháp; **Ngọc đã duyệt** | `05ea3f9` (C10 Risk register, C11 checklist + Runbook 4–5) |
| CP5 | Quyết định v2 (**Tiếp tục**, 2 depot HN + HCM) + ba dòng bắt buộc | Phiếu C C12 | Đức | Trân soạn thay theo report; **Đức cần xác nhận và ký** | grade `R-S7-grade-20261118-170103-5d6948`, `R-S7-grade-20261118-195952-5d6948` (`PASS-VISIBLE`, "Được phép cân nhắc 'Tiếp tục'") |
| CP5 | Điền `submission.json` (team, members, incident S7, v1 Thu hẹp, v2 Tiếp tục, three_lines chép từ C12) | `submission/submission.json` | Ngọc | Trân điền thay; **Ngọc cần soát** | commit nộp bài |
| CP5 | Chạy lại lệnh 6 trước khi gom bài | `runs/` | Trân | Trân | `R-S7-grade-20261118-195952-5d6948` |
| CP5 | Lệnh 7 `check_submission --collect` tới `ĐỦ THÀNH PHẦN` | `submission/` | Ngọc | Trân chạy thay trên máy của Trân (nơi có `runs/journal.jsonl`) | commit nộp bài |
| CP5 | Demo ba mốc, phản biện | — | Cả bàn | **Chưa làm** (làm tại lớp) | — |
| CP5 | Nộp link repo trên LMS | LMS | Từng người | **Mỗi người tự nộp** | — |

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
- Vòng 2 (thẻ S7): nhận thẻ, `grade` trước khi sửa, dò 4 ticket, tìm 2 nguyên nhân độc lập (`customer_note` chép chữ khách gõ; `recipient_contact` tự thêm khi `is_gift`); thêm sự kiện `notice_fields_stripped` ở Cổng 3 và 3 monitor; điền Phiếu C C0–C11 (C3.3, C4, C10, C11 là nháp cho Ngọc duyệt).
- Dùng trợ lý AI (Claude) để đọc code `lab10/`, gợi ý cách viết cổng, soạn nháp phiếu và kiểm tra hash; mọi số trong phiếu lấy từ lần chạy thật.

### Bằng chứng

- Commit: `4f7a0da`, `84ccfbe`, `36645aa`, `0699b71`, commit chốt vòng 1 trên `main`.
- Lần chạy: `R-base-before-20261118-154100-bde05c` (base), `R-base-after-20261118-154125-84ee27` (cổng vòng 1), `R-base-after-20261118-155700-ff7de9` (sửa khoá PII), `R-base-prepared-20261118-164140-b5bfcd` (prepared).
- Hash chốt vòng 1: `e8c93d4a`. Phiếu B: B0 dòng 1–5, B1, B2, B7.1–B7.3.
- Vòng 2: `R-S7-grade-20261118-165613-b5bfcd` (trước khi sửa), `R-S7-grade-20261118-170103-5d6948` (`PASS-VISIBLE`), `R-base-after-20261118-170033-5d6948` (không regression). Phiếu C: C0–C11.

### Exit ticket

- **Một điều học được:** chặn theo **danh sách được phép** khác hẳn chặn theo **mẫu dò**. Cổng 3 chỉ cho đi 4 trường trong hợp đồng nên đỡ trọn thẻ S7 ngay từ vòng 1 (lộ dữ liệu 30 → 0 ở mốc prepared), kể cả ca `S7-04` chỉ có địa chỉ và ca `S7-20` khách không gõ gì; nếu dò mẫu số điện thoại thì đã lọt `S7-04` và che nhầm mã vận đơn ở `S7-05`. Cũng học được rằng chỉ số `pii_leaks` cũ báo 0 trong khi 55/110 lần chạy bộ nền vẫn gửi chữ khách gõ cho hãng: một con số "sạch" chưa chắc là đã đo đúng chỗ.
- **Một điều còn chưa chắc:** cổng lọc theo **tên trường** chứ không kiểm **giá trị**; nếu kho nhập cả địa chỉ nhà vào `district` thì vẫn lộ (đã ghi ở risk register C10). Chưa chắc bài kiểm tra ẩn có ca như vậy không, và chưa chắc cổng 2 (ghi lỗi hãng) chạy đúng với đơn nhiều kiện vì bộ nền lẫn gói S7 chưa kích hoạt nó lần nào.

## PhamThiHongNgoc-2A202603602

### Phần việc phụ trách

Vận hành và pháp lý. Câu 2.4 (B4, B5), câu 2.10 (B7.5, B7.6), C3.3, C4, C10, C11. File: `config/operating_gates.json` mục `operations`, `legal`; `submission/submission.json`.

### Đóng góp cụ thể

- Vòng 1: điền cổng `operations` (`pic: NV-TUNG`, `approver_id: NV-HANH`, `reviewers_on_shift: 1`, `review_capacity_per_hour: 6`, `max_queue_wait_minutes: 60`, `stop_conditions`, `alert_channel`) và `legal` (`pii_fields_blocked_to_third_party`, `carrier_fault_requires_recorded_cause: true`) trong `config/operating_gates.json`.
- Viết Phiếu B: B4 (HAZOP vòng 1 trên `file_carrier_fault` + 3 dòng ngoài kỹ thuật), B5 (Checklist 9 nhóm việc kèm PIC có tên), B7.5 (Runbook phần 1–3), B7.6 (Giờ cao điểm); sửa các điểm review CP3 (khớp khóa PII `["recipient_contact", "customer_note"]`, tên trường thật trong `data/world.json`, giả định giờ cao điểm từ `ops_facts`).
- Vòng 2 (thẻ S7): rà soát và duyệt các mục C3.3 (Hiệu chỉnh lòng tin), C4 (HAZOP của thẻ trên `notify_carrier`), C10 (Risk register), C11 (cập nhật checklist + Runbook 4–5).

### Bằng chứng

- Commit: `2ecd269`, `d61411c` (vòng 1 + sửa review CP3); `05ea3f9` (duyệt C3.3, C4, C10, C11).
- File & phiếu: `config/operating_gates.json` (mục `operations`, `legal`), Phiếu B (B4, B5, B7.5, B7.6), Phiếu C (C3.3, C4, C10, C11).

### Exit ticket

- **Điều học được:** Một cổng pháp lý/vận hành chỉ thực sự **bảo đảm** an toàn khi vừa khớp đúng tên trường ở tầng dữ liệu thực tế (whitelist `carrier_notice_fields` và khóa cấp đầu `recipient_contact`, `customer_note`) vừa có runbook quy định rõ người bấm dừng, ngưỡng đỏ và cách xử lý với bên thứ ba.
- **Điều còn chưa chắc:** Với các trường được phép gửi như `district`, nếu kho nhập tay lẫn địa chỉ chi tiết vào ô quận/huyện thì bộ lọc theo tên khóa hiện tại chưa chặn được; cần kiểm chứng thêm bằng bước kiểm tra danh mục quận/huyện và theo dõi số liệu thật trong pilot trước Bước đánh giá 2.
