# NHẬT KÝ SỬ DỤNG AI (AI USAGE LOG) - PA2

- **Thành viên thực hiện:** Trần Duy Khang (Designer)
- **Nhiệm vụ liên quan:** Review chéo §5.4 Acceptance Criteria (tác giả: Phan Phú Trọng); kiểm tra lại §2 Introduction và §4 Stakeholders sau khi chỉnh sửa; vẽ mockup và prototype cho §8
- **Dự án:** BadminBookingHub (PA2 - 08 - Nhập môn Công nghệ Phần mềm)
- **Công cụ AI:** Claude (Anthropic)
- **Thời gian:** 01/11/2026 – 11/11/2026

---

## TÓM TẮT (dùng cho bảng §11 AI Usage Log trong PA2)

| # | Member | Tool | Task / purpose |
|---|---|---|---|
| 1 | Khang | Claude | Review §5.4 Acceptance Criteria against FR/NFR/BR (3 rounds) |
| 2 | Khang | Claude | Explain Acceptance Criteria and map them to lecture slides (RE, Processes, PM) |
| 3 | Khang | Claude | Re-check §2 Introduction and §4 Stakeholders against the 28/10 review |
| 4 | Khang | Claude | Apply the round-2 review fixes to §5.4 Acceptance Criteria directly in the PA2 file |
| 5 | Khang | Claude | Draft use case specifications for UC-22 and UC-23 following the lecture structure |
| 6 | Khang | Claude | Check Hiếu's review of UC-22/UC-23 and make the remaining consistency fixes |
| 7 | Khang | Claude | Review the use case diagram (§6.1) against the use case list, specifications and FRs, then re-check Phúc's revised diagram |
| 12 | Khang | Claude | Review Hiếu's use case specifications UC-17 to UC-21 against FRs, BRs, ACs and the team's writing conventions |
| 13 | Khang | Claude (Penpot MCP) | Draw the §8 mockups in Penpot: 15 screens, component library, clickable prototype, review notes on unresolved requirements |
| 14 | Khang | Claude | Export mockup images and list the 12 open requirement issues found while drawing, for the team review |
| 15 | Khang | Claude (Penpot MCP) | Add desktop versions of the remaining Player screens |
| 16 | Khang | Claude | Insert Figures 8.4–8.15 into §8 of the PA2 docx, unify image sizes and link the Mockup column to each figure |
| 17 | Khang | Claude (Penpot MCP) | Re-check the mockups against the PA2 version of 11/11/2026 and update them: court location "Khu A/Khu B", court status on the daily schedule, closed slots after an opening-hours change, review notes removed |
| 18 | Khang | Claude (Penpot MCP) | Draw the new states required by the baseline: registration success (UC-01), last-Admin role error (BR-39, AC-06.14), walk-in booking in the Admin sidebar; export §8 as a separate file |

---

## PHIÊN 1 (01/11/2026): Review §5.4 Acceptance Criteria (vòng 1)

### MỤC ĐÍCH
- Review phần Acceptance Criteria (Given/When/Then) do Trọng viết trong bản PA2 mới cập nhật.
- Đối chiếu AC với FR-01 → FR-31, NFR và BR-01 → BR-36 để kiểm tra độ phủ, tính đúng và khả năng kiểm thử.

### KẾT QUẢ ĐẠT ĐƯỢC
- AI đọc bản PA2 trên máy, phát hiện số FR đã đổi so với bản trong Project, và dùng bản mới nhất để đối chiếu.
- AI kiểm tra lại thứ trong tuần của các ngày và các số tiền trong AC (240k, 160k, 200k, 180k…). Kết quả đều đúng.
- **Kết luận:** 🟡 *Approve with changes*. AC phủ 30/30 Must FR, có giá trị biên tốt, có case đồng thời.
- **5 vấn đề chính:**
  1. Chưa có mốc thời gian chung, nên AC không lặp lại được khi chạy ở PA4.
  2. Nhiều AC gộp nhiều kịch bản.
  3. Một số Then không kiểm chứng được hoặc thêm hành vi ngoài FR (07.5, 01.1, 06.6, 04.1, 07.1).
  4. AC-05.1 và AC-07.6 chỉ kiểm tra UI, không kiểm tra API.
  5. Thiếu khoảng 12 case âm và case biên.
- **Phát hiện thêm:**
  - 5 câu hỏi về requirement cho BA (Tú).
  - §6.3 Use Case List vẫn dùng số FR cũ.
- **File kết quả:** `PA2-5.4-AC-review.md`. Sau đó AI rút gọn thành bản ngắn `PA2-5.4-AC-review-short.md` để gửi nhóm.

---

## PHIÊN 2 (01/11/2026): Giải thích Acceptance Criteria và liên hệ với slide

### MỤC ĐÍCH
- Hiểu mục 5.4 đang nói gì, và kiến thức này nằm ở đâu trong slide đã học để phục vụ ôn thi.

### KẾT QUẢ ĐẠT ĐƯỢC
- **Khái niệm:** AC là các điều kiện kiểm chứng được để một requirement được chấp nhận. Format Given (bối cảnh) / When (một hành động) / Then (kết quả quan sát được).
- **Phân biệt FR – BR – AC – Test case**, có ví dụ từ dự án: FR-18 ↔ BR-08 ↔ AC-05.7.
- **Vị trí trong slide:**

  | Slide | Nội dung |
  |---|---|
  | 04 RE – slide 46 (slide gốc) | INVEST, Given/When/Then, *"Acceptance criteria become acceptance test cases"* |
  | 04 RE – slide 26 | Quy trình RE: Specification → Validation |
  | 04 RE – slide 51, 52 | Verifiability, Test-case generation |
  | 04 RE – slide 58 | Traceability matrix |
  | 02 Processes – slide 46, 54, 58 | XP Acceptance Testing, Definition of Done, user story testable |
  | 03 PM – slide 14, 18 | Software acceptance plan, UAT |

- **Kiến thức bổ sung (không có trong slide):** V-model, Requirements ↔ Acceptance testing.
- AI định ghi bài vào Notion (bảng Concepts, tag SE), nhưng thao tác bị hệ thống chặn nên **chưa lưu**.

---

## PHIÊN 3 (01/11/2026): Re-review §5.4 vòng 2

### MỤC ĐÍCH
- Kiểm tra bản AC Trọng đã sửa theo review vòng 1.

### KẾT QUẢ ĐẠT ĐƯỢC
- **Kết luận:** 🟢 *Gần đạt*.
- **Đã sửa:**
  - Có mục *Test Execution Context* (mốc 02/11 10:00, so sánh theo phút).
  - Đã viết lại các Then mơ hồ.
  - Đã kiểm tra cả API.
  - Đã thêm 13 case mới.
- **Còn phải sửa:**
  - **R1:** Mất 2 test biên khi viết lại: No-show lúc 18:25, làm tròn giờ bắt đầu walk-in theo BR-12. AI đề xuất thêm AC-07.13 và AC-07.14.
  - **R2:** AC-03.10 có case No-show không thể xảy ra.
  - **R3:** Thông báo lỗi chưa thống nhất, trái NFR-09.
  - **R4:** Còn vài AC gộp hoặc sai cấu trúc (05.2, 06.10, 06.11, 07.6, 07.10).
- **Ngoài §5.4:**
  - FR-24 chưa có hành vi mà AC-06.9 kiểm tra.
  - FR-14 chưa nói slot đã qua giờ hiển thị thế nào.
- **File kết quả:** `PA2-5.4-AC-review-v2.md`

---

## PHIÊN 4 (05/11/2026): Kiểm tra lại §2 Introduction và §4 Stakeholders

### MỤC ĐÍCH
- Kiểm tra file `PA/PA2 - 08.docx` đã cập nhật theo bản tóm tắt review §2 & §4 (`PA2-2-4-review-summary.md`, 28/10) chưa.

### KẾT QUẢ ĐẠT ĐƯỢC
- **Kết luận:** §2 đã sửa khoảng 60%, §4 khoảng 40%.
- **Đã sửa:**
  - Phương án single venue đã áp dụng.
  - Guest được đồng bộ sang FR, Actors, UC.
  - Out of scope đã bổ sung.
  - Đã thêm Walk-in Customer và Instructor/TA.
- **Lỗi nặng nhất:** 5 định nghĩa trong Glossary mâu thuẫn với BR/FR mới:
  - Booking Quota vẫn ghi theo tuần.
  - No-show ghi 15 phút thay vì 25 phút.
  - Time Slot ghi tối đa 3 giờ.
  - Cancellation Deadline chưa rõ chỉ áp dụng cho Player tự hủy online.
  - Rentable Equipment vẫn còn dù đã bỏ thiết bị cho thuê.
  
  Ngoài ra còn 10 chỗ ghi tạm `BR-xx`/`FR-xx` chưa điền số thật.
- **Chưa làm:**
  - Bảng F01–F13.
  - Bảng External systems.
  - Bổ sung trách nhiệm của Admin.
  - FR thông tin liên hệ của venue.
  - §10 Requirements Review vẫn trống.
- **File kết quả:** `PA2-2-4-recheck.md`

---

## PHIÊN 5 (05/11/2026): Re-check §5.4 vòng 3

### MỤC ĐÍCH
- Kiểm tra AC sau khi Trọng báo đã sửa theo review.

### KẾT QUẢ ĐẠT ĐƯỢC
- AI so sánh file trong folder PA với bản trong Project. Kết quả: **§5.4 không thay đổi gì so với bản đã review ở vòng 2**, tất cả các điểm R1–R4 và minor vẫn còn mở.
- §6.3 Use Case List **đã sửa xong**: 30 UC đều map đúng số FR mới.
- FR-24 và FR-14 vẫn chưa cập nhật.
- **File kết quả:** `PA2-5.4-AC-recheck-v3.md`. Đề xuất hỏi lại Trọng xem đã chép bản sửa vào file chung chưa.

---

## PHIÊN 6 (05/11/2026): Sửa §5.4 Acceptance Criteria theo review vòng 2

### MỤC ĐÍCH
- Kiểm tra §5.4 trong `PA2 - 08.docx` đã sửa theo review vòng 2 (R1–R4 và các điểm minor) chưa; nếu chưa thì AI sửa trực tiếp vào file.
- Hỏi lại AI: 5 thông báo lỗi mới mà AI tự viết nằm ở những AC nào.

### KẾT QUẢ ĐẠT ĐƯỢC
- **Kết luận kiểm tra:** chưa có điểm nào được sửa, nên AI sửa thẳng vào docx (giữ nguyên file gốc).
- **R1:** thêm AC-07.13 (đánh No-show lúc 18:25 bị từ chối, BR-30) và AC-07.14 (walk-in lúc 14:10 thì giờ bắt đầu sớm nhất là 14:30, BR-12).
- **R2:** AC-03.10 chỉ giữ case Cancelled.
- **R3:** bỏ thông báo chung "Thời gian đặt không hợp lệ". AC-05.1 và AC-07.12 chuyển thành Scenario Outline, mỗi rule một thông báo (theo NFR-09). AC-05.11 chỉ còn case biên 22:00–23:00 được chấp nhận.
- **R4:** tách AC-05.2, 07.6, 07.10 thành a/b; AC-06.10 thành Scenario Outline 6 dòng; AC-06.11 chỉ kiểm tra booking ngày 12/11 vẫn Booked sau khi đổi N (BR-13).
- **Minor:**
  - Given không còn chứa hành động (AC-06.8, 07.5).
  - AC-05.12 ghi rõ booking còn hơn 6 giờ (BR-08).
  - AC-07.6 có HTTP 400 và message.
  - Đổi 15 equation object sang text thường.
  - Bỏ ô "Password Confirmation" ở AC-01.1 cho khớp FR-01.
- Dùng hậu tố a/b khi tách để giữ ID cũ; RTM và PA4 chỉ cần thêm ID mới (05.2b, 07.6b, 07.10b, 07.13, 07.14).
- **Cần chốt với nhóm:** 5 thông báo do AI tự viết, nằm ở AC-07.6a, 07.6b, 07.10b, 07.14 và AC-06.10 (dòng 1).
- **File kết quả:** `PA2 - 08 (AC fixed).docx`

---

## PHIÊN 7 (05/11/2026): Viết Use Case Specification cho UC-22 và UC-23

### MỤC ĐÍCH
- Viết đặc tả UC-22 *Manage User Accounts* và UC-23 *Configure Booking Policies* theo cấu trúc trong slide.
- Nhờ AI tóm tắt lại 2 UC để hiểu, và liệt kê những chỗ AI tự thêm mà chưa hỏi ý.

### KẾT QUẢ ĐẠT ĐƯỢC
- **Cấu trúc:** dùng template §7 của PA2, viết flow theo slide 05 Use Case Modeling (slide 18–19: ví dụ PayVAT, DisplayBasket). Các bước đánh số, mở đầu bằng "The use case starts when…", mỗi alternative flow có Postconditions riêng.
- **UC-22** (FR-03, FR-24, FR-04): luồng chính tạo tài khoản; A1 đổi vai trò, có hiệu lực ngay ở request tiếp theo (AC-06.9); A3 xử lý yêu cầu xóa tài khoản (BR-34, BR-35); các exception: email trùng, sai dữ liệu, thiếu quyền Admin (403).
- **UC-23** (FR-25, FR-32): sửa N, quota, M; A1 cấu hình cọc khi có F08. Ý chính là BR-13: thay đổi không áp dụng hồi tố (AC-06.11).
- **AI tự nêu 12 quyết định tự đặt**, ví dụ: cấm Admin tự đổi vai trò, giới hạn giá trị tối thiểu, Admin đặt mật khẩu ban đầu, tên nút và message tiếng Việt.
- **Thiếu sót AI tự nêu:** chưa có khóa tài khoản, reset mật khẩu, consent (BR-33) khi Admin tạo Player, audit log; mâu thuẫn BR-19 (cọc cố định 30%) với FR-32 (cấu hình được).
- **File kết quả:** `PA2 - 08 (AC fixed + UC-22, UC-23).docx`

---

## PHIÊN 8 (09/11/2026): Kiểm tra review của Hiếu cho UC-22 và UC-23

### MỤC ĐÍCH
- Kiểm tra file Hiếu đã sửa (`PA2 - reviewed Khang UC 22-23.docx`), sửa tiếp nếu cần và nói rõ đã sửa những gì.

### KẾT QUẢ ĐẠT ĐƯỢC
- **Kết luận:** mọi điểm Hiếu review đều đã áp dụng đúng. Không còn ID nằm ngoài hàng Related requirements/BR/NFR, không còn tên nút hay message tiếng Việt. Mọi ID FR/BR/AC/NFR đều có trong PA2 hiện tại.
- **AI sửa thêm 4 chỗ:**
  1. UC-22, E4.1 (nay là E5.1): sửa lỗi câu "returns and changes no data".
  2. UC-22, A3: tách thành A3 (hủy form hoặc xác nhận thì quay về bước 2) và A4 (rời màn hình thì kết thúc), giống UC-17 và UC-21.
  3. UC-22: thêm E4 "không lưu được", giống UC-17 (E2), UC-21 (E3), UC-23 (E2).
  4. UC-23: thêm tiêu đề cho main flow, giống UC-17, UC-21, UC-22.
- **Cần trao đổi với Hiếu:**
  - UC-17 và UC-21 vẫn ghi tên nút, message và chỉ dẫn NFR-09/10, nên quy ước của nhóm chưa thống nhất.
  - Bỏ rule "Admin không tự đổi vai trò" có thể dẫn tới hệ thống không còn Admin; nếu cần thì thêm BR mới.
  - UC-23 bước 4 vẫn chấp nhận N = 0 hoặc giá trị âm.
  - BR-19 và FR-32 mâu thuẫn.
  - File PA2 chung vẫn còn bản UC-22/23 cũ.
- **File kết quả:** `PA2 - UC 22-23 (fixed after Hieu review).docx`

---

## PHIÊN 9 (06/11/2026): Review §6.1 Use Case Diagram

### MỤC ĐÍCH
- Review 2 use case diagram (Must-have F01–F07 và Should-have) trong bản PA2 mới nhất. Đối chiếu với §6.2 Actors, §6.3 Use Case List, §7 UC Specs và bảng FR.
- Lấy phần review dạng Markdown để copy gửi nhóm.

### KẾT QUẢ ĐẠT ĐƯỢC
- **Phần quan hệ đúng:** generalization Player/Staff/Admin → System User; «include» UC-07/08/09 từ UC-06 và UC-15; mọi «extend» vẽ đúng chiều; FR-01 → FR-40 đều có ít nhất một UC phủ.
- 🔴 **Số UC trong hình lệch với Use Case List từ UC-20.** List đã tách Manage Price Lists (UC-20) và Manage Public Holidays (UC-21), nhưng hình vẫn gộp. Vì vậy các UC từ UC-21 trở đi trong hình lệch 1 so với list và spec (ví dụ: hình ghi UC-21 Manage User Accounts, list ghi UC-22).
- 🔴 Hai hình chưa có caption, trong khi ghi chú trong hình 2 có nhắc tới "Figure 1".
- 🟡 Ghi chú "grey use cases" không đúng với Manage User Accounts (UC này không là base của «extend» nào). Đường E-wallet ↔ Refund Deposit cắt qua ellipse Send Booking Confirmation Email (slide 05: *minimize line crosses*). Tiêu đề hình 2 trộn mã FR-04 với mã feature F08–F10. Các «extend» chưa có condition.
- 🟢 Tuỳ chọn: Pay Booking Deposit vừa extend UC-06 vừa nối trực tiếp với Player; email xác nhận theo FR-38 nên extend cả Pay Booking Deposit (FR-35); việc tự huỷ khi hết giờ giữ chỗ (FR-34) chưa có chỗ trace.
- **File kết quả:** `PA2-6.1-UCD-review.md`

---

## PHIÊN 10 (07/11/2026): Bổ sung review cho việc đổi tên UC-19

### MỤC ĐÍCH
- Viết thêm đoạn review ghi nhận UC-19 đổi tên từ *Deactivate Court* thành *Change Court Status*.

### KẾT QUẢ ĐẠT ĐƯỢC
- AI kiểm tra file trên máy thì bản PA2 lúc đó vẫn ghi UC-19 *Deactivate Court*. Vì vậy đoạn review viết theo tên mới Khang đưa, kèm danh sách chỗ cần đồng bộ: hình, Use Case List, RTM, spec UC-19.
- Tên mới hàm ý đổi trạng thái theo **hai chiều** (Active ↔ Inactive), nhưng FR-21, BR-14 và AC-06.4 / AC-06.5 / AC-06.12 mới chỉ mô tả chiều deactivate. Đề xuất: thêm FR/AC cho chiều activate, hoặc đổi tên thành *Activate / Deactivate Court*.
- Cụm "court status" dễ nhầm với trạng thái real-time "Đang sử dụng / Trống" trong AC-07.1. Đề xuất định nghĩa trong Glossary.
- **File kết quả:** không có (đoạn Markdown trong chat để chèn vào file review).

---

## PHIÊN 11 (09/11/2026): Re-check Use Case Diagram sau khi Phúc sửa

### MỤC ĐÍCH
- Kiểm tra lại use case diagram mà Phúc vừa sửa trong `PA2 - 08.docx`, so với review ở phiên 9 và 10.

### KẾT QUẢ ĐẠT ĐƯỢC
- **Đã sửa:** 2 hình gộp thành 1 (xanh = Must, vàng = Should). UC-01 → UC-30 khớp Use Case List và spec; UC-20/UC-21 đã tách. UC-28 extend cả UC-06 và UC-25. Đã thêm actor Time. UC-19 *Change Court Status* đã đồng bộ ở hình, list, FR-21 (thêm chiều activate) và spec UC-19 (A1 = activate).
- **Chưa sửa:** caption chưa đánh số; các «extend» vẫn chưa có condition.
- 🔴 **Vấn đề mới:**
  1. Hình có generalization **Admin → Staff**, tức Admin kế thừa UC-12 → UC-16. Điều này mâu thuẫn với Actors table ("Specialises System User"), với FR-26 → FR-29 (chỉ ghi Staff) và với UC-16 (Primary actor chỉ có Staff). Đề xuất: đổi lại thành Admin → System User và thêm association Admin — UC-16.
  2. FR-21 đã có chiều activate nhưng chưa có AC tương ứng. Đề xuất thêm AC-06.13.
  3. "Court status" đang dùng với 2 nghĩa: Active/Inactive (UC-19) và "Đang sử dụng / Trống" (UC-12, UC-13). Đề xuất định nghĩa trong Glossary §2.2.
- 🟡 Có cụm 4 đường «extend» cắt nhau (UC-27 → UC-11, UC-29 → UC-16, UC-28 → UC-06, UC-28 → UC-25). Actor E-wallet chạm vào đường biên boundary. Mô tả Admin trong Actors table còn thiếu UC-19 và UC-26.
- **File kết quả:** `PA2-6.1-UCD-recheck.md`

---

## PHIÊN 12 (09/11/2026): Review UC-17 → UC-21 của Hiếu

### MỤC ĐÍCH
- Review đặc tả UC-17 → UC-21 (Manage Court Information, Configure Opening Hours, Change Court Status, Manage Price Lists, Manage Public Holidays) do Hiếu viết, trong bản `project/PA/PA2 - 08.docx` vừa cập nhật.

### KẾT QUẢ ĐẠT ĐƯỢC
- AI tìm thấy bản PA2 mới nhất trên máy (09/11, 13:04) và so với bản 08/11. Thay đổi chính: đã bỏ hết tên nút và câu thông báo tiếng Việt, thay bằng "chooses to…", "informs the Admin that…".
- Đối chiếu với FR-19 → FR-23, BR-01 → BR-18, BR-36, AC-02.1/02.2, AC-03.6, AC-04.1/04.2, AC-06.1 → 06.7, AC-06.12, NFR-09/10 và quy ước viết UC trong biên bản họp chuẩn bị chốt PA2 (mục 7).
- **Kết luận:** không có lỗi 🔴 bắt buộc sửa. Đạt cả 3 quy ước của nhóm: không ghi ID trong flow, không ghi tên nút hay thông báo, không thêm quy định ngoài BR. Quyết định 07/11 (sân bật/tắt hai chiều, sân mới Active ngay) đã vào UC-17 và UC-19.
- 🟡 **4 điểm nên sửa:**
  1. UC-18 chưa kiểm giờ mở/đóng cửa theo bước 30 phút, dù ô Business rules có BR-02 và lịch chia slot 30 phút (FR-14).
  2. UC-18 có 2 post-condition mâu thuẫn: slot ngoài giờ mới là Closed nhưng booking cũ vẫn giữ. Với AC-06.3, ô 21:00–22:00 hiển thị Closed hay Booked chưa rõ.
  3. "Booking còn hiệu lực" viết khác nhau: UC-18 ghi "from today onward", UC-19 ghi "end time has not passed" (BR-14).
  4. UC-21 bước 7 và A1.2: câu "created after saving on that date" đọc ra hai nghĩa.
- 🟢 **Lỗi nhỏ / tuỳ chọn:**
  - Dấu chấm thừa ở UC-17 E3.1; thụt lề UC-19 không đều.
  - UC-20 post-condition chưa loại trừ sân Inactive khỏi catalog.
  - UC-21 thiếu FR-10.
  - UC-17 chỉ kiểm capacity có điền chưa, chưa kiểm có phải số dương.
  - UC-19 E1 chưa nhắc No-show (BR-30, BR-31) và Pending payment tự hủy (BR-21).
  - Hai điểm về capacity và giờ mở cửa tối thiểu 60 phút cần hỏi Tú (BA) trước khi thêm.
- **File kết quả:** `PA2-7.17-7.21-UC-review.md`

---

## PHIÊN 13 (09/11/2026): Vẽ mockup §8 trên Penpot

### MỤC ĐÍCH
- Vẽ prototype/mockup cho §8 dựa trên PA2 hiện có, dùng Penpot (kết nối Claude qua Penpot MCP).

### KẾT QUẢ ĐẠT ĐƯỢC
- File Penpot có 3 page: Cover & Components, Player (mobile), Staff & Admin (desktop). Thư viện gồm 22 màu, 8 kiểu chữ, 15 component.
- 15 màn hình SCR-01 → SCR-15, tổng 35 board, mỗi màn có trạng thái chính và trạng thái lỗi. Câu thông báo lấy nguyên văn từ AC; giá tính đúng theo BR.
- Nối 6 luồng prototype: đặt sân, hủy lượt đặt, đăng nhập/đăng ký, desktop, quầy lễ tân, Admin.
- Đặt 10 ghi chú cam ở những chỗ PA2 chưa chốt, ví dụ ô lịch Closed hay Booked (UC-18/UC-05), "Đang sử dụng" (UC-12/UC-13), trang đích sau đăng nhập.
- **File kết quả:** file Penpot, `PA2-8-Penpot-handoff.md`

---

## PHIÊN 14 (09/11/2026): Xuất ảnh mockup và tổng hợp điểm cần chốt

### MỤC ĐÍCH
- Xuất ảnh PNG để chèn vào §8; tổng hợp các ghi chú cam thành bảng gửi nhóm trước buổi review.

### KẾT QUẢ ĐẠT ĐƯỢC
- Xuất 17 ảnh (Figure 8.1 → 8.15) vào thư mục `PA2-8-mockups`, cài sẵn thiết lập xuất 2x trong Penpot.
- Bảng 12 điểm cần chốt, mỗi điểm có vị trí trong PA2, câu gốc tiếng Anh kèm bản dịch, và phân loại: 5 mâu thuẫn, 7 thiếu sót.
- **File kết quả:** `PA2-8-can-chot-12-diem.md`, `PA2-mockup-mau-thuan-va-thieu-sot.md`

---

## PHIÊN 15 (10/11/2026): Bổ sung bản desktop cho màn Player

### MỤC ĐÍCH
- Mọi màn Player đều có cả mobile và desktop; Staff/Admin giữ desktop (theo §3 Operating Environment và NFR-08).

### KẾT QUẢ ĐẠT ĐƯỢC
- Thêm 6 board desktop: SCR-01, 02, 03, 06, 07, 14; nối vào luồng "Player – Desktop"; xuất thêm 7 ảnh desktop.
- Thêm chú thích hình tiếng Anh cho bảng §8 trong file bàn giao.
- **File kết quả:** file Penpot, `PA2-8-Penpot-handoff.md`

---

## PHIÊN 16 (10/11/2026): Chèn mockup vào §8 của PA2

### MỤC ĐÍCH
- Chèn hình cho SCR-04 → SCR-15 theo cách Khang đã trình bày 3 SCR đầu, đồng nhất kích thước ảnh, điền cột Mockup / links. Chỉ sửa §8.

### KẾT QUẢ ĐẠT ĐƯỢC
- Thêm Figure 8.4 → 8.15 (mobile + desktop cạnh nhau cho màn Player, desktop cho Staff/Admin), chú thích tiếng Anh.
- Đồng nhất kích thước: mobile rộng 1,70 inch, desktop 5,20 inch, kể cả 3 hình đã có.
- Cột Mockup / links có link nhảy tới từng Figure.
- **File kết quả:** `PA2 - 08 (muc 8 cap nhat).docx`

---

## PHIÊN 17 (11/11/2026): Cập nhật mockup theo PA2 bản 11/11

### MỤC ĐÍCH
- Đối chiếu mockup với PA2 mới để xem 12 điểm cần chốt đã được nhóm sửa chưa, rồi sửa mockup cho khớp.

### KẾT QUẢ ĐẠT ĐƯỢC
- 9/12 điểm đã có câu trả lời trong PA2. Mockup sửa theo: vị trí sân "Khu A / Khu B" (SCR-03, SCR-10); sân chỉ có "Đang sử dụng" / "Trống" (SCR-08, AC-07.1); hộp thoại đổi giờ ghi các ô ngoài giờ mới hiện "Đóng" (UC-18, UC-05).
- Xóa các ghi chú cam đã giải quyết; xuất lại Figure 8.3, 8.3b, 8.8, 8.10.
- **File kết quả:** file Penpot, `PA2-8-can-chot-12-diem.md` (mục Cập nhật 11/11), `PA2-8-Penpot-handoff.md`

---

## PHIÊN 18 (11/11/2026): Hoàn thiện mockup theo baseline PA2 và tách riêng §8

### MỤC ĐÍCH
- Kiểm tra bản PA2 cuối (baseline 11/11) và vẽ thêm các trạng thái tài liệu yêu cầu; tách §8 thành file riêng.

### KẾT QUẢ ĐẠT ĐƯỢC
- PA2 cuối đã sửa 2 điểm còn lại: UC-13 bỏ "the court as in use"; thêm BR-39, AC-06.14 và UC-22 A9 (không đổi vai trò của Admin cuối cùng). Xóa hết ghi chú cam.
- Vẽ thêm: SCR-01 "Tạo tài khoản thành công" (mobile + desktop, UC-01 bước 9); SCR-12 lỗi "Hệ thống phải còn ít nhất một tài khoản Admin" (AC-06.14); mục "Tạo đặt sân tại quầy" trong sidebar của 10 board Admin (Admin làm được mọi việc của Staff). Nối prototype cho các board mới.
- Phát hiện còn lệch trong PA2: FR-15 và BR-02 vẫn ghi 60–180 phút, trong khi §10 dòng 5 và Glossary đã bỏ giới hạn 180 phút. Mockup chỉ ghi "tối thiểu 60 phút, theo bước 30 phút" nên không bị ảnh hưởng.
- File §8 riêng gồm bảng màn hình và Figure 8.1 → 8.15, thêm 3 hình mới.
- **File kết quả:** file Penpot, `PA2 - 08 - Muc 8 Prototype-Mockups.docx`, ảnh mới trong `PA2-8-mockups`

---

## CÁCH KIỂM CHỨNG OUTPUT CỦA AI
- Mọi nhận xét đều dẫn tới ID cụ thể (AC/FR/BR/NFR) để đối chiếu trực tiếp trong file docx.
- Ngày trong tuần và các số tiền được AI kiểm tra bằng script tính lại, không ước lượng.
- Trạng thái "đã sửa / chưa sửa" được kiểm tra bằng cách so sánh văn bản giữa các phiên bản docx.
- Các đề xuất về requirement (FR-24, FR-14, venue profile…) chỉ là **câu hỏi cho BA**; nhóm quyết định, AI không tự sửa tài liệu PA2.
- Từ phiên 6, theo yêu cầu, AI sửa trực tiếp file docx. Mỗi lần sửa được lưu thành file mới (không ghi đè file gốc) và AI liệt kê từng chỗ đã sửa để Khang duyệt lại.
- Sau khi sửa docx, AI chạy script kiểm tra cấu trúc file và chuyển sang PDF/ảnh để xem lại bố cục bảng và AC.
- AI tìm tự động trong file các chuỗi phải loại bỏ (thông báo cũ, equation object, ID nằm ngoài hàng Related requirements, tên nút tiếng Việt) để xác nhận đã sửa hết.
- Mỗi ID mà UC dẫn tới được đối chiếu với file PA2 mới nhất của nhóm; cách viết UC được so sánh với UC-17 và UC-21 để giữ nhất quán.
- Với use case diagram, AI trích ảnh sơ đồ từ file docx và phóng to từng vùng để kiểm tra chiều mũi tên include/extend/generalization và các chỗ line cắt nhau.
- Số UC, tên UC và actor trong hình được so khớp từng dòng với Use Case List, spec §7 và cột Related FR. Quy tắc vẽ được đối chiếu với slide 05 (include vs extend, minimize line crosses).
- Bản review UC được đối chiếu với quy ước viết UC ghi trong biên bản họp nhóm (không ID trong flow, không tên nút/thông báo, không thêm quy định ngoài BR), và với các con số AC cụ thể (ví dụ AC-06.3) để tìm chỗ hai post-condition mâu thuẫn.
- Mockup: AI xuất từng board thành ảnh để xem lại, sửa các chỗ chữ tràn hoặc đè nhau; giá và câu thông báo trên mockup được đối chiếu với BR và AC.
- §8 trong docx: AI so phần trước và sau §8 với file gốc (trùng khớp hoàn toàn), chạy kiểm tra cấu trúc file và xuất PDF để xem bố cục các trang hình.
- Bản cập nhật 11/11: AI so văn bản PA2 giữa hai phiên bản Drive để biết chỗ nào đã sửa; ảnh trong file §8 được khớp với board Penpot bằng so sánh điểm ảnh trước khi thay, rồi xuất PDF để xem lại bố cục.
