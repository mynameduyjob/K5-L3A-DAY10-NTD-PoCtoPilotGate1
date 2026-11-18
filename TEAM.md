# Team

## Thông tin nhóm

- Tên nhóm (`TenNhom`, không dấu, không khoảng trắng): `NTD`
- Lớp: `L3A`
- Repo của bàn: `K5-L3A-DAY10-NTD-PoCtoPilotGate1` (https://github.com/mynameduyjob/K5-L3A-DAY10-NTD-PoCtoPilotGate1)
- Thẻ sự cố đã bốc (S1–S8): *(điền ở phút 125)*

## Thành viên

Họ tên đầy đủ và MSSV của **mọi** thành viên; thêm dòng nếu cần. Vai: Kỹ sư cổng · Sản phẩm và kinh doanh · Vận hành và pháp lý (README mục 3, phút 0–15).

| STT | Họ và tên | MSSV | Vai | Trưởng nhóm |
| --: | --------- | ---- | --- | :---------: |
|   1 | Phạm Duy Đức | 2A202603611 | Sản phẩm và kinh doanh | X |
|   2 | Nguyễn Trần Tú Trân | 2A202603603 | Kỹ sư cổng | |
|   3 | Phạm Thị Hồng Ngọc | 2A202603602 | Vận hành và pháp lý | |

### Phân công theo vai

| Vai | Người | Câu của đề · mục phiếu | File phụ trách |
|---|---|---|---|
| Sản phẩm và kinh doanh (trưởng nhóm) | Phạm Duy Đức | 1.1–1.6 (Phiếu A, A1–A5) · 2.3 bản đồ dữ liệu, drift (B3) · 2.9 cổng `business` (B7.4) · quyết định v1 (B8) và v2 (C12) | `config/acceptance_criteria.json` (ký một lần), `config/operating_gates.json` mục `business` |
| Kỹ sư cổng | Nguyễn Trần Tú Trân | 2.1 (B0, B1) · 2.2 soát lỗi `T-002@55` (B2) · 2.6–2.8 cổng code, chống rò rỉ, ticket hiểm `--adhoc` (B7.1–B7.3) · 3.0–3.6 trace thẻ, C2, C5–C9 · lệnh 2–6 | `lab10/guards.py` (`pre_guard`, `write_gate`), `lab10/monitors.py` (`MONITORS`) |
| Vận hành và pháp lý | Phạm Thị Hồng Ngọc | 2.4 HAZOP vòng 1 + checklist 9 nhóm có PIC (B4, B5) · 2.10 cổng `operations`, `legal`, runbook 1–3, giờ cao điểm (B7.5, B7.6) · C3, C4 HAZOP thẻ, C10 risk register, C11 runbook 4–5 · lệnh 7 | `config/operating_gates.json` mục `operations`, `legal`; `submission/submission.json` |
| Cả bàn | Đức · Trân · Ngọc | 2.5 pre-mortem bốn lăng kính (B6) · demo, phản biện | `templates/form-*.md` |

Ghi `members` trong `submission/submission.json` theo dạng `"HoVaTen-MSSV"`, khớp bảng trên.

## Cá nhân

Mỗi thành viên tự viết một mục bên dưới (chép mẫu, đổi tiêu đề thành họ tên không dấu và MSSV, ví dụ `## NguyenVanAn-20241234`).


## PhamDuyDuc-2A202603611

### Phần việc phụ trách

Trưởng nhóm · Sản phẩm và kinh doanh. Phụ trách câu 1.1–1.6 (Phiếu A, mục A1–A5), câu 2.3 (Bản đồ dữ liệu và ví dụ drift, Phiếu B mục B3), câu 2.5 (lăng kính Kinh doanh trong Pre-mortem, Phiếu B mục B6), câu 2.9 (Cổng kinh doanh, Phiếu B mục B7.4), quyết định v1 (Phiếu B mục B8) và câu 3.2, quyết định v2 (Phiếu C mục C5, C12). File phụ trách: `config/acceptance_criteria.json` (ký một lần), `config/operating_gates.json` mục `business`, `templates/form-a-criteria.md`, `templates/form-b-evaluation-gates.md` (B3, B6, B7.4, B8). Đẩy commit ký tiêu chí, chốt vòng 1 và bài nộp lên `origin`.

### Đóng góp cụ thể

- Khởi tạo và cấu hình Git repository cho bàn (`K5-L3A-DAY10-NTD-PoCtoPilotGate1`), gắn remote `origin` (repo bàn) và `upstream` (repo mẫu giảng viên), cấu hình danh tính Git trưởng nhóm (`2A202603611`).
- Hoàn thiện toàn bộ **Phiếu A (`templates/form-a-criteria.md`, mục A1–A5)**:
  - Xác định mục tiêu cấp hệ thống của trợ lý hoàn tiền LogiX-VN (A1 · câu 1.1) và mục tiêu nhìn từ kế toán đối soát Phạm Kiều Oanh (`NV-OANH`) cùng trưởng ca CSKH Trần Thị Hạnh (`NV-HANH`) (câu 1.2).
  - Thiết kế thước đo Offline cho bước `file_carrier_fault` và Telemetry production theo dõi tỉ lệ khiếu nại lỗi hãng theo ca 4h / 24h (A2 · câu 1.3, 1.4).
  - Phân tích khoảng tin cậy 95% bootstrap ở câu 1.5 (chọn kết luận `(b)`, giải thích vì sao chênh lệch 1/50 lần chạy nằm trong CI 95% `[0,9400; 1,0]`).
  - Xây dựng Bản tiêu chí thành công (A4 · câu 1.6) kèm hành động cụ thể, ranh giới đầu ra (cấm tự hoàn vượt `auto_limit_vnd = 200.000đ` hoặc vượt `300.000đ/khách/ngày` khi không có `approval_id` hợp lệ), soát qua 4 câu hỏi và thiết lập nhóm `business_ops` (`cost_per_ticket_vnd_max: 10000`, `roi_min: 0.2`, `queue_stuck_max: 0`).
- Điền và ký niêm phong `config/acceptance_criteria.json` bằng `python -m lab10.criteria sign` trước khi chạy đánh giá lần nào (A5).
- Hoàn thiện **Bản đồ dữ liệu và phân tích Drift (Phiếu B mục B3 · câu 2.3)**: phân tách nguồn sự thật (`orders[].parcels[].promised_date`, `delivered_date`, `delay_cause`, `policies`) với bản sao/lời khai trong `ticket.text`; chỉ ra ví dụ concept drift cụ thể vào ngày `2026-12-01` khi chính sách chuyển từ `REFUND-v3` sang `REFUND-v4` (`FORCE_MAJEURE` vẫn hoàn phí cho khách nhưng không còn nằm trong `fault_causes` để phạt hãng, `auto_limit_vnd` giảm từ `200.000đ` xuống `100.000đ`).
- Đóng góp lăng kính **Kinh doanh** trong Pre-mortem (Phiếu B mục B6 · câu 2.5) và thiết lập **Cổng kinh doanh (`config/operating_gates.json` mục `business` & Phiếu B mục B7.4 · câu 2.9)**:
  - Đặt `daily_refund_cap_vnd: 2000000` khớp ngân sách `daily_auto_refund_budget_vnd` của Finance.
  - Đặt `cost_budget_per_ticket_vnd: 1000` để sau khi cộng phí `policy_check` (`200đ`), retry (`200đ`), `confirm` (`100đ`), `decision_note` (`100đ`), tổng tiền LLM mỗi ticket không bao giờ vượt trần `max_llm_cost_per_ticket_vnd = 1500đ`.
  - Đặt `pilot_scope: {"mode": "warehouse", "warehouses": ["HN", "HCM", "DN", "CT"], "percent": 100}` để phục vụ 100% đơn lẻ cá nhân ở 4 kho bán lẻ và loại trừ kho sỉ `HCM-B2B` (đơn từ 2 triệu đồng luôn vượt `auto_limit_vnd` phải chuyển người duyệt tốn `10.000đ` công duyệt + phí LLM > `10.000đ` làm tay).
  - Đặt `roi_min: 0.2` và soạn khung **Quyết định Gate 1 · v1 (Phiếu B mục B8)**.

### Bằng chứng

- Mã commit ký tiêu chí: `7059dbb` (`Sign acceptance criteria`, SHA256 `e0527fc8d15c551af9d1316466b26ff2219395e80d229383e7f893766d45ca1d` trong `config/acceptance_criteria.lock`, ký lúc `2026-11-18T15:12:30`).
- Mã commit hoàn thiện Phiếu A, cổng kinh doanh và bản đồ dữ liệu trên nhánh cá nhân `PhamDuyDuc-2A202603611`: `1152571`.
- File và mục phiếu: `config/acceptance_criteria.json`, `config/acceptance_criteria.lock`, `config/operating_gates.json` (mục `business`), `templates/form-a-criteria.md` (mục A1–A5), `templates/form-b-evaluation-gates.md` (mục B3, B6 dòng Kinh doanh, B7.4, B8).

### Exit ticket

- **Một điều học được:** Hiểu rõ vì sao ở Gate 1 phải ký niêm phong `acceptance_criteria.json` bằng hash trước khi chạy `eval` lần đầu ("đặt luật trước, xem số sau"), cũng như cách một nhóm đơn hàng như kho sỉ `HCM-B2B` (giá trị đơn $\ge 2$ triệu đồng luôn vượt hạn mức tự động `200.000đ` phải chuyển người duyệt) làm chi phí mỗi ticket cộng phí LLM + công người duyệt (`10.000đ`) luôn đắt hơn làm tay dù model không hề chạy sai.
- **Một điều còn chưa chắc:** Khi chính sách đổi từ `REFUND-v3` sang `REFUND-v4` vào `2026-12-01` (hạn mức tự động giảm từ `200.000đ` xuống `100.000đ`), tỉ lệ ticket phải chuyển người duyệt (`escalation_rate`) sẽ tăng lên bao nhiêu phần trăm và liệu 1 người trực mỗi ca (`NV-HANH`, công suất 6 ca/giờ) có còn giữ được `queue_stuck = 0` mà không làm giảm ROI dưới ngưỡng `0.2` hay không.

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