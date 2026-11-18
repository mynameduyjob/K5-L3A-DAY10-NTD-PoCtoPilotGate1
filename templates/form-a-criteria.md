# Phiếu A · Tiêu chí và cách đo · Khối 1 (phút 15–65)

**Bàn:** K5-L3A-DAY10-NTD-PoCtoPilotGate1 · **Người cầm bút chính:** vai Sản phẩm và kinh doanh (Phạm Duy Đức) (câu 1.3: Kỹ sư cổng; câu 1.2, 1.4: Vận hành và pháp lý)

Điền phiếu này **trước khi chạy trợ lý lần nào**. Viết xong thì chép ngưỡng sang `config/acceptance_criteria.json`, ký ở phút 60–65,
rồi mới chạy đánh giá. Khối 1 không sửa code.

**Mục lục**
- [A1 · Mục tiêu (câu 1.1, 1.2) · phút 15–20](#a1)
- [A2 · Thước đo → Dữ liệu → Cách tính (câu 1.3, 1.4) · phút 20–35](#a2)
- [A3 · Đọc một kết quả có khoảng tin cậy (câu 1.5) · phút 35–40](#a3)
- [A4 · Câu tiêu chí thành công và ranh giới đầu ra (câu 1.6) · phút 40–60](#a4)
- [A5 · Ký và đẩy tiêu chí · phút 60–65](#a5)

---

<a id="a1"></a>

## A1 · Mục tiêu (phút 15–20)

### Câu 1.1 · Một mục tiêu cấp hệ thống (khác "model trả lời đúng")

> Tự động hoá xử lý khiếu nại hoàn tiền do giao trễ, giảm thời gian giải quyết ticket từ 24h xuống dưới 15 phút, đồng thời đảm bảo tính toàn vẹn tài chính (0 đồng hoàn sai, 0 lỗi oan cho đối tác vận chuyển) và chi phí vận hành máy trên mỗi ticket thấp hơn chi phí làm tay (10.000đ/ticket).

### Câu 1.2 · Mục tiêu nhìn từ hai người

- Chị Oanh, kế toán đối soát (không dùng trợ lý, nhưng phải khớp sổ với hãng và shop mỗi tuần): Mọi khoản tiền hoàn ghi sổ cái (`ledger`) phải có căn cứ chính sách rõ ràng, 100% khớp với tracking thực tế; không có tình trạng ghi nhận lỗi sai hoặc phạt nhầm hãng vận chuyển (0 lỗi oan) làm phát sinh khiếu nại đối soát hoặc lệch dòng tiền cuối tuần.
- Chị Hạnh, trưởng ca CSKH (phải duyệt những ca trợ lý chuyển sang): Trợ lý chỉ chuyển các ca thực sự phức tạp hoặc vượt hạn mức thẩm quyền (tỉ lệ chuyển dưới 30%), mỗi ca chuyển phải có kèm lý do/bối cảnh rõ ràng để xử lý nhanh dưới 10 phút, không làm quá tải hàng chờ hay gây ùn ứ ticket quá hạn SLA 60 phút.

---

<a id="a2"></a>

## A2 · Thước đo → Dữ liệu → Cách tính (phút 20–35)

**Khung tư duy.** Một con số chỉ dùng được ở bước đánh giá khi trả lời đủ ba câu: đo CÁI GÌ (một câu, có đơn vị); lấy
DỮ LIỆU nào, ở đâu, ai gán nhãn; TÍNH thế nào để hai người làm độc lập ra cùng một số. Thiếu ô thứ ba thì chưa phải thước đo.

**Câu hỏi dẫn dắt**
- Thước đo này nói về MỘT bước của agent hay cả luồng? Nếu cả luồng hỏng, nó có chỉ ra bước nào hỏng không?
- Dữ liệu đã có sẵn (trace, sổ cái) hay phải thu thêm? Nhãn đúng/sai đến từ đâu?
- Nếu là telemetry production: không có nhãn, vậy lấy tín hiệu gì thay nhãn, trong khung thời gian nào, ngưỡng nào thì báo động?

### Câu 1.3 · Offline metric cho MỘT bước · Câu 1.4 · Telemetry production

Câu 1.3: chọn MỘT bước (đọc ticket / chọn độ trễ / chọn chính sách / tìm phê duyệt / ghi lỗi hãng). Câu 1.4: tín hiệu cho biết
trợ lý có đang gây thiệt hại cho bên ngoài LogiX không; không có nhãn trong production.

| | Offline, cho MỘT bước (câu 1.3) | Telemetry production (câu 1.4) |
|---|---|---|
| **Bước / hành vi được đo** | Bước: **Ghi lỗi hãng vận chuyển** (`file_carrier_fault`) | Hành vi: **Khiếu nại/tranh chấp từ hãng vận chuyển về các khoản phạt lỗi giao hàng** |
| **Thước đo** (một câu, có đơn vị) | Tỉ lệ ghi lỗi hãng oan (số lần ghi lỗi hãng khi tracking không xác nhận lỗi do carrier), đơn vị: % hoặc số ca (max = 0 ca). | Tỉ lệ ticket bị hãng vận chuyển khiếu nại bác bỏ lỗi trên tổng số lỗi đã ghi trong ngày, đơn vị: %. |
| **Dữ liệu** (lấy ở đâu, bao nhiêu, ai gán nhãn) | Lấy sự kiện `carrier_fault` trong trace của đợt chạy eval (22 ticket × 5 seed) so sánh với trường `delay_cause` trong `parcels` của đơn hàng tại `data/world.json`. Nhãn ground truth là dữ liệu hệ thống tracking. | Dữ liệu từ cổng tiếp nhận khiếu nại đối soát B2B của LogiX (chị Oanh quản lý) và nhật ký webhook báo lỗi hãng trong ngày. |
| **Cách tính** (công thức, mẫu số, cách xử lý ca thiếu dữ liệu) | $\text{Wrongful Carrier Faults} = \sum [\text{agent ghi lỗi hãng NHƯNG } delay\_cause \notin fault\_causes \text{ của chính sách đang hiệu lực, hoặc số ngày trễ theo tracking} < min\_days\_fee]$ (REFUND-v3: `fault_causes = [CARRIER, FORCE_MAJEURE]`, `min_days_fee = 3`; từ REFUND-v4 chỉ còn `CARRIER`). Nếu thiếu thông tin tracking, ca đó bắt buộc phải chuyển người duyệt, nếu agent tự ghi lỗi thì tính là 1 vi phạm. | $\text{Dispute Rate} = \frac{\text{Số ticket bị hãng khiếu nại trong ngày}}{\text{Tổng số ticket bị ghi lỗi tự động trong ngày}} \times 100\%$. Nếu mẫu số = 0 thì Dispute Rate = 0%. |
| **Khung thời gian / ngưỡng báo động** | (không áp dụng) | Khung thời gian: theo dõi theo từng ca làm việc (4 giờ) và tổng kết mỗi 24 giờ. Ngưỡng báo động: Vàng nếu $> 1\%$, Đỏ (báo động khẩn cấp dừng auto-fault) nếu $> 3\%$ hoặc có $\ge 2$ khiếu nại liên tiếp từ cùng một hãng. |
| **Điểm mù** (thước đo này KHÔNG thấy gì) | Không phát hiện được trường hợp chính hệ thống tracking DB bị tài xế/kho ghi nhận sai nguyên nhân từ đầu. | Không phát hiện được các lỗi mà hãng vận chuyển chấp nhận bỏ qua hoặc không đối soát kịp trong ngày (độ trễ phản hồi từ đối tác). |

---

<a id="a3"></a>

## A3 · Đọc một kết quả có khoảng tin cậy (phút 35–40)

### Câu 1.5 · Chọn MỘT kết luận và giải thích một câu

Số minh hoạ trong đề (không phải số của bàn). Khoanh: **(b)**

Giải thích một câu: Khoảng tin cậy 95% của bản X là [0,9400; 1,0] bao trùm cả giá trị pass_rate 1,0 của bản Y, sự chênh lệch 1 lần chạy (49/50 so với 50/50) hoàn toàn có thể do ngẫu nhiên của mẫu thử nên chưa đủ ý nghĩa thống kê để khẳng định Y vượt trội hơn X.

---

<a id="a4"></a>

## A4 · Câu tiêu chí thành công (phút 40–60)

### Câu 1.6 · Bản tiêu chí

**Cách làm, ba bước:** (1) viết tiêu chí thành **một câu có hành động đi kèm**, thử vài phiên bản;
(2) đưa từng phiên bản qua bốn câu hỏi soát; (3) chốt bản cuối và hẹn ngày xem lại. Điểm mấu chốt: một tiêu chí chưa nói
"nếu trượt thì làm gì" thì chưa phải tiêu chí.

#### Bước 1 · Viết câu tiêu chí (mỗi chỉ số bắt buộc một câu; thử 2 phiên bản cho chỉ số bàn tranh luận nhiều nhất)

> Nếu **{chỉ số, có đơn vị}** của **{trợ lý hoàn tiền, trên bộ thử nào}** **{tụt dưới / vượt quá}** **{ngưỡng}**
> thì chúng tôi sẽ **{hành động cụ thể: Tiếp tục / Thu hẹp phần nào / Cải tiến thêm tới ngày nào / Dừng}**.

| Chỉ số (khoá trong `acceptance_criteria.json`) | Phiên bản 1 | Phiên bản 2 (nếu có) |
|---|---|---|
| `pass_rate_min` | Nếu pass_rate trên bộ nền tụt dưới 0.95 thì chúng tôi sẽ Cải tiến thêm cổng kiểm tra logic trước khi xem xét pilot. | Nếu pass_rate trên bộ nền tụt dưới 0.90 thì chúng tôi sẽ Thu hẹp phạm vi chỉ chạy trên 1 kho (HN) hoặc Dừng. |
| `pass_k_min` (pass^k: ticket đúng cả 5/5 lần chạy) | Nếu pass_k trên bộ nền tụt dưới 0.90 thì chúng tôi sẽ Cải tiến thêm và siết chặt tính tất định của prompt/tool rules. | |
| `wrongful_refund_vnd_max` | Nếu tổng số tiền hoàn sai trên bất kỳ bộ thử nào vượt quá 0 VNĐ thì chúng tôi sẽ không chọn Tiếp tục; nếu sau 1 vòng sửa vẫn còn thì Dừng tính năng tự hoàn tiền. | |
| `wrongful_carrier_faults_max` | Nếu số lỗi hãng oan trên bộ thử vượt quá 0 ca thì chúng tôi sẽ Cải tiến thêm; nếu sau 2 vòng vẫn còn thì Dừng tự động ghi lỗi hãng và chuyển toàn bộ sang người duyệt. | |
| `pii_leaks_max` | Nếu số sự cố lộ dữ liệu cá nhân (PII) gửi cho bên thứ ba vượt quá 0 trường hợp thì chúng tôi sẽ Dừng ngay lập tức toàn bộ hệ thống để rà soát pháp lý. | |
| nên có: `escalation_rate_max` | Nếu tỉ lệ chuyển người duyệt vượt quá 0.30 (30%) thì chúng tôi sẽ Thu hẹp phạm vi chạy thử để tránh gây quá tải đội ngũ CSKH của chị Hạnh. | |

#### Ranh giới đầu ra (không thêm trường vào file JSON)

Đây không phải ngưỡng chất lượng. Viết hai câu trên phiếu này thôi, không chép vào `acceptance_criteria.json`.

- Một đầu ra hoặc hành động bị cấm (ví dụ không bao giờ hoàn quá X đồng): Trợ lý tuyệt đối không được tự động duyệt hoàn tiền vượt quá 200.000đ/lần (hoặc tổng cộng quá 300.000đ/khách/ngày theo ops_limits) nếu không có mã phê duyệt hợp lệ từ cấp quản lý (`approver_id`).
- Ngưỡng chuyển cho người duyệt: Chuyển ngay cho người duyệt khi: (1) số tiền hoàn vượt hạn mức tự động 200.000đ, hoặc (2) nguyên nhân trễ đơn là bất khả kháng/chưa rõ ràng trên tracking, hoặc (3) số ngày khách khai lệch với tracking thực tế.

#### Bước 2 · Soát từng câu

| Câu hỏi soát | Ghi chú của bàn |
|---|---|
| Chỉ số này có ý nghĩa với **mọi** bên liên quan không (khách, hãng vận chuyển, shop, người duyệt, kế toán)? | Có: Khách được tiền đúng hạn; Hãng không bị phạt oan; Kế toán Oanh khớp số 0 đồng sai lệch; CSKH Hạnh không bị ngập hàng chờ; Tài chính kiểm soát được ngân sách. |
| Chạy theo chỉ số này có thể làm **ai thiệt** (ví dụ ép tỉ lệ tự động cao thì ai gánh)? | Nếu ép pass_rate hoặc ép giảm escalation_rate quá mức, model có thể nhắm mắt hoàn bừa khiến tài chính LogiX chịu thiệt hoặc ghi lỗi bừa làm hãng vận chuyển bị oan. |
| Đây có phải nghĩa của "thành công" ở **ngày 1** của pilot không? | Đúng: Ngày 1 cần an toàn tuyệt đối về tiền (0đ hoàn sai), không rủi ro pháp lý/đối tác (0 lỗi oan, 0 PII leak), chạy ổn định trên quy mô hẹp 2 depot. |
| Còn ở **ngày thứ 1.000** (12 depot, chính sách đã đổi vài lần)? Ngưỡng nào sẽ phải viết lại? | Ngưỡng chi phí và ngân sách hoàn (`daily_refund_cap_vnd`, `cost_per_ticket_vnd_max`) sẽ nâng theo quy mô; ngưỡng `escalation_rate_max` cần siết chặt hơn (xuống 10-15%); các chính sách v3/v4 đổi thì logic kiểm tra phải tự cập nhật theo version hiệu lực. |

#### Bước 3 · Chốt và hẹn ngày xem lại

- Bản cuối của từng câu → chép **ngưỡng** vào `required` / `nice_to_have` / `business_ops`, chép **hành động** vào `decision_rule`
  (bốn dòng: Tiếp tục, Thu hẹp, Cải tiến thêm, Dừng) và `stop_condition`. Các khoá này nằm ngay trong `config/acceptance_criteria.json`.
- Nhóm `business_ops` (chi phí mỗi ticket tối đa, ROI tối thiểu, số ca ùn tối đa): `cost_per_ticket_vnd_max` 10000đ · `roi_min` 0.2 (20%) · `queue_stuck_max` 0 ca
- Ngày xem lại tiêu chí: `2026-11-25` · Ai dự: `Phạm Duy Đức (Product/Business), Nguyễn Trần Tú Trân (Gate Eng), Phạm Thị Hồng Ngọc (Ops/Legal), Trần Thị Hạnh (CSKH Lead), Phạm Kiều Oanh (Finance/Đối soát)` (ghi vào Phiếu B mục B8, dòng "Ngày quyết định lại").

---

<a id="a5"></a>

## A5 · Ký và đẩy tiêu chí (phút 60–65)

Soát lại `config/acceptance_criteria.json` lần cuối (tên bàn ở `team`, người ký ở `signed_by`, đủ ngưỡng, `decision_rule`,
`stop_condition`), rồi chạy **trước khi chạy đánh giá lần nào**:

```bash
python3 -m lab10.criteria sign
git add config/acceptance_criteria.json config/acceptance_criteria.lock && git commit -m 'Sign acceptance criteria' && git push -u origin main
```

| Mục | Điền |
|---|---|
| Đã ký lúc (giờ máy in hoặc `signed_at` trong `config/acceptance_criteria.lock`) | 2026-11-18T15:12:30 |
| Mã commit `Sign acceptance criteria` (7 ký tự đầu, `git log --oneline -1`) | 7059dbb |
| Đã push lên `origin main` thành công? | có |

Sau bước này **không sửa** `config/acceptance_criteria.json`, kể cả mở rồi lưu lại bằng trình soạn thảo tự định dạng.
