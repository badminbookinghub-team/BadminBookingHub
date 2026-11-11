Here is our PA2 document about a badminton court booking app. this is a college project. now list all UC for me



Here are all 30 use cases from your Use Case List (section 6.3):



ID	Use case	Primary actor	Priority	Related FR

UC-01	Register Account	Guest	Must	FR-01

UC-02	Log In	System User	Must	FR-02, FR-03

UC-03	Log Out	System User	Must	FR-02

UC-04	View Court Catalog	Guest, Player	Must	FR-05

UC-05	Search Available Courts	Guest, Player	Must	FR-13, FR-14

UC-06	Book Court Online	Player	Must	FR-06, FR-08, FR-10, FR-31

UC-07	Calculate Booking Price	(included by UC-06, UC-15)	Must	FR-07

UC-08	Validate Booking Rules	(included by UC-06, UC-15)	Must	FR-15, FR-16, FR-17

UC-09	Check Court Availability	(included by UC-06, UC-15)	Must	FR-09

UC-10	View My Bookings	Player	Must	FR-11

UC-11	Cancel My Booking	Player	Must	FR-12, FR-18, FR-31

UC-12	View Daily Schedule	Staff	Must	FR-26

UC-13	Check In Customer	Staff	Must	FR-27, FR-31

UC-14	Mark No-show	Staff	Must	FR-28, FR-31

UC-15	Create Walk-in Booking	Staff	Must	FR-29, FR-31

UC-16	Cancel Booking on Behalf of Player	Staff, Admin	Must	FR-30, FR-31

UC-17	Manage Court Information	Admin	Must	FR-19

UC-18	Configure Opening Hours	Admin	Must	FR-20

UC-19	Change Court Status	Admin	Must	FR-21

UC-20	Manage Price Lists	Admin	Must	FR-22

UC-21	Manage Public Holidays	Admin	Must	FR-23

UC-22	Manage User Accounts	Admin	Must (FR-04 part Should)	FR-03, FR-24, FR-04

UC-23	Configure Booking Policies	Admin	Must (F08 settings Should)	FR-25, FR-32

UC-24	Request Account Deletion	Player	Should	FR-04

UC-25	Pay Booking Deposit	Player (extends UC-06)	Should	FR-33, FR-34, FR-35

UC-26	View Booking and Cancellation History	Admin	Should	FR-36

UC-27	Refund Deposit	(extends UC-11, UC-16)	Should	FR-37

UC-28	Send Booking Confirmation Email	(extends UC-06)	Should	FR-38

UC-29	Send Cancellation Email	(extends UC-11, UC-16)	Should	FR-39

UC-30	Send Booking Reminder	Time	Should	FR-40

Specification status (section 7), since this may help with your remaining work:



Fully written: UC-04 to UC-11, UC-17 to UC-23

Partially written (placeholders like “A1: …”, “E1: …”, empty Post-conditions/Related requirements/Business rules): UC-01, UC-02, UC-03

Blank templates: UC-12 to UC-16

No specification section at all: UC-24 to UC-30 (these are Should-have, so they may be optional)

Also, section 7 only goes up to UC-23, while the list goes to UC-30. I can draft any of the missing specs (e.g., UC-12 to UC-16) in the same style if you’d like.



fill in UC 12 - 16

Use case ID: UC-12

Use case name: View Daily Schedule

Brief description: Staff views the booking schedule of a day and the current status of each active court. For each booking the system shows the court, time, customer name, phone number and booking status, so that Staff can prepare check-ins, no-shows and walk-in bookings.

Primary actor: Staff

Secondary actors: None

Priority: Must

Related requirements: FR-03, FR-26, FR-31; AC-01.9, AC-07.1

Trigger: Staff chooses to view the daily schedule.

Pre-conditions:

1\. Staff is logged in with the Staff role and has an active authenticated session.

2\. The courts and their opening hours have been set up by the Admin.

Post-conditions:

1\. The bookings of the selected date and the current status of each active court are displayed.

2\. No data is changed.

Main flow:

1\. The use case starts when Staff chooses to view the daily schedule.

2\. The system verifies Staff's authentication and role.

3\. The system selects today's date (Asia/Ho\_Chi\_Minh) and finds the courts whose status is Active.

4\. For each active court, the system reads its bookings on that date, in any status.

5\. The system determines the current status of each court: "Đang sử dụng" if a Checked-in booking covers the current time, otherwise "Trống".

6\. The system displays the schedule ordered by court and start time. Each booking shows court, start and end time, customer name, phone number and status.

7\. Staff reviews the schedule.

8\. The use case ends.

Alternative flows:

A1 (at step 7): Staff selects another date

A1.1 The use case continues at step 4 with the new date. The current court status of step 5 is shown only for today.

Postconditions: no data is changed.

A2 (at step 7): A booking changes while the schedule is open

A2.1 A booking on the displayed date is created, cancelled, checked in, marked No-show, or becomes Completed.

A2.2 The system updates the affected rows and court status without the user reloading the page (NFR-03). The use case continues at step 7.

Postconditions: the schedule shows the latest data.

A3 (at step 4): A court has no booking on the date

A3.1 The system shows the court with no bookings and status "Trống". The use case continues at step 7.

A4 (at step 3): There is no active court

A4.1 The system displays an empty schedule and informs Staff that no court is available. The use case ends.

Exception flows:

E1 (at step 2): The session is invalid or has expired

E1.1 The system refuses access and takes Staff to the login page (UC-02). No data is returned.

E2 (at step 2): The user does not have the Staff role

E2.1 The system rejects the request with HTTP 403 Forbidden and returns no data. The use case ends.

E3 (at step 4 or 5): The schedule cannot be loaded

E3.1 The system informs Staff that the schedule cannot be loaded now and shows no partial or outdated schedule. The use case ends.

Postconditions: no data is changed.

Business rules: BR-25, BR-27, BR-31, BR-32, BR-36

Non-functional constraints: NFR-03, NFR-07, NFR-08, NFR-10

Use case ID: UC-13

Use case name: Check In Customer

Brief description: Staff records the arrival of a customer for a Booked booking. Check-in is allowed from 15 minutes before to 25 minutes after the booking start time. The system changes the booking status to Checked-in.

Primary actor: Staff

Secondary actors: None

Priority: Must

Related requirements: FR-03, FR-27, FR-31; AC-07.2, AC-07.10b

Trigger: Staff chooses to check in a customer for a booking in the daily schedule.

Pre-conditions:

1\. Staff is logged in with the Staff role and has an active authenticated session.

2\. The booking exists and is shown in the daily schedule (UC-12).

Post-conditions:

1\. On successful check-in, the booking status is Checked-in.

2\. The booking keeps its court, time and price, and continues to occupy the court.

3\. At the scheduled end time the booking becomes Completed automatically (BR-27).

4\. On rejected check-in, the booking status and the court schedule are unchanged.

Main flow:

1\. The use case starts when Staff selects a booking in the daily schedule and chooses to check in the customer.

2\. The system verifies Staff's authentication and role.

3\. The system checks that the booking status is Booked.

4\. The system checks that the current time is within the check-in window: from 15 minutes before the start time (inclusive) to 25 minutes after the start time (inclusive).

5\. The system changes the booking status to Checked-in.

6\. The system displays "Check-in thành công" and shows the booking with status Checked-in. The court status becomes "Đang sử dụng".

7\. The use case ends.

Alternative flows:

A1 (at step 4): Check-in is too early

A1.1 The current time is earlier than 15 minutes before the start. The system rejects the check-in with "Check-in chỉ mở từ HH:mm (trước 15 phút)", where HH:mm is the opening time of the window (for example 17:45 for an 18:00 booking). The use case ends.

Postconditions: the booking stays Booked.

A2 (at step 4): Check-in is too late

A2.1 The current time is later than 25 minutes after the start. The system rejects the check-in with "Đã hết thời gian check-in". The use case ends.

Postconditions: the booking stays Booked. Staff may mark it as No-show (UC-14).

Exception flows:

E1 (at step 3): The status does not allow check-in

E1.1 The booking is Completed, Cancelled or No-show. The system rejects the request (HTTP 400 Bad Request, "Đặt sân đã kết thúc, không thể thay đổi trạng thái"). The Check-in button is disabled. The use case ends.

E1.2 The booking is already Checked-in, or is in Pending payment status (F08). The system rejects the request because BR-25 does not allow this transition. The use case ends.

Postconditions: the status does not change.

E2 (at step 2): The session is invalid or the user is not Staff

E2.1 The system rejects the request (HTTP 401 for an invalid session, HTTP 403 Forbidden for a wrong role) and changes no data. The use case ends.

E3 (at step 5): The status cannot be saved

E3.1 The system informs Staff that the check-in cannot be completed now and can be tried again. The booking stays Booked. The use case ends.

Business rules: BR-25, BR-26, BR-27, BR-29

Non-functional constraints: NFR-03, NFR-07, NFR-08, NFR-10

Use case ID: UC-14

Use case name: Mark No-show

Brief description: Staff marks a Booked booking as No-show when the customer has not checked in more than 25 minutes after the start time. The system never marks a No-show by itself. A No-show booking no longer occupies the court, so its remaining time can be offered for walk-in bookings.

Primary actor: Staff

Secondary actors: None

Priority: Must

Related requirements: FR-03, FR-28, FR-31; AC-07.3, AC-07.4, AC-07.10b, AC-07.13

Trigger: Staff chooses to mark a booking that has not been checked in as No-show.

Pre-conditions:

1\. Staff is logged in with the Staff role and has an active authenticated session.

2\. The booking exists and is shown in the daily schedule (UC-12).

Post-conditions:

1\. On success, the booking status is No-show.

2\. The booking no longer occupies the court. The remaining time of the booking, from the next half hour after the current time, is Available in the availability calendar and can be given to a walk-in booking (UC-15).

3\. The booking record is kept.

4\. On rejection, the booking status is unchanged.

Main flow:

1\. The use case starts when Staff selects a Booked booking and chooses to mark it as No-show.

2\. The system verifies Staff's authentication and role.

3\. The system checks that the booking status is Booked.

4\. The system checks that the current time is more than 25 minutes after the booking start time.

5\. The system changes the booking status to No-show.

6\. The system releases the remaining time slots of the booking in the availability calendar.

7\. The system informs Staff that the booking is marked as No-show and shows the updated schedule.

8\. The use case ends.

Alternative flows:

A1 (at step 4): The No-show time has not been reached

A1.1 The current time is not later than 25 minutes after the start (for example 18:25 for an 18:00 booking). The system rejects the request with "Chỉ có thể đánh dấu vắng mặt sau HH:mm", where HH:mm is the start time plus 25 minutes (for example 18:25). The use case ends.

Postconditions: the booking stays Booked.

A2 (at step 1): Staff takes no action

A2.1 The customer has not checked in and Staff does not act. The booking stays Booked and the system does not change the status automatically (for example at 18:40 for an 18:00 booking).

Postconditions: the booking stays Booked.

Exception flows:

E1 (at step 3): The status does not allow No-show

E1.1 The booking is Checked-in, Completed, Cancelled or Pending payment. For Completed, Cancelled and No-show, the buttons are disabled and an API request is rejected with HTTP 400 Bad Request and "Đặt sân đã kết thúc, không thể thay đổi trạng thái". For the other statuses the system rejects the request because BR-25 does not allow the transition. The use case ends.

Postconditions: the status does not change.

E2 (at step 2): The session is invalid or the user is not Staff

E2.1 The system rejects the request (HTTP 401 or HTTP 403 Forbidden) and changes no data. The use case ends.

E3 (at step 5 or 6): The status cannot be saved

E3.1 The system informs Staff that the booking cannot be marked now and saves nothing. The booking stays Booked and keeps occupying the court. The use case ends.

Business rules: BR-25, BR-30, BR-31

Non-functional constraints: NFR-03, NFR-07, NFR-08, NFR-10

Use case ID: UC-15

Use case name: Create Walk-in Booking

Brief description: Staff creates a booking on the same day for a Walk-in Customer who arrives without a reservation. Staff selects an available court, a start time and a duration, and records the customer's consent to the use of personal data. The system validates the booking, calculates the price and creates the booking directly in Checked-in status.

Primary actor: Staff

Secondary actors: None

Priority: Must

Related requirements: FR-03, FR-07, FR-09, FR-15, FR-29, FR-31; includes: Validate Booking Rules (UC-08), Check Court Availability (UC-09), Calculate Booking Price (UC-07); AC-07.5, AC-07.6a, AC-07.6b, AC-07.7, AC-07.10a, AC-07.12, AC-07.14

Trigger: Staff chooses to create a walk-in booking.

Pre-conditions:

1\. Staff is logged in with the Staff role and has an active authenticated session.

2\. The selected court exists and has Active status.

3\. The opening hours and price lists have been configured.

Post-conditions:

1\. On success, a walk-in booking is created in Checked-in status for today, with the selected court, start time, end time, duration and calculated price (BR-18).

2\. The booking stores the customer's name and phone number and the consent record.

3\. The booking occupies the court and is shown as Booked in the availability calendar.

4\. The booking does not count toward any Player's booking quota (BR-11).

5\. At the scheduled end time the booking becomes Completed automatically.

6\. If Staff leaves before confirming, or a check fails, no booking is created.

Main flow:

1\. The use case starts when Staff chooses to create a walk-in booking.

2\. The system displays the walk-in booking form. The date is fixed to today and the earliest start time offered is the next half hour not earlier than the current time (for example 14:30 when the current time is 14:10).

3\. Staff selects an active court, a start time and a duration.

4\. Staff enters the customer's full name and phone number and ticks the box confirming that the customer agreed to the personal data policy.

5\. Staff submits the form.

6\. The system validates the booking information (include: Validate Booking Rules, walk-in rules).

7\. The system checks that the court and time interval are available (include: Check Court Availability).

8\. The system calculates the price (include: Calculate Booking Price).

9\. The system displays the booking summary: court, date, start and end time, duration, price in VND, and customer.

10\. Staff confirms the booking.

11\. Before creating the booking, the system rechecks the booking rules and availability.

12\. The system creates the booking in Checked-in status and records the customer's consent.

13\. The system displays the result, and the court slots show Booked in the availability calendar.

14\. The use case ends.

Alternative flows:

A1 (after step 6): The booking rules are not satisfied

A1.1 The system rejects the request and shows the message next to the field: "Thời gian đặt nằm ngoài giờ mở cửa của sân", "Giờ bắt đầu phải là giờ chẵn hoặc giờ rưỡi", "Thời lượng tối thiểu 60 phút, theo bước 30 phút", or "Giờ bắt đầu không được sớm hơn thời điểm hiện tại".

A1.2 Staff corrects the data. The use case continues at step 5.

Postconditions: no booking is created.

A2 (after step 7 or at step 11): The time interval is not available

A2.1 The interval overlaps an active booking, or another booking took it after step 7. The system rejects the request with "Khung giờ này không còn trống". At most one of two simultaneous requests is created (BR-04).

A2.2 Staff selects another court or time. The use case continues at step 3.

Postconditions: no overlapping booking is created and existing bookings are unchanged.

A3 (at step 5): The consent box is not ticked

A3.1 The system rejects the request and shows "Cần xác nhận khách hàng đã đồng ý với chính sách dữ liệu cá nhân" next to the consent checkbox. The entered values are kept. The use case continues at step 4.

Postconditions: no booking is created.

A4 (at step 10): Staff does not confirm

A4.1 Staff closes the summary or leaves the form. No booking is created and no slot is reserved. The use case ends.

Exception flows:

E1 (at step 2 or 5): The booking is not for today

E1.1 The date picker allows only today. A request for another date sent directly to the API is rejected with HTTP 400 Bad Request and "Chỉ được tạo đặt sân tại quầy cho ngày hôm nay". The use case ends.

E2 (at step 5): The customer information is invalid

E2.1 The system shows next to each invalid field which rule is violated (for example "Số điện thoại phải gồm 10 chữ số, bắt đầu bằng 0") and keeps the valid values. The use case continues at step 4.

E3 (at any step): The session is invalid or the user is not Staff

E3.1 The system rejects the request (HTTP 401 or HTTP 403 Forbidden) and creates nothing. The use case ends.

E4 (at step 6, 7, 8, 11 or 12): A check or the save cannot be completed

E4.1 The system creates no partial booking and informs Staff that the booking cannot be completed now. The use case ends.

Business rules: BR-01, BR-02, BR-03, BR-04, BR-11, BR-12, BR-15, BR-16, BR-17, BR-18, BR-20, BR-26, BR-27, BR-32, BR-33, BR-36

Non-functional constraints: NFR-02, NFR-07, NFR-08, NFR-09, NFR-10, NFR-12

Use case ID: UC-16

Use case name: Cancel Booking on Behalf of Player

Brief description: Staff or Admin cancels a booking that has not started, on behalf of the customer (at the customer's request) or because the venue cannot provide the court. The system changes the booking to Cancelled, records who cancelled and the reason, and releases the court's time slots.

Primary actor: Staff, Admin

Secondary actors: None

Priority: Must

Related requirements: FR-03, FR-30, FR-31; optional extensions: Refund Deposit (FR-37), Send Cancellation Email (FR-39); AC-07.8, AC-07.9, AC-07.10b, AC-07.11

Trigger: Staff or Admin chooses to cancel a booking.

Pre-conditions:

1\. The user is logged in with the Staff or Admin role and has an active authenticated session.

2\. The booking exists in the system.

Post-conditions:

1\. On success, the booking status is Cancelled.

2\. The cancellation record stores the Staff or Admin user ID as the canceller and the reason (customer request, or venue closed / court problem).

3\. The booking's time slots no longer occupy the court and are Available in the availability calendar.

4\. The booking price and record are kept.

5\. If F08/F09 or F10 are implemented, the Refund Deposit and Send Cancellation Email extensions may run.

6\. On rejection, the booking is unchanged.

Main flow:

1\. The use case starts when Staff or Admin selects a booking and chooses to cancel it. The cancel action is offered only for bookings that have not started.

2\. The system verifies the user's authentication and role.

3\. The system checks that the booking status is Booked (or Pending payment when F08 is implemented) and that the current time is earlier than the start time.

4\. The system asks the user to select a reason: "Khách hàng yêu cầu" or "Sân đóng cửa / Sự cố sân", and shows the court, date, time, customer and price.

5\. The user selects the reason and confirms.

6\. The system repeats the checks of step 3 using the latest status and current time.

7\. The system changes the status to Cancelled and records the user as the canceller and the selected reason (stored as "customer request" or "venue closed / court problem").

8\. The system informs the user that the booking is cancelled and shows the court slots as Available.

9\. The use case ends.

Alternative flows:

A1 (at step 5): No reason is selected

A1.1 The system rejects the request, asks the user to select a reason, and saves nothing. The use case continues at step 4.

Postconditions: the booking is unchanged.

A2 (at step 5): The user does not confirm

A2.1 The user closes the confirmation. The use case ends.

Postconditions: the booking is unchanged.

A3 (after step 7): Optional features are in use

A3.1 Extension point Booking cancelled: Refund Deposit extends here when a deposit was paid, and Send Cancellation Email extends here when booking emails are in use.

A3.2 The use case continues at step 8.

Postconditions: the booking stays Cancelled.

Exception flows:

E1 (at step 3 or 6): The booking has started

E1.1 The current time is equal to or later than the start time. The system rejects the cancellation. The cancel action is not offered, and a direct API request is rejected with HTTP 400 Bad Request. The use case ends.

Postconditions: the booking is unchanged.

E2 (at step 3 or 6): The status does not allow cancellation

E2.1 The booking is Checked-in, Completed, Cancelled or No-show. For the last three the buttons are disabled and an API request is rejected with HTTP 400 Bad Request and "Đặt sân đã kết thúc, không thể thay đổi trạng thái". A Checked-in booking cannot be cancelled either (BR-25). The use case ends.

Postconditions: the status does not change.

E3 (at step 2): The session is invalid or the user is not Staff or Admin

E3.1 The system rejects the request (HTTP 401 or HTTP 403 Forbidden), including for a Player, and changes no data. The use case ends.

E4 (at step 7): The cancellation cannot be saved

E4.1 The system informs the user that the booking cannot be cancelled now and can be tried again. The booking is unchanged. The use case ends.

Business rules: BR-10, BR-25, BR-28

Non-functional constraints: NFR-03, NFR-07, NFR-08, NFR-10



change the Acceptance Criteria based on these review



REVIEW



🔴 Major: nên sửa trước baseline



M1. Chưa có mốc thời gian chung, nên AC dùng ngày tuyệt đối không lặp lại được



Phần lớn AC dùng ngày cố định (09/11, 12/11, 16/11…) nhưng chỉ AC-05.2 ghi "today is 02/11/2026". Khi chạy test ở PA4 (vài tuần sau), các ngày này đã ở quá khứ hoặc ngoài cửa sổ 14 ngày (BR-05), nên test fail dù hệ thống đúng.







Ví dụ AC-05.5 "has already played 8 hours this week": nếu "hôm nay" là Thứ 2 02/11 10:00 như AC-05.2 thì tuần này mới có tối đa 5 giờ (05:00–10:00), nên không có cách nào dựng dữ liệu cho case này.



Đề xuất: thêm vào đoạn mở đầu §5.4:



Unless a criterion states otherwise: the current time is Monday 02/11/2026 10:00 (Asia/Ho\_Chi\_Minh) and the test environment can set the system clock; the Player is logged in and holds no other upcoming booking; Court A is active, open 05:00–23:00, uses the default rates and has no other bookings.



Sửa AC-05.5: "Given a Player has 8 hours of Completed bookings in the last 7 days and holds no upcoming booking…"



Hệ quả cho Dev (Phúc): backend cần inject được clock (không gọi new Date() rải rác) thì PA4 mới test được. Nên ghi vào design PA3.



M2. Nhiều AC gộp 2–4 kịch bản vào một, khó map 1-1 sang test case



Các AC đang gộp: 01.3, 01.5, 03.2, 03.3, 05.1, 05.3, 05.4, 05.7, 06.1, 06.3, 06.6, 06.7, 07.2, 07.3, 07.6, 07.10. Ví dụ AC-01.5 vừa test login đúng vừa test sai mật khẩu, AC-07.6 gộp hai rule không liên quan (consent và chọn ngày).



Khi một nửa pass, một nửa fail thì không biết đánh dấu AC đó thế nào trong RTM.



Đề xuất (chọn 1):



Tách thành AC-xx.ya / AC-xx.yb, mỗi AC chỉ 1 When, 1 Then; hoặc







Với case chỉ khác dữ liệu (03.2, 07.2, 05.1) thì viết kiểu Scenario Outline + bảng Examples:



StartEndExpected17:44–"Check-in mở lúc 17:45"17:45–Checked-in18:25–Checked-in18:26–"Đã hết thời gian check-in"



M3. Một số Then không kiểm chứng được hoặc đặt thêm hành vi không có trong FR



ACVấn đềĐề xuất07.5"does not count towards any Player's booking quota": khách walk-in không có tài khoản Player, nên câu này luôn đúng và không test được gì."Given Player P1 with phone 0901234567 holds 10 hours of upcoming bookings, when Staff creates a 1-hour walk-in booking with that phone number, then it is created, and P1 still cannot book another hour online."01.1"they are logged in as a Player": FR-01 không nói đăng ký xong thì tự đăng nhập. AC đang thêm requirement.Bổ sung vào FR-01, hoặc đổi Then thành "…and they can log in with that email and password".06.6"at the next login": FR-24 không quy định. Nếu hạ quyền Staff → Player mà session cũ vẫn giữ quyền Staff thì là lỗ hổng bảo mật.Chốt với BA: "…then the user's next request to a Staff API is refused (HTTP 403), even in a session opened before the change."07.1"each court shows whether it is in use now": chưa định nghĩa thế nào là "in use"."Given it is 18:30 and Court A has a Checked-in booking 18:00–19:00 and Court C has none, then Court A shows 'Đang sử dụng' and Court C shows 'Trống'." Nêu rõ trạng thái của 5 booking trong Given.04.1"its other slots are marked Available or Booked": Then này đúng với hầu hết mọi output."Given Court A (06:00–22:00) has a Booked booking 18:00–19:00 and Court B (05:00–23:00) has none… then Court A shows 05:00–06:00 and 22:00–23:00 Closed, 18:00–19:00 Booked, every other slot Available; all 36 slots of Court B are Available."



M4. AC-05.1 và AC-07.6 chỉ kiểm tra UI ("cannot be selected")



Chặn ở UI không chứng minh được FR-15 / FR-29. Ai gọi thẳng API (Postman, k6) vẫn có thể gửi 18:15 hoặc 45 phút. Riêng AC-05.8 đã làm đúng khi kiểm tra cả UI và API.







Đề xuất: áp dụng cùng pattern với AC-05.8:



"…a start time of 18:15 or a duration of 45 minutes cannot be selected, and the same request sent to the API is rejected."



Tương tự cho AC-07.6 (ngày khác hôm nay).



M5. Còn thiếu một số case âm và case biên quan trọng



Bảng dưới là các AC đề xuất thêm. Thông báo lỗi trong bảng chỉ là đề xuất.



AC mớiFR / BRKịch bản (Given / When / Then rút gọn)AC-01.3bFR-01Mật khẩu "12345678" (không có chữ cái) → không tạo tài khoản, hiện cùng thông báo như AC-01.3. (AC-01.3 mới có case thiếu số và thiếu độ dài, chưa có case thiếu chữ.)AC-01.8FR-01, BR-36, NFR-09SĐT "090123456" (9 số) hoặc "1901234567" → hiện "Số điện thoại phải gồm 10 chữ số, bắt đầu bằng 0" cạnh ô SĐT; các ô hợp lệ giữ nguyên giá trị.AC-01.9FR-03Chưa đăng nhập mà gọi API booking → HTTP 401, không trả dữ liệu.AC-03.8FR-03, FR-11, NFR-15P1 dùng ID booking của P2 để xem hoặc hủy qua API → bị từ chối (403/404), booking của P2 không đổi. (Lỗi IDOR, rất hay gặp.)AC-03.9FR-09, BR-03Booking 18:00–19:00 đã Cancelled (hoặc No-show) → Player khác đặt 18:00–19:00 thành công.AC-05.9FR-1518:00–18:30 (30 phút, dưới tối thiểu) bị từ chối · 22:00–23:00 (kết thúc đúng giờ đóng cửa) được nhận · 04:30–05:30 bị từ chối. (AC-05.1 có test 45 phút nhưng đó là test "bội số 30", chưa test "tối thiểu 60".)AC-05.10FR-17, BR-07Đang giữ 10h, hủy online 1 booking 2h → đặt thêm 2h thành công (quota được trả lại).AC-05.11FR-17, BR-07Player có 1 booking 2h đã bắt đầu 10 phút, còn Booked (chưa check-in) và 8h booking khác sắp tới → đặt thêm 2h thành công (booking đã bắt đầu không tính vào quota).AC-06.8FR-25, BR-13Case dương cho AC-06.7: N = 7 thì đặt trước 7 ngày được nhận · quota 8h, đang giữ 7h, đặt thêm 1h được nhận · M = 12h thì hủy booking còn 12h được nhận · booking tạo trước khi đổi cài đặt (10 ngày tới) vẫn ở Booked.AC-06.9FR-21Sân chỉ có booking Completed/Cancelled → ngừng hoạt động sân thành công.AC-07.11FR-30, BR-28Admin hủy với lý do "venue closed / court problem" → Cancelled, ghi lại Admin và lý do · không nhập lý do → không hủy.AC-07.12FR-29, FR-15Walk-in 22:30–23:30 (quá giờ đóng cửa) hoặc dài 30 phút → bị từ chối. (Chưa có AC nào kiểm tra FR-15 áp dụng cho Staff.)AC-07.10 (bổ sung)FR-31, BR-25Thêm No-show vào danh sách trạng thái kết thúc: booking No-show không check-in, không hủy, không đánh dấu lại được.







Minor



m1. Dùng Given/When/Then chưa đúng vai trò. Given nên là trạng thái đã có, When là một hành động:Có hành động nằm trong Given: AC-06.1 "Given the Admin creates Court D", 06.4 "changes", 06.5 "adds", 06.7 "sets" → đổi sang thì hoàn thành: "Given the Admin has set…".



Có dữ liệu nhập nằm trong Given: AC-01.3 "Given the password is…" → chuyển sang When: "When the visitor submits the password 'abcdefgh'".



m2. Tag FR chưa đủ. Nên bổ sung để RTM chính xác:AC-02.2 và 03.5: thêm FR-22



AC-03.7: thêm FR-18 (ghi người hủy và lý do)



AC-04.3: thêm NFR-03 (5 giây)



AC-03.4: thêm NFR-12



m3. Lý do hủy đang để tiếng Anh ("Player online", "customer request"), trong khi đoạn mở đầu nói thông báo được trích theo UI tiếng Việt (NFR-10). Cần ghi rõ đây là mã lý do lưu trong DB, hoặc đổi sang nhãn tiếng Việt hiển thị trên UI.



m4. Độ chính xác thời gian. "18:25 được nhận, 18:26 bị từ chối", vậy 18:25:40 thì sao? Nên thêm một câu vào đoạn mở đầu: "Times are compared to the minute" hoặc ghi biên theo giây.



m5. AC-05.2 nên ghi cả giờ (vd. "16/11/2026 21:00–22:00 is accepted") để chốt cách hiểu "today + 14 calendar days" là tính cả ngày 16/11.



m6. Đoạn mở đầu ghi "F08 is not built" như một quyết định đã chốt, trong khi F08 là Should. Nên đổi thành "These criteria assume F08 is not built; if it is, AC for Pending payment will be added."



m7. Định dạng. AC-07.5 → AC-07.9 đang ở dạng blockquote với ký tự "●" (có vẻ paste từ nơi khác), khác style list của các AC còn lại. Dòng hướng dẫn template "\[For each Must-have feature…]" nên xóa ở bản nộp. 



Here is the complete, revised Section 5.4 Acceptance Criteria for your SRS document, updated based on all major and minor feedback points from the review.



The section now includes a standardized testing context (fixing M1/m4/m6), split single-purpose scenario outlines and criteria (fixing M2/m7), hardened UI+API assertions (fixing M4), refined domain logic and boundaries (fixing M3), explicit missing edge cases (fixing M5), corrected Given/When/Then roles (fixing m1), complete FR/NFR traceability tags (fixing m2), and unified Vietnamese cancellation reason labels (fixing m3).



5.4 Acceptance Criteria

Test Execution Context \& Conventions

Unless explicitly stated otherwise in a criterion, the following test environment conditions apply:



System Clock \& Time Zone: The current time is Monday 02/11/2026 10:00:00 (Asia/Ho\_Chi\_Minh, UTC+7). The test environment can set or inject the system clock. Times are compared to the minute.



Date Offset Rules: Today 

D 

today

​

&#x20;=02/11/2026. The 14-day advance booking window (BR-05) covers bookings starting up to 16/11/2026 23:00.



Initial State: The test Player is logged in and holds no upcoming bookings. Court A is active, open 05:00–23:00, uses default rates (Normal 80,000 / Peak 120,000 / Weekend 120,000 VND), and has no existing bookings.



Scope Assumption: These criteria assume optional feature F08 (Deposit payment) is not enabled; new online bookings start directly in Booked status. (If F08 is enabled, additional criteria for Pending payment status apply).



Cancellation Reason Labels: Stored database reason codes map to user interface labels as: "Player online" 

→ "Người chơi hủy trực tuyến", "customer request" 

→ "Khách hàng yêu cầu", and "venue closed / court problem" 

→ "Sân đóng cửa / Sự cố sân".



F01 – User registration \& login

AC-01.1a (FR-01, BR-33, BR-36)

Given a visitor is on the registration page and the email user@example.com is not in the system,



When the visitor submits the registration form with Full Name "Nguyễn Văn A", Phone "0901234567", Email "user@example.com", Password "abc12345", Password Confirmation "abc12345", and ticks the personal data consent box,



Then a new Player account is created, personal data consent is recorded, and the user can successfully log in using user@example.com and "abc12345".



AC-01.1b (FR-01, NFR-09)

Given a visitor is on the registration page,



When the visitor submits otherwise valid registration data without ticking the personal data consent box,



Then no account is created and "Bạn cần đồng ý với chính sách dữ liệu cá nhân" is displayed next to the consent checkbox.



AC-01.3a (FR-01, NFR-09)

Given a visitor is on the registration page,



When the visitor submits the registration form with password "abcdefgh" (missing digits) or "abc1234" (7 characters),



Then no account is created and "Mật khẩu phải có ít nhất 8 ký tự, gồm cả chữ và số" is displayed next to the password field.



AC-01.3b (FR-01, NFR-09)

Given a visitor is on the registration page,



When the visitor submits the registration form with password "12345678" (missing letters),



Then no account is created and "Mật khẩu phải có ít nhất 8 ký tự, gồm cả chữ và số" is displayed next to the password field.



AC-01.4 (FR-01, NFR-09)

Given an account with email existing@example.com already exists,



When a visitor submits the registration form with email existing@example.com,



Then no account is created and "Email này đã được đăng ký" is displayed next to the email field.



AC-01.5a (FR-02)

Given a registered Player account exists with email player@example.com and password "abc12345",



When the user logs in with email player@example.com and password "abc12345",



Then authentication succeeds and the user session is established.



AC-01.5b (FR-02, NFR-09)

Given a registered Player account exists with email player@example.com and password "abc12345",



When the user logs in with email player@example.com and password "wrongpass",



Then authentication fails, "Email hoặc mật khẩu không đúng" is displayed, and the user remains logged out.



AC-01.6 (FR-02)

Given a logged-in Player,



When the Player logs out and subsequently navigates to the "Lịch đặt của tôi" (My Bookings) page,



Then the application redirects to the login page.



AC-01.7 (FR-03)

Given a logged-in Player,



When the Player navigates to any Staff or Admin URL or sends a request to a Staff/Admin API endpoint,



Then access is denied with HTTP 403 Forbidden and no data is returned.



AC-01.8 (FR-01, BR-36, NFR-09)

Given a visitor is on the registration page,



When the visitor enters phone number "090123456" (9 digits) or "1901234567" (does not start with 0) and submits,



Then no account is created, "Số điện thoại phải gồm 10 chữ số, bắt đầu bằng 0" is displayed next to the phone field, and all valid input fields retain their values.



AC-01.9 (FR-03)

Given an unauthenticated visitor (Guest),



When the visitor sends a request directly to the booking creation API (POST /api/v1/bookings),



Then the request is rejected with HTTP 401 Unauthorized and no booking is created.



F02 – Resource catalog

AC-02.1 (FR-05)

Given 3 active courts and 1 inactive court exist in the system,



When a visitor opens the court catalog,



Then exactly the 3 active courts are displayed—each showing court name, location, capacity, surface type, opening hours, and price list—and the inactive court is hidden.



AC-02.2 (FR-05, FR-22)

Given the Admin has updated the Peak rate of Court A from 120,000 VND/h to 150,000 VND/h,



When a visitor views Court A in the catalog,



Then the displayed Peak rate is 150,000 VND/h.



F03 – Book \& cancel court

AC-03.1 (FR-06, FR-07)

Given Court A has no existing bookings on Monday 09/11/2026 18:00–20:00,



When a Player completes a booking for Court A on 09/11/2026 18:00–20:00,



Then a booking record with status Booked and calculated total price 240,000 VND is created, and the four 30-minute time slots display Booked on the calendar grid.



AC-03.2 (Scenario Outline: Price Preview) (FR-07, FR-08)

Given a Player selects Court A for a reservation,



When the Player chooses the target date and time range specified in the table below,



Then the price preview displayed prior to confirmation matches the expected amount:



Target Date \& Time	Rate Components	Expected Price (VND)

Monday 09/11/2026 16:30–18:00	0.5 h Normal + 1.0 h Peak	160,000

Monday 09/11/2026 20:00–22:00	1.0 h Peak + 1.0 h Normal	200,000

Saturday 07/11/2026 09:00–10:30	1.5 h Weekend	180,000

AC-03.3a (FR-09)

Given Court A has an active booking on 09/11/2026 18:00–19:00,



When another Player attempts to book Court A on 09/11/2026 18:30–19:30,



Then the booking is rejected with "Khung giờ này không còn trống".



AC-03.3b (FR-09, BR-03)

Given Court A has an active booking on 09/11/2026 18:00–19:00,



When another Player attempts to book Court A on 09/11/2026 19:00–20:00 (adjacent half-open interval 

\[19:00,20:00)),



Then the booking request is accepted.



AC-03.4 (FR-09, NFR-12)

Given Court A is free on 09/11/2026 18:00–19:00,



When Player 1 and Player 2 submit booking requests for Court A on 09/11/2026 18:00–19:00 simultaneously,



Then exactly one booking is created in the database, and the unsuccessful Player receives "Khung giờ này không còn trống".



AC-03.5 (FR-10, FR-22)

Given a booking was created on Court A for 09/11/2026 18:00–19:00 at the locked price of 120,000 VND,



When the Admin subsequently updates Court A's Peak rate to 150,000 VND/h,



Then the existing booking retains its original price of 120,000 VND, while a new booking for Tuesday 10/11/2026 18:00–19:00 costs 150,000 VND.



AC-03.6 (FR-11)

Given Player P1 owns 2 bookings and Player P2 owns 1 booking,



When Player P1 opens the "Lịch đặt của tôi" page,



Then exactly P1's 2 bookings are displayed with court, date, time, price, and status, and P2's booking is not listed.



AC-03.7 (FR-12, FR-18, BR-28)

Given a Player owns a Booked booking that starts in 30 hours,



When the Player cancels the booking online,



Then the status transitions to Cancelled, the canceller is recorded as the Player with stored reason "Player online", and the court slots display Available.



AC-03.8 (FR-03, FR-11, NFR-15)

Given Player P1 owns booking BK-100 and Player P2 owns booking BK-200,



When Player P1 issues an API request to view or cancel booking BK-200 using its ID,



Then the request is rejected with HTTP 403 Forbidden or 404 Not Found, and booking BK-200 remains unchanged in Booked status.



AC-03.9 (FR-09, BR-03)

Given Court A had a booking on 09/11/2026 18:00–19:00 that is currently in Cancelled or No-show status,



When another Player books Court A on 09/11/2026 18:00–19:00,



Then the booking is successfully created.



F04 – Availability calendar

AC-04.1 (FR-13, FR-14)

Given Court A (open 06:00–22:00) has a Booked booking on Thursday 05/11/2026 18:00–19:00, and Court B (open 05:00–23:00) has no bookings,



When a Player searches for Thursday 05/11/2026 on the availability calendar,



Then Court A displays time slots 05:00–06:00 and 22:00–23:00 as Closed, 18:00–19:00 as Booked, and all remaining 30-minute slots as Available; and Court B displays all 36 30-minute slots (05:00–23:00) as Available.



AC-04.2 (FR-13)

Given Court C is inactive,



When a Player searches the calendar for any date,



Then Court C is excluded from the results list.



AC-04.3 (FR-14, NFR-03)

Given User 1 and User 2 both have the calendar for 05/11/2026 open,



When User 1 confirms a booking on Court A 18:00–19:00,



Then User 2's calendar updates to show slots 18:00–19:00 as Booked within 5 seconds without requiring a manual page refresh.



F05 – Booking rules

AC-05.1 (FR-15)

Given Court A is open 05:00–23:00,



When a Player attempts to select time slot 22:00–23:30 (exceeds closing time), or start time 18:15 (not on hour/half-hour), or duration 45 minutes,



Then the user interface prevents selection, and if the same payload is transmitted directly to the booking API, the request is rejected with HTTP 400 Bad Request and message "Thời gian đặt không hợp lệ".



AC-05.2 (FR-16, BR-05)

Given current system time is Monday 02/11/2026 10:00,



When a Player books a slot on Monday 16/11/2026 21:00–22:00 (14 calendar days ahead), the booking is accepted; when a Player attempts to book a slot on Tuesday 17/11/2026 09:00–10:00 (15 days ahead), the booking is rejected with "Chỉ được đặt sân trước tối đa 14 ngày".



AC-05.3a (FR-16, BR-05)

Given current system time is 17:00,



When a Player books Court A starting at 17:30 (exactly 30 minutes lead time),



Then the booking is accepted.



AC-05.3b (FR-16, BR-05)

Given current system time is 17:01,



When a Player attempts to book Court A starting at 17:30 (29 minutes lead time),



Then the request is rejected with "Phải đặt trước giờ chơi ít nhất 30 phút", and the earliest available start time offered is 18:00.



AC-05.4 (FR-17, BR-06)

Given a Player currently holds 9 hours of upcoming Booked reservations,



When the Player attempts to book an additional 2-hour slot,



Then the booking is rejected with "Bạn chỉ có thể đặt thêm 1 giờ" (10-hour quota limit reached).



AC-05.5 (FR-17, BR-06, BR-07)

Given a Player has 8 hours of Completed bookings in the past 7 days and currently holds 0 upcoming bookings,



When the Player sequentially creates four new bookings of 3 h, 3 h, 2 h, and 2 h duration (total 10 hours upcoming),



Then all four booking requests are accepted.



AC-05.6 (FR-17, BR-06)

Given a Player currently holds 9 hours of upcoming Booked reservations,



When the Player submits two separate 1-hour booking requests simultaneously,



Then exactly one request is accepted, and the second request is rejected with "Bạn đã đạt giới hạn 10 giờ đặt sân".



AC-05.7a (FR-18, BR-08)

Given current time is 12:00 and a Player owns a Booked booking scheduled for today at 18:00 (exactly 6 hours away),



When the Player requests online cancellation,



Then the cancellation is accepted and status changes to Cancelled.



AC-05.7b (FR-18, BR-08)

Given current time is 12:01 and a Player owns a Booked booking scheduled for today at 18:00 (5 hours 59 minutes away),



When the Player requests online cancellation,



Then the request is rejected with "Đã quá hạn hủy trực tuyến, vui lòng liên hệ sân" and the status remains Booked.



AC-05.8 (FR-18, BR-10)

Given a booking's scheduled start time has passed (

T 

current

​

&#x20;≥T 

start

​

&#x20;),



When the Player views the "Lịch đặt của tôi" page,



Then no "Hủy đặt sân" button is rendered, and an explicit API cancellation request sent for this booking is rejected with HTTP 400 Bad Request.



AC-05.9 (FR-15)

Given Court A is open 05:00–23:00,



When a Player attempts a 30-minute booking from 18:00 to 18:30, or a booking from 04:30 to 05:30 (starts before opening),



Then the system rejects the request with "Thời lượng đặt sân tối thiểu là 60 phút và phải nằm trong giờ mở cửa"; when a Player books from 22:00 to 23:00 (ends exactly at closing time), the request is accepted.



AC-05.10 (FR-17, BR-07)

Given a Player holds 10 hours of upcoming Booked reservations,



When the Player cancels a 2-hour booking online,



Then the booking status becomes Cancelled, and a subsequent 2-hour booking attempt by the Player succeeds (quota is released).



AC-05.11 (FR-17, BR-07)

Given a Player owns 8 hours of upcoming reservations plus a 2-hour booking on Court A 09:00–11:00 that started 10 minutes ago (current time 09:10, status still Booked),



When the Player books an additional 2-hour slot for tomorrow,



Then the request is accepted (bookings whose start time has passed no longer count toward the upcoming quota).



F06 – Court management (Admin)

AC-06.1a (FR-19)

Given the Admin has created Court D with Name "Sân 04", Location "Khu B", Capacity 4, and Surface Type "Thảm PVC",



When a visitor opens the court catalog,



Then Court D is listed with those properties.



AC-06.1b (FR-19)

Given Court D exists in the catalog,



When the Admin updates Court D's surface type to "Gỗ thảm",



Then the catalog displays "Gỗ thảm" for Court D.



AC-06.2 (FR-20)

Given Court A has a Booked booking on Thursday 12/11/2026 21:00–22:00,



When the Admin updates Court A's closing time from 23:00 to 21:00,



Then the existing 21:00–22:00 booking is preserved, while new booking attempts for Court A past 21:00 on Friday 13/11/2026 are rejected.



AC-06.3a (FR-21)

Given Court B has a future Booked reservation,



When the Admin attempts to deactivate Court B,



Then the system refuses with "Không thể ngừng hoạt động sân còn lịch đặt" and displays the list of active bookings.



AC-06.3b (FR-21)

Given Court B's future active bookings have all been cancelled,



When the Admin deactivates Court B,



Then deactivation succeeds, and Court B no longer appears in the public court catalog.



AC-06.4 (FR-22)

Given the Admin has updated Court A's Normal rate to 90,000 VND/h,



When a Player selects Court A on Thursday 12/11/2026 10:00–11:00,



Then the calculated price displayed is 90,000 VND.



AC-06.5 (FR-23)

Given the Admin has added Monday 16/11/2026 to the public holiday list,



When a Player selects Court A 10:00–11:00 on 16/11/2026,



Then the calculated price displayed is 120,000 VND (Weekend rate) instead of 80,000 VND.



AC-06.6a (FR-24)

Given the Admin creates a new Staff account,



When the Staff user logs in,



Then the interface displays front-desk operational functions and blocks access to Admin management pages.



AC-06.6b (FR-24, FR-03)

Given a user is logged in with an active Staff session token,



When the Admin downgrades that user's role to Player,



Then the user's next request to a Staff API endpoint is rejected with HTTP 403 Forbidden, even within the existing session.



AC-06.7 (FR-25)

Given the Admin has updated system policies to: Advance Window 

N=7 days, Booking Quota 

=8 hours, and Cancellation Deadline 

M=12 hours,



When a Player attempts to book 8 days ahead, or holds 7 upcoming hours and attempts a 2-hour booking, or attempts to cancel online a booking starting in 10 hours,



Then all three operations are rejected according to the new policy limits.



AC-06.8 (FR-25, BR-13)

Given the Admin has set 

N=7 days, Quota 

=8 hours, and 

M=12 hours,



When a Player books 7 days ahead, or holds 7 upcoming hours and books 1 additional hour, or cancels online a booking starting in 12 hours,



Then all three operations are accepted. Existing bookings created prior to the policy update retain their validity.



AC-06.9 (FR-21)

Given Court C has only past Completed or Cancelled bookings and zero future active bookings,



When the Admin deactivates Court C,



Then the court status changes to Inactive successfully.



F07 – Front-desk operations (Staff)

AC-07.1 (FR-26)

Given current system time is 18:30 on 02/11/2026, Court A has a Checked-in booking 18:00–19:00, Court B has a Booked booking 19:00–20:00, and Court C has no bookings today,



When Staff opens today's schedule view,



Then the schedule lists both bookings with customer name, phone number, and status; and the real-time status indicator displays "Đang sử dụng" for Court A, and "Trống" for Court B and Court C.



AC-07.2 (Scenario Outline: Check-in Window) (FR-27, BR-29)

Given Court A has a Booked booking starting at 18:00,



When Staff executes a check-in request at the specified timestamp 

T 

check−in

​

&#x20;,



Then the outcome matches the expected result:



Check-in Time (T 

check−in

​

&#x20;)	Expected Result / Status	UI Message

17:44	Rejected (Booked)	"Check-in chỉ mở từ 17:45 (trước 15 phút)"

17:45	Accepted (Checked-in)	"Check-in thành công"

18:25	Accepted (Checked-in)	"Check-in thành công"

18:26	Rejected (Booked)	"Đã hết thời gian check-in"

AC-07.3 (FR-28, BR-30, BR-31)

Given Court A has a Booked booking on 18:00–20:00 and current time is 18:26 (customer failed to check in),



When Staff marks the booking as No-show,



Then the status updates to No-show, and Court A's time slots 18:30–20:00 become Available on the calendar for walk-in bookings.



AC-07.4 (FR-28)

Given Court A has a Booked booking 18:00–19:00 and customer does not check in,



When system time reaches 18:40 and no Staff action has been taken,



Then the booking status remains Booked (the system does not execute automatic no-shows).



AC-07.5 (FR-29, BR-11, BR-33)

Given Player P1 (phone 0901234567) holds 10 hours of upcoming online bookings, Court A is free on 02/11/2026 14:15, and Staff creates a 1-hour walk-in booking for a customer with phone 0901234567 starting at 14:30 while ticking personal data consent,



Then the walk-in booking is created directly in Checked-in status at 80,000 VND, and Player P1's online booking quota remains maxed out (P1 still cannot make new online bookings).



AC-07.6 (FR-29, FR-15)

Given Staff is creating a walk-in booking,



When Staff leaves the personal data consent box unticked, or selects a date other than today,



Then the user interface prevents creation, and an API request with an invalid date or missing consent is rejected.



AC-07.7 (FR-09, FR-29)

Given Court A has an online booking 18:00–19:00 today,



When Staff attempts to create a walk-in booking on Court A 18:30–19:30,



Then the system rejects the creation with "Khung giờ này không còn trống".



AC-07.8 (FR-30, BR-28)

Given a Booked booking starts in 3 hours,



When Staff cancels the booking selecting reason "Khách hàng yêu cầu",



Then booking status becomes Cancelled, court slots show Available, and the record logs the Staff user ID and reason "customer request".



AC-07.9 (FR-30)

Given a booking's start time has passed (

T 

current

​

&#x20;≥T 

start

​

&#x20;),



When Staff or Admin attempts to cancel the booking,



Then the cancellation request is rejected.



AC-07.10 (FR-31, BR-25, BR-27)

Given a booking is in Checked-in status for slot 18:00–19:00,



When system time passes 19:00:00,



Then the status automatically updates to Completed. For bookings in terminal states (Completed, Cancelled, No-show), Staff actions for check-in, no-show marking, or cancellation are disabled and rejected by the API.



AC-07.11 (FR-30, BR-28)

Given Court A encounters a net damage issue,



When Admin cancels an upcoming booking on Court A providing reason "Sân đóng cửa / Sự cố sân",



Then the booking status becomes Cancelled with recorded canceller Admin and reason "venue closed / court problem"; if Admin submits the cancellation without selecting/entering a reason, the request is rejected.



AC-07.12 (FR-29, FR-15)

Given Court A closes at 23:00,



When Staff attempts to create a walk-in booking for 22:30–23:30 (exceeds closing time) or for a 30-minute duration,



Then the system rejects the walk-in booking creation with "Thời gian đặt không hợp lệ".

