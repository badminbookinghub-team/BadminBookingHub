---
title: "PA2-ai-usage-log-Phuc"
source: https://chatgpt.com/c/6aded020-9b80-83ec-847a-d4c8790cd1f8
exported: 2026-11-11T11:25:09.647Z
messages: 34
---
# PA2-ai-usage-log-Phuc

---

## You

`1 of 34`

Web search
 Hướng dẫn tôi viết nonfunctional requirement cho một dự án phần mềm, tham khảo từ những sách/blog/post/khóa học.


---

## ChatGPT

`2 of 34`

### Hướng dẫn viết Non-Functional Requirements (NFR) cho dự án phần mềm

Tôi đã tìm được một số tài liệu từ **Microsoft, Carnegie Mellon University (SEI), ISO, Volere Requirements** và các sách chuyên ngành Requirements Engineering.

Nếu mục tiêu của bạn là vừa học lý thuyết, vừa biết cách viết phần *Non-Functional Requirements* trong Software Requirements Specification (SRS) cho đồ án đại học, tôi đề xuất tập trung vào ba câu hỏi:

1. **Identification:** Làm thế nào để xác định dự án cần những NFR nào?
2. **Specification:** Làm thế nào để chuyển yêu cầu chung chung thành yêu cầu rõ ràng, có thể đo lường?
3. **Verification:** Làm thế nào để chứng minh phần mềm đáp ứng được từng NFR?

#### 1. Trước hết, NFR là gì?

Functional Requirements (FR) mô tả chức năng mà phần mềm phải cung cấp. Non-Functional Requirements mô tả những thuộc tính chất lượng và ràng buộc mà hệ thống phải đáp ứng.

Ví dụ với ứng dụng đặt sân cầu lông:

| Functional Requirement | Non-Functional Requirement |
| --- | --- |
| Người dùng có thể tìm sân còn trống | 95% yêu cầu tìm sân hoàn thành trong 2 giây khi có 30 người dùng đồng thời |
| Người dùng có thể đăng nhập | Thông tin đăng nhập phải được truyền qua kết nối HTTPS |
| Chủ sân có thể quản lý lịch đặt | Giao diện quản lý phải sử dụng được trên màn hình có độ rộng 360px trở lên |
| Nhân viên có thể xem danh sách đặt sân | Dữ liệu đặt sân phải được khôi phục trong vòng 4 giờ sau một sự cố đã xác định |

Các con số ở đây chỉ là **mục tiêu minh họa**, chưa phải tiêu chuẩn bắt buộc hay số liệu đã được kiểm chứng cho dự án.

Microsoft đưa ra một nguyên tắc rất đáng chú ý: NFR phải cụ thể, có thể đo lường, kiểm thử được, gắn với mục tiêu nghiệp vụ và có xét đến các đánh đổi kỹ thuật.

Cấu trúc đơn giản bạn có thể áp dụng là:

Mẫu viết một Non-Functional Requirement

**Trong điều kiện** $environment$, **khi** $event/workload$, **hệ thống phải** $expected behavior$, **đạt** $measurable target$, **được kiểm chứng bằng** $verification method$.

Điểm quan trọng nhất: **Không nên chỉ viết “The system must be fast, secure and user-friendly”.** Những mô tả đó chưa đủ cụ thể để người phát triển hoặc người kiểm thử xác định yêu cầu đã được đáp ứng hay chưa.

#### 2. Các tài liệu nên đọc

Đây là 8 nguồn tôi đánh giá phù hợp nhất, sắp xếp theo mục đích học.

**1. Microsoft — Non-Functional Requirements Capture Guide** (Ưu tiên đọc)

Engineering guide · Miễn phí

Hướng dẫn trực tiếp cách xác định, ghi chép, ưu tiên và kiểm chứng NFR. Có mẫu với Description, Priority, Metric, Verification Method, Constraints và nhiều loại quality attributes.

**Phù hợp:** Bạn muốn đọc một tài liệu rồi bắt đầu viết NFR ngay.

[*[Embedded image]*

Đọc Microsoft NFR Capture Guide](https://github.com/microsoft/code-with-engineering-playbook/blob/main/docs/design/design-patterns/non-functional-requirements-capture-guide.md?plain=1&utm_source=chatgpt.com)

---

**2. Old Dominion University — Writing Requirements**

University lecture · Miễn phí

Bài giảng có ví dụ về FR/NFR, đặc điểm của một SRS tốt, cách viết requirements bằng Structured English và cách tổ chức tài liệu theo chuẩn SRS. Đọc kỹ phần 4.3–4.5, đặc biệt các ví dụ có yêu cầu hiệu năng đo bằng thời gian.

[Xem bài giảng Writing Requirements](https://www.cs.odu.edu/~zeil/cs350/latest/Public/reqts/reqts__slides.html?utm_source=chatgpt.com)

---

**3. Volere Requirements Specification Template**

Template + Worked Examples · Có bản xem miễn phí

Nguồn rất đáng đọc nếu bạn muốn học cách viết NFR trong một bản SRS hoàn chỉnh. Đặc biệt quan trọng là khái niệm *Fit Criterion*, tức tiêu chí cho phép xác nhận một requirement đã đạt hay chưa.

Website có mẫu và ví dụ công khai; bộ đầy đủ kèm hai worked examples thường có phí, nhưng có ngoại lệ dành cho mục đích học thuật.

[Xem Volere Template và ví dụ](https://www.volere.org/templates/volere-requirements-specification-template/?utm_source=chatgpt.com)

---

**4. SEI — Quality Attribute Workshop (QAW)**

Carnegie Mellon University · Báo cáo và workshop miễn phí

Giải quyết câu hỏi khó hơn: làm thế nào khám phá các NFR từ mục tiêu kinh doanh, stakeholders và những tình huống xảy ra trong thực tế? SEI sử dụng phương pháp phát triển các quality attribute scenarios, đánh giá và ưu tiên chúng trước khi quyết định kiến trúc.

[Đọc Quality Attribute Workshop Collection](https://www.sei.cmu.edu/library/quality-attribute-workshop-collection/?utm_source=chatgpt.com)

---

**5.**

Sách chuyên ngành · Suzanne Robertson & James Robertson

Đây là lựa chọn sách chuyên sâu phù hợp nhất cho mục tiêu của bạn. Đọc **Chapter 11 — Non-functional Requirements (trang 245–277)** và **Chapter 12 — Fit Criteria and Rationale (trang 279–301)**. Hai chương giải thích cách tìm NFR, phân loại, tránh mô tả giải pháp quá sớm và xây dựng các tiêu chí đo lường.

[Xem sách và mục lục tại Pearson](https://www.pearson.com/en-us/subject-catalog/p/Robertson-Mastering-the-Requirements-Process-Getting-Requirements-Right-3rd-Edition/P200000000572/9780321815743?utm_source=chatgpt.com)

---

**6.**

Sách kiến trúc phần mềm · Bass, Clements & Kazman

Tập trung Chapter 3 — Understanding Quality Attributes, đặc biệt mục 3.3 *Specifying Quality Attribute Requirements*. Những chương sau liên hệ NFR với Availability, Performance, Security, Testability, Deployability và các lựa chọn thiết kế kiến trúc.

[Xem mục lục và giới thiệu sách](https://www.oreilly.com/library/view/software-architecture-in/9780136885979/?utm_source=chatgpt.com)

---

**7. ISO/IEC 25010:2023 — Product Quality Model**

Tiêu chuẩn quốc tế · Bản đầy đủ có phí

Khung tham chiếu để không bỏ sót các nhóm quality attributes. Phiên bản 2023 có 9 đặc tính chất lượng, trong đó có Performance Efficiency, Reliability, Security, Maintainability, Interaction Capability và Flexibility.

[Xem tiêu chuẩn ISO/IEC 25010:2023](https://www.iso.org/standard/78176.html?utm_source=chatgpt.com)

---

**8. OWASP ASVS và Google SRE Workbook**

Các hướng dẫn thực hành chuyên sâu · Miễn phí

OWASP ASVS 5.0 cung cấp yêu cầu có thể kiểm chứng về bảo mật ứng dụng web. Google SRE Workbook, Chapter 2 hướng dẫn cách lựa chọn chỉ số SLI và mục tiêu SLO cho latency, availability và reliability, có ví dụ cụ thể.

[OWASP ASVS](https://asvs.owasp.org/?utm_source=chatgpt.com) · [Google SRE — Implementing SLOs](https://sre.google/workbook/implementing-slos/?utm_source=chatgpt.com)

#### 3. Quy trình viết NFR từ một mô tả nghiệp vụ

Tôi đề xuất quy trình 5 bước dưới đây, tổng hợp từ Microsoft NFR Capture Guide, Volere và phương pháp QAW của SEI.

**01 — Business Goals & Functional Requirements**

Đọc các chức năng chính và nhu cầu của stakeholders

**02 — Quality Attributes**

Chọn Performance, Security, Reliability, Usability...

**03 — Quality Attribute Scenarios**

Xác định tình huống, tải hệ thống, điều kiện sử dụng

**04 — Measurable Requirements**

Viết ngưỡng chấp nhận, độ ưu tiên, phạm vi áp dụng

**05 — Verification & Validation**

Thiết kế bài kiểm thử, thực hiện và so sánh kết quả

##### Ví dụ chi tiết: Hiệu năng tìm kiếm sân

**Bước 1 — Xác định chức năng**

> Người chơi cần tìm danh sách sân còn trống theo ngày, giờ và khu vực.

Đây là Functional Requirement. Bây giờ chúng ta cần tìm hiểu những đặc tính chất lượng liên quan.

**Bước 2 — Đặt câu hỏi để khám phá NFR**

Đối với chức năng tìm sân, những câu hỏi phù hợp là: người dùng chấp nhận chờ bao lâu? Có bao nhiêu người có thể tìm sân đồng thời? Hệ thống chạy trên cấu hình nào? Số lượng sân và lịch đặt dự kiến bao nhiêu?

Điều này dẫn đến hai nhóm NFR quan trọng: Performance Efficiency và Capacity.

**Bước 3 — Tạo Quality Attribute Scenario**

Theo cách tiếp cận SEI, một scenario đầy đủ gồm sáu thành phần.

| Thành phần | Ví dụ |
| --- | --- |
| Source | Người chơi |
| Stimulus | Gửi yêu cầu tìm sân |
| Environment | 30 người dùng đồng thời, 10.000 bản ghi lịch đặt |
| Artifact | Search API và database |
| Response | Trả về danh sách sân còn trống |
| Response Measure | p95 latency không vượt 2 giây |

**Bước 4 — Viết thành NFR hoàn chỉnh**

**NFR-PERF-01 — Search Response Time** (High Priority)

Requirement Statement

The system shall respond to at least 95% of valid court availability search requests within 2 seconds under a workload of 30 concurrent virtual users and a database containing 10,000 booking records, when tested in the designated staging environment.

---

Metric

**p95 latency ≤ 2 seconds**

Verification

**k6 / Load testing**

Scope

**Court search API**

Status

**Proposed target**

Ở đây, p95 latency ≤ 2 giây có nghĩa là ít nhất 95% các yêu cầu được đo có thời gian phản hồi không vượt quá 2 giây. Cần quy định thêm thời lượng chạy test, tốc độ gửi yêu cầu, tiêu chí tính request thành công và cấu hình môi trường.

**Bước 5 — Kiểm chứng**

Bạn sử dụng công cụ load testing, tạo workload phù hợp, thu thập latency và đối chiếu với ngưỡng 2 giây. Nếu bài test không đạt, requirement vẫn giữ nguyên cho đến khi nhóm quyết định điều chỉnh mục tiêu hoặc cải thiện hệ thống.

Cách làm này quan trọng hơn việc chỉ liệt kê các mục “Performance”, “Security”, “Reliability” mà không có phương pháp kiểm chứng.

#### 4. Bộ NFR mẫu cho đồ án đặt sân cầu lông

Dưới đây là bộ yêu cầu minh họa tương đối thực tế cho một ứng dụng web nhỏ, có backend Express, PostgreSQL và triển khai trên EC2.

Các ngưỡng cần được nhóm thống nhất sau khi đánh giá nhu cầu và khả năng triển khai; không nên sao chép chúng như những kết quả đã được bảo đảm.

| ID | Quality Attribute | Requirement mẫu | Verification |
| --- | --- | --- | --- |
| NFR-01 | Performance | p95 thời gian phản hồi của Search API ≤ 2 giây dưới tải thử nghiệm đã xác định | Load test |
| NFR-02 | Capacity | Hệ thống xử lý được 30 người dùng tìm sân đồng thời mà không vượt ngưỡng lỗi 1% trong bài test 10 phút | k6 |
| NFR-03 | Security | Tất cả truy cập HTTP tới ứng dụng phải được chuyển hướng sang HTTPS, ngoại trừ các endpoint phục vụ xác thực chứng chỉ nếu cần | HTTPS test |
| NFR-04 | Reliability | Khi tiến trình backend dừng bất thường, dịch vụ phải tự khởi động lại trong vòng 60 giây nếu host và các dependency vẫn hoạt động | Fault-injection test |
| NFR-05 | Recoverability | Trong kịch bản mất dữ liệu giả lập, cơ sở dữ liệu phải khôi phục được từ bản backup gần nhất trong vòng 4 giờ | Restore drill |
| NFR-06 | Usability | Ít nhất 80% người tham gia thử nghiệm lần đầu hoàn tất quy trình đặt sân trong 3 phút mà không cần hướng dẫn | Usability testing |
| NFR-07 | Compatibility | Các luồng đăng nhập, tìm sân và đặt sân phải hoàn tất trên các phiên bản Chrome và Firefox được chọn trong test matrix | Cross-browser E2E |
| NFR-08 | Maintainability | Thay đổi một mức giá sân theo chính sách hiện có không đòi hỏi sửa mã nguồn frontend hoặc redeploy ứng dụng | Change scenario test |
| NFR-09 | Deployability | Sau khi artifact được build thành công, quy trình triển khai tự động phải hoàn tất trong vòng 10 phút trong môi trường demo bình thường | CI/CD timing |

Không nhất thiết phải có NFR cho mọi nhóm chất lượng trong ISO. Ưu tiên những thuộc tính ảnh hưởng trực tiếp đến nghiệp vụ và có khả năng kiểm chứng.

Một phân biệt đáng chú ý: **“Không cho phép hai người đặt trùng một sân trong cùng khung giờ”** chủ yếu là Functional Requirement hoặc Business Rule về tính toàn vẹn đặt chỗ, không nên mặc định xếp nó vào NFR chỉ vì liên quan đến reliability.

#### 5. Template nên sử dụng trong tài liệu SRS

Bạn có thể chọn mẫu dưới đây, kết hợp cách trình bày của Microsoft với *Fit Criterion* của Volere.

**Reusable NFR Specification Template** \[Copy\]

Với một đồ án nhỏ, bạn có thể rút gọn còn ID, Requirement, Priority, Fit Criterion và Verification Method.

#### 6. Nên học theo thứ tự nào?

Tôi khuyên bạn bắt đầu với [bài giảng Writing Requirements của Old Dominion University](https://www.cs.odu.edu/~zeil/cs350/latest/Public/reqts/reqts__slides.html?utm_source=chatgpt.com) để hiểu cách diễn đạt, sau đó chuyển sang [*[Embedded image]*

Microsoft NFR Capture Guide](https://github.com/microsoft/code-with-engineering-playbook/blob/main/docs/design/design-patterns/non-functional-requirements-capture-guide.md?plain=1&utm_source=chatgpt.com) để có template và phương pháp áp dụng. Tiếp theo, đọc ví dụ Fit Criterion của [Volere](https://www.volere.org/templates/volere-requirements-specification-template/?utm_source=chatgpt.com).

Nếu muốn đào sâu Requirements Engineering thay vì chỉ hoàn thành phần SRS, hãy học Chapter 11 và 12 của *Mastering the Requirements Process*, rồi nghiên cứu phương pháp scenario-based requirements của SEI.

Điều quan trọng cuối cùng là **viết NFR dựa trên nhu cầu chất lượng của hệ thống, không dựa trên những công nghệ bạn đã lựa chọn**. Ví dụ, “The system shall use PostgreSQL” thường là một ràng buộc thiết kế/công nghệ nếu đã được áp đặt, không phải NFR về hiệu năng hay độ tin cậy. Cần phân biệt rõ *what quality is required* và *how the architecture achieves it*.


---

## You

`3 of 34`

PA1 - 08.docx
 
PA0 - 08.docx
 Bạn có thể gợi ý những NFR cần thiết cho dự án của tôi được không


---

## ChatGPT

`4 of 34`

### Đề xuất Non-Functional Requirements cho BadminBookingHub

Sau khi đối chiếu nội dung PA0 và PA1, tôi đề xuất **12 Non-Functional Requirements (NFR)** cho dự án BadminBookingHub, tập trung vào những thuộc tính chất lượng có ảnh hưởng trực tiếp đến hệ thống đặt sân cầu lông.

Bộ NFR này được thiết kế cho phần **2.2.2 — Non-Functional Requirements của PA2**, với ba nguyên tắc:

- Mỗi NFR phải có tiêu chí đo lường và phương pháp kiểm chứng.
- Phù hợp với phạm vi 7 Must-have features (F01–F07), nhóm 5 sinh viên và thời gian triển khai ngắn.
- Không đặt ra yêu cầu vượt xa khả năng của kiến trúc một EC2 instance dùng React, Express và PostgreSQL.

PA1 yêu cầu mọi NFR đều measurable, trong khi PA5 yêu cầu các Must-have features được triển khai và kiểm thử trước ngày 09/12/2026.

#### 1. Những đặc tính chất lượng thực sự quan trọng

Dựa trên mục tiêu và phạm vi của dự án, tôi đề xuất thứ tự ưu tiên sau.

| Quality Attribute | Độ ưu tiên | Lý do |
| --- | --- | --- |
| Security | Must | Có đăng nhập và ba vai trò Player, Staff, Admin |
| Data Integrity | Must | Booking, cancellation và pricing cần dữ liệu nhất quán |
| Performance Efficiency | Must | Tìm kiếm và đặt sân, nhất là giờ cao điểm |
| Usability | Must | Người dùng phổ thông phải đặt sân dễ dàng |
| Compatibility | Must | Ứng dụng web dùng trên desktop và mobile |
| Reliability | Should | Đảm bảo khả năng khôi phục từ một số lỗi thông thường |
| Maintainability | Should | Nhóm cần dễ dàng sửa lỗi và mở rộng |
| Observability | Should | Hỗ trợ chẩn đoán lỗi khi demo và kiểm thử |

Theo PA1, giá trị cốt lõi của BadminBookingHub là giảm sai sót đặt sân, ngăn đặt trùng lịch, quản lý booking policies và hỗ trợ hoạt động của nhân viên lễ tân. Đây là cơ sở để lựa chọn NFR, thay vì cố gắng bao phủ mọi đặc tính chất lượng trong ISO 25010.

#### 2. Bộ NFR cốt lõi đề xuất cho PA2

Các requirement statement được viết bằng tiếng Anh để có thể đưa vào SRS.

Các ngưỡng như 2 giây, 20 người dùng hoặc 80% là giá trị đề xuất ban đầu, chưa phải kết quả benchmark đã kiểm chứng. Nhóm cần phê duyệt chúng khi lập PA2.

| ID | Requirement Statement | Priority | Verification |
| --- | --- | --- | --- |
| NFR-01 | **Performance:** The system shall respond to at least 95% of court search and availability requests within 2 seconds under a workload of 20 concurrent virtual users and 5,000 booking records in the designated test environment. | Must | Load test với k6 |
| NFR-02 | **Booking Transaction Performance:** At least 95% of valid booking requests shall complete within 3 seconds under 20 concurrent virtual users, excluding network delays outside the test environment. | Must | API load testing |
| NFR-03 | **Security — Authorization:** All protected API endpoints shall reject requests from unauthenticated or unauthorized users, according to the approved Player–Staff–Admin permission matrix. | Must | Authorization test matrix với Supertest |
| NFR-04 | **Security — Data Protection:** In public deployment, all browser-to-server application traffic shall use HTTPS. User passwords shall never be stored in plaintext or included in API responses. | Must | HTTPS inspection, DB inspection, API tests |
| NFR-05 | **Data Integrity:** After a successful booking, cancellation or check-in transaction, all subsequent database reads shall reflect the committed operation without partially persisted changes. | Must | Integration tests, rollback tests |
| NFR-06 | **Usability:** At least 80% of first-time test users shall complete a court booking within 2 minutes without external assistance, excluding registration and payment. | Must | Task-based usability testing |
| NFR-07 | **Responsive Design:** All Must-have user workflows shall remain usable at viewport widths of 360px and 1280px without horizontal page scrolling or inaccessible controls. | Must | Playwright viewport tests |
| NFR-08 | **Browser Compatibility:** All Must-have workflows shall pass the same end-to-end acceptance tests on the agreed Chrome and Firefox desktop versions. | Must | Playwright cross-browser tests |

Đặc biệt, NFR-06 liên hệ trực tiếp với mục tiêu ban đầu trong PA0: người chơi có thể tìm và đặt sân trong thời gian dưới hai phút. Tuy nhiên, tôi loại trừ payment khỏi phép đo vì trong PA1, F08 — Deposit Payment chỉ là Should-have, không phải tính năng bắt buộc.

#### 3. Các NFR bổ sung nên cân nhắc

| ID | Requirement Statement | Priority | Verification |
| --- | --- | --- | --- |
| NFR-09 | **Availability Freshness:** When a booking is confirmed or cancelled, the corresponding court availability changes shall become visible to other users within 5 seconds while their availability calendars remain open. | Must | Multi-user E2E test |
| NFR-10 | **Recoverability:** The team shall be able to restore the application database from a valid backup no more than 24 hours old within 30 minutes in the designated test environment. | Should | Backup/restore drill |
| NFR-11 | **Observability:** Every server-side HTTP 5xx response shall produce a diagnostic log containing a timestamp, request identifier, route and status code, without exposing passwords or authentication tokens. | Should | Fault-injection test và log inspection |
| NFR-12 | **Testability:** Automated unit tests shall achieve at least 70% statement coverage of the backend service layer. | Should | Vitest coverage report |

NFR-12 không phải ngưỡng mới được suy đoán: mục tiêu tối thiểu 70% statement coverage đã xuất hiện trong kế hoạch PA5 của nhóm.

Tôi xếp NFR-09 vào Must vì F04 của PA1 ghi rõ availability calendar cần được cập nhật theo thời gian thực. Ngưỡng 5 giây chỉ là đề xuất để cụ thể hóa khái niệm đó. Nhóm nên thống nhất thêm liệu chức năng sẽ dùng polling, WebSocket hay cơ chế khác trong PA3.

#### 4. Ánh xạ NFR với Functional Requirements

NFR thường là yêu cầu xuyên suốt, có thể ảnh hưởng nhiều FR. Vì vậy, bảng sau chỉ thể hiện các mối liên hệ trực tiếp nhất.

| Feature trong PA1 | NFR liên quan |
| --- | --- |
| F01 — User registration & login | NFR-03, 04 |
| F02 — Resource catalog | NFR-01, 07, 08 |
| F03 — Book & cancel court | NFR-02, 05, 06, 09 |
| F04 — Availability calendar | NFR-01, 07, 09 |
| F05 — Booking rules | NFR-05, 12 |
| F06 — Court management | NFR-03, 05, 08 |
| F07 — Front-desk operations | NFR-03, 05, 07, 08 |
| Across all features | NFR-10, 11, 12 |

#### 5. Điểm cần phân biệt: Business Rules và NFR

Đây là vấn đề đặc biệt quan trọng đối với BadminBookingHub.

Trong PA0 và PA1, nhóm xác định ngăn chặn *double booking* là một trong những yêu cầu quan trọng nhất, kể cả khi hai người thực hiện đặt cùng khung giờ đồng thời.

Tôi khuyến nghị đặc tả nó trước tiên như một Business Rule:

**BR-01 — Booking Exclusivity**

> For any given court, the system shall not maintain more than one active, confirmed booking covering overlapping time intervals.

Sau đó xây dựng bài kiểm thử đồng thời. Ví dụ, gửi 50 yêu cầu đặt cùng một sân và khung giờ từ 50 người dùng khác nhau; hệ thống chỉ được xác nhận tối đa một booking và không được tạo trạng thái dữ liệu mâu thuẫn.

Đây là kiểm thử tính đúng đắn của nghiệp vụ dưới điều kiện đồng thời, không nên thay thế Business Rule bằng một NFR chung chung như “The system must be reliable”.

Tương tự, weekly booking-hour limits, advance-booking windows và cancellation deadlines thuộc Business Rules. Các NFR chỉ bổ sung những yêu cầu chất lượng như thời gian phản hồi, bảo mật, tính toàn vẹn và khả năng kiểm chứng.

#### 6. Làm thế nào để chọn những NFR khả thi?

Tôi đề xuất một nhóm NFR chỉ được đưa vào baseline PA2 sau khi trả lời được bốn câu hỏi:

- NFR đó xuất phát từ mục tiêu hay rủi ro cụ thể nào trong PA0/PA1?
- Nó có metric và ngưỡng chấp nhận xác định hay không?
- Có thể kiểm chứng bằng một bài test phù hợp với nguồn lực của nhóm hay không?
- Nếu chưa đạt, nhóm có thời gian và khả năng cải thiện trước PA5 hay không?

Đối với những NFR về performance, cần thống nhất thêm cấu hình test environment, dữ liệu mẫu, thời lượng test, tải đồng thời và định nghĩa latency. Không nên chỉ ghi response time <escape><</escape> 2 seconds.

Đối với reliability, tôi không đề xuất availability 99.9%, auto-scaling, multi-region failover hay zero-downtime deployment. PA1 giới hạn hệ thống ở mức demo trên một EC2 instance và nêu rõ production support cùng SLA thực tế nằm ngoài phạm vi của đồ án.

**Khuyến nghị cho bản PA2:** Sử dụng NFR-01 đến NFR-09 làm bộ yêu cầu chính, giữ NFR-10 đến NFR-12 nếu nhóm cam kết có thể kiểm chứng. Đặc biệt, ưu tiên chuẩn bị test cho performance, security, data integrity và availability freshness trước khi mở rộng sang các NFR ít liên quan hơn đến chức năng cốt lõi.

Tiêu đề chat đề xuất: $Software Engineering$ - Thiết kế NFR cho BadminBookingHub (26/10/2026)


---

## You

`5 of 34`

Tôi muốn hỏi về NFR-07 bạn đề xuất, hiện nay một phần mềm webapp nên responsive ở những loại khung hình/tỷ lệ nào để đáp ứng được như cầu đa nền tảng, Computer/Mobile phone


---

## ChatGPT

`6 of 34`

Đối với **BadminBookingHub**, tôi khuyến nghị thiết kế Responsive Web Design để hỗ trợ viewport từ **320px đến 1920px**, thay vì chỉ kiểm thử ở hai kích thước 360px và 1280px như NFR-07 trước đó.

Điểm quan trọng là: các hướng dẫn từ [MDN](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/CSS_layout/Responsive_Design) và [Google web.dev](https://web.dev/articles/responsive-web-design-basics) đều khuyến nghị xây dựng breakpoint dựa trên nội dung và bố cục, không dựa cứng vào từng dòng điện thoại hoặc độ phân giải thiết bị.

### 1. Các kích thước viewport nên hỗ trợ

Đây là bộ kích thước kiểm thử tôi đề xuất cho một ứng dụng web phục vụ cả smartphone, tablet và computer.

| Loại thiết bị | Viewport (CSS px) | Tỷ lệ gần đúng | Mức ưu tiên |
| --- | --- | --- | --- |
| Small Mobile | 320 × 568 | 9:16 | Cao |
| Mobile | 360 × 800 | 9:20 | Cao |
| Large Mobile | 390 × 844 | 9:19.5 | Cao |
| Tablet Portrait | 768 × 1024 | 3:4 | Trung bình |
| Tablet Landscape | 1024 × 768 | 4:3 | Trung bình |
| Laptop | 1366 × 768 | 16:9 | Cao |
| Desktop | 1440 × 900 | 16:10 | Cao |
| Full HD Desktop | 1920 × 1080 | 16:9 | Trung bình |

Các kích thước này là **test viewports**, không phải danh sách đầy đủ các thiết bị hoặc tỷ lệ mà ứng dụng phải giới hạn hỗ trợ.

#### Vì sao nên bắt đầu từ 320px?

Tiêu chuẩn [WCAG 2.2 — Success Criterion 1.4.10 Reflow](https://www.w3.org/WAI/WCAG21/Understanding/reflow?utm_source=chatgpt.com) yêu cầu nội dung cuộn dọc có thể hiển thị ở độ rộng tương đương 320 CSS pixels mà không mất thông tin hoặc chức năng, ngoại trừ những thành phần thực sự cần bố cục hai chiều. Đây là tiêu chí cấp AA.

Điều này cũng hỗ trợ người dùng desktop phóng to trình duyệt. Chẳng hạn, viewport 1280 CSS pixels khi zoom 400% tương đương 320 CSS pixels.

Lưu ý: CSS pixels khác physical screen pixels. Một điện thoại có màn hình vật lý 1170px vẫn có thể có CSS viewport khoảng 390px ở mức hiển thị mặc định.

### 2. Nên thiết kế theo những breakpoints nào?

Vì BadminBookingHub đang dùng React và có thể sử dụng Tailwind CSS, bạn có thể tham khảo các breakpoints mặc định của Tailwind.

| Breakpoint | Min-width | Định hướng layout |
| --- | --- | --- |
| Base | 0px | Mobile-first |
| sm | 640px | Mobile lớn hoặc khung hiển thị hẹp |
| md | 768px | Tablet |
| lg | 1024px | Tablet ngang / laptop |
| xl | 1280px | Desktop |
| 2xl | 1536px | Desktop rộng |

Đây là các ngưỡng mặc định hiện tại của Tailwind, không phải một tiêu chuẩn bắt buộc của mọi web application.

Với ứng dụng của bạn, tôi đề xuất ba bố cục chính:

**Mobile layout (320–767px)**

Menu thu gọn, danh sách sân một cột, biểu mẫu đặt sân theo chiều dọc. Lịch đặt sân có thể chuyển thành danh sách time slots hoặc lưới cuộn trong một vùng riêng.

---

**Tablet layout (768–1023px)**

Danh sách sân có thể dùng hai cột. Các bộ lọc và bảng lịch cần co giãn; không nên mặc định hiển thị đầy đủ một lịch lớn như trên desktop.

---

**Desktop layout (≥1024px)**

Sidebar cho Admin/Staff, bảng quản lý nhiều cột, bộ lọc và lịch đặt sân mở rộng. Trên màn hình lớn có thể giới hạn max-width cho nội dung thay vì kéo giãn toàn bộ giao diện.

Đây là bố cục đề xuất, không có nghĩa mọi component phải thay đổi đúng tại 768px hoặc 1024px. Nếu một bảng cần thêm không gian, bạn có thể đặt breakpoint riêng phù hợp với bảng đó.

### 3. Trường hợp quan trọng nhất của BadminBookingHub: Availability Calendar

F04 — Availability Calendar là thành phần đáng quan tâm nhất về responsiveness vì dữ liệu hai chiều gồm sân và các khung giờ.

Chẳng hạn, desktop có thể hiển thị dạng:

| Court / Time | 17:00 | 18:00 | 19:00 |
| --- | --- | --- | --- |
| Court 01 | Free | Booked | Free |
| Court 02 | Booked | Free | Free |
| Court 03 | Free | Free | Booked |

Nhưng trên mobile, các lựa chọn dễ sử dụng hơn là hiển thị mỗi sân như một card kèm các time slots, hoặc cho phép lịch cuộn ngang bên trong một container mà không khiến toàn bộ trang bị tràn ngang.

WCAG cho phép các thành phần dữ liệu dạng bảng cần bố cục hai chiều sử dụng scrolling thích hợp. Vì thế, không nên viết NFR cấm mọi hình thức horizontal scrolling; cần phân biệt **page-level horizontal scrolling** với **component-level scrolling**.

Ngoài ra, cần kiểm thử cả chiều cao viewport. Điện thoại xoay ngang có thể cung cấp chiều rộng 800px nhưng chiều cao chỉ khoảng 360px. Khi đó, modal, thanh điều hướng cố định hoặc nút xác nhận đặt sân rất dễ bị che khuất.

### 4. NFR-07 nên viết lại như thế nào?

Tôi đề xuất phiên bản sau cho tài liệu PA2.

**NFR-07 — Responsive User Interface** (Must)

Requirement Statement

> The system shall maintain the usability of all Must-have workflows across viewport widths from 320 to 1920 CSS pixels. No essential information or interactive controls shall be clipped, obscured, or rendered inaccessible. Horizontal scrolling of the overall page shall not be required, except for self-contained components whose content inherently requires a two-dimensional layout.

---

**Fit Criteria**

- All seven Must-have workflows remain completable at the agreed viewport test sizes.
- No unintended document-level horizontal overflow.
- All essential buttons, form inputs and navigation controls remain visible or reachable through normal scrolling.
- Booking calendar and management tables remain operable on mobile.

**Verification Method:** Playwright responsive viewport testing, supplemented with manual resizing and mobile portrait/landscape testing.

Để tránh kiểm thử quá nhiều, có thể chia thành hai mức.

**Core Responsive Test Matrix** /5 checked

---

Đề xuất 5 viewport kiểm thử tự động cốt lõi \[Reset\]

Các viewport 360px, 1366px, 1920px, điện thoại xoay ngang và các kích thước nằm sát breakpoint nên được kiểm thử bổ sung bằng cách resize trình duyệt. Chrome DevTools hỗ trợ nhập kích thước và giả lập orientation, nhưng kiểm thử thực tế trên điện thoại vẫn hữu ích để phát hiện vấn đề về bàn phím ảo và thao tác chạm.

**Kết luận:** Đối với BadminBookingHub, mục tiêu hỗ trợ viewport rộng 320–1920 CSS pixels là hợp lý. Bạn không cần tạo riêng giao diện cho mọi tỷ lệ 16:9, 16:10, 19.5:9 hay 20:9. Thay vào đó, hãy xây dựng layout co giãn theo chiều rộng, kiểm thử các kích thước đại diện và đặc biệt bảo đảm Availability Calendar, Booking Form và Front-desk Dashboard vẫn dùng được trên mobile.

Tiêu đề chat đề xuất: $Software Engineering$ - Responsive NFR và Viewport Testing (26/10/2026)


---

## You

`7 of 34`

Tôi thắc mắc về NFR-03 tôi thấy yêu cầu này khá giống với một phần của một FR điều này có hợp lý ?


---

## ChatGPT

`8 of 34`

**Đúng. NFR-03 mà tôi đề xuất đang bị trùng lặp đáng kể với FR-01 của BadminBookingHub.** Đây là một vấn đề cần điều chỉnh khi viết Software Requirements Specification (SRS).

Tuy nhiên, điều đó không có nghĩa Functional Requirements (FR) và Non-Functional Requirements (NFR) không được liên quan đến nhau. Quan trọng là chúng phải mô tả những khía cạnh khác nhau của hệ thống.

### 1. Phân tích trường hợp NFR-03

Trong PA1, nhóm đã xác định:

**F01 — User Registration & Login**

> Player self-registration; staff and admin accounts with role-based permissions; login/logout, password hashing.

Nghĩa là phân quyền theo vai trò đã nằm trong phạm vi chức năng của F01.

Trong khi đó, NFR-03 mà tôi đề xuất là:

> All protected API endpoints shall reject requests from unauthenticated or unauthorized users, according to the approved Player–Staff–Admin permission matrix.

Hai requirement này thực sự mô tả gần như cùng một hành vi: hệ thống phải kiểm tra quyền trước khi cho phép người dùng thực hiện các thao tác được bảo vệ.

NFR-03 cụ thể hơn ở cấp API, nhưng **chỉ thêm chi tiết triển khai và kiểm chứng không đủ để biến một FR thành NFR**.

### 2. Phân biệt FR và NFR trong trường hợp Security

Hãy xem một vài ví dụ:

| Requirement | Phân loại phù hợp hơn | Giải thích |
| --- | --- | --- |
| Player can log in using an email and password | FR | Chức năng đăng nhập |
| Only Admin can modify court prices | FR / Business Rule | Quy định thao tác nào được phép |
| The server must reject unauthorized attempts to modify prices | Security FR | Hành vi kiểm soát quyền truy cập |
| The system must limit repeated failed login attempts | Security requirement | Cơ chế chống tấn công brute force |
| Authentication credentials must not appear in application logs | Security NFR | Ràng buộc bảo mật xuyên suốt hệ thống |

Có một điểm lý thuyết đáng lưu ý: **Security không mặc nhiên là Non-Functional**.

Trong Requirements Engineering, yêu cầu bảo mật có thể là functional hoặc non-functional. Chẳng hạn, authentication, authorization và password reset thường được mô tả bằng những Security Functional Requirements cụ thể. Trong khi đó, các thuộc tính chất lượng như confidentiality, integrity và resistance to attacks thường được xem xét trong nhóm Security Quality Attributes.

Ranh giới này không phải lúc nào cũng tuyệt đối. Một số mẫu SRS vẫn gom nhiều security controls vào NFR. Điều quan trọng là nhất quán, không trùng lặp và có khả năng kiểm thử.

### 3. Tôi đề xuất sửa NFR-03 như thế nào?

Với BadminBookingHub, tôi đề xuất:

**Giữ authorization trong Functional Requirements.**

Ví dụ:

> **FR-AUTH-03 — Role-Based Access Control:** The system shall restrict protected operations according to the permissions assigned to the Player, Staff, and Admin roles.

Và bổ sung acceptance criteria:

> Given a Player account, when the player directly sends an API request to modify court prices, then the system shall deny the request and leave the stored prices unchanged.

Sau đó, nếu muốn có thêm một NFR về Security không trùng lặp trực tiếp với FR-AUTH-03, có thể sử dụng:

**NFR-03 — Authentication Abuse Protection**

Proposed Requirement

> The system shall apply rate limiting to the authentication endpoint, allowing no more than 10 failed login attempts per account within a rolling 15-minute window before temporarily restricting further attempts.

---

Verification

Execute automated tests that submit repeated invalid login attempts and verify that the configured restriction takes effect.

Ngưỡng 10 lần/15 phút là đề xuất ban đầu; cơ chế hạn chế cần được thiết kế để giảm nguy cơ khóa tài khoản do người khác cố tình gửi yêu cầu sai.

NFR này bổ sung khả năng chống lạm dụng cho chức năng đăng nhập, thay vì lặp lại yêu cầu phân quyền. Tuy nhiên, ngay cả rate limiting cũng có thể được xem là một security functional control tùy phương pháp phân loại.

### 4. Nguyên tắc áp dụng cho toàn bộ SRS

Tôi khuyến nghị nhóm áp dụng cách phân loại sau:

- **FR:** Hệ thống phải cung cấp hành vi hoặc chức năng gì?
- **Business Rule:** Nghiệp vụ quy định những điều kiện, giới hạn hay chính sách gì?
- **NFR:** Hệ thống phải đạt được những thuộc tính chất lượng và ràng buộc nào khi thực hiện các chức năng đó?

Một NFR có thể tham chiếu nhiều FR mà không phải là yêu cầu độc lập hoàn toàn. Ví dụ, NFR về response time có thể áp dụng đồng thời cho tìm sân và xem lịch, nhưng không mô tả lại chức năng của chúng.

**Kết luận cho BadminBookingHub:** Tôi khuyên bạn chuyển nội dung NFR-03 cũ thành acceptance criteria của FR về phân quyền, thay vì giữ nguyên nó như một NFR độc lập. Nếu phạm vi dự án chưa đủ để triển khai rate limiting, có thể bỏ NFR-03 và giữ các yêu cầu Security khác có giá trị hơn, thay vì cố tạo thêm NFR cho đủ số lượng.

Tiêu đề chat đề xuất: $Software Engineering$ - Phân biệt FR và NFR trong Security (26/10/2026)


---

## You

`9 of 34`

Web search
 Bạn hãy tìm giúp tôi một trang blog/post chia sẻ ví dụ về cách họ viết FR và NFR cho một scenario ứng dụng để tôi tìm hiểu


---

## ChatGPT

`10 of 34`

Tôi tìm được **3 tài liệu có ví dụ Functional Requirements (FR) và Non-Functional Requirements (NFR) cho cùng một ứng dụng**. Trong đó, có một bài case study về Hotel Booking System rất giống BadminBookingHub và một bài giảng viết SRS hoàn chỉnh cho Railway Reservation System.

### 1. Hotel Booking System — Business Analysis Case Study

(Phù hợp nhất với BadminBookingHub)

[Hotel Booking System — Gihansa Buwanayake](https://gihansa.me/hotel-booking-case-study.html?utm_source=chatgpt.com)

Business Analysis Case Study · Blog cá nhân · Miễn phí

Bài viết mô tả một khách sạn quản lý đặt phòng bằng điện thoại, email và spreadsheet, dẫn đến double booking. Tác giả lần lượt phân tích Business Problems, As-Is/To-Be Process, Functional Requirements, Non-Functional Requirements, User Stories, Acceptance Criteria và Use Cases.

Ví dụ lấy từ nội dung bài viết, được diễn giải ngắn gọn:

| Functional Requirements | Non-Functional Requirements |
| --- | --- |
| Khách tìm phòng trống theo ngày và loại phòng | Kết quả tìm kiếm trả về dưới 2 giây |
| Hệ thống không cho phép đặt phòng trùng thời gian | Nền tảng đạt availability 99.5% |
| Khách thực hiện đặt phòng và thanh toán deposit | Dữ liệu thanh toán qua cổng đạt yêu cầu PCI; không lưu số thẻ tại hệ thống |
| Quản trị viên xem và thay đổi booking | Quy trình đặt phòng trên mobile không quá 4 bước |

**Điểm đáng học:** Tác giả bắt đầu bằng vấn đề nghiệp vụ rồi mới xác định FR và NFR. Đây là trình tự rất phù hợp cho đồ án PA2.

**Điểm cần cải thiện:** Một vài NFR chưa đủ điều kiện kiểm thử. Chẳng hạn, thời gian tìm kiếm dưới 2 giây chưa nêu số người dùng đồng thời, môi trường và tỷ lệ yêu cầu phải đáp ứng. Mục tiêu scalability gấp 3 lần lưu lượng trung bình cũng chưa định nghĩa rõ workload.

### 2. Railway Reservation System — Complete SRS Example

(Chi tiết nhất về cách viết)

[Software Requirements Specification for Railway Reservation System — Syntax Lab](https://syntax.theether.in/mcs-217/session-3/?utm_source=chatgpt.com)

University-style practical lesson · Cập nhật 06/10/2026 · Miễn phí

Đây là bài giảng thực hành xây dựng SRS cho ứng dụng đặt vé tàu, gồm Problem Statement, Scope, Functional Requirements, Non-Functional Requirements và Requirements Traceability. Tài liệu sử dụng ID, câu mô tả có shall và nhiều ngưỡng định lượng.

Điểm đáng chú ý là hai nhóm yêu cầu được trình bày rõ ràng:

**Functional Requirement — FR-3.1**

Hệ thống cho phép bất kỳ người dùng nào tìm tàu theo ga đi, ga đến và ngày đi, không cần đăng nhập.

**Non-Functional Requirement — NFR-P1**

Kết quả tìm kiếm phải xuất hiện trong vòng 2 giây đối với ít nhất 95% yêu cầu khi có 500 người dùng đồng thời.

Đây chính là sự khác biệt bạn đang tìm hiểu:

- FR mô tả hành vi *tìm kiếm tàu*.
- NFR mô tả mức hiệu năng mà hành vi tìm kiếm phải đáp ứng.

Tài liệu còn có các NFR thuộc Performance, Security, Reliability, Availability, Usability và Maintainability. Tuy nhiên, vẫn có trường hợp lặp ý giữa FR và NFR, ví dụ kiểm soát role hoặc password hashing. Bạn nên đọc chúng với tư duy phản biện, không coi mọi phân loại là chuẩn tuyệt đối.

### 3. Booking Management System — GitHub Case Study

[*[Embedded image]*

Pauline-WN / requirement-analysis — GitHub](https://github.com/Pauline-WN/requirement-analysis?utm_source=chatgpt.com)

GitHub Repository · Miễn phí

Repository minh họa Requirements Analysis cho hệ thống quản lý booking, gồm FR, NFR, Use Case Diagram và Acceptance Criteria. Ví dụ FR bao gồm tạo, sửa, hủy booking và tìm dịch vụ còn trống; NFR bao gồm response time, security, availability và concurrent users.

Nguồn này gần với domain của BadminBookingHub, nhưng còn ở mức giới thiệu. Một số NFR như uptime 99.9% hoặc hỗ trợ 10.000 concurrent users chưa được giải thích cách lựa chọn ngưỡng, nên không phù hợp để sao chép trực tiếp vào đồ án nhỏ.

### Tôi khuyên bạn đọc tài liệu nào trước?

| Mục tiêu học tập | Nguồn phù hợp |
| --- | --- |
| Học cách đi từ Business Problem đến FR và NFR | Hotel Booking Case Study |
| Học cách viết FR/NFR cụ thể, đánh ID, đặt metric | Railway Reservation System |
| Xem repository phân tích requirements cho booking app | GitHub Booking Management System |

**Đề xuất:** Đọc Hotel Booking System trước vì bối cảnh gần như tương đồng với BadminBookingHub. Sau đó đọc Railway Reservation System, đặc biệt hai phần 3.1 Functional Requirements và 3.3 Non-functional Requirements, để học cách chuyển các yêu cầu sang câu có thể kiểm chứng.

Một bài tập hữu ích là chọn FR về tìm kiếm phòng trong Hotel Booking, tự đề xuất ba NFR thuộc Performance, Usability và Reliability, rồi so sánh với cách viết trong Railway Reservation System. Qua đó bạn sẽ nhận ra NFR nào thực sự mô tả chất lượng và NFR nào chỉ đang lặp lại chức năng.

Tiêu đề chat đề xuất: $Software Engineering$ - Case Study viết FR và NFR (26/10/2026)


---

## You

`11 of 34`

Với một dự án demo thì NFR-01 có thực hiện được không, tool k6 có hỗ trợ không, và tôi phải đo lường yêu cầu này bằng metric như thế nào, cài đặt bộ đo metric này ở module nào, làm rõ cách virification hơn. Tôi muốn tách NFR-04 ra thành hai NFR nhỏ là tất cả các traffic đều phải sử dụng HTTPS, dùng HTTP thì phải từ chối hoặc làm gì đó (bổ sung cách verification), và NFR thứ hai là tất cả các loại mật khẩu phải lưu trong DB dưới dạng mã hóa nào đó (tìm kiếm giúp tôi phương thức mã hóa phù hợp và cách verification hợp lý)


---

## ChatGPT

`12 of 34`

### Thiết kế và kiểm chứng NFR-01, NFR-04 cho BadminBookingHub

**Cả ba yêu cầu bạn đang xem xét đều khả thi với một dự án demo triển khai trên EC2.** Đặc biệt, k6 hoàn toàn có thể đo NFR-01 mà không cần tích hợp một hệ thống monitoring phức tạp như Prometheus + Grafana vào backend.

Tôi khuyến nghị điều chỉnh bộ NFR thành:

| ID | Requirement | Phương pháp kiểm chứng chính |
| --- | --- | --- |
| NFR-01 | API Response Time | k6 Load Testing |
| NFR-04A | HTTPS Enforcement | HTTP/TLS integration testing |
| NFR-04B | Secure Password Storage | Unit test + Database inspection |

Có một điểm cần thống nhất ngay: **load testing, monitoring và verification là ba hoạt động có liên quan nhưng không giống nhau.**

- *Load testing:* Chủ động tạo lưu lượng để đo hệ thống chịu tải và phản hồi như thế nào.
- *Monitoring:* Quan sát tình trạng hệ thống trong lúc nó đang chạy.
- *Verification:* Đối chiếu kết quả đo hoặc kiểm thử với tiêu chí chấp nhận được viết trong NFR.

Với đồ án của bạn, chúng ta có thể sử dụng k6 để thực hiện cả load testing và verification cho NFR-01.

---

#### 1. NFR-01 — Performance Efficiency

##### 1.1. Một dự án demo có thực hiện được không?

Có. Dựa trên kế hoạch PA1, BadminBookingHub triển khai thử nghiệm trên một EC2 t3.medium, gồm 2 vCPU, 4 GiB RAM, với frontend React, backend Express và PostgreSQL chạy trong các Docker containers.

Đây là quy mô đủ để thực hiện bài kiểm thử 20 virtual users ở mức thử nghiệm. Tuy nhiên, **không thể khẳng định hệ thống sẽ đạt response time 2 giây trước khi đo thực tế**. Hiệu năng còn phụ thuộc vào truy vấn SQL, indexes, dữ liệu mẫu, cấu hình instance và mức sử dụng CPU.

##### 1.2. Cần đo những metrics nào?

Theo tài liệu chính thức của Grafana k6, công cụ này tự thu thập nhiều metrics cho mỗi HTTP request.

| Metric | Ý nghĩa | Vai trò |
| --- | --- | --- |
| http_req_duration | Thời gian gửi request, chờ server và nhận response | Metric chính |
| p(95) | Phân vị thứ 95 của thời gian phản hồi | Tiêu chí hiệu năng |
| http_req_failed | Tỷ lệ HTTP request được đánh dấu thất bại | Tiêu chí lỗi |
| http_reqs | Tổng request và throughput (req/s) | Thông tin hỗ trợ |
| http_req_waiting | Thời gian chờ response bắt đầu trả về (TTFB) | Chẩn đoán |
| checks | Tỷ lệ các assertions thành công | Kiểm tra tính đúng đắn |

Một chi tiết quan trọng: http_req_duration của k6 không tính DNS lookup, TCP connection setup và TLS handshake. Nó bao gồm thời gian gửi request, chờ server và nhận response. Do đó, metric này phù hợp cho HTTP API performance nhưng không tương đương với thời gian người dùng nhìn thấy toàn bộ trang web.

##### 1.3. Vì sao nên đo p95 thay vì average?

Giả sử bạn thu thập được 100 HTTP response times. Sau khi sắp xếp chúng từ nhanh nhất đến chậm nhất, biểu đồ minh họa dưới đây cho thấy sự khác nhau giữa trung bình và phần đuôi chậm của phân phối.

Phân phối response time minh họa

svg![Image generated by the assistant](data:image/svg+xml;utf8,%3Csvg%20viewBox%3D%220%200%20340%20125%22%20width%3D%22100%25%22%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%3E%3Crect%20x%3D%2210%22%20y%3D%2225%22%20width%3D%22304%22%20height%3D%2234%22%20rx%3D%225%22%20fill%3D%22%2394a3b8%22%20opacity%3D%22.15%22%3E%3C%2Frect%3E%3Crect%20x%3D%2210%22%20y%3D%2225%22%20width%3D%22289%22%20height%3D%2234%22%20rx%3D%225%22%20fill%3D%22%2316a34a%22%20opacity%3D%22.75%22%3E%3C%2Frect%3E%3Crect%20x%3D%22299%22%20y%3D%2225%22%20width%3D%2215%22%20height%3D%2234%22%20rx%3D%222%22%20fill%3D%22%23dc6b47%22%3E%3C%2Frect%3E%3Cpath%20d%3D%22M299%2015%20V72%22%20stroke%3D%22currentColor%22%20stroke-dasharray%3D%223%203%22%20opacity%3D%22.7%22%3E%3C%2Fpath%3E%3Ctext%20x%3D%2210%22%20y%3D%2217%22%20font-size%3D%2211%22%20fill%3D%22currentColor%22%3E95%20requests%3C%2Ftext%3E%3Ctext%20x%3D%22270%22%20y%3D%2217%22%20font-size%3D%2211%22%20fill%3D%22currentColor%22%3E5%3C%2Ftext%3E%3Ctext%20x%3D%2210%22%20y%3D%2285%22%20font-size%3D%2211%22%20fill%3D%22currentColor%22%3E0%20ms%3C%2Ftext%3E%3Ctext%20x%3D%22299%22%20y%3D%2285%22%20text-anchor%3D%22end%22%20font-size%3D%2211%22%20fill%3D%22currentColor%22%3Ep95%3C%2Ftext%3E%3Ctext%20x%3D%22314%22%20y%3D%22103%22%20text-anchor%3D%22end%22%20font-size%3D%2211%22%20fill%3D%22currentColor%22%3ETail%20latency%3C%2Ftext%3E%3Ctext%20x%3D%2210%22%20y%3D%22105%22%20font-size%3D%2211%22%20fill%3D%22currentColor%22%3ENhanh%20h%C6%A1n%3C%2Ftext%3E%3C%2Fsvg%3E)

Minh họa khái niệm, không phải dữ liệu benchmark thực tế.

Nếu p95 = 1.800 ms, nghĩa là khoảng 95% requests hoàn thành trong tối đa 1,8 giây; còn khoảng 5% có thể chậm hơn.

NFR-01 ban đầu đặt ngưỡng:

$$
p95(\text{HTTP response time})\leq 2000\,\text{ms}
$$

Khi sử dụng k6, bạn có thể định nghĩa một threshold p(95)<2000, nghĩa là điều kiện kiểm thử phải có phân vị thứ 95 nhỏ hơn 2.000 ms. Đây là cơ chế pass/fail tích hợp sẵn của k6.

##### 1.4. Metric cần cài đặt ở module nào?

Kiến trúc kiểm thử tôi đề xuất

k6 đóng vai trò load generator và measurement client. Không cần cài k6 trong Express hoặc PostgreSQL.

Bộ test nên được đặt trong repository ở một thư mục riêng:

Plain text`BadminBookingHub/
├── src/
│ ├── frontend/
│ └── backend/
├── tests/
│ ├── performance/
│ │ ├── availability.js
│ │ └── booking.js
│ ├── security/
│ └── e2e/
├── reports/
│ └── performance/
└── .github/
    └── workflows/
        └── ci.yml`

**Không nên chạy k6 trên chính EC2 đang được kiểm thử** nếu muốn đo khả năng chịu tải một cách tương đối khách quan. Load generator cũng dùng CPU, RAM và network, khiến kết quả bị sai lệch do cạnh tranh tài nguyên.

Bạn có thể chạy k6 trên laptop Linux hoặc một máy test riêng, gửi request đến EC2 qua HTTPS. Trong CI, có thể sử dụng GitHub Actions runner cho những bài smoke test nhỏ; bài load test nên chạy theo yêu cầu để tránh phát sinh tải không cần thiết lên demo server.

##### 1.5. Cách cài đặt k6

Trên Ubuntu Linux, bạn có thể cài đặt k6 bằng các lệnh chính thức sau:

Bash

```
curl -fsSL https://dl.k6.io/key.gpg \
  | sudo gpg --dearmor \
      -o /usr/share/keyrings/k6-archive-keyring.gpg

echo "deb [signed-by=/usr/share/keyrings/k6-archive-keyring.gpg] https://dl.k6.io/deb stable main" \
  | sudo tee /etc/apt/sources.list.d/k6.list

sudo apt update
sudo apt install k6

k6 version
```

Nếu không muốn cài trực tiếp, k6 cũng có Docker image grafana/k6.

##### 1.6. Viết script kiểm thử NFR-01

Giả sử Express backend cung cấp hai endpoints:

- GET /api/courts?date=...&area=...
- GET /api/courts/:id/availability?date=...

Đây là các **đường dẫn minh họa**; cần thay bằng routes thực tế của nhóm.

Tạo file tests/performance/availability.js:

JavaScript

```

import http from 'k6/http';
import { check, sleep } from 'k6';

const BASE_URL = __ENV.BASE_URL;
const TEST_DATE = __ENV.TEST_DATE;

if (!BASE_URL || !TEST_DATE) {
  throw new Error('BASE_URL and TEST_DATE are required');
}

export const options = {
  scenarios: {
    normal_load: {
      executor: 'constant-vus',
      vus: 20,
      duration: '5m',
    },
  },
  thresholds: {
    'http_req_duration{endpoint:search,expected_response:true}': [
      'p(95)<2000',
    ],
    'http_req_duration{endpoint:availability,expected_response:true}': [
      'p(95)<2000',
    ],
    'http_req_failed{endpoint:search}': ['rate<0.01'],
    'http_req_failed{endpoint:availability}': ['rate<0.01'],
    checks: ['rate>0.99'],
  },
};

export default function () {
  const date = encodeURIComponent(TEST_DATE);

  const searchResponse = http.get(
    `${BASE_URL}/api/courts?date=${date}&area=district-1`,
    { tags: { endpoint: 'search' } }
  );

  check(searchResponse, {
    'search HTTP 200': (r) => r.status === 200,
  });

  const availabilityResponse = http.get(
    `${BASE_URL}/api/courts/1/availability?date=${date}`,
    { tags: { endpoint: 'availability' } }
  );

  check(availabilityResponse, {
    'availability HTTP 200': (r) => r.status === 200,
  });

  sleep(1);
}
```

Script này làm bốn việc:

1. Tạo 20 virtual users, mỗi user lặp lại hai yêu cầu HTTP trong 5 phút.
2. Đo thời gian phản hồi riêng cho Search API và Availability API.
3. Kiểm tra p95 của các HTTP responses thành công phải dưới 2.000 ms và tỷ lệ request thất bại dưới 1%.
4. Kiểm tra HTTP status bằng check().

Các thresholds theo tags như endpoint:search được k6 hỗ trợ chính thức.

Script trên chưa kiểm tra nội dung JSON có chính xác về mặt nghiệp vụ hay không. Bạn có thể bổ sung assertions về cấu trúc response, dữ liệu trả về và trạng thái sân sau khi API được hoàn thiện.

##### 1.7. Thực hiện verification

Tôi đề xuất quy trình sau cho PA5:

1. **Chuẩn bị dữ liệu:** Seed PostgreSQL với tối thiểu 5.000 booking records hợp lệ, đủ phân bố theo sân và ngày để truy vấn thực sự phải xử lý dữ liệu. Cố định seed dataset cho các lần chạy.
2. **Chuẩn bị môi trường:** Chạy frontend, backend, database trên EC2 theo cấu hình đã được nhóm xác định; ghi nhận phiên bản ứng dụng, cấu hình máy và kích thước dữ liệu.
3. **Warm-up:** Gửi một lượng request nhỏ để kiểm tra endpoint, TLS và dữ liệu trước khi chạy bài test chính.
4. **Load test:** Chạy 20 VUs trong 5 phút bằng máy khác với EC2, không thay đổi cấu hình hệ thống trong lúc đo.
5. **Evaluation:** Kiểm tra các thresholds, error rate và thông tin throughput.
6. **Evidence:** Lưu báo cáo k6 kèm phiên bản ứng dụng, thông tin môi trường và kết luận Pass/Fail.

Lệnh chạy ví dụ:

Bash

```
mkdir -p reports/performance
set -o pipefail

BASE_URL=https://booking.example.org \
TEST_DATE=2026-12-15 \
k6 run --summary-mode=full \
  tests/performance/availability.js \
  | tee reports/performance/nfr-01.txt
```

Ngày, domain và API routes phải được thay bằng dữ liệu test hợp lệ.

Để lưu báo cáo dạng JSON có thể dùng handleSummary() của k6, thay vì chỉ giữ terminal output.

Giả sử kết quả đo nhận được là:

Ví dụ đánh giá kết quả k6 (số liệu giả định)

**Overall verification** (PASS (minh họa))

Để bài test không cho kết quả sai lệch, bạn nên ghi nhớ:

- 20 VUs không có nghĩa là luôn có đúng 20 HTTP requests đang được xử lý ở mỗi thời điểm. Đây là mô hình các virtual users liên tục thực hiện iterations.
- Một bài test với response nhanh có thể tạo nhiều requests/second hơn bài test với response chậm. Nếu muốn cố định arrival rate, k6 hỗ trợ constant-arrival-rate.
- Nếu server trả lỗi 500 rất nhanh, riêng p95 latency có thể tạo cảm giác hệ thống tốt. Vì vậy, phải kiểm tra error rate song song.
- Nếu cần đo *toàn bộ quá trình người dùng tương tác với trang*, nên sử dụng browser testing hoặc Web Vitals, không chỉ HTTP API testing.

Hai mô hình workload này được giải thích trong tài liệu [k6 Scenarios](https://grafana.com/docs/k6/latest/using-k6/scenarios/?utm_source=chatgpt.com).

##### 1.8. Phiên bản NFR-01 sau khi chỉnh sửa

**NFR-01 — Court Availability API Performance**

Requirement Statement

> Under a workload of 20 concurrent virtual users and a test database containing at least 5,000 booking records, the system shall achieve a 95th-percentile HTTP response duration below 2 seconds for successful court search and availability API requests, with a failed HTTP request rate below 1% for each endpoint.

**Verification Method**

> Execute a 5-minute load test using Grafana k6 against the designated deployment environment. Measure http_req_duration and http_req_failed separately for the search and availability endpoints. The requirement passes only if all defined performance and error-rate thresholds are satisfied.

**Test Environment:** BadminBookingHub demo deployment on the specified EC2 instance, with test load generated from a separate machine.

**Evidence:** k6 test script, seeded dataset description, test report, deployment configuration and Pass/Fail result.

Điểm còn cần hoàn thiện trước khi đóng băng NFR là chọn dữ liệu test đại diện, xác định các routes thực tế và thống nhất liệu bạn đang đo normal load hay peak load. Nếu app có ít dữ liệu hơn nhiều so với 5.000 booking records trong phạm vi demo, nhóm có thể hạ quy mô kiểm thử nhưng cần ghi rõ lý do.

---

#### 2. NFR-04A — HTTPS Enforcement

##### 2.1. Viết yêu cầu HTTPS thế nào cho chính xác?

Trước hết, cần làm rõ phạm vi từ “all traffic”.

Hệ thống BadminBookingHub có thể có luồng:

```
<svg viewBox="0 0 340 230" width="100%" xmlns="http://www.w3.org/2000/svg"><rect x="12" y="10" width="316" height="207" rx="8" fill="#94a3b8" fill-opacity=".06" stroke="#94a3b8" /><rect x="26" y="29" width="103" height="46" rx="7" fill="#64748b" fill-opacity=".18" stroke="#64748b" /><text x="77" y="47" text-anchor="middle" font-size="12" fill="currentColor" font-weight="600">Browser</text><text x="77" y="63" text-anchor="middle" font-size="10" fill="currentColor">Player / Staff</text><rect x="209" y="29" width="104" height="46" rx="7" fill="#64748b" fill-opacity=".18" stroke="#64748b" /><text x="261" y="47" text-anchor="middle" font-size="12" fill="currentColor" font-weight="600">NGINX</text><text x="261" y="63" text-anchor="middle" font-size="10" fill="currentColor">TLS termination</text><path d="M129 52 H209" stroke="#16a34a" stroke-width="2" /><text x="168" y="40" text-anchor="middle" font-size="10" fill="#16a34a">HTTPS</text><rect x="209" y="107" width="104" height="44" rx="7" fill="#64748b" fill-opacity=".16" stroke="#64748b" /><text x="261" y="125" text-anchor="middle" font-size="12" fill="currentColor">Express API</text><text x="261" y="140" text-anchor="middle" font-size="10" fill="currentColor">Docker network</text><path d="M261 75 V107" stroke="#64748b" stroke-width="1.8" /><text x="272" y="94" font-size="10" fill="currentColor">HTTP</text><rect x="209" y="174" width="104" height="32" rx="7" fill="#64748b" fill-opacity=".16" stroke="#64748b" /><text x="261" y="194" text-anchor="middle" font-size="12" fill="currentColor">PostgreSQL</text><path d="M261 151 V174" stroke="#64748b" stroke-width="1.8" /><text x="275" y="166" font-size="10" fill="currentColor">TCP</text></svg>
```

Nếu viết “all traffic must use HTTPS”, bạn đang ngầm yêu cầu cả NGINX → Express và Express → PostgreSQL cũng phải dùng HTTPS. Điều này không hợp lý vì PostgreSQL sử dụng giao thức database riêng, còn HTTP giữa các containers trong mạng nội bộ có thể chấp nhận được trong phạm vi demo, nếu mạng được cô lập thích hợp.

Vì vậy, tôi khuyến nghị NFR tập trung vào **mọi giao tiếp ứng dụng từ client bên ngoài tới hệ thống phải được bảo vệ bằng HTTPS**.

##### 2.2. Khi truy cập HTTP thì nên làm gì?

Theo [OWASP Transport Layer Security Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Transport_Layer_Security_Cheat_Sheet.html?utm_source=chatgpt.com), có hai cách xử lý phù hợp tùy loại request.

| Loại request | Hành vi đề xuất |
| --- | --- |
| http://domain/ | 301 Redirect → https://domain/ |
| http://domain/courts | 301 Redirect → HTTPS |
| http://domain/api/auth/login | 403 Forbidden |
| http://domain/api/bookings | 403 Forbidden |
| https://domain/api/bookings | Xử lý theo authentication, authorization và nghiệp vụ |

Đối với các trang web thông thường, redirect HTTP sang HTTPS giúp người dùng truy cập thuận tiện hơn.

Đối với API, đặc biệt là API đăng nhập, nên từ chối HTTP ngay tại reverse proxy thay vì redirect. Điều này tránh việc ứng dụng chấp nhận xử lý request qua kênh không được mã hóa.

Lưu ý rằng nếu client đã gửi mật khẩu bằng HTTP, dữ liệu đó có thể bị lộ *trước khi* server trả 403. Vì vậy, ứng dụng phải chủ động sử dụng HTTPS, kết hợp HSTS và không tạo các URL đăng nhập HTTP.

##### 2.3. Cấu hình trên NGINX

Ví dụ cho NGINX đang làm HTTPS reverse proxy:

nginx`server {
    listen 80;
    server_name booking.example.org;

    location ^~ /api/ {
        return 403;
    }

    location / {
        return 301 https://booking.example.org$request_uri;
    }
}`

Đây chỉ là phần cấu hình HTTP listener. Bạn vẫn cần một server block riêng cho HTTPS trên cổng 443, chứng chỉ TLS hợp lệ và reverse proxy tới backend.

Nếu sử dụng Certbot với cơ chế HTTP-01 webroot, cần bổ sung xử lý cho /.well-known/acme-challenge/ để việc cấp và gia hạn chứng chỉ không bị ảnh hưởng.

NGINX hỗ trợ trả các mã redirect như 301 và 308 bằng directive return.

##### 2.4. Verification cho NFR-04A

Tôi đề xuất chia verification thành các test cases cụ thể:

| Test ID | Hành động | Expected Result |
| --- | --- | --- |
| TC-HTTPS-01 | Gửi HTTP GET tới / | Status 301 và Location dùng HTTPS |
| TC-HTTPS-02 | Gửi HTTP GET tới /courts | Redirect HTTPS, giữ path/query |
| TC-HTTPS-03 | Gửi HTTP POST tới /api/auth/login bằng test data | Status 403; request không được xử lý |
| TC-HTTPS-04 | Gửi HTTPS GET tới / | TLS handshake thành công với chứng chỉ hợp lệ |
| TC-HTTPS-05 | Truy cập các Must-have pages | Không có mixed active content HTTP |
| TC-HTTPS-06 | Thử truy cập trực tiếp backend qua public IP và port nội bộ | Không thể bypass HTTPS reverse proxy |

Ví dụ kiểm thử bằng curl:

Bash

```
# Kiểm tra HTTP redirect
curl -I http://booking.example.org/

# Kiểm tra API không chấp nhận HTTP
curl -i http://booking.example.org/api/courts

# Kiểm tra HTTPS và chứng chỉ TLS
curl -vI https://booking.example.org/
```

Kết quả mong đợi cho lệnh đầu:

Plain text`HTTP/1.1 301 Moved Permanently
Location: https://booking.example.org/`

Ngoài ra, bạn có thể sử dụng công cụ [Qualys SSL Labs Server Test](https://www.ssllabs.com/ssltest/) để đánh giá TLS configuration của public endpoint.

Không dùng tùy chọn -k của curl khi kiểm tra tính hợp lệ của chứng chỉ vì nó bỏ qua xác thực certificate.

##### 2.5. NFR-04A hoàn chỉnh cho SRS

**NFR-04A — HTTPS Enforcement**

Requirement Statement

> All external client-to-application communication shall use HTTPS with a valid TLS certificate. HTTP requests to web pages shall be permanently redirected to their HTTPS equivalents, while HTTP requests to API endpoints shall be rejected without executing application operations.

**Verification Method**

> Perform HTTP and HTTPS integration tests against the deployed application. Verify redirect status codes and locations, API request rejection, TLS certificate validity, and the absence of publicly accessible unencrypted application endpoints.

**Pass Criteria:** All specified HTTP/TLS test cases pass.

**Applicable Environment:** Public deployment.

---

#### 3. NFR-04B — Secure Password Storage

##### 3.1. Không nên mã hóa mật khẩu bằng AES hoặc SHA-256 thông thường

Trước hết, cần phân biệt hai thuật ngữ:

| Phương pháp | Đặc tính | Dùng lưu mật khẩu? |
| --- | --- | --- |
| AES Encryption | Có thể giải mã bằng khóa | Không nên |
| SHA-256 | Hàm hash nhanh, không được thiết kế riêng để lưu mật khẩu | Không nên |
| bcrypt | Password hashing có salt và cost factor | Có thể |
| scrypt | Password hashing tiêu tốn bộ nhớ và CPU | Có thể |
| Argon2id | Password hashing có khả năng chống lại tấn công đoán mật khẩu quy mô lớn tốt hơn | Khuyến nghị |

Theo [OWASP Password Storage Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Password_Storage_Cheat_Sheet.html?utm_source=chatgpt.com), mật khẩu xác thực nên được lưu dưới dạng **one-way salted password hash**, không phải reversible encryption. OWASP khuyến nghị Argon2id và đưa ra cấu hình tối thiểu gồm 19 MiB memory, 2 iterations và parallelism 1.

Tôi đề xuất sử dụng **Argon2id** cho BadminBookingHub.

##### 3.2. Argon2id hoạt động như thế nào?

```
<svg viewBox="0 0 336 225" width="100%" xmlns="http://www.w3.org/2000/svg"><rect x="8" y="8" width="143" height="42" rx="7" fill="#94a3b8" fill-opacity=".18" stroke="#64748b" /><text x="80" y="25" text-anchor="middle" font-size="12" font-weight="600" fill="currentColor">User password</text><text x="80" y="40" text-anchor="middle" font-size="10" fill="currentColor">Plaintext (temporary)</text><rect x="186" y="8" width="142" height="42" rx="7" fill="#94a3b8" fill-opacity=".18" stroke="#64748b" /><text x="257" y="25" text-anchor="middle" font-size="12" font-weight="600" fill="currentColor">Random salt</text><text x="257" y="40" text-anchor="middle" font-size="10" fill="currentColor">Unique per hash</text><path d="M80 50 V71 H168 M257 50 V71 H168 V91" stroke="#64748b" stroke-width="1.7" fill="none" /><rect x="99" y="91" width="138" height="42" rx="7" fill="#64748b" fill-opacity=".18" stroke="#64748b" /><text x="168" y="108" font-size="13" text-anchor="middle" fill="currentColor" font-weight="600">Argon2id</text><text x="168" y="123" font-size="10" text-anchor="middle" fill="currentColor">Memory + iterations</text><path d="M168 133 V153" stroke="#64748b" stroke-width="1.7" /><path d="M163 148 L168 154 L173 148" fill="none" stroke="#64748b" stroke-width="1.7" /><rect x="40" y="156" width="256" height="57" rx="7" fill="#16a34a" fill-opacity=".1" stroke="#16a34a" /><text x="168" y="176" font-size="12" text-anchor="middle" font-weight="600" fill="currentColor">PostgreSQL</text><text x="168" y="192" font-size="10" text-anchor="middle" fill="currentColor">Encoded password hash + salt + parameters</text><text x="168" y="205" font-size="10" text-anchor="middle" fill="currentColor">Không lưu plaintext password</text></svg>
```

Khi người dùng đăng ký, backend sử dụng Argon2id để tạo password hash. PostgreSQL chỉ lưu chuỗi encoded hash chứa thuật toán, tham số, salt và kết quả hash.

Khi người dùng đăng nhập, backend lấy hash từ database, sau đó gọi hàm argon2.verify() để so sánh với mật khẩu người dùng cung cấp. Không có bước giải mã mật khẩu.

##### 3.3. Cài đặt Argon2id trong Express + TypeScript

Thư viện [node-argon2](https://www.npmjs.com/package/argon2?utm_source=chatgpt.com) hỗ trợ tạo và xác minh Argon2id hashes.

Cài đặt:

Bash

```
npm install argon2
```

Tạo file ví dụ src/backend/src/services/password.service.ts:

TypeScript

```

import * as argon2 from "argon2";

export async function hashPassword(
  plaintextPassword: string
): Promise<string> {
  return argon2.hash(plaintextPassword, {
    type: argon2.argon2id,
    memoryCost: 19456,
    timeCost: 2,
    parallelism: 1,
  });
}

export async function verifyPassword(
  plaintextPassword: string,
  storedHash: string
): Promise<boolean> {
  return argon2.verify(storedHash, plaintextPassword);
}
```

Cấu hình này theo ngưỡng tối thiểu của OWASP. Nếu ngân sách CPU/RAM cho phép, có thể tăng cost sau khi benchmark tốc độ đăng nhập và đăng ký.

Database có thể dùng trường:

SQL

```
password_hash TEXT NOT NULL
```

Một chuỗi hash ví dụ sẽ có cấu trúc:

Plain text`$argon2id$v=19$m=19456,t=2,p=1$<salt>$<hash>`

Các phần salt và hash là dữ liệu encoded do thư viện tạo ra. Không cần tự viết thuật toán sinh salt hoặc thêm salt cố định vào mật khẩu.

##### 3.4. Verification cho NFR-04B

Tôi khuyến nghị thực hiện cả unit testing và integration testing.

**Unit testing với Vitest**

TypeScript

```

import { describe, it, expect } from "vitest";
import {
  hashPassword,
  verifyPassword,
} from "./password.service";

describe("Secure Password Storage", () => {
  const password = "Example-Password-123!";

  it("should produce an Argon2id hash", async () => {
    const hash = await hashPassword(password);

    expect(hash.startsWith("$argon2id$")).toBe(true);
    expect(hash).not.toBe(password);
  });

  it("should generate unique salted hashes", async () => {
    const hash1 = await hashPassword(password);
    const hash2 = await hashPassword(password);

    expect(hash1).not.toBe(hash2);
  });

  it("should verify correct passwords", async () => {
    const hash = await hashPassword(password);

    expect(await verifyPassword(password, hash))
      .toBe(true);
  });

  it("should reject incorrect passwords", async () => {
    const hash = await hashPassword(password);

    expect(
      await verifyPassword("IncorrectPassword", hash)
    ).toBe(false);
  });
});
```

Nhưng chỉ unit test chưa chứng minh dữ liệu thực tế được lưu đúng trong PostgreSQL.

Vì vậy, cần thêm integration tests:

| Test ID | Hành động | Expected Result |
| --- | --- | --- |
| TC-PWD-01 | Đăng ký tài khoản bằng API | Database lưu hash Argon2id, không lưu plaintext |
| TC-PWD-02 | Tạo hai tài khoản có cùng mật khẩu | Hai encoded hashes khác nhau |
| TC-PWD-03 | Đăng nhập bằng mật khẩu đúng | Authentication thành công |
| TC-PWD-04 | Đăng nhập bằng mật khẩu sai | Authentication thất bại |
| TC-PWD-05 | Đổi hoặc đặt lại mật khẩu (nếu được triển khai) | Hash mới được tạo, hash cũ không còn dùng để xác thực |
| TC-PWD-06 | Kiểm tra response đăng ký và đăng nhập | Không trả password hoặc password hash cho client |
| TC-PWD-07 | Kiểm tra toàn bộ luồng tạo và cập nhật tài khoản | Không có luồng nào lưu plaintext password vào DB |

Đặc biệt, TC-PWD-07 cần bao gồm cả tài khoản Player tự đăng ký và tài khoản Staff/Admin do quản trị viên tạo, vì PA1 hỗ trợ cả ba vai trò.

##### 3.5. Phạm vi “all passwords” nên hiểu như thế nào?

Không nên dùng một NFR duy nhất để bắt buộc tất cả mọi loại secret đều phải được hash.

Cần phân biệt:

- **User passwords:** dùng để người dùng xác thực; phải được password-hash một chiều.
- **Database connection passwords:** ứng dụng cần sử dụng để kết nối PostgreSQL; nên quản lý qua environment secrets hoặc secret manager, không lưu trong bảng users.
- **API keys / service credentials:** cần được quản lý theo mục đích sử dụng và có thể cần encryption hoặc secret storage phù hợp.

Vì vậy, NFR-04B nên giới hạn vào mật khẩu của các tài khoản sử dụng ứng dụng.

##### 3.6. NFR-04B hoàn chỉnh cho SRS

**NFR-04B — Secure User Password Storage**

Requirement Statement

> All user account passwords stored in the database shall be protected using the Argon2id password-hashing algorithm with a unique randomly generated salt per hash and cost parameters of at least 19 MiB memory, 2 iterations, and 1 degree of parallelism. Plaintext passwords and reversibly encrypted passwords shall not be stored.

**Verification Method**

> Perform unit and database integration tests covering all implemented account-creation and password-update workflows. Inspect the persisted password hashes to verify their algorithm identifiers, cost parameters, and unique salts. Confirm that valid passwords can be verified, incorrect passwords are rejected, and plaintext passwords are never persisted.

**Pass Criteria:** All password-storage test cases pass, with no plaintext password found in any tested credential-persistence workflow.

**Applies to:** Player, Staff and Admin accounts.

---

#### 4. Tổng hợp bộ verification cho dự án

Đối với ba yêu cầu này, bạn chỉ cần những công cụ và vị trí triển khai sau:

| NFR | Công cụ | Vị trí cài đặt / thực thi |
| --- | --- | --- |
| NFR-01 | k6 | Laptop test hoặc dedicated CI runner |
| NFR-04A | NGINX, curl, TLS inspection | Cấu hình NGINX trên EC2; test từ client bên ngoài |
| NFR-04B | Argon2id + Vitest + Supertest | Backend authentication service; tests và PostgreSQL test DB |

Thứ tự thực hiện hợp lý là hoàn thiện backend authentication và password hashing trước; triển khai HTTPS khi public endpoint hoạt động; sau đó thực hiện load test NFR-01 trên phiên bản ứng dụng gần hoàn thiện. Các bài unit/integration tests có thể chạy trong CI, còn load test đầy đủ chạy theo yêu cầu trước khi chốt báo cáo PA5.

Tôi cũng đề xuất giữ bằng chứng kiểm thử theo từng NFR: test scripts, cấu hình môi trường, số liệu đầu ra và trạng thái Pass/Fail. Như vậy, từ PA2 đến PA5, nhóm có thể chứng minh mỗi yêu cầu đã được kiểm chứng thay vì chỉ tuyên bố là đã triển khai.

##### Tài liệu kỹ thuật chính thức để tham khảo

- [Grafana k6 — Thresholds](https://grafana.com/docs/k6/latest/using-k6/thresholds/?utm_source=chatgpt.com): cách viết điều kiện pass/fail.
- [Grafana k6 — Built-in Metrics](https://grafana.com/docs/k6/latest/using-k6/metrics/reference/?utm_source=chatgpt.com): ý nghĩa các số liệu HTTP.
- [OWASP — Transport Layer Security](https://cheatsheetseries.owasp.org/cheatsheets/Transport_Layer_Security_Cheat_Sheet.html?utm_source=chatgpt.com): quy định TLS, HTTP redirects, API và HSTS.
- [OWASP — Password Storage](https://cheatsheetseries.owasp.org/cheatsheets/Password_Storage_Cheat_Sheet.html?utm_source=chatgpt.com): Argon2id, salt và cost parameters.
- [*[Embedded image]*

  node-argon2](https://github.com/ranisalt/node-argon2): thư viện và API để hash/verify mật khẩu.

**Kết luận:** NFR-01 có thể được kiểm chứng bằng k6 mà không cần sửa backend để thu thập metric; NFR-04A chủ yếu được đảm bảo tại tầng HTTPS reverse proxy; NFR-04B phải được triển khai trong authentication service và kiểm chứng bằng cả unit test lẫn database integration test. Đây là ba NFR có tiêu chí xác định rõ ràng và phù hợp với quy mô đồ án BadminBookingHub.

Tiêu đề chat đề xuất: $Software Engineering$ - Verification NFR bằng k6, HTTPS và Argon2id (26/10/2026)


---

## You

`13 of 34`

Hãy viết lại giúp tôi bảng NFR đến hiện tại, tôi thấy Argon2id hơi overkill cho dự án demo hiện tại tôi muốn bạn sử dụng công nghệ hashing khác đơn giản hơn nhưng vẫn đáp ứng mức bảo mật cần thiết.


---

## ChatGPT

`14 of 34`

Tôi đề xuất sử dụng **bcrypt với cost factor 12** thay cho Argon2id trong BadminBookingHub. bcrypt có API đơn giản, dễ tích hợp vào Express + TypeScript, tự tạo salt và hỗ trợ xác minh mật khẩu bằng bcrypt.compare().

Tuy nhiên, cần phân biệt: OWASP hiện ưu tiên Argon2id cho ứng dụng mới và chỉ khuyến nghị bcrypt chủ yếu cho hệ thống cũ khi Argon2id hoặc scrypt không khả dụng. Đối với đồ án demo, bcrypt với cost factor 12 là một lựa chọn đơn giản hơn về triển khai, với mức bảo vệ hợp lý cho mật khẩu thử nghiệm. OWASP đưa ra ngưỡng bcrypt tối thiểu là 10.

### 1. Bảng NFR tổng hợp — BadminBookingHub (PA2)

Tôi giữ cách đánh ID trước đây, cập nhật NFR-01 và NFR-07, tách NFR-04 thành hai yêu cầu riêng. NFR-03 cũ về role-based access control được chuyển về Functional Requirements để tránh trùng lặp.

Writing

### 2.2.2. Non-Functional Requirements

The following non-functional requirements define the expected quality attributes of BadminBookingHub, including performance, security, usability, compatibility, reliability, maintainability, and testability.

#### Non-Functional Requirements Specification

| ID | Category | Requirement Statement | Priority | Verification Method |
| --- | --- | --- | --- | --- |
| NFR-01 | Performance — Court Search | The system shall achieve a 95th-percentile HTTP response duration below 2 seconds for successful court search and availability API requests, under 20 concurrent virtual users and a database containing at least 5,000 booking records. The HTTP request failure rate shall remain below 1%. | Must | Run a 5-minute k6 load test. Verify `http_req_duration` p95 and `http_req_failed` separately for both API endpoints. |
| NFR-02 | Performance — Booking | At least 95% of valid booking requests shall complete within 3 seconds under 20 concurrent virtual users, using available and non-conflicting booking slots. | Must | Execute k6 API load tests and measure p95 response duration. Verify booking results against the database. |
| NFR-03 | Security — Login Abuse Protection | The system shall restrict repeated failed login attempts, allowing no more than 10 failed attempts per account within a rolling 15-minute window before temporarily throttling further attempts. | Should | Submit repeated invalid login requests and verify that additional attempts are throttled without permanently disabling accounts. |
| NFR-04A | Security — HTTPS Enforcement | All external client-to-application communication shall use HTTPS with a valid TLS certificate. HTTP requests to web pages shall redirect to HTTPS, while HTTP requests to API endpoints shall be rejected without processing application operations. | Must | Test HTTP redirects, API rejection, TLS certificate validity, and public network exposure using curl and integration tests. |
| NFR-04B | Security — Password Storage | All user account passwords shall be stored as bcrypt password hashes with a unique randomly generated salt and a cost factor of at least 12. Plaintext passwords shall never be persisted. | Must | Use Vitest and database integration tests to verify hashing, salt uniqueness, cost factor, password comparison, and absence of plaintext credentials. |
| NFR-05 | Data Integrity | Booking, cancellation, and check-in database transactions shall be atomic. Failed transactions shall not leave partially committed booking records or inconsistent booking statuses. | Must | Run integration and fault-injection tests; verify transaction rollback and persisted database state. |
| NFR-06 | Usability | At least 80% of first-time test users shall complete a court booking within 2 minutes without external assistance, excluding registration and payment. | Must | Conduct task-based usability testing with at least 5 first-time users, measuring task completion and elapsed time. |
| NFR-07 | Responsive Design | All Must-have workflows shall remain usable across viewport widths from 320 to 1920 CSS pixels without clipped or inaccessible essential controls or unintended page-level horizontal scrolling. Components inherently requiring a two-dimensional layout may scroll independently. | Must | Execute Playwright viewport tests at 320×568, 390×844, 768×1024, 1024×768, and 1440×900, supplemented by manual resizing. |
| NFR-08 | Browser Compatibility | All Must-have workflows shall operate correctly on the agreed current stable versions of Google Chrome and Mozilla Firefox. | Must | Execute the same Playwright end-to-end acceptance tests on both browsers and record versions used. |
| NFR-09 | Availability Freshness | After a booking is confirmed or cancelled, its updated availability shall become visible to other users viewing the affected court's availability calendar within 5 seconds, without requiring manual page reload. | Must | Perform multi-user browser tests, measure update propagation time, and verify consistency with the stored booking state. |
| NFR-10 | Recoverability | The system shall support restoring the application database from a valid backup no more than 24 hours old within 30 minutes in the designated recovery test environment. | Should | Conduct a controlled PostgreSQL backup-and-restore test and measure recovery time and restored data correctness. |
| NFR-11 | Observability | Every server-side HTTP 5xx response shall generate a diagnostic log containing a timestamp, request identifier, route, and HTTP status code, without exposing passwords or authentication tokens. | Should | Trigger controlled server errors, inspect generated logs, and verify required diagnostic fields and absence of sensitive credentials. |

#### Additional Project Quality Requirement

| ID | Category | Requirement Statement | Priority | Verification Method |
| --- | --- | --- | --- | --- |
| NFR-12\* | Testability / Quality Gate | Automated unit tests shall achieve at least 70% statement coverage in the backend service layer. | Must for PA5 | Generate and inspect the Vitest coverage report during CI. |

*Note: NFR-12 is primarily a development quality gate rather than an observable runtime product quality attribute. It may be documented separately under Testing and Quality Assurance Constraints.*

All proposed numeric thresholds must be reviewed and approved by the project team before the PA2 requirements baseline is finalized.

### 2. Điều chỉnh quan trọng so với phiên bản trước

| NFR | Thay đổi |
| --- | --- |
| NFR-01 | Làm rõ metric p95, error rate, workload và thời gian chạy k6 |
| NFR-03 | Thay authorization trùng FR bằng login abuse protection, ưu tiên Should |
| NFR-04A | Tách riêng HTTPS Enforcement |
| NFR-04B | Thay Argon2id bằng bcrypt, cost factor ≥ 12 |
| NFR-07 | Hỗ trợ viewport 320–1920 CSS px, có ngoại lệ hợp lý cho calendar/table |
| NFR-12 | Phân loại rõ là quality gate của quá trình phát triển |

Một số điểm cần lưu ý trước khi đưa vào bản SRS cuối cùng:

**NFR-01 và NFR-02:** Các ngưỡng 2–3 giây và 20 virtual users mới là chỉ tiêu đề xuất. k6 hỗ trợ kiểm tra bằng thresholds p(95)<2000 và rate<0.01, nhưng bài test chỉ đạt khi kết quả thực tế thỏa điều kiện.

**NFR-03:** Nếu nhóm muốn giữ phạm vi đơn giản, có thể chuyển login throttling thành Security Functional Requirement hoặc bỏ khỏi bản Must-have. Nếu triển khai, cần lưu ý việc throttling theo tài khoản có thể bị kẻ khác lợi dụng để gây từ chối dịch vụ.

**NFR-07:** Việc cho phép calendar và data table cuộn ngang trong một vùng riêng phù hợp với ngoại lệ dành cho nội dung hai chiều của WCAG 2.2 Reflow.

### 3. Cách triển khai bcrypt đơn giản cho NFR-04B

Trong backend Node.js + Express:

Bash

```
npm install bcrypt
npm install -D @types/bcrypt
```

Ví dụ password.service.ts:

TypeScript

```
import bcrypt from "bcrypt";

const SALT_ROUNDS = 12;

export async function hashPassword(
  password: string
): Promise<string> {
  if (Buffer.byteLength(password, "utf8") > 72) {
    throw new Error("Password exceeds bcrypt input limit");
  }

  return bcrypt.hash(password, SALT_ROUNDS);
}

export async function verifyPassword(
  password: string,
  hash: string
): Promise<boolean> {
  if (Buffer.byteLength(password, "utf8") > 72) {
    return false;
  }

  return bcrypt.compare(password, hash);
}
```

Khi tạo tài khoản, gọi hashPassword() trước khi lưu vào trường password_hash của PostgreSQL.

Một bcrypt hash có dạng:

Plain text`$2b$12$...`

Trong đó 2b là định danh phiên bản bcrypt, 12 là cost factor. Salt được tạo tự động và nằm trong chuỗi hash.

Điểm cần chú ý là bcrypt chỉ sử dụng tối đa 72 **bytes**, không phải 72 ký tự. Điều này đặc biệt quan trọng với Unicode hoặc tiếng Việt có dấu.

Để chứng minh NFR-04B đạt yêu cầu, nhóm nên kiểm tra tối thiểu: hai tài khoản dùng cùng mật khẩu tạo ra hai hashes khác nhau; mật khẩu đúng được xác minh; mật khẩu sai bị từ chối; hash lưu trong PostgreSQL có cost factor ≥ 12; không có plaintext trong bản ghi người dùng.

### 4. NFR nào nên ưu tiên triển khai và kiểm chứng?

Với thời gian và nhân lực của BadminBookingHub, tôi đề xuất:

- **Bắt buộc kiểm chứng trong demo:** NFR-01, 04A, 04B, 05, 07, 08, 09.
- **Kiểm chứng khi hoàn thành các workflow liên quan:** NFR-02, 06.
- **Ưu tiên sau:** NFR-03, 10, 11.
- **Đưa vào CI quality gate:** NFR-12, theo đúng PA5.

Riêng **NFR-04B**, tôi đánh giá bcrypt với cost factor 12 là lựa chọn hợp lý cho đồ án vì dễ triển khai và dễ xác minh. Tuy nhiên, nên benchmark thời gian hash/verify trên EC2 và điều chỉnh cost nếu cần; không nên chuyển sang SHA-256 hoặc MD5 chỉ để làm việc triển khai đơn giản hơn.

Bộ bảng này có thể làm bản nháp cho PA2. Trước khi chốt, nhóm nên xác nhận các chỉ tiêu định lượng và thống nhất với phần Functional Requirements, Business Rules để không phát sinh yêu cầu trùng lặp.

Tiêu đề chat đề xuất: $Software Engineering$ - Tổng hợp NFR và bcrypt cho BadminBookingHub (26/10/2026)


---

## You

`15 of 34`

Những thành phần của bcrypt như cost factor tôi chưa hiểu rõ thì có nên ghi vào báo cáo không


---

## ChatGPT

`16 of 34`

**Tôi khuyên bạn không nên đưa cost factor = 12 vào NFR nếu chưa hiểu rõ ý nghĩa và lý do lựa chọn giá trị đó.** Tuy nhiên, bạn nên tìm hiểu khái niệm này trước khi triển khai, vì nó ảnh hưởng trực tiếp đến cả bảo mật và hiệu năng.

Với đồ án BadminBookingHub, cần phân biệt giữa **yêu cầu chất lượng trong SRS** và **quyết định kỹ thuật trong tài liệu thiết kế**.

### 1. Cost factor trong bcrypt là gì?

bcrypt là thuật toán hash mật khẩu một chiều. Nó sử dụng hai cơ chế quan trọng:

- **Salt:** Một giá trị ngẫu nhiên riêng cho từng password hash, giúp hai người dùng có cùng mật khẩu vẫn có hash khác nhau.
- **Cost factor (work factor):** Tham số điều chỉnh lượng công việc tính toán cần thiết để hash và kiểm tra mật khẩu.

Cost factor càng cao thì việc thử đoán mật khẩu hàng loạt càng tốn tài nguyên, nhưng quá trình đăng nhập cũng chậm hơn.

Độ khó tính toán của bcrypt tăng xấp xỉ theo $2^{cost}$.

| Cost factor | Mức công việc tương đối | So với cost 10 |
| --- | --- | --- |
| 10 | $2^{10}=1.024$ | 1× |
| 11 | $2^{11}=2.048$ | 2× |
| 12 | $2^{12}=4.096$ | 4× |
| 13 | $2^{13}=8.192$ | 8× |

Đây là mức công việc tương đối, không phải số mili giây thực tế. Thời gian hash còn phụ thuộc CPU và môi trường chạy.

OWASP quy định bcrypt nên có work factor tối thiểu 10, đồng thời khuyến nghị điều chỉnh theo khả năng của server. OWASP hiện ưu tiên Argon2id cho ứng dụng mới, nhưng bcrypt vẫn có hướng dẫn sử dụng và cấu hình an toàn.

### 2. Có nên đưa cost factor vào báo cáo SRS không?

Tôi đề xuất chia làm hai cấp độ:

| Tài liệu | Nội dung cần viết |
| --- | --- |
| PA2 — SRS | Mật khẩu phải được lưu bằng thuật toán password hashing phù hợp, có salt riêng và không lưu plaintext |
| PA3 — Software Design | Quyết định sử dụng bcrypt, chọn cost factor, giải thích lý do và giới hạn |
| PA5 — Implementation & Testing | Kiểm chứng password hashing hoạt động đúng, ghi nhận cấu hình và kết quả kiểm thử |

Lý do là NFR chủ yếu mô tả **hệ thống phải đáp ứng thuộc tính chất lượng gì**, còn việc sử dụng bcrypt với cost factor 12 là một lựa chọn triển khai cụ thể.

Bạn có thể đưa thuật toán vào SRS nếu đó là ràng buộc thiết kế đã được nhóm thống nhất. Nhưng việc đưa thêm các thông số kỹ thuật không cần thiết sẽ khiến requirement khó bảo trì và khó giải thích khi bảo vệ đồ án.

### 3. Tôi đề xuất viết lại NFR-04B

Thay vì viết:

> All user account passwords shall be stored as bcrypt password hashes with a unique randomly generated salt and a cost factor of at least 12.

Tôi đề xuất:

**NFR-04B — Secure Password Storage**

**Requirement Statement**

> All user account passwords shall be stored using a secure, salted, one-way password hashing algorithm. Plaintext passwords shall never be stored in the database.

---

**Verification Method**

> Perform integration tests to verify that passwords are hashed before database storage, identical passwords produce different salted hashes, and user authentication correctly validates passwords against their stored hashes.

**Priority:** Must

**Related Feature:** F01 — User Registration & Login

Yêu cầu này vẫn có thể kiểm chứng, không phụ thuộc quá nhiều vào công nghệ và phù hợp với phạm vi demo.

Sau đó, trong PA3, bạn có thể ghi:

> The system will use bcrypt for password hashing, with a configurable work factor initially set to 12. The configuration will be evaluated against the deployment environment's authentication performance.

Cách này giúp nhóm giữ được sự linh hoạt. Nếu benchmark cho thấy cost 12 không phù hợp với tài nguyên demo, nhóm có thể đánh giá điều chỉnh mà không phải thay đổi yêu cầu cốt lõi về bảo vệ mật khẩu.

### 4. Những điều cần hiểu trước khi đưa vào báo cáo

Đối với bcrypt, tôi cho rằng bạn chỉ cần nắm vững bốn vấn đề:

1. Tại sao cần hash mật khẩu thay vì lưu plaintext hoặc mã hóa có thể giải mã?
2. Salt là gì, tại sao hai mật khẩu giống nhau lại cần hai hashes khác nhau?
3. Cost factor ảnh hưởng đến bảo mật và tốc độ đăng nhập như thế nào?
4. Làm sao kiểm chứng mật khẩu được hash và xác minh đúng trong Express/PostgreSQL?

Bạn không cần hiểu toàn bộ cơ chế mật mã bên trong bcrypt để sử dụng thư viện một cách hợp lý, nhưng cần giải thích được những tham số mà nhóm đã lựa chọn.

**Kết luận:** Với PA2, tôi khuyến nghị dùng phiên bản NFR-04B không quy định trực tiếp cost factor = 12. Hãy đưa bcrypt và cost factor sang PA3 như một quyết định thiết kế, rồi kiểm chứng tại PA5. Đây là cách tách biệt Requirements, Design và Verification rõ ràng hơn, đặc biệt phù hợp với V-model của đồ án.

Tiêu đề chat đề xuất: $Software Engineering$ - Cost Factor và viết NFR bảo mật (26/10/2026)


---

## You

`17 of 34`

Tôi muốn có thêm 2 phi chức năng là những lỗi input phải được show cho người dùng xem để họ có thể nhập đúng hơn, có hai ngôn ngữ cho giao diện là Tiếng anh và tiếng việt có thể đổi ngôn ngữ ở mọi trang. Tôi thắc mắc là 2 yêu cầu về môi trường webapp như Mozilla, Chromium, Safari và yêu cầu về responsive nên được xếp vào Usability hay Portability. Tôi muốn mở rộng cái yêu cầu về browser engine ra Mozilla và Chormium và Safari nói chung có hợp lý không.


---

## ChatGPT

`18 of 34`

Tôi đồng ý bổ sung hai yêu cầu này cho **BadminBookingHub**, vì chúng cải thiện trực tiếp trải nghiệm của Player, Staff và Admin. Tuy nhiên, cần phân loại đúng để tránh nhầm lẫn giữa Functional Requirements và Non-Functional Requirements như trường hợp NFR-03 trước đây.

Tôi đề xuất:

- **NFR-13 — Input Error Feedback:** thuộc Usability.
- **NFR-14 — Multilingual User Interface:** thuộc Usability / Internationalization, nhưng chức năng chuyển đổi ngôn ngữ nên được mô tả bằng FR riêng.
- **NFR-07 — Responsive Design:** chủ yếu thuộc Usability, cũng liên quan đến Adaptability.
- **NFR-08 — Cross-Browser Support:** phù hợp hơn với Portability / Adaptability nếu sử dụng ISO/IEC 25010:2011.

### 1. Usability hay Portability? Phân loại theo ISO 25010

Có một điểm đáng chú ý: ISO/IEC 25010 đã thay đổi trong phiên bản 2023.

| ISO/IEC 25010:2011 | ISO/IEC 25010:2023 |
| --- | --- |
| Usability | Interaction Capability |
| Portability | Flexibility |
| Portability → Adaptability | Flexibility → Adaptability |
| Compatibility | Compatibility |

Ở ISO 25010:2023, *Interaction Capability* tập trung vào khả năng người dùng tương tác với phần mềm để hoàn thành nhiệm vụ, còn *Flexibility* đề cập đến khả năng thích ứng với môi trường và bối cảnh sử dụng.

Dựa trên sự khác biệt đó, tôi khuyến nghị:

| NFR | Phân loại theo ISO 2011 | Phân loại theo ISO 2023 |
| --- | --- | --- |
| NFR-07 — Responsive Design | Usability / Portability (Adaptability) | Interaction Capability / Flexibility (Adaptability) |
| NFR-08 — Cross-Browser Support | Portability → Adaptability | Flexibility → Adaptability |
| NFR-13 — Input Error Feedback | Usability → User Error Protection | Interaction Capability → User Error Protection |
| NFR-14 — Multilingual UI | Usability / Accessibility | Interaction Capability → Inclusivity |

**Đối với NFR-07**, vì yêu cầu của bạn tập trung vào việc giao diện vẫn dễ sử dụng trên màn hình có kích thước khác nhau, tôi sẽ chọn Usability làm category chính.

**Đối với NFR-08**, bản chất là hệ thống hoạt động được trong những browser runtime khác nhau. Vì vậy, Portability → Adaptability là cách phân loại hợp lý theo ISO 2011.

Bạn vẫn có thể đặt tên category thực hành là *Browser Compatibility*. Tuy nhiên, nếu bám sát taxonomy ISO, Compatibility có hai subcharacteristics là Co-existence và Interoperability, không hoàn toàn tương đương với việc chạy được trên nhiều trình duyệt.

### 2. Có nên mở rộng NFR-08 sang ba browser engines?

Có. Đây là một cải tiến hợp lý và cũng dễ kiểm thử với Playwright.

Tuy nhiên, cách gọi của bạn cần sửa một chút:

| Browser Engine | Các trình duyệt tiêu biểu |
| --- | --- |
| **Blink (Chromium)** | Chrome, Edge, Brave, Opera |
| **Gecko** | Firefox |
| **WebKit** | Safari |

Mozilla là tổ chức phát triển Firefox, không phải browser engine. Chromium là dự án trình duyệt mã nguồn mở sử dụng Blink. Safari sử dụng WebKit.

Playwright hiện hỗ trợ kiểm thử trên cả Chromium, Firefox và WebKit.

**Recommended Browser Test Matrix** BadminBookingHub

**Chromium**

Blink

**Firefox**

Gecko

**WebKit**

Safari engine

Playwright WebKit không phải trình duyệt Safari chính thức. Nếu muốn tuyên bố hỗ trợ Safari đầy đủ, nên kiểm thử bổ sung trên Safari thực tế ở macOS hoặc iOS.

Vì vậy, tôi khuyến nghị viết yêu cầu về **three major browser engines** thay vì tuyên bố hỗ trợ mọi trình duyệt dựa trên những engines đó.

---

### 3. Bản NFR cập nhật để đưa vào PA2

Dưới đây là bốn yêu cầu đã được viết lại bằng tiếng Anh, gồm hai NFR mới và hai NFR được chỉnh sửa.

Writing

### NFR-07 — Responsive User Interface

**Category:** Usability — Responsive Design

**Priority:** Must

**Requirement Statement:**

The system shall maintain the usability of all Must-have workflows across viewport widths from 320 to 1920 CSS pixels. Essential content and interactive controls shall remain accessible without unintended page-level horizontal scrolling. Components requiring two-dimensional layouts, such as availability calendars and data tables, may support independent horizontal scrolling.

**Verification Method:**

Execute responsive layout tests using Playwright at representative viewport sizes of 320×568, 390×844, 768×1024, 1024×768, and 1440×900. Supplement these tests with manual browser resizing and landscape orientation checks.

**Acceptance Criteria:**

All Must-have workflows remain operable, with no clipped essential information, inaccessible controls, or unintended page-level horizontal overflow.

---

### NFR-08 — Cross-Browser Support

**Category:** Portability — Adaptability

**Priority:** Must

**Requirement Statement:**

The system shall support the three major web browser engine families: Chromium/Blink, Firefox/Gecko, and WebKit. All Must-have workflows shall function correctly without browser-specific functional failures in the browser versions included in the approved test environment.

**Verification Method:**

Execute automated end-to-end tests using Playwright with its bundled Chromium, Firefox, and WebKit browsers. Record the browser versions and test results.

**Acceptance Criteria:**

All Must-have acceptance tests pass on all three tested browser engines without browser-specific functional failures.

---

### NFR-13 — Input Error Feedback

**Category:** Usability — User Error Protection

**Priority:** Must

**Requirement Statement:**

The system shall provide clear, field-specific error messages for all detected invalid user inputs in the Must-have workflows. Each message shall identify the affected input and explain how to correct it whenever a safe and applicable correction is known. Error messages shall be displayed in the currently selected interface language.

**Verification Method:**

Execute UI and form-validation tests covering missing required fields, invalid data formats, and applicable business-rule validation errors. Verify that error messages are displayed correctly and that users can correct their inputs without unnecessarily re-entering valid information.

**Acceptance Criteria:**

- Every detected validation error in the test cases is communicated using a readable text message.
- The affected input field can be identified.
- Correction guidance is provided when applicable and safe.
- Valid previously entered data remains available for correction.
- Error messages follow the selected interface language.

---

### NFR-14 — Multilingual User Interface

**Category:** Usability — Internationalization / Inclusivity

**Priority:** Must

**Requirement Statement:**

The system shall provide all system-generated user interface text in English and Vietnamese across all Must-have workflows. The selected language shall remain consistent across page navigation and page reloads. Users shall be able to change the interface language from every application page without losing their current workflow progress.

**Verification Method:**

Execute automated UI tests for both supported languages across all Must-have pages. Verify the completeness of translated interface text, language selection availability, language persistence across navigation and reloads, and preservation of user-entered data during language changes.

**Acceptance Criteria:**

- All system-generated interface labels, buttons, navigation elements, and validation messages in Must-have workflows have English and Vietnamese versions.
- Users can select either language from every application page.
- The selected language persists after navigation and browser reload.
- Language switching does not reset user-entered form data or terminate the current workflow.
- The document's HTML language attribute matches the selected language.

### 4. Làm rõ NFR-13 — Input Error Feedback

Yêu cầu này rất phù hợp với WCAG 2.2:

- **3.3.1 — Error Identification:** Xác định trường dữ liệu lỗi và mô tả lỗi bằng văn bản.
- **3.3.3 — Error Suggestion:** Đưa ra hướng dẫn sửa lỗi khi có thể và không gây rủi ro bảo mật.

Ví dụ, trong form đăng ký:

**Minh họa: Input validation**

- Tiếng Việt
- English
  Current selection unavailable.

\[Input placeholder: name@example.com\] (Current value unavailable.)

Thử sửa email hoặc chuyển ngôn ngữ để quan sát hành vi mong muốn của NFR-13 và NFR-14.

Đây là ví dụ về feedback chất lượng tốt hơn so với thông báo chung chung Invalid input.

Một lưu ý: **không nên hiển thị chi tiết lỗi nội bộ cho người dùng**. Ví dụ, PostgreSQL constraint violation hoặc stack trace cần được chuyển thành thông báo dễ hiểu và an toàn.

### 5. NFR-14 có bị trùng với Functional Requirement không?

Có một phần.

Câu “Users shall be able to change the interface language” mô tả một chức năng có thể quan sát được. Vì vậy, nếu muốn phân loại chặt chẽ, tôi đề xuất thêm:

**FR — Change Interface Language**

> The system shall allow users to switch between English and Vietnamese from any application page.

Sau đó, NFR-14 chỉ tập trung vào *chất lượng của việc hỗ trợ đa ngôn ngữ* như tính đầy đủ của bản dịch, tính nhất quán, lưu lựa chọn và không làm gián đoạn thao tác.

Đây là cách phù hợp hơn với việc phân biệt FR/NFR mà chúng ta đã trao đổi trước đó.

Về mặt kiểm thử, nên kiểm tra cả <html lang="vi"> và <html lang="en"> vì W3C khuyến nghị khai báo ngôn ngữ tài liệu bằng thuộc tính lang để trình duyệt và công nghệ hỗ trợ nhận diện đúng ngôn ngữ.

### 6. Tổng hợp các điều chỉnh

| NFR | Category nên ghi trong PA2 | Trạng thái |
| --- | --- | --- |
| NFR-07 | Usability — Responsive Design | Cập nhật |
| NFR-08 | Portability — Adaptability | Mở rộng sang 3 browser engines |
| NFR-13 | Usability — User Error Protection | Thêm mới |
| NFR-14 | Usability — Internationalization | Thêm mới |

**Khuyến nghị cuối cùng:** Nếu môn học sử dụng ISO 25010:2011, hãy giữ hai nhãn Usability và Portability như bảng trên. Nếu được tự chọn phiên bản, nên sử dụng ISO/IEC 25010:2023 và điều chỉnh thành Interaction Capability và Flexibility tương ứng.

Đối với nhóm 5 sinh viên, kiểm thử Chromium, Firefox và WebKit bằng Playwright cùng với hai bộ ngôn ngữ là khả thi. Tuy nhiên, nên ưu tiên tự động hóa một số workflow đại diện trước, sau đó mở rộng để đáp ứng tất cả Must-have workflows đã cam kết trong SRS.

Tiêu đề chat đề xuất: $Software Engineering$ - Phân loại và mở rộng NFR cho BadminBookingHub (26/10/2026)


---

## You

`19 of 34`

Hãy viết lại bảng NFR giúp tôi với các thay đổi vừa rồi, giúp tôi viết với văn phong ngắn nhưng vẫn phải đủ các thông tin cần thiết


---

## ChatGPT

`20 of 34`

Dưới đây là bảng **Non-Functional Requirements (NFR)** đã cập nhật cho BadminBookingHub, với văn phong ngắn gọn, có thể đưa vào **PA2 — Section 2.2.2**.

Tôi giữ các chỉ số đo lường và verification method, đồng thời dùng cách phân loại Usability/Portability theo ISO/IEC 25010:2011.

Writing

### 2.2.2. Non-Functional Requirements

| ID | Category | Requirement Statement | Priority | Verification Method |
| --- | --- | --- | --- | --- |
| NFR-01 | Performance | Court search and availability APIs shall achieve p95 response time below 2 seconds and error rate below 1% under 20 concurrent virtual users and 5,000 booking records. | Must | k6 load test (5 minutes); measure p95 latency and error rate. |
| NFR-02 | Performance | At least 95% of valid booking requests shall complete within 3 seconds under 20 concurrent virtual users. | Must | k6 load test; measure booking response time. |
| NFR-03 | Security | The system shall temporarily throttle login attempts after 10 failed attempts per account within 15 minutes. | Should | Automated repeated-login tests. |
| NFR-04A | Security | All external application traffic shall use HTTPS with a valid TLS certificate. HTTP page requests shall redirect to HTTPS, while HTTP API requests shall be rejected. | Must | curl tests for redirects, API rejection, and TLS certificate validity. |
| NFR-04B | Security | User passwords shall be stored using salted, one-way password hashing. Plaintext passwords shall never be stored. | Must | Unit and database integration tests; verify hash uniqueness and password validation. |
| NFR-05 | Data Integrity | Booking, cancellation, and check-in transactions shall be atomic, leaving no partial database updates upon failure. | Must | Integration tests; verify transaction rollback. |
| NFR-06 | Usability | At least 80% of first-time users shall complete a court booking within 2 minutes without assistance, excluding registration and payment. | Must | Usability testing with at least 5 first-time users. |
| NFR-07 | Usability — Responsive Design | All Must-have workflows shall remain usable across viewport widths of 320–1920 CSS pixels without inaccessible controls or unintended page-level horizontal scrolling. | Must | Playwright viewport tests and manual resizing. |
| NFR-08 | Portability — Adaptability | All Must-have workflows shall function correctly on Chromium/Blink, Firefox/Gecko, and WebKit browser engines. | Must | Playwright cross-browser E2E tests. |
| NFR-09 | Reliability — Data Freshness | Booking availability changes shall appear to other users within 5 seconds without manual page reload. | Must | Multi-user E2E tests; measure update delay. |
| NFR-10 | Recoverability | The system shall support database recovery from a backup no older than 24 hours within 30 minutes in the recovery test environment. | Should | PostgreSQL backup-and-restore test. |
| NFR-11 | Observability | Every server-side HTTP 5xx error shall be logged with timestamp, request ID, route, and status code, without exposing sensitive credentials. | Should | Trigger controlled errors and inspect logs. |
| NFR-12 | Testability | Automated tests shall achieve at least 70% statement coverage of the backend service layer. | Must | Vitest coverage report in CI. |
| NFR-13 | Usability — Error Feedback | Invalid form inputs shall display clear, field-specific error messages with correction guidance where applicable, while preserving valid entered data. | Must | Form-validation tests using invalid inputs. |
| NFR-14 | Usability — Internationalization | All system-generated UI text shall support English and Vietnamese. The selected language shall persist across navigation and reloads without losing user input. | Must | Playwright localization and language-persistence tests. |

#### Notes

- **NFR-04B:** bcrypt is the planned implementation, but the algorithm and its cost factor will be specified in the design phase.
- **NFR-07:** Self-contained calendars and tables may scroll horizontally when necessary.
- **NFR-08:** Playwright tests cover the three browser engines; official Safari compatibility requires additional testing on Safari.
- **NFR-12:** This is primarily a development quality gate and may be moved to the Testing and Quality Assurance section.
- **NFR-14:** The ability to switch languages from every page should be specified separately as a Functional Requirement.
- **Performance thresholds:** The proposed values must be validated against the project's actual test environment before final acceptance.

### Một số điều chỉnh tôi khuyến nghị trước khi chốt PA2

**1. Tách chức năng chuyển đổi ngôn ngữ khỏi NFR-14.** Bổ sung vào FR:

> The system shall allow users to switch between English and Vietnamese from any application page.

NFR-14 sẽ chịu trách nhiệm về tính đầy đủ, nhất quán và khả năng duy trì trạng thái khi thay đổi ngôn ngữ.

**2. Giữ NFR-12 nhưng có thể chuyển sang Quality Assurance.** Mục tiêu 70% statement coverage đã thuộc tiêu chí PA5, nên không cần đặt thêm một yêu cầu tương tự.

**3. Đánh giá lại NFR-03 và NFR-10.** Đây là hai yêu cầu tương đối độc lập với 7 chức năng Must-have. Nếu nhóm không đủ thời gian triển khai và kiểm chứng, có thể giữ ở mức Should.

**4. Với NFR-08, chỉ cam kết kiểm thử các phiên bản browser engines được Playwright hỗ trợ**, không tuyên bố rằng hệ thống hoạt động trên mọi trình duyệt hoặc mọi phiên bản cũ.

Như vậy, bảng hiện có **15 yêu cầu**, gồm 11 Must và 4 Should (nếu tính NFR-12 là Must theo PA5). Nếu chuyển NFR-12 ra khỏi bảng, bộ NFR của sản phẩm còn 14 yêu cầu.

Tiêu đề chat đề xuất: $Software Engineering$ - Hoàn thiện bảng NFR cho BadminBookingHub (26/10/2026)


---

## You

`21 of 34`

Tôi muốn hỏi về NFR-09 nếu muốn thực hiện cập nhật realtime như thế này thì phải sử dụng những giao thức như Socket, ... đúng khồng


---

## ChatGPT

`22 of 34`

**Không nhất thiết.** Để thực hiện NFR-09 của BadminBookingHub, bạn không bắt buộc phải sử dụng WebSocket hoặc Socket.IO.

NFR-09 hiện tại của chúng ta là:

> **NFR-09 — Availability Freshness:** Booking availability changes shall appear to other users within 5 seconds without manual page reload.

Yêu cầu này có hai điều kiện chính:

1. Khi một người đặt hoặc hủy sân, những người khác phải thấy trạng thái mới trong vòng 5 giây.
2. Người dùng không cần tự nhấn Refresh để cập nhật.

**NFR-09 không quy định phải dùng công nghệ nào.** Bạn có thể đáp ứng bằng HTTP Polling, Server-Sent Events (SSE), WebSocket hoặc Socket.IO.

### 1. So sánh các phương pháp cập nhật dữ liệu

| Phương pháp | Cách hoạt động | Độ phức tạp | Phù hợp demo |
| --- | --- | --- | --- |
| HTTP Polling | Client tự gọi API mỗi 2–3 giây | Thấp | Rất phù hợp |
| Server-Sent Events (SSE) | Server chủ động gửi sự kiện tới client | Trung bình | Phù hợp |
| WebSocket | Client và server duy trì kết nối hai chiều | Trung bình–cao | Phù hợp |
| Socket.IO | Thư viện realtime hỗ trợ events, rooms, reconnect | Trung bình | Phù hợp |

Với hệ thống đặt sân có khoảng vài chục người dùng đồng thời, polling là phương án đơn giản nhất. Nếu muốn học cách xây dựng ứng dụng event-driven hoặc realtime thực sự, WebSocket hoặc Socket.IO đáng để triển khai.

### 2. HTTP Polling hoạt động như thế nào?

Giả sử Player A và Player B đang xem lịch của Court 01.

Player B gọi lại API định kỳ, nhận dữ liệu mới sau khi booking đã commit và React cập nhật giao diện.

Nếu React frontend dùng TanStack Query, việc polling khá đơn giản:

TypeScript

```
const { data: availability } = useQuery({
  queryKey: ["availability", courtId, date],
  queryFn: () => fetchCourtAvailability(courtId, date),
  refetchInterval: 2000,
  refetchOnWindowFocus: true,
});
```

refetchInterval: 2000 yêu cầu truy vấn được thực hiện lại mỗi 2 giây khi query đang được quan sát. Đây là tính năng được hỗ trợ trực tiếp trong TanStack Query.

Giả sử mỗi lần request mất 200 ms, thì trong điều kiện bình thường, Player B sẽ thấy thay đổi sau khoảng 0,2–2,2 giây.

Tuy nhiên, polling mỗi 2 giây **không bảo đảm tuyệt đối** luôn đáp ứng ngưỡng 5 giây, do độ trễ server, mạng hoặc việc trình duyệt tạm dừng hoạt động nền. TanStack Query mặc định cũng tạm dừng polling khi tab mất focus.

### 3. Nếu dùng WebSocket hoặc Socket.IO thì sao?

Đối với Socket.IO, luồng xử lý sẽ khác:

> **[Mermaid diagram]**

Thay vì đợi lần polling tiếp theo, server chủ động thông báo cho Player B ngay sau khi booking được commit thành công.

Socket.IO cung cấp giao tiếp hai chiều dựa trên events, tự động kết nối lại và hỗ trợ nhiều transport như WebSocket, HTTP long-polling. Socket.IO không phải là giao thức WebSocket thuần túy.

Bạn cũng có thể dùng **SSE**, vì BadminBookingHub chủ yếu cần server thông báo thay đổi tới các client khác. SSE hỗ trợ luồng sự kiện một chiều từ server đến browser thông qua EventSource.

### 4. Một điểm cần chú ý: realtime không ngăn được double booking

Giả sử cả Player A và B đều thấy Court 01 còn trống. Họ đồng thời nhấn Book trước khi giao diện cập nhật.

Dù dùng WebSocket, cả hai vẫn có thể gửi yêu cầu đặt sân.

Vì vậy:

- **NFR-09:** Giao diện nhận được thông tin availability mới đủ nhanh.
- **Business Rule — No Double Booking:** Backend/database phải ngăn hai booking trùng thời gian được xác nhận.

Trong kiến trúc BadminBookingHub, PostgreSQL transaction và cơ chế kiểm soát tính nhất quán phải là nơi thực thi quy tắc đặt sân. Realtime chỉ giúp giao diện kịp thời phản ánh kết quả.

### 5. Tôi khuyến nghị gì cho đồ án?

Với năm sinh viên và thời gian triển khai ngắn, tôi nghiêng về **HTTP Polling mỗi 2 giây bằng TanStack Query**. Phương án này sử dụng REST API sẵn có, không cần thêm giao thức kết nối thường trực hoặc cơ chế quản lý subscriptions.

Bạn có thể giữ NFR-09 nhưng làm rõ phạm vi:

> **NFR-09 — Booking Availability Freshness:** For active clients with a functioning network connection, confirmed booking and cancellation changes shall be reflected in the availability calendar within 5 seconds, without requiring manual page reload.

**Verification:** Dùng Playwright mở hai browser contexts. Player A đặt hoặc hủy sân; bắt đầu đo thời gian khi giao dịch commit thành công; kiểm tra Player B nhìn thấy trạng thái mới trong tối đa 5 giây. Lặp lại nhiều lần với cả booking và cancellation.

Nếu muốn nâng cao kiến trúc dự án và học thêm về event-driven communication, Socket.IO hoặc SSE là hướng mở rộng phù hợp. Nhưng đối với NFR-09 hiện tại, polling hoàn toàn có thể đáp ứng yêu cầu và dễ kiểm thử hơn.

Tiêu đề chat đề xuất: $Software Engineering$ - Real-time Availability bằng Polling và WebSocket (26/10/2026)


---

## You

`23 of 34`

Tôi muốn thêm requirements về Reliability là khi đặt cọc (payment) thành công thì phải cập nhật trạng thái, còn nếu không thành công thì không được để là thành công


---

## ChatGPT

`24 of 34`

Tôi đề xuất bổ sung **NFR-15 — Payment Status Consistency** thuộc nhóm **Reliability / Data Integrity** cho BadminBookingHub.

Yêu cầu này rất quan trọng nếu nhóm triển khai F08 — Deposit Payment (Should-have), vì hệ thống không được ghi nhận một giao dịch thanh toán thành công khi cổng thanh toán chưa xác nhận thành công.

Tuy nhiên, nên phân biệt hai phần:

- **Functional Requirement / Business Rule:** Khi thanh toán thành công, hệ thống phải cập nhật trạng thái; khi thất bại, không được ghi nhận thành công.
- **Non-Functional Requirement:** Trạng thái thanh toán phải luôn nhất quán với kết quả được xác minh từ cổng thanh toán, kể cả khi có lỗi mạng, callback trùng lặp hoặc phản hồi đến chậm.

Phần thứ hai phù hợp hơn để đưa vào nhóm Reliability vì nó mô tả khả năng duy trì tính đúng đắn khi hệ thống gặp sự cố.

### 1. NFR-15 đề xuất cho SRS

Writing

**NFR-15 — Payment Status Consistency**

**Category:** Reliability — Data Integrity

**Priority:** Should (applicable to F08 — Deposit Payment)

**Requirement Statement:**

The system shall update the payment status only based on verified payment gateway results. Successful payments shall be recorded as successful, while failed or unverified payments shall never be marked as successful. Duplicate payment notifications shall not cause inconsistent payment or booking states.

**Verification Method:**

Perform payment gateway sandbox integration tests covering successful, failed, pending, and duplicate payment notifications. Verify the resulting payment and booking statuses in the database.

**Acceptance Criteria:**

- All verified successful payments are recorded correctly.
- No failed or unverified payment is recorded as successful.
- Duplicate notifications do not produce inconsistent states.

### 2. Các trạng thái thanh toán cần phân biệt

Tôi khuyến nghị dùng ít nhất ba trạng thái:

svg![Image generated by the assistant](data:image/svg+xml;utf8,%3Csvg%20viewBox%3D%220%200%20330%20177%22%20width%3D%22100%25%22%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%3E%3Crect%20x%3D%22116%22%20y%3D%228%22%20width%3D%2298%22%20height%3D%2237%22%20rx%3D%228%22%20stroke%3D%22%2394a3b8%22%20fill%3D%22%2394a3b8%22%20fill-opacity%3D%22.13%22%3E%3C%2Frect%3E%3Ctext%20x%3D%22165%22%20y%3D%2231%22%20text-anchor%3D%22middle%22%20font-size%3D%2212%22%20fill%3D%22currentColor%22%20font-weight%3D%22600%22%3EPENDING%3C%2Ftext%3E%3Cpath%20d%3D%22M145%2045%20L76%20104%20M185%2045%20L253%20104%22%20fill%3D%22none%22%20stroke%3D%22%2364748b%22%20stroke-width%3D%221.5%22%3E%3C%2Fpath%3E%3Cpath%20d%3D%22M77%2096%20L76%20104%20L84%20101%20M245%20100%20L253%20104%20L252%2096%22%20fill%3D%22none%22%20stroke%3D%22%2364748b%22%20stroke-width%3D%221.5%22%3E%3C%2Fpath%3E%3Ctext%20x%3D%2274%22%20y%3D%2268%22%20font-size%3D%2210%22%20fill%3D%22currentColor%22%3EVerified%3C%2Ftext%3E%3Ctext%20x%3D%2274%22%20y%3D%2280%22%20font-size%3D%2210%22%20fill%3D%22currentColor%22%3Esuccess%3C%2Ftext%3E%3Ctext%20x%3D%22227%22%20y%3D%2268%22%20font-size%3D%2210%22%20fill%3D%22currentColor%22%3EVerified%3C%2Ftext%3E%3Ctext%20x%3D%22227%22%20y%3D%2280%22%20font-size%3D%2210%22%20fill%3D%22currentColor%22%3Efailure%3C%2Ftext%3E%3Crect%20x%3D%226%22%20y%3D%22107%22%20width%3D%22133%22%20height%3D%2242%22%20rx%3D%227%22%20stroke%3D%22%2316a34a%22%20fill%3D%22%2316a34a%22%20fill-opacity%3D%22.11%22%3E%3C%2Frect%3E%3Ctext%20x%3D%2272%22%20y%3D%22133%22%20text-anchor%3D%22middle%22%20font-size%3D%2212%22%20font-weight%3D%22600%22%20fill%3D%22currentColor%22%3ESUCCESS%3C%2Ftext%3E%3Crect%20x%3D%22191%22%20y%3D%22107%22%20width%3D%22133%22%20height%3D%2242%22%20rx%3D%227%22%20stroke%3D%22%23c97448%22%20fill%3D%22%23c97448%22%20fill-opacity%3D%22.11%22%3E%3C%2Frect%3E%3Ctext%20x%3D%22257%22%20y%3D%22133%22%20text-anchor%3D%22middle%22%20font-size%3D%2212%22%20font-weight%3D%22600%22%20fill%3D%22currentColor%22%3EFAILED%3C%2Ftext%3E%3Ctext%20x%3D%22165%22%20y%3D%22168%22%20text-anchor%3D%22middle%22%20font-size%3D%2210%22%20fill%3D%22currentColor%22%3ESimplified%20payment%20lifecycle%3C%2Ftext%3E%3C%2Fsvg%3E)

Điểm quan trọng nhất là **timeout hoặc mất kết nối không đồng nghĩa thanh toán thất bại**. Giao dịch có thể đã thành công tại cổng thanh toán nhưng callback chưa đến backend. Khi chưa xác minh được kết quả cuối cùng, hệ thống nên giữ trạng thái PENDING hoặc một trạng thái cần đối soát.

Các cổng thanh toán thực tế như Adyen sử dụng webhooks để đồng bộ những kết quả thanh toán bất đồng bộ và yêu cầu xử lý cả thông báo trùng lặp.

### 3. Verification nên kiểm thử những trường hợp nào?

| Test case | Input / Scenario | Expected result |
| --- | --- | --- |
| TC-PAY-01 | Gateway xác nhận thanh toán thành công | Payment → SUCCESS; booking được cập nhật theo chính sách |
| TC-PAY-02 | Gateway xác nhận thất bại | Payment → FAILED; booking không được đánh dấu đã thanh toán |
| TC-PAY-03 | Gateway chưa trả kết quả hoặc timeout | Payment vẫn PENDING, không phải SUCCESS |
| TC-PAY-04 | Gateway gửi cùng một callback thành công hai lần | Chỉ ghi nhận một kết quả thanh toán hợp lệ |
| TC-PAY-05 | Callback không vượt qua xác thực | Không cập nhật trạng thái thanh toán |
| TC-PAY-06 | Lỗi database khi cập nhật payment và booking | Không lưu trạng thái cập nhật dở dang |

Nếu F08 yêu cầu xác nhận booking sau khi thanh toán đặt cọc, nhóm nên cập nhật bản ghi payment và booking trong cùng một PostgreSQL transaction. Đây là quyết định thiết kế nhằm đáp ứng tính nhất quán dữ liệu.

### 4. Có nên thêm yêu cầu thời gian cập nhật không?

Bạn có thể đặt thêm tiêu chí:

> Verified payment results shall be reflected in the database within 5 seconds after being received by the application.

Như vậy, ngoài tính chính xác, NFR còn kiểm tra được độ trễ đồng bộ trạng thái. Cần hiểu rõ đây là 5 giây **kể từ khi backend nhận được kết quả hợp lệ**, không phải 5 giây kể từ khi người dùng thanh toán ở gateway. Thời gian gateway gửi callback nằm ngoài quyền kiểm soát trực tiếp của ứng dụng.

**Khuyến nghị:** Giữ NFR-15 ở mức Should, vì F08 trong PA1 cũng là Should-have. NFR này chỉ áp dụng khi nhóm triển khai thanh toán sandbox. Hãy giữ Business Rule về kết quả thanh toán ở phần nghiệp vụ, còn NFR-15 tập trung vào tính nhất quán, khả năng xử lý lỗi và thông báo trùng lặp.

Tiêu đề chat đề xuất: $Software Engineering$ - Reliability và Payment Status Consistency (26/10/2026)


---

## You

`25 of 34`

Hướng dẫn tôi viết phần 2.1 2.2 và 3.


---

## ChatGPT

`26 of 34`

Trong tài liệu **PA2 – Software Requirements Specification (SRS)** của BadminBookingHub, ba phần bạn cần viết là:

- **2.1. Purpose and Scope:** Mục đích của tài liệu SRS, phạm vi phần mềm và đối tượng đọc tài liệu.
- **2.2. Glossary:** Định nghĩa các thuật ngữ nghiệp vụ và kỹ thuật được sử dụng trong SRS.
- **3. Problem Statement:** Mô tả bối cảnh nghiệp vụ, các vấn đề hiện tại, mục tiêu, môi trường hoạt động và các ràng buộc của dự án.

Đây cũng là những nội dung được yêu cầu trực tiếp trong template PA2.

Tôi đề xuất giữ ba phần này tương đối ngắn, tận dụng nội dung đã thống nhất trong PA1, nhưng chuyển sang văn phong đặc tả yêu cầu thay vì trình bày một project proposal.

### 1. Hướng dẫn viết từng phần

#### 2.1. Purpose and Scope

Nên chia thành ba đoạn:

| Thành phần | Nội dung cần trả lời |
| --- | --- |
| Purpose | Tại sao viết SRS? Nó được sử dụng vào việc gì? |
| Scope | Phần mềm làm gì, không làm gì? |
| Intended Readers | Ai sẽ sử dụng tài liệu này? |

**Lưu ý:** Purpose ở đây chủ yếu là mục đích của *tài liệu SRS*, không phải mục tiêu kinh doanh của BadminBookingHub. Mục tiêu của hệ thống sẽ được giải thích sâu hơn trong phần 3.

#### 2.2. Glossary

Chỉ nên đưa vào glossary những thuật ngữ có thể gây hiểu nhầm hoặc cần được định nghĩa thống nhất giữa BA, Developer và Tester.

Chẳng hạn, *Booking*, *Time Slot*, *Walk-in Booking*, *No-show*, *Advance Booking Window* và *Cancellation Deadline* đều cần được hiểu thống nhất trước khi viết Business Rules hoặc Use Case Specifications.

Không cần giải thích các thuật ngữ phổ thông như Web Application hoặc Database nếu chúng không gây ra sự mơ hồ.

#### 3. Problem Statement

Theo template PA2, phần này phải phát triển từ Preliminary Problem Statement của PA1 và bao gồm đủ năm nội dung.

| Nội dung | Câu hỏi cần trả lời |
| --- | --- |
| Business Context | Hiện nay sân cầu lông được quản lý như thế nào? |
| Current Problems | Người chơi, nhân viên và chủ sân gặp khó khăn gì? |
| Project Goals | Hệ thống dự kiến giải quyết những vấn đề nào? |
| Operating Environment | Ai sử dụng, trên thiết bị nào, hệ thống hoạt động ở đâu? |
| Constraints | Những giới hạn về thời gian, nhân lực, công nghệ và phạm vi là gì? |

Tôi khuyên giữ các tiêu đề con này. Giảng viên sẽ dễ đối chiếu nội dung của nhóm với rubric PA2.

---

### 2. Bản mẫu tiếng Anh cho BadminBookingHub

Bản dưới đây được viết theo các quyết định trong PA1, đặc biệt là phạm vi F01–F13, các nhóm stakeholders và kiến trúc dự kiến. Những tính năng Should/Could được mô tả là tùy chọn, không phải cam kết phải triển khai.

Writing

### 2. Introduction

#### 2.1. Purpose and Scope

**Purpose**

This Software Requirements Specification (SRS) defines the functional, non-functional, and domain requirements of BadminBookingHub, a web-based badminton court booking and management system. It provides a common understanding of the system requirements and serves as a reference for system design, implementation, testing, and validation.

**Scope**

BadminBookingHub allows players to search for available badminton courts, view prices, make and cancel bookings, and manage their reservations. It also enables court owners and staff to manage court information, booking schedules, pricing policies, and daily front-desk operations.

The system focuses on seven Must-have features: user authentication, resource catalog, court booking and cancellation, availability calendar, booking rules, court management, and front-desk operations.

Optional features include deposit payments through a sandbox payment gateway, booking history management, email notifications, revenue reporting, and court reviews.

The system excludes native mobile applications, real payment processing, cash payments, multi-branch management, other sports, tax management, chat, recurring weekly bookings, and food and drink ordering.

**Intended Readers**

This document is intended for the project team, including the project manager, business analyst, developers, designer, and tester, as well as the course instructors and teaching assistants who review and evaluate the project.

#### 2.2. Glossary

| Term | Definition |
| --- | --- |
| SRS | Software Requirements Specification; a document defining the requirements that a software system must satisfy. |
| FR | Functional Requirement; a specification of a function or behavior the system must provide. |
| NFR | Non-Functional Requirement; a specification of a quality attribute or constraint the system must satisfy. |
| Business Rule (BR) | A policy or constraint governing how business operations must be performed. |
| Use Case (UC) | A description of interactions between an actor and the system to achieve a particular goal. |
| Player | A registered user who searches for courts and manages personal bookings. |
| Staff | A court employee responsible for daily schedules, check-ins, no-shows, and walk-in bookings. |
| Admin | A court owner or authorized administrator who manages courts, prices, accounts, and booking policies. |
| Court | A badminton playing area available for reservation. |
| Booking | A reservation of a particular court for a specified time interval. |
| Time Slot | A defined period during which a court can be booked. |
| Availability | The status indicating whether a court can be booked for a particular time interval. |
| Overlapping Booking | Two or more bookings assigned to the same court with intersecting time intervals. |
| Peak Hours | Periods of high court demand that may have different booking prices. |
| Booking Policy | Rules governing reservations, including booking limits and cancellation restrictions. |
| Advance Booking Window | The maximum period before the playing date during which a reservation can be made. |
| Cancellation Deadline | The latest permitted time for cancelling a booking before its scheduled start. |
| Check-in | The process of recording a player's arrival for a scheduled booking. |
| No-show | A booking for which the player fails to arrive within the permitted check-in period. |
| Walk-in Booking | A reservation created by staff for a customer who arrives without an existing booking. |
| Deposit | An advance payment made to secure a booking, if the optional payment feature is implemented. |
| Sandbox Payment | A simulated payment performed in a test environment without transferring real money. |
| MoSCoW | A requirements prioritization method: Must-have, Should-have, Could-have, and Won't-have. |

### 3. Problem Statement

#### Business Context

Many small and medium-sized badminton venues manage reservations through phone calls, Zalo, Facebook, or manual records such as notebooks and spreadsheets. Court availability, pricing, and booking information are often maintained separately, making reservation management inefficient.

#### Current Problems

Players must contact venues individually to check court availability and prices, especially during peak hours. This process is time-consuming and may provide outdated information.

Court owners and staff face difficulties maintaining accurate schedules, calculating prices, and coordinating reservations. Manual management increases the risk of overlapping bookings, pricing errors, and inconsistent records. Additionally, customers who fail to attend their reservations may leave courts unused.

#### Project Goals

BadminBookingHub aims to centralize badminton court booking and management in a single web application.

The system will allow players to find available courts and make reservations conveniently, while helping staff and court owners manage schedules, prices, booking policies, and customer attendance.

It will also enforce booking restrictions and prevent overlapping confirmed reservations, improving booking accuracy and reducing manual work.

#### Operating Environment

BadminBookingHub is a responsive web application accessible through modern desktop and mobile web browsers.

The frontend uses React and TypeScript, while the backend uses Node.js, Express, and TypeScript, with PostgreSQL for data storage.

The application is planned for deployment using Docker containers on a single AWS EC2 instance. GitHub Actions supports automated testing and deployment.

#### Design and Implementation Constraints

The project is developed by a five-member student team within the course schedule, following the Waterfall process with V-model-based test planning.

Development prioritizes the seven Must-have features. Optional features will be implemented only if sufficient time and resources remain.

The system must use TypeScript for both frontend and backend development and PostgreSQL for data storage. The team must rely on free or low-cost development and deployment resources.

The application is limited to badminton court booking and management. Advanced features and long-term production operations are outside the project scope.

### 3. Những điểm cần chú ý trước khi nộp

**Thứ nhất, phần 2.1 và phần 3 không nên bị trùng nội dung.** Phần 2.1 giới thiệu phạm vi ở mức tổng quan, còn phần 3 giải thích lý do dự án tồn tại và những khó khăn cụ thể mà nó giải quyết. Vì thế, việc nhắc lại tên các tính năng là chấp nhận được, nhưng không nên sao chép toàn bộ danh sách features từ PA1.

**Thứ hai, Glossary phải nhất quán với Business Rules.** Ví dụ, định nghĩa *No-show* hiện chưa xác định cụ thể thời gian check-in trễ bao lâu thì được coi là không đến. Đó là tham số nghiệp vụ cần được nhóm thống nhất ở phần Domain Requirements and Business Rules, chứ không nên tự đặt một giá trị trong Glossary.

**Thứ ba, cần làm rõ phạm vi triển khai.** PA1 có đề cập Docker local deployment và phương án cloud, nhưng phần Hardware and Operating Environment đã chọn EC2 làm môi trường triển khai dự kiến; kế hoạch PA5 còn yêu cầu public URL. Vì vậy, bản mẫu trên viết là *planned for deployment*, thay vì khẳng định hệ thống đã được triển khai.

**Thứ tư, phần 3 nên tránh đưa ra những khẳng định chưa có dữ liệu kiểm chứng.** Chẳng hạn, không nên viết BadminBookingHub giúp tăng doanh thu 30% hay giảm thời gian đặt sân 50% khi nhóm chưa có kết quả khảo sát hoặc thử nghiệm thực tế.

**Cuối cùng, tôi đề xuất giữ phần 2.1 khoảng 200–250 từ, phần 2.2 khoảng 15–25 thuật ngữ và phần 3 khoảng 250–350 từ.** Đây là mức độ chi tiết hợp lý vì các phần FR, NFR, Business Rules và Use Case Specifications phía sau mới là trọng tâm của SRS.

Tiêu đề chat đề xuất: $Software Engineering$ - Viết Introduction và Problem Statement PA2 (26/10/2026)


---

## You

`27 of 34`

Tôi muốn một phần NFR về quy trình CICD của dự án, và nêu lại cho tôi NFR về testing


---

## ChatGPT

`28 of 34`

Đối với BadminBookingHub, tôi đề xuất bổ sung **NFR-11 — CI/CD Automation** và giữ **NFR-12 — Automated Test Coverage** như đã thảo luận.

Trong PA1, nhóm đã lựa chọn GitHub Actions cho CI/CD, Docker để đóng gói ứng dụng, Amazon ECR để lưu trữ images và EC2 để triển khai. PA5 cũng đã quy định mức tối thiểu **70% statement coverage cho backend service layer**.

### 1. Hai NFR đề xuất cho PA2

Writing

| ID | Category | Requirement (Measurable) | How It Will Be Verified |
| --- | --- | --- | --- |
| NFR-11 | Maintainability — CI/CD Automation | Every pull request to the main branch shall automatically trigger code quality checks, automated tests, and production builds. Deployment to the demo environment shall occur only after all required CI checks pass. | Use GitHub Actions to test successful and failing pull requests. Verify that failed checks block merging and prevent deployment. |
| NFR-12 | Testability — Test Coverage | Automated unit tests shall achieve at least 70% statement coverage of the backend service layer. | Generate a test coverage report using Vitest and verify that statement coverage meets the 70% threshold. |

### 2. Có nên bổ sung yêu cầu CD riêng?

Nếu nhóm muốn thể hiện rõ cả Continuous Deployment, tôi khuyên tách NFR-11 thành hai yêu cầu độc lập:

| ID | Requirement |
| --- | --- |
| NFR-11A — Continuous Integration | Every pull request targeting the main branch shall automatically run linting, type checking, automated tests, and production builds. Merging shall be blocked if any required check fails. |
| NFR-11B — Continuous Deployment | Every approved merge to the main branch shall automatically deploy the new application version to the designated demo environment, provided all required CI checks pass. |

Verification cho NFR-11B: Merge một pull request hợp lệ, kiểm tra GitHub Actions đã build và push Docker images lên Amazon ECR, triển khai lên EC2 và xác nhận ứng dụng hoạt động với phiên bản mới.

Tách như vậy giúp mỗi requirement có một trách nhiệm riêng và dễ kiểm thử hơn.

### 3. Phân biệt Test Coverage và Test Success Rate

Đây là hai chỉ số khác nhau và bạn không nên nhầm lẫn:

| Metric | Ý nghĩa | Yêu cầu PA5 |
| --- | --- | --- |
| Statement Coverage | Tỷ lệ câu lệnh trong backend service layer được thực thi bởi unit tests | ≥ 70% |
| Test Execution Rate | Tỷ lệ Must-have test cases được thực hiện | 100% |
| Test Pass Rate | Tỷ lệ test cases đã thực hiện có kết quả Pass | ≥ 90% |
| Critical/High Defects | Số lỗi mức nghiêm trọng cao chưa giải quyết | 0 |

Ví dụ, đạt 80% coverage không chứng minh rằng 80% chức năng hoạt động đúng. Coverage chỉ đo mức độ mã nguồn được thực thi trong quá trình kiểm thử, không đo trực tiếp tính chính xác của hệ thống.

**Khuyến nghị:** NFR-12 chỉ nên giữ yêu cầu về automated unit-test coverage. Các chỉ số test execution, pass rate và defect count nên đặt trong phần Test Plan hoặc PA5 Exit Criteria để tránh trùng lặp.

Một lưu ý về phân loại: CI/CD và test coverage chủ yếu là **process constraints / development quality requirements**, không phải thuộc tính mà người dùng cuối quan sát trực tiếp. Nếu template PA2 cho phép, bạn có thể đặt chúng trong nhóm *Development and Quality Assurance Constraints*. Nếu bắt buộc đưa vào bảng NFR, cách trình bày ở trên vẫn phù hợp, miễn là tiêu chí kiểm chứng rõ ràng.

Tiêu đề chat đề xuất: $Software Engineering$ - NFR cho CI/CD và Testing (27/10/2026)


---

## You

`29 of 34`

"Court search and availability APIs shall achieve p95 response time below 2 seconds and error rate below 1% under 20 concurrent virtual users and 5,000 booking records." Chức năng này có khả thi với một instance EC2 medium không và thông 5000 là số data đã có sẵn trong database đúng không hãy làm rõ, tại sao số records có sẵn trong database lại ảnh hưởng đến hiệu năng


---

## ChatGPT

`30 of 34`

**Có, NFR-01 tương đối khả thi trên EC2 t3.medium với BadminBookingHub.** Đây là mức tải hợp lý để thử nghiệm một ứng dụng đặt sân quy mô nhỏ. Tuy nhiên, chưa thể bảo đảm đạt p95 dưới 2 giây nếu chưa benchmark trên hệ thống thực tế.

Và bạn hiểu đúng: **5.000 booking records là 5.000 bản ghi đặt sân đã tồn tại trong PostgreSQL trước khi bắt đầu chạy load test**, không phải 5.000 requests mà k6 phải gửi.

#### 1. EC2 t3.medium có đáp ứng được không?

Theo AWS, t3.medium có cấu hình:

| Tài nguyên | Cấu hình |
| --- | --- |
| CPU | 2 vCPU |
| RAM | 4 GiB |
| Baseline CPU | 20% mỗi vCPU |
| CPU credits | 24 credits/giờ |
| Storage | EBS, tùy dung lượng cấp phát |

Với BadminBookingHub, instance này dự kiến chạy NGINX, Express API, React frontend và PostgreSQL. Nếu frontend được build thành static files và phục vụ bằng NGINX thì phần lớn công việc xử lý động nằm ở Express và PostgreSQL.

Tôi đánh giá như sau:

| Yêu cầu | Đánh giá |
| --- | --- |
| 20 virtual users | Phù hợp với quy mô demo |
| 5.000 booking records | Bộ dữ liệu nhỏ đối với PostgreSQL |
| p95 dưới 2 giây | Mục tiêu hợp lý, cần kiểm chứng |
| Error rate dưới 1% | Hợp lý nếu API và môi trường hoạt động ổn định |
| Chạy load test liên tục nhiều giờ | Cần chú ý CPU credits và tài nguyên |

Điểm cần chú ý nhất là t3.medium thuộc nhóm **burstable instances**. Nó có thể sử dụng CPU vượt baseline trong những khoảng thời gian nhất định, nhưng hiệu năng và chi phí còn phụ thuộc vào chế độ CPU credits.

Vì thế, test 5 phút có thể đạt yêu cầu, nhưng điều đó không chứng minh server chịu được cùng mức tải trong nhiều giờ.

#### 2. Vì sao 5.000 records trong database ảnh hưởng đến hiệu năng?

Giả sử database có những bảng sau:

Plain text`courts
├── court_id
├── name
└── location

bookings
├── booking_id
├── court_id
├── start_time
├── end_time
└── status`

Người dùng tìm sân còn trống từ 17:00 đến 18:00 ngày 15/12/2026.

Để trả kết quả, backend phải tìm những sân không có booking đang hoạt động trùng với khoảng thời gian yêu cầu.

Ví dụ:

SQL

```
SELECT c.*
FROM courts c
WHERE NOT EXISTS (
    SELECT 1
    FROM bookings b
    WHERE b.court_id = c.court_id
      AND b.status = 'confirmed'
      AND b.start_time < :requested_end
      AND b.end_time > :requested_start
);
```

Đây là câu SQL minh họa, chưa phải truy vấn chính thức của dự án.

##### Trường hợp không có index phù hợp

Database có thể phải đọc nhiều bản ghi booking để tìm các booking bị trùng thời gian.

- Với 100 records, công việc có thể rất ít.
- Với 5.000 records, số bản ghi cần xem xét có thể nhiều hơn.
- Với 1.000.000 records, truy vấn thiếu index phù hợp có thể trở nên đắt đỏ.

##### Trường hợp có index phù hợp

PostgreSQL có thể sử dụng index để giảm số bản ghi cần kiểm tra, tùy điều kiện truy vấn và kế hoạch thực thi.

Minh họa cách PostgreSQL tìm dữ liệu

Sequential Scan

Kiểm tra nhiều bản ghi

Index-assisted Scan

svg![Image generated by the assistant](data:image/svg+xml;utf8,%3Csvg%20viewBox%3D%220%200%20130%2061%22%20width%3D%22100%25%22%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%3E%3Crect%20x%3D%2248%22%20y%3D%222%22%20width%3D%2234%22%20height%3D%2216%22%20rx%3D%223%22%20fill%3D%22%2364748b%22%20fill-opacity%3D%22.7%22%3E%3C%2Frect%3E%3Cpath%20d%3D%22M65%2018%20V26%20M65%2026%20H24%20V34%20M65%2026%20H104%20V34%22%20stroke%3D%22currentColor%22%20stroke-width%3D%221.3%22%20fill%3D%22none%22%3E%3C%2Fpath%3E%3Crect%20x%3D%227%22%20y%3D%2234%22%20width%3D%2234%22%20height%3D%2214%22%20rx%3D%223%22%20fill%3D%22%2364748b%22%20fill-opacity%3D%22.35%22%3E%3C%2Frect%3E%3Crect%20x%3D%2287%22%20y%3D%2234%22%20width%3D%2234%22%20height%3D%2214%22%20rx%3D%223%22%20fill%3D%22%2316a34a%22%20fill-opacity%3D%22.6%22%3E%3C%2Frect%3E%3Ctext%20x%3D%2265%22%20y%3D%2259%22%20text-anchor%3D%22middle%22%20font-size%3D%229%22%20fill%3D%22currentColor%22%3ESelected%20records%3C%2Ftext%3E%3C%2Fsvg%3E)

Thu hẹp phạm vi tìm kiếm

Sơ đồ khái niệm, không biểu diễn chính xác một PostgreSQL execution plan.

PostgreSQL lựa chọn kế hoạch thực thi dựa trên các thống kê, kích thước bảng và chi phí ước tính. Với bảng nhỏ, PostgreSQL thậm chí có thể chọn Sequential Scan dù đã có index, vì đọc tuần tự có thể rẻ hơn.

Do đó, số lượng bản ghi ảnh hưởng đến hiệu năng, nhưng **không có nghĩa gấp đôi records thì response time cũng tăng gấp đôi**.

Các yếu tố khác cũng tác động đến performance:

- Số lượng records phù hợp với điều kiện lọc.
- Indexes trên court_id, thời gian và trạng thái booking.
- JOIN, sorting, pagination và số lượng records trả về.
- Mức độ dữ liệu đã được cache trong RAM.
- Số truy vấn mà backend thực hiện cho mỗi API request.
- Tải đồng thời lên CPU, PostgreSQL connections và disk I/O.

Với chỉ 5.000 booking records, nhiều truy vấn được thiết kế hợp lý có thể hoàn thành rất nhanh. Mục tiêu 2 giây chủ yếu để đảm bảo ứng dụng vẫn phản hồi tốt khi có tải, chứ không phải vì PostgreSQL cần đến 2 giây để tìm trong 5.000 bản ghi.

#### 3. Phân biệt 20 Virtual Users và 5.000 Booking Records

Hai con số này đo hai khía cạnh hoàn toàn khác nhau của hệ thống.

### 20 VUs

Concurrent virtual users

Tạo tải lên API trong thời gian kiểm thử.

### 5.000

Existing booking records

Dữ liệu có sẵn trong PostgreSQL để API truy vấn.

Trong k6, 20 VUs là 20 người dùng giả lập thực hiện các vòng thao tác. Không nhất thiết có đúng 20 HTTP requests cùng đang xử lý tại mọi thời điểm. Số requests/second phụ thuộc vào thời gian phản hồi, thời gian nghỉ và kịch bản mô phỏng.

Bạn có thể tạo 5.000 booking records trước khi chạy test bằng một seed script, chẳng hạn phân bổ trên 50 sân, nhiều ngày, nhiều khung giờ và những trạng thái khác nhau.

Dữ liệu cần đủ thực tế để tránh benchmark một database toàn những booking cũ không liên quan hoặc tất cả booking tập trung vào một sân.

#### 4. Làm sao kiểm chứng ảnh hưởng của số records?

Bạn có thể thực hiện một thí nghiệm khá hay để đưa vào PA5:

| Thí nghiệm | Số booking records | VUs | Metrics |
| --- | --- | --- | --- |
| A | 100 | 20 | p95, error rate |
| B | 1.000 | 20 | p95, error rate |
| C | 5.000 | 20 | p95, error rate |
| D (mở rộng) | 50.000 | 20 | p95, error rate |

Giữ nguyên cấu hình EC2, API, loại truy vấn và thời lượng test. Dùng các dữ liệu được tạo theo cùng một quy luật phân bố. Sau đó so sánh kết quả để xem performance có suy giảm khi database lớn hơn không.

Ngoài k6, hãy sử dụng PostgreSQL:

SQL

```
SELECT COUNT(*) FROM bookings;
```

Để xem số records có trong database, và:

SQL

```
EXPLAIN (ANALYZE, BUFFERS)
SELECT *
FROM bookings
WHERE court_id = 1
  AND status = 'confirmed'
  AND start_time < TIMESTAMP '2026-12-15 18:00:00'
  AND end_time > TIMESTAMP '2026-12-15 17:00:00';
```

Để kiểm tra thời gian thực thi truy vấn, số rows được xử lý, số buffers sử dụng và việc PostgreSQL lựa chọn Sequential Scan hay Index Scan.

Cần nhớ rằng EXPLAIN ANALYZE đo ở tầng database, còn k6 đo response time ở tầng HTTP. Kết quả của chúng sẽ không giống nhau vì HTTP response còn phụ thuộc Express, network, serialization và các bước xử lý khác.

#### 5. NFR-01 nên viết lại thế nào cho rõ ràng?

Tôi đề xuất sửa một chút để làm rõ 5.000 records là dữ liệu đã tồn tại trước khi test, đồng thời bổ sung thời lượng kiểm thử.

> **NFR-01 — Court Search Performance**
>
> The court search and availability APIs shall achieve a p95 response time below 2 seconds and an HTTP error rate below 1% under 20 concurrent virtual users, with at least 5,000 pre-seeded booking records in the database.

**Verification Method:**

> Execute a 5-minute load test using k6 against the deployed application. Measure p95 HTTP response duration and error rate for each API endpoint separately.

Đối với phương án này, tôi đề xuất nhóm thống nhất thêm điều kiện 20 VUs thực hiện các thao tác tìm kiếm theo tập ngày, sân và khung giờ cố định, dùng cả những trường hợp có và không có sân trống. Kết quả chỉ Pass khi cả hai endpoints đạt thresholds. k6 hỗ trợ tự động hóa các thresholds này.

**Kết luận:** Bạn có thể giữ nguyên ngưỡng 20 VUs, 5.000 booking records và p95 dưới 2 giây cho EC2 t3.medium. Nó đủ thực tế đối với phạm vi demo và không đòi hỏi hệ thống Big Data hay distributed database. Nếu muốn làm phần Performance Testing thuyết phục hơn, hãy bổ sung thí nghiệm với nhiều kích thước database và dùng EXPLAIN ANALYZE để giải thích nguyên nhân thay đổi hiệu năng, thay vì chỉ báo cáo một giá trị p95.

Tiêu đề chat đề xuất: $Software Engineering$ - NFR Performance và Database Load Testing (28/10/2026)


---

## You

`31 of 34`

Review giúp tôi phần Non-functional requirements


---

## ChatGPT

`32 of 34`

### Review Non-Functional Requirements — BadminBookingHub (PA2)

Tôi đã đọc phần **5.2 — Non-Functional Requirements** trong tài liệu PA2 - 08.docx updated.md và đối chiếu với Functional Requirements (FR) và Business Rules (BR) trong cùng tài liệu.

Hiện tại, nhóm có **15 NFR**, bao gồm Performance, Reliability, Security, Usability, Maintainability và các ràng buộc về CI/CD.

#### 1. Đánh giá tổng quan

**Đánh giá: 7,5/10 — Khá tốt, nhưng nên chỉnh sửa trước khi chốt PA2.**

Đây là đánh giá chất lượng đặc tả của tôi, không phải điểm chấm chính thức theo rubric của môn học.

| Tiêu chí | Đánh giá | Nhận xét |
| --- | --- | --- |
| Completeness | Khá | Bao phủ nhiều quality attributes quan trọng nhưng thiếu tính nhất quán giao dịch và thanh toán |
| Clarity | Khá | Phần lớn yêu cầu rõ ràng; một số câu còn mơ hồ |
| Measurability | Tốt | Performance, responsiveness và test coverage có metric cụ thể |
| Verifiability | Khá | Có phương pháp kiểm thử nhưng một số thiếu điều kiện Pass/Fail |
| Consistency | Cần cải thiện | NFR-12 trùng với FR-09 và Business Rules |
| Feasibility | Khá | Phần lớn khả thi với đồ án demo, nhưng một số cam kết cần cân nhắc |
| Classification | Cần cải thiện | NFR-07, NFR-13 và NFR-15 chưa được phân loại phù hợp |

##### Bốn vấn đề quan trọng nhất

**1. NFR-12 bị trùng với FR-09 và BR-03/BR-04.**

NFR-12 yêu cầu khi 20 người đặt đồng thời cùng một khung giờ thì chính xác một booking được xác nhận.

Tuy nhiên, FR-09 đã yêu cầu hệ thống ngăn double booking, kể cả với các request đồng thời. BR-03 và BR-04 cũng quy định vấn đề tương tự.

Đây là vấn đề nghiêm trọng nhất cần sửa vì nó tạo ra yêu cầu trùng lặp và có thể gây mâu thuẫn khi tính năng thanh toán được triển khai.

**2. Thiếu yêu cầu về tính nhất quán khi cập nhật database.**

Hệ thống có các nghiệp vụ booking, cancellation, check-in và payment. Tôi khuyến nghị bổ sung NFR về transaction atomicity để bảo đảm lỗi trong quá trình xử lý không tạo ra dữ liệu cập nhật dở dang.

**3. NFR-14 về CI/CD chưa quy định rõ Continuous Deployment.**

Yêu cầu hiện tại nói chỉ những thay đổi merge vào main mới được triển khai, nhưng không nói rõ deployment có tự động diễn ra sau khi CI thành công hay không.

**4. NFR-15 đang được phân loại là External.**

NFR-15 thực chất là yêu cầu **Security — Privacy / Confidentiality**, vì nó bảo vệ thông tin cá nhân của Player.

---

#### 2. Review chi tiết 15 NFR

##### 2.1. Performance & Reliability

| ID | Đánh giá | Nhận xét và đề xuất |
| --- | --- | --- |
| NFR-01 | ✅ Tốt | Có workload, dataset, p95, error rate và thời lượng kiểm thử. Nên yêu cầu đo riêng từng API và ghi rõ điều kiện của dữ liệu seed. |
| NFR-02 | ⚠️ Sửa nhẹ | Cần giải thích cách tạo các booking slots không xung đột để 20 VUs liên tục tạo booking mà không hết dữ liệu hợp lệ. |
| NFR-03 | ⚠️ Sửa nhẹ | Cần quy định thời điểm bắt đầu tính 5 giây và điều kiện kết nối của người dùng. |
| NFR-12 | ❌ Nên thay thế | Trùng FR-09, BR-03, BR-04 và có thể xung đột với quy trình Pending payment. |

**NFR-01 — Court Search Performance**

Tôi đánh giá yêu cầu này đã khá hoàn chỉnh:

> The court search and availability APIs shall achieve a p95 response time below 2 seconds and an HTTP error rate below 1% under 20 concurrent virtual users, with at least 5,000 pre-seeded booking records in the database.

Có thể giữ nguyên.

Tuy nhiên, verification hiện chỉ nói đo p95 latency và error rate bằng k6. Bạn nên bổ sung điều kiện **cả hai API đều phải đạt ngưỡng**.

Ví dụ, nếu Search API có p95 = 1,2 giây nhưng Availability API có p95 = 2,4 giây thì NFR-01 phải được đánh giá là Failed.

**NFR-02 — Booking Performance**

Vấn đề chính không nằm ở requirement statement mà ở cách thiết kế load test.

Nếu 20 VUs liên tục đặt cùng một sân và khung giờ, các request tiếp theo sẽ bị từ chối do quy tắc chống double booking.

Do đó, cần chuẩn bị đủ các time slots hợp lệ, không xung đột, đồng thời xác định cách reset dữ liệu giữa các lần kiểm thử.

Verification nên viết cụ thể hơn:

> Run a 5-minute k6 load test using non-conflicting booking slots; verify p95 response time, HTTP error rate, and persisted booking results.

**NFR-03 — Booking Availability Freshness**

Hiện tại:

> Booking availability changes shall appear to other users within 5 seconds without manual page reload.

Vấn đề là chưa rõ 5 giây được tính từ lúc nào.

Tôi đề xuất:

> Confirmed booking and cancellation changes shall appear in other users' active availability calendars within 5 seconds after the database transaction commits, under normal network conditions.

Cách này giúp Tester biết chính xác phải bắt đầu và kết thúc phép đo ở đâu.

Ngoài ra, không cần quy định phải sử dụng WebSocket. HTTP polling vẫn có thể đáp ứng yêu cầu này.

##### 2.2. Security

| ID | Đánh giá | Nhận xét và đề xuất |
| --- | --- | --- |
| NFR-04 | ⚠️ Sửa nhẹ | Cần làm rõ cửa sổ tính số lần đăng nhập sai và thời điểm bắt đầu khóa. |
| NFR-05 | ✅ Tốt | Phạm vi HTTPS rõ ràng, nhưng verification nên kiểm tra cả khả năng truy cập trực tiếp backend. |
| NFR-06 | ✅ Tốt | bcrypt với cost ≥ 10 là lựa chọn đã được nhóm xác định. Verification cần kiểm tra cả cost thực tế trong hash. |
| NFR-15 | ⚠️ Sai category | Nên đổi từ External thành Security — Privacy. |

**NFR-04 — Login Rate Limiting**

Hiện tại:

> The system shall temporarily throttle login attempts after 10 failed attempts per account within 15 minutes, further login attempts for that account are rejected with HTTP 429 for 15 min.

Câu này có vấn đề ngữ pháp và chưa diễn đạt rõ thời điểm hạn chế đăng nhập.

Tôi đề xuất:

> After 10 failed login attempts for an account within a rolling 15-minute window, the system shall reject further login attempts for that account with HTTP 429 for 15 minutes.

Tuy nhiên, có một rủi ro cần cân nhắc: kẻ tấn công có thể cố tình nhập sai mật khẩu để khóa tài khoản của người khác. Nhóm cần quyết định xem đây là yêu cầu Must-have hay Should-have.

**NFR-05 — HTTPS**

Requirement hiện tại hợp lý.

Tuy nhiên, nếu backend Express vẫn được công khai qua một cổng riêng, chẳng hạn 3000, người dùng có thể bỏ qua NGINX và truy cập HTTP trực tiếp.

Vì vậy, verification nên bổ sung:

> Verify HTTP redirects, API rejection, TLS certificate validity, and that backend services cannot be accessed directly through public HTTP endpoints.

Điều này giúp chứng minh HTTPS thực sự được thực thi thay vì chỉ cấu hình ở frontend.

**NFR-06 — Password Hashing**

Requirement hiện tại:

> User passwords shall be stored using bcrypt (cost ≥ 10) to salt and hash the passwords cryptographically. Plaintext passwords shall never be stored.

Tôi đề xuất viết tự nhiên hơn:

> All user passwords shall be stored as salted bcrypt hashes with a cost factor of at least 10. Plaintext passwords shall never be persisted.

Verification cần kiểm tra bốn điểm: thuật toán bcrypt, cost factor, salt riêng giữa các hashes và khả năng xác minh đúng/sai mật khẩu.

Ngoài ra, khi thiết kế authentication, nhóm cần xử lý giới hạn đầu vào 72 bytes của bcrypt để tránh việc phần mật khẩu vượt giới hạn bị bỏ qua.

##### 2.3. Usability & Portability

| ID | Đánh giá | Nhận xét và đề xuất |
| --- | --- | --- |
| NFR-07 | ⚠️ Sai category | Chuyển thành Portability — Adaptability. |
| NFR-08 | ✅ Tốt | Nên bổ sung ngoại lệ horizontal scrolling cho calendar và tables. |
| NFR-09 | ✅ Tốt | Yêu cầu cụ thể; cần kiểm thử lỗi format và lỗi business-rule validation. |
| NFR-10 | ⚠️ Sửa nhẹ | Cần phân biệt duy trì lựa chọn ngôn ngữ và duy trì dữ liệu form khi reload trang. |
| NFR-11 | ⚠️ Sửa nhẹ | Cần xác định điểm bắt đầu/kết thúc thao tác và điều kiện thành công. |

**NFR-07 — Browser Compatibility**

Yêu cầu hiện tại đã xác định ba browser engines:

- Blink — Chromium
- Gecko — Firefox
- WebKit — Safari

Tuy nhiên, category hiện được ghi là Usability. Tôi khuyến nghị đổi thành:

**Portability — Adaptability**

Đây là cách phân loại phù hợp hơn nếu nhóm dùng ISO/IEC 25010:2011.

Verification bằng Playwright trên Chromium, Firefox và WebKit là hợp lý. Cần lưu ý kiểm thử Playwright WebKit chưa đủ để khẳng định hỗ trợ tất cả phiên bản Safari thực tế.

**NFR-08 — Responsive Design**

Yêu cầu về chiều rộng 320–1920 CSS pixels là hợp lý.

Tuy nhiên, phần Availability Calendar có thể cần horizontal scrolling.

Bạn nên bổ sung:

> Independently scrollable calendars and data tables are exempt from the page-level horizontal scrolling restriction.

Điều này tránh việc nhóm vô tình đặt ra một yêu cầu khó đáp ứng đối với bảng dữ liệu nhiều cột.

**NFR-09 — Input Validation Feedback**

Yêu cầu hiện tại khá tốt vì đã chỉ rõ thông báo lỗi phải xuất hiện gần trường nhập và giữ lại những giá trị hợp lệ.

Tuy nhiên, không phải mọi lỗi đều có thể gắn với một trường.

Ví dụ, lỗi một khung giờ vừa được người khác đặt không nhất thiết liên quan đến riêng trường ngày hay giờ.

Tôi khuyến nghị bổ sung khả năng hiển thị lỗi ở cấp form cho những trường hợp không thể gắn lỗi với một field cụ thể.

**NFR-10 — Multilingual UI**

Điểm cần làm rõ là hai hành vi:

1. Lựa chọn ngôn ngữ được lưu sau khi chuyển trang hoặc reload.
2. Khi chuyển ngôn ngữ, dữ liệu người dùng đang nhập không bị mất.

Yêu cầu hiện tại có thể được hiểu là dữ liệu form cũng phải được giữ lại sau khi reload trang. Đây là một cam kết lớn hơn mức cần thiết.

Tôi đề xuất:

> All system-generated UI text shall support English and Vietnamese. Language preferences shall persist across navigation and reloads, and switching languages shall not clear user-entered data.

Ngoài ra, tôi chưa thấy FR riêng cho chức năng chuyển đổi ngôn ngữ trong danh sách FR-01 đến FR-40.

Nên bổ sung một FR liên quan đến việc người dùng có thể chuyển ngôn ngữ từ mọi trang, còn NFR-10 đảm bảo chất lượng và tính nhất quán của tính năng đó.

**NFR-11 — Booking Usability**

Hiện tại yêu cầu ít nhất 80% người dùng lần đầu hoàn tất booking trong 2 phút.

Với 5 người tham gia thử nghiệm, ngưỡng 80% tương đương **ít nhất 4/5 người hoàn thành thành công**.

Nhưng cần định nghĩa rõ:

- Người dùng đã đăng nhập trước khi bắt đầu?
- Thời gian được tính từ màn hình tìm kiếm sân hay màn hình đặt sân?
- Hoàn thành khi booking được tạo hay khi xuất hiện thông báo xác nhận?

Đây là những chi tiết cần bổ sung vào Test Procedure. Không nhất thiết phải làm câu NFR dài hơn.

##### 2.4. Maintainability & CI/CD

| ID | Đánh giá | Nhận xét và đề xuất |
| --- | --- | --- |
| NFR-13 | ⚠️ Sửa category | Nên dùng Testability hoặc Development Quality Assurance. |
| NFR-14 | ⚠️ Cần làm rõ | Thiếu điều kiện tự động triển khai sau khi merge thành công. |

**NFR-13 — Automated Test Coverage**

Ngưỡng 70% statement coverage phù hợp với kế hoạch PA5 của nhóm.

Tuy nhiên, requirement này thuộc Testability hoặc Development Quality Assurance hơn là Maintainability thuần túy.

Verification hiện tại cũng chưa nói coverage không đạt thì CI phải làm gì.

Tôi đề xuất:

> Generate a Vitest coverage report during CI and fail the required test check if backend service-layer statement coverage is below 70%.

**NFR-14 — CI/CD**

Yêu cầu hiện tại:

> Every pull request to main runs lint, tests and build, and cannot be merged unless all pass; only merges to main are deployed to the demo environment.

Tôi đề xuất viết rõ hơn:

> Every pull request targeting main shall automatically run linting, automated tests, and production builds. Merging shall be blocked if any required check fails. Successful merges to main shall trigger automated deployment to the demo environment.

Verification:

> Test successful and failing pull requests, verify branch protection rules, and confirm automatic deployment after a successful merge.

Nên đổi category thành **Development Process — CI/CD**.

---

#### 3. Hai yêu cầu quan trọng còn thiếu

##### 3.1. Data Integrity — Transaction Atomicity

Tôi đề xuất **thay NFR-12 hiện tại** bằng yêu cầu này.

Lý do là FR-09 và BR-03/BR-04 đã quy định tính đúng đắn của double booking. NFR nên tập trung vào việc hệ thống duy trì dữ liệu nhất quán khi quá trình xử lý bị lỗi.

| ID | Category | Requirement | Verification |
| --- | --- | --- | --- |
| NFR-12 | Reliability — Data Integrity | Booking, cancellation, and check-in operations involving multiple database updates shall be atomic. Failed operations shall not leave partially committed changes or inconsistent booking states. | Database integration tests; simulate transaction failures and verify rollback. |

Ví dụ, khi hủy booking, hệ thống có thể cần cập nhật booking status và các dữ liệu liên quan. Nếu một bước bị lỗi, không được để dữ liệu ở trạng thái cập nhật dở dang.

**Đối với double booking**, tôi đề xuất giữ bài kiểm thử 20 concurrent requests trong Acceptance Criteria của FR-09.

Một điểm đặc biệt quan trọng: khi F08 được triển khai, một booking mới bắt đầu ở trạng thái Pending payment, chưa phải Booked. Do đó, câu “exactly 1 booking is confirmed” trong NFR-12 hiện tại không đúng cho mọi cấu hình của hệ thống.

Kiểm thử đồng thời nên xác minh tối đa một active booking giữ cùng một slot, thay vì luôn yêu cầu đúng một booking đã được xác nhận.

##### 3.2. Payment Status Consistency

Trong các cuộc trao đổi trước, chúng ta đã thảo luận về yêu cầu đảm bảo tính nhất quán của trạng thái thanh toán.

Tuy nhiên, **tôi không thấy yêu cầu này trong bảng NFR hiện tại**.

FR-35 đã quy định cập nhật booking sang Booked sau khi thanh toán thành công, nhưng chưa bao quát rõ các trường hợp callback trùng lặp, kết quả chưa xác minh hoặc lỗi trong quá trình cập nhật.

Tôi đề xuất bổ sung:

| ID | Category | Requirement | Verification |
| --- | --- | --- | --- |
| NFR-16 | Reliability — Payment Consistency | Payment and booking states shall remain consistent with verified payment results, including when payment notifications are delayed, duplicated, or invalid. Unverified payments shall never cause a booking to be marked as paid. | Sandbox payment tests covering success, failure, timeout, duplicate callbacks, and database errors. |

**Priority: Should**, vì F08 — Deposit Payment là Should-have.

Nếu F08 không được triển khai, NFR-16 cũng không cần nằm trong phạm vi kiểm thử của bản demo.

---

#### 4. Đề xuất sửa bảng NFR trước khi nộp

Đây là danh sách các thay đổi tôi ưu tiên, không yêu cầu viết lại toàn bộ bảng:

| NFR | Hành động | Mức độ |
| --- | --- | --- |
| NFR-01 | Làm rõ kiểm thử từng API riêng biệt | Minor |
| NFR-02 | Làm rõ test dataset và non-conflicting slots | Minor |
| NFR-03 | Xác định thời điểm bắt đầu đo 5 giây | Important |
| NFR-04 | Sửa câu và làm rõ login throttling | Minor |
| NFR-05 | Bổ sung kiểm tra không bypass được HTTPS proxy | Important |
| NFR-06 | Sửa diễn đạt, bổ sung kiểm chứng bcrypt cost | Minor |
| NFR-07 | Đổi category thành Portability — Adaptability | Important |
| NFR-08 | Bổ sung ngoại lệ cho calendar và tables | Minor |
| NFR-09 | Bổ sung xử lý lỗi ở cấp form | Minor |
| NFR-10 | Làm rõ tính nhất quán khi đổi ngôn ngữ | Important |
| NFR-11 | Xác định quy trình usability testing | Minor |
| NFR-12 | Thay bằng Transaction Atomicity | **Critical** |
| NFR-13 | Đổi category, bổ sung CI coverage gate | Important |
| NFR-14 | Làm rõ automated deployment | Important |
| NFR-15 | Đổi category thành Security — Privacy | Important |
| NFR-16 | Bổ sung Payment Status Consistency | Important, conditional |

Tôi cũng đề xuất bổ sung cột **Priority (Must/Should)** và **Related FR** vào bảng. Đây không phải yêu cầu bắt buộc của template hiện tại, nhưng sẽ giúp nhóm xác định phạm vi kiểm thử và quản lý các yêu cầu chỉ áp dụng khi có tính năng tùy chọn.

#### 5. Kết luận

Phần NFR của bạn đã có nền tảng tốt, đặc biệt là Performance, HTTPS, Password Storage, Responsive Design và CI/CD. Những yêu cầu này đã có phương pháp kiểm chứng tương đối cụ thể, phù hợp với quy mô BadminBookingHub.

**Ba việc nên ưu tiên trước khi chốt bản PA2:**

1. **Loại bỏ trùng lặp giữa NFR-12 và FR-09**, thay bằng yêu cầu về transaction atomicity.
2. **Bổ sung Payment Status Consistency** nếu nhóm dự định triển khai F08.
3. **Làm rõ các điều kiện kiểm thử**, đặc biệt là thời điểm đo, môi trường, dữ liệu test và điều kiện Pass/Fail.

Sau các điều chỉnh này, bộ NFR sẽ có **16 yêu cầu**, trong đó NFR-12 được thay thế và NFR-16 được bổ sung. Các yêu cầu như CI/CD và test coverage vẫn có thể giữ trong bảng theo template của môn học, nhưng nên ghi nhận chúng là ràng buộc chất lượng của quy trình phát triển thay vì thuộc tính vận hành của sản phẩm.

**Tiêu đề chat đề xuất:** \[Software Engineering\] - Review NFR cho PA2 BadminBookingHub (29/10/2026)


---

## You

`33 of 34`

Sửa theo review và cho tôi bản final


---

## ChatGPT

`34 of 34`

Tôi đã chỉnh sửa toàn bộ **15 NFR hiện tại** theo phần review, thay thế NFR-12 bị trùng lặp và bổ sung NFR-16 về Payment Consistency.

Bản dưới đây giữ nguyên hệ thống ID của tài liệu PA2, sử dụng văn phong ngắn gọn, đồng thời bảo đảm mỗi NFR có điều kiện kiểm chứng rõ ràng. Tôi cũng bổ sung cột Priority để phân biệt các yêu cầu bắt buộc với những yêu cầu phụ thuộc vào tính năng Should-have.

### Final Version — Section 5.2. Non-Functional Requirements

BadminBookingHub — Final Non-Functional Requirements

#### 5.2. Non-Functional Requirements

| ID | Category | Requirement (Measurable) | How It Will Be Verified | Priority |
| --- | --- | --- | --- | --- |
| NFR-01 | Performance | Court search and availability APIs shall each achieve p95 response time below 2 seconds and HTTP error rate below 1% under 20 concurrent virtual users, with at least 5,000 pre-seeded booking records. | Run a 5-minute k6 load test on the EC2 demo deployment; measure p95 latency and error rate separately for each API. | Must |
| NFR-02 | Performance | Valid booking requests shall achieve p95 response time below 3 seconds and HTTP error rate below 1% under 20 concurrent virtual users, with at least 5,000 pre-seeded booking records. | Run a 5-minute k6 load test using non-conflicting booking slots; measure p95 latency, error rate, and verify booking results. | Must |
| NFR-03 | Reliability — Data Freshness | Confirmed booking and cancellation changes shall appear in other users' active availability calendars within 5 seconds after the database transaction commits, under normal network conditions. | Use Playwright multi-user E2E tests to measure the delay between transaction commit and calendar update. | Must |
| NFR-04 | Security | After 10 failed login attempts for an account within a rolling 15-minute window, the system shall reject further login attempts for that account with HTTP 429 for 15 minutes. | Execute repeated-login tests; verify the attempt limit, HTTP 429 response, and restriction duration. | Should |
| NFR-05 | Security — HTTPS | All external application traffic shall use HTTPS with a valid TLS certificate. HTTP page requests shall redirect to HTTPS, while HTTP API requests shall be rejected without executing application operations. | Use curl to verify redirects, API rejection, TLS certificate validity, and prevention of direct public HTTP access to backend services. | Must |
| NFR-06 | Security — Password Storage | All user passwords shall be stored as salted bcrypt hashes with a cost factor of at least 10. Plaintext passwords shall never be persisted. | Use unit and database integration tests to verify hash algorithm, cost factor, salt uniqueness, and password validation. | Must |
| NFR-07 | Portability — Adaptability | All Must-have workflows shall function correctly on the Chromium/Blink, Firefox/Gecko, and WebKit browser engines supported by the approved test environment. | Run Playwright cross-browser E2E tests on Chromium, Firefox, and WebKit. | Must |
| NFR-08 | Usability — Responsive Design | All Must-have workflows shall remain usable across viewport widths of 320–1920 CSS pixels without inaccessible controls or unintended page-level horizontal scrolling. | Run Playwright viewport tests and manual resizing; allow independent horizontal scrolling for calendars and data tables. | Must |
| NFR-09 | Usability — Error Feedback | Invalid inputs shall display clear error messages identifying the affected fields and applicable correction rules. Form-level errors shall also be explained, while valid entered data shall be preserved. | Run form-validation tests covering invalid fields, business-rule violations, and preservation of valid inputs. | Must |
| NFR-10 | Usability — Internationalization | All system-generated UI text shall support English and Vietnamese. Language preferences shall persist across navigation and reloads, and switching languages shall not clear user-entered data. | Run Playwright localization tests on all Must-have pages; verify translations, language persistence, and form-data preservation. | Must |
| NFR-11 | Usability | At least 80% of first-time users shall successfully create a court booking within 2 minutes without assistance, excluding registration and payment. | Test with at least 5 first-time users, starting from the court search page with an authenticated account; measure completion time and success rate. | Must |
| NFR-12 | Reliability — Data Integrity | Booking, cancellation, and check-in operations involving multiple database updates shall be atomic. Failed operations shall not leave partially committed changes or inconsistent booking states. | Run database integration tests; simulate transaction failures and verify rollback and data consistency. | Must |
| NFR-13 | Testability | Automated unit tests shall achieve at least 70% statement coverage of the backend service layer. | Generate a Vitest coverage report during CI; fail the required check if coverage falls below 70%. | Must |
| NFR-14 | Development Process — CI/CD | Every pull request targeting `main` shall automatically run linting, automated tests, and production builds. Merging shall be blocked if any required check fails. Successful merges to `main` shall trigger automated deployment to the demo environment. | Test successful and failing pull requests; verify GitHub branch protection, CI results, and automated deployment after merging. | Must |
| NFR-15 | Security — Privacy | The system shall not expose a Player's name, phone number, or email address to other Players. Availability calendars shall display only booking availability information without identifying the booking owner. | Test API responses and UI visibility using different Player accounts; verify that personal information is not disclosed. | Must |
| NFR-16 | Reliability — Payment Consistency | If F08 is implemented, payment and booking states shall remain consistent with verified payment results. Failed, unverified, duplicate, or delayed notifications shall not produce incorrect payment or booking states. | Run sandbox integration tests covering successful, failed, pending, duplicate, delayed, and invalid payment notifications; verify database consistency. | Should |

### Những lưu ý trước khi đưa vào PA2

**1. NFR-12 đã được thay thế hoàn toàn.** Yêu cầu ngăn double booking khi có 20 requests đồng thời nên được chuyển thành acceptance test của FR-09. Trong tài liệu hiện tại, FR-09 và BR-03/BR-04 đã quy định việc ngăn đặt trùng sân.

**2. NFR-16 chỉ áp dụng nếu F08 được triển khai.** Nhóm cần thống nhất thêm cách xử lý trường hợp cổng thanh toán xác nhận thành công sau khi thời gian giữ sân đã hết. Đây là tình huống nghiệp vụ cần được đặc tả, không thể chỉ giải quyết bằng NFR về tính nhất quán.

**3. NFR-01 và NFR-02 cần có test dataset cố định.** Việc sử dụng 5.000 booking records phải được ghi nhận trong Test Plan của PA4. Với NFR-02, cần sử dụng đủ tài khoản và khung giờ hợp lệ để tránh những lỗi nghiệp vụ dự kiến làm sai lệch kết quả performance test.

**4. NFR-10 cần một FR đi kèm.** Nhóm nên bổ sung Functional Requirement cho phép người dùng chuyển đổi giữa tiếng Anh và tiếng Việt từ mọi trang. NFR-10 chỉ tập trung vào chất lượng hiển thị và duy trì trạng thái.

**5. NFR-13 và NFR-14 là development/process requirements.** Có thể giữ chúng trong bảng NFR theo phạm vi của đồ án, nhưng cần phân biệt với các quality attributes của sản phẩm. Riêng NFR-13 phù hợp với mục tiêu coverage 70% đã được xác định trong kế hoạch PA5.

**6. Các con số trong bảng là mục tiêu được đề xuất, chưa phải kết quả đã kiểm chứng.** Nhóm cần thống nhất chúng trước khi chốt requirements baseline và chuẩn bị bằng chứng Pass/Fail trong PA4–PA5.

#### Kết quả sau chỉnh sửa

| Nội dung | Kết quả |
| --- | --- |
| Tổng số NFR | **16** |
| Must-have | **14** |
| Should-have | **2** |
| NFR trùng lặp được xử lý | NFR-12 |
| NFR được bổ sung | NFR-16 |
| Các yêu cầu có verification method | 16/16 |
| Phù hợp để đưa vào PA2 | Có, sau khi nhóm phê duyệt các ngưỡng và phạm vi kiểm thử |

**Tiêu đề chat đề xuất:** \[Software Engineering\] - Final NFR Specification cho PA2 (29/10/2026)

