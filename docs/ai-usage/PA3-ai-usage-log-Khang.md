# NHẬT KÝ SỬ DỤNG AI (AI USAGE LOG) - PA3

- **Thành viên thực hiện:** Trần Duy Khang (Designer)
- **Nhiệm vụ liên quan:** Review chéo PA3 §4.1–4.3 (Domain model, class diagram, class specifications) và §4.6 (Design Principles and Patterns); viết nội dung §7 Traceability Update; chỉnh §6; rà và sửa §8; sửa mâu thuẫn trong PA3 và thiết kế hạn giữ chỗ F08; đối chiếu và bổ sung mockup; soạn §9 AI Usage Log
- **Dự án:** BadminBookingHub (PA3 - 08 - Nhập môn Công nghệ Phần mềm)
- **Công cụ AI:** Claude (Anthropic)
- **Thời gian:** bắt đầu 24/11/2026
- **Ghi chú:** các đường dẫn `Claude outputs/…` và `Review/…` trong file này nằm trên máy cá nhân, không có trong repo.

---

## TÓM TẮT (dùng cho bảng AI Usage Log trong PA3)

| # | Member | Tool | Task / purpose |
|---|---|---|---|
| 1 | Khang | Claude | Review §4.1–4.3 (domain model, class diagram, class specifications) against the PA2 requirements (read-only, results as a table) |
| 2 | Khang | Claude | Review §4.6 Design Principles and Patterns against §4.1–4.3, §5 and lecture slide 07 (read-only, results as a table) |
| 3 | Khang | Claude | Draft §7 Traceability Update (FR/NFR/BR to use case, screen, component, class, table, AC) as a separate Word file |
| 4 | Khang | Claude (Penpot MCP) | Checked which use-case flows the PA2 §8 Penpot mockups show for SCR-02/05/06/08/09/12, and drew the two missing SCR-12 states (confirm account deletion, deletion succeeded) in the existing style |
| 5 | Khang | Claude (Google Docs connector) | Cross-checked and revised §7 (internal notes removed, open points reworded as design status, FR-41/42 added to the traceability table, component coverage corrected); added UC-24 to SCR-12 in §6.1 and a caption for the two SCR-07 mockups in §6.2 |
| 6 | Khang | Claude (Google Docs connector) | Checked §7 Traceability Update against the updated §5 Data Design, then corrected index, column and table references in §7 after approval |
| 7 | Khang | Claude (Google Drive connector) | Checked a list of suggested PA3 inconsistency fixes against PA3 and PA2, and drafted a fix plan for approval (read-only) |
| 8 | Khang | Claude (Google Docs connector) | Applied the approved inconsistency fixes to PA3 (§3, §4.1, §4.5, §5, §6, §7) and compared the document before and after |
| 9 | Khang | Claude (Google Drive connector) | Reviewed §8 Changes to the Requirements Since PA2 against PA2 and PA3, and drafted a fix proposal for approval (read-only) |
| 10 | Khang | Claude (Google Docs connector) | Applied the approved wording fixes to PA3 §8 Changes to the Requirements Since PA2 and compared the document before and after |
| 11 | Khang | Claude (Google Docs connector) | Recorded the team-approved even hourly rate refinement in PA3 §8 and compared options for fixing the F08 hold expiry design |
| 12 | Khang | Claude (Google Docs connector, Penpot MCP) | Updated the F08 hold expiry design in PA3 §4 (class specification, state transition) and in three §4 diagrams |
| 13 | Khang | Claude (Google Drive connector) | Drafted PA3 §9 AI Usage Log (Khang's entries) as a separate Word file from this log |
| 14 | Khang | Claude (Penpot MCP, Google Drive and Docs connectors) | Re-exported three PA3 §4 diagrams at 2x resolution and replaced their full-resolution links in the document with view-only links |

---

## PHIÊN 1 (24/11/2026): Review PA3 §4.1–4.3
**Mục đích:** kiểm tra domain model, class diagram và class specifications có khớp với FR/UC/BR/AC của PA2 và nhất quán với nhau (tên lớp, thuộc tính, multiplicity, quan hệ).

### KẾT QUẢ ĐẠT ĐƯỢC
- Chỉ đọc Google Doc PA3, không sửa. Kết luận: **Approve with changes**, chưa có lỗi chặn.
- Nêu các chỗ lệch cần nhóm thống nhất; có 2 điểm chưa chốt (trong đó BR-37/38/39 và UC-22/23 có trong PA3 nhưng chưa đối chiếu được với bản PA2 mới nhất trên Google Doc, vì bản trên máy là bản 09/11).
- Bổ sung: đối chiếu thêm hình trong `PA3.penpot` (Figure 4.1, 4.2a và chữ của các hình còn lại).
- Phiên review báo đã đăng comment lên issue #69 (repo badminbookinghub-team), tag Phúc: https://github.com/badminbookinghub-team/BadminBookingHub/issues/69#issuecomment-7133049629
- **File kết quả:** bảng review Markdown trong phiên và trong comment issue #69.

## PHIÊN 2 (24/11/2026): Review PA3 §4.6 Design Principles and Patterns
**Mục đích:** kiểm tra nguyên lý và pattern nêu ra có đúng định nghĩa, có áp dụng thật vào class/kiến trúc của nhóm.

### KẾT QUẢ ĐẠT ĐƯỢC
- Chỉ đọc Google Doc PA3, không sửa. Kết luận: **Approve with changes**.
- Cập nhật sau khi đối chiếu hình trong `PA3.penpot` (DomainClassDiagram, Application/PortsAdapters/Interface class diagram, StateMachine): các hàm `Session.start()`, `Email.of()`, `Money.vnd()`… có trong Fig 4.2a nên bỏ vấn đề "thiếu class"; còn 7 điểm (gọi sai tên Factory Method/Strategy, OCP quá mạnh, mã NFR, nhãn nguyên lý, thiếu ví dụ hủy/F08). **Chưa** đọc slide 06, chưa đối chiếu PA2 (BR-35, NFR-04/06).
- Đã đăng review lên issue #67 (repo badminbookinghub-team) theo yêu cầu của Khang, tag Phúc.
- **File kết quả:** `Review/PA3-review-4.6-design-principles-patterns.md`.

## PHIÊN 3 (24/11/2026): Viết PA3 §7 Traceability Update
**Mục đích:** soạn nội dung §7 để nối truy vết yêu cầu → thiết kế.

### KẾT QUẢ ĐẠT ĐƯỢC
- Tạo file Word riêng (không sửa Google Doc), chỉ gồm §7: 6 bảng (FR→UC/SCR/thành phần/lớp/bảng/AC gồm 40 hàng, NFR, BR, kiểm tra phủ, các điểm cần xác nhận ở §7.5.4).
- Kiểm tra bằng đọc lại file và script đếm; **chưa mở bằng Word** để xem bố cục.
- **File kết quả:** `Claude outputs/PA3-7-Traceability-Update.docx`

## PHIÊN 4 (24/11/2026): Đối chiếu màn hình ↔ use case trong Penpot, vẽ bổ sung SCR-12
**Mục đích:** giải quyết lệch giữa RTM (PA2, ánh xạ theo FR) và §6.1 (PA3) về use case của SCR-02, 05, 06, 08, 09, 12.

### KẾT QUẢ ĐẠT ĐƯỢC
- Kiểm tra mockup Penpot: SCR-05/06/08/09 đã thể hiện đủ các trạng thái của FR-31 (Đã đặt, Đã check-in, Hoàn thành, Vắng mặt, Đã hủy); "Chờ thanh toán" chỉ ở SCR-14 (F08). SCR-02 không có thao tác đăng xuất (đăng xuất nằm ở SCR-07/08/12).
- Vẽ 2 board còn thiếu cho FR-04/UC-24 ở SCR-12: hộp thoại xác nhận xóa và trạng thái xóa thành công. Dữ liệu mẫu "Lê Minh K" là giả định do AI đặt, cần Khang duyệt.
- Vẽ thêm 2 board mobile (390×844) cho phía Player ở SCR-07: "đã gửi yêu cầu xóa" và "không thể gửi yêu cầu xóa" (còn lượt đặt BK-1024). Dữ liệu mẫu do AI đặt.
- PNG xuất ở 1x (1440×900 / 390×844), chưa phải 2x. Không sửa Google Doc.
- File kết quả thêm: `PA3-6.1-SCR-07-da-gui-yeu-cau-xoa.png`, `PA3-6.1-SCR-07-khong-the-gui-yeu-cau-xoa.png`
- **File kết quả:** `Claude outputs/PA3-6.1-SCR-12-xac-nhan-xoa-tai-khoan.png`, `PA3-6.1-SCR-12-xoa-tai-khoan-thanh-cong.png` (nguồn: file Penpot, page 02, hàng SCR-12)

## PHIÊN 5 (25/11/2026): Kiểm tra và chỉnh §7, §6.1, §6.2 trên Google Doc PA3
**Mục đích:** bỏ ghi chú nội bộ và sửa số liệu sai ở §7 theo review; đồng bộ §6 với mockup mới.

### KẾT QUẢ ĐẠT ĐƯỢC
- Đối chiếu NFR-16 và RTM với bản baseline PA2 trên Google Doc; tạo bản `Claude outputs/PA3-7-Traceability-Update-v2.docx`.
- §6.1: thêm UC-24 cho SCR-12. §6.2: thêm chú thích Figure 6.2 cho 2 mockup SCR-07.
- §7 (Khang duyệt phương án trước khi sửa): xóa §7.5.4; đổi cột "Suggestion" thành "Status in PA3"; thêm FR-41, FR-42 vào Table 7.1 ("not designed in PA3"); FR-17 đổi `UserRepository` thành `Repository Ports` ở cột Component; số component được truy vết sửa thành 20/21.
- Kiểm tra bằng cách đọc lại doc và script đếm. Chưa xem bố cục trang bằng mắt.
- Còn mở (lúc đó): `sessions (expires_at, ended_at)` ở Table 7.2 (đã sửa ở phiên 6); mockup SCR-12 còn lệch FR-04.
- **File kết quả:** Google Doc "T08 - PA3" (§6.1, §6.2, §7); file .docx v2 ở trên (chưa gồm các sửa đổi §7 lần này).

## PHIÊN 6 (25/11/2026): Đối chiếu §7 với §5 Data Design mới
**Mục đích:** tìm chỗ §7 lệch với §5 (data diagram, table specs, chuẩn hóa, index) vừa cập nhật.

### KẾT QUẢ ĐẠT ĐƯỢC
- Đối chiếu (chỉ đọc), tìm thấy: tên index ở Table 7.2 (NFR-01 – NFR-04) không còn khớp §5.3.4; NFR-16 còn ghi cột `expires_at` đã bỏ khi chuẩn hóa; vài ô cột "Table" ở Table 7.1 nên bổ sung.
- Khang duyệt, đã sửa trên Google Doc: Table 7.2 (NFR-01 – NFR-04, NFR-16), cột Table của FR-04, FR-34, FR-36 và dòng 1 Table 7.5; đọc lại để kiểm tra.
- Chưa đối chiếu các hình trong §5 (ERD, relational schema). Tham chiếu sai ở §3.1 chưa sửa (phần của người khác).
- Kiểm tra lại doc sau khi nhóm báo có chỉnh: không đổi so với lần đọc trên; phương án giữ nguyên, thêm một tham chiếu sai ở §3.1 (G3 trỏ §5.3.3, đúng là §5.3.4).
- **File kết quả:** Google Doc "T08 - PA3" (§7).

## PHIÊN 7 (25/11/2026): Kiểm tra file góp ý "sửa pa3" và lập phương án sửa
**Mục đích:** xác nhận từng điểm góp ý còn tồn tại và hợp lý không trước khi sửa PA3.

### KẾT QUẢ ĐẠT ĐƯỢC
- Đối chiếu 10 điểm góp ý và 3 mục "đang khớp" với PA3 và PA2: cả 10 điểm còn tồn tại và hợp lý (điểm đơn giá chẵn cần nhóm quyết).
- Phát hiện thêm: users.email cùng lỗi candidate key; hạn giữ chỗ tính theo cấu hình hiện hành trái UC-23.
- Chưa sửa Google Doc; chờ Khang duyệt. Chưa xem hình trong doc.
- **File kết quả:** `Claude outputs/PA3-fix-plan.md`.

## PHIÊN 8 (25/11/2026): Sửa mâu thuẫn trên Google Doc PA3
**Mục đích:** sửa các điểm Khang đã duyệt trong phương án ở phiên 7.

### KẾT QUẢ ĐẠT ĐƯỢC
- Sửa trực tiếp điểm 1–9 và 11: SCR-05, SCR-14, §6.1, §6.3, §5.1.3, §5.3.3, §5.2, §4.1, §4.5, §3 (G3, G4), ADR-005, Table 7.1 và Table 7.5. Một số phần do thành viên khác phụ trách.
- So bản trước và sau bằng script: 27 đoạn thay đổi đúng nội dung dự định, không có đoạn nào khác đổi chữ hay định dạng. Chưa xem bố cục trang bằng mắt.
- Còn mở: đơn giá giờ chẵn (chờ duyệt §8); hạn giữ chỗ so với UC-23; sân có phải đặt lại ngay tại hạn; confirmDeposit() chưa chặn thanh toán muộn; mockup SCR-12.
- **File kết quả:** Google Doc "T08 - PA3".

---

## PHIÊN 9 (25/11/2026): Rà §8 Changes to the Requirements Since PA2
- Mục đích: tìm chỗ mâu thuẫn hoặc không hợp lý trong §8, đề xuất cách sửa để Khang duyệt.
- Kết quả: 4 đề xuất sửa câu chữ trong §8 (S1–S4) và 3 điểm cần nhóm quyết (D1–D3). Chưa sửa Google Doc. Phát hiện §9 AI Usage Log trong doc PA3 còn là mẫu trống.
- **File kết quả:** `Claude outputs/PA3-sec8-fix-plan.md`.

---

## PHIÊN 10 (25/11/2026): Sửa §8 trên Google Doc PA3
- Mục đích: sửa 4 điểm Khang đã duyệt trong §8 (phần do thành viên khác phụ trách).
- Kết quả: sửa câu mở đầu; chuyển mục HTTP 404 sang danh sách lựa chọn thiết kế; bổ sung "Affected items"; xóa đoạn "Baseline confirmation". So trước/sau bằng script: không đoạn nào ngoài dự định bị đổi. Chưa xem bố cục trang bằng mắt.
- Còn mở: đơn giá giờ chẵn chờ nhóm duyệt; hạn giữ chỗ so với UC-23; PA2 sửa sau baseline hay không; §9 trong doc PA3 còn là mẫu trống.
- **File kết quả:** Google Doc "T08 - PA3".

---

## PHIÊN 11 (25/11/2026): Ghi quyết định đơn giá giờ chẵn vào §8
- Mục đích: ghi quyết định nhóm duyệt đơn giá giờ chẵn vào §8; tìm cách sửa hạn giữ chỗ ít ảnh hưởng sơ đồ.
- Kết quả: sửa câu dẫn, cột "Change" và dòng "Approval status" (ngày duyệt do Khang xác nhận). So trước/sau: đúng 3 đoạn đổi. Phương án D2 mới trao đổi, chưa sửa.
- **File kết quả:** Google Doc "T08 - PA3".

---

## PHIÊN 12 (25/11/2026): Sửa thiết kế hạn giữ chỗ F08 trong §4
- Mục đích: lưu hạn giữ chỗ lúc tạo booking để khớp UC-23 (hướng A, Khang duyệt). Phần §5 để người phụ trách §5 làm.
- Kết quả: sửa §4.3 (C1, C5) và §4.5 trên Google Doc; sửa 3 trang Penpot (DomainClassDiagram, BookingOnlineSequenceDiagram, BookingStateMachineDiagram), dời hộp Booking và 2 đường nối cho khỏi đè. Đã xuất ảnh xem lại. Chưa thay ảnh trong Google Doc.
- Còn mở: §5 chưa có cột hold_expires_at; state machine chưa thể hiện cancelByStaff() cho PendingPayment.
- **File kết quả:** Google Doc "T08 - PA3"; file Penpot PA3; `Claude outputs/PA3-4.*-v2.png`.

---

## PHIÊN 13 (25/11/2026): Viết PA3 §9 AI Usage Log (phần của Khang)
- Mục đích: tạo file Word §9 theo mẫu bảng 5 cột của doc PA3, từ nhật ký này.
- Kết quả: bảng 13 dòng, đánh số 6–18 (nối sau 5 dòng đã có trong doc), tiếng Anh; đọc lại bằng script và xem bản xuất PDF. Không sửa Google Doc; chờ Khang rà trước khi dán.
- Khang yêu cầu chỉ giữ task chính: bản v2 gộp còn 6 dòng (đánh số 6–11), gồm cả việc ở phiên 14.
- **File kết quả:** `Claude outputs/PA3-9-AI-Usage-Log-Khang-v2.docx` (bản chi tiết 13 dòng: file không có hậu tố v2).

## PHIÊN 14 (25/11/2026): Thay ảnh và link "full-resolution" của 3 hình §4
- Mục đích: link dưới Figure 4.2a, 4.3, 4.8 trong PA3 vẫn trỏ tới ảnh cũ trên Drive.
- Kết quả: AI xuất 3 hình từ Penpot ở 2x (ghép nền trắng cho class diagram); Khang đổi folder sang chế độ xem và tự tải ảnh lên; AI kiểm tra quyền chỉ xem từng file, thay 3 link và so trước/sau (chỉ 3 URL đổi).
- **File kết quả:** `Claude outputs/PA3-drive-upload/`.

---

## CÁCH KIỂM CHỨNG OUTPUT CỦA AI
- Các phiên review chỉ đọc; những lần sửa tài liệu (gồm cả phần do thành viên khác phụ trách) được thực hiện sau khi Khang duyệt; mọi vấn đề dẫn tới mục và mã yêu cầu cụ thể để đối chiếu trực tiếp trong doc.
- Các điểm AI chưa chốt được (BR-37/38/39, UC-22/23; slide 06; hình 4.2) được nêu rõ để Khang và nhóm xác nhận, AI không tự quyết.
- §7 chỉ dùng mã FR/UC/SCR/lớp có trong tài liệu; chỗ chưa chắc được báo riêng để đưa vào họp nhóm (§7.5.4 đã bỏ khỏi bản nộp).