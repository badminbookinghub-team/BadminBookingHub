# NHẬT KÝ SỬ DỤNG AI (AI USAGE LOG) - PA3

- **Thành viên thực hiện:** Nguyễn Đại Phúc (Developer)
- **Nhiệm vụ liên quan:** §3.1 Architectural Style, §3.3 Container Diagram, §3.4 Component Diagram, §3.5 Deployment Diagram; §4 Object-Oriented Design (Domain Model, Class Diagram, Class Specifications, Design Principles); chuyển toàn bộ sơ đồ sang Penpot; review §3.6 (ADR) và review bản PA3 v2 (§2 – §5)
- **Dự án:** BadminBookingHub (PA3 - 08 - Nhập môn Công nghệ Phần mềm)
- **Công cụ AI:** Claude Code (Anthropic); Penpot MCP (sơ đồ), draw.io / PlantUML (giai đoạn đầu)
- **Thời gian:** 16/11/2026 – 23/11/2026

---

## TÓM TẮT (dùng cho bảng AI Usage Log trong PA3)

| # | Member | Tool | Task / purpose |
|---|---|---|---|
| 1 | Phuc | Claude Code | Find and install design skills; plan how to write and draw §3.1, §3.3, §3.4, §3.5 |
| 2 | Phuc | Claude Code (draw.io) | Draw the Container, Component and Deployment diagrams in C4 style and write the §3.5 text |
| 3 | Phuc | Claude Code | Restyle the three diagrams to a reference style, review them with a sub-agent, enlarge the text for A4 printing |
| 4 | Phuc | Claude Code | Revise §3.1 after the peer review; sync the Google Docs text into the local PA3 file |
| 5 | Phuc | Claude Code (PlantUML, draw.io) | Set up UML/OOP tooling and draft §4 Object-Oriented Design with class diagrams |
| 6 | Phuc | Claude Code | Compare §4 with another branch, review the class design against OOP principles, build one overview class diagram |
| 7 | Phuc | Claude Code | Redraw the Container/Component diagrams, write the component diagram caption, write §3.5 and check PA1/PA2/PA3 consistency (EBS, backup) |
| 8 | Phuc | Claude Code | Apply the team review of §3.3 – §3.5 and review §3.6 (ADRs); connect the self-hosted Penpot MCP |
| 9 | Phuc | Claude Code (Penpot MCP) | Move the four C4 diagrams (System Context, Container, Component, Deployment) into Penpot as native, grouped shapes |
| 10 | Phuc | Claude Code (Penpot MCP) | Migrate the class diagrams to Penpot with a shared `UmlKit` asset library; write `CLAUDE.md` and `docs/design/PENPOT.md` for later AI sessions |
| 11 | Phuc | Claude Code | Fix the document after GitHub issue reviews (#130 – #132), align §3 with §4, rewrite and merge §4 into the PA3 file, post the §3.6 review on issue #129 |
| 12 | Phuc | Claude Code | Referee-style review of the PA3 v2 draft (§2 – §5) and Penpot diagrams against PA1, PA2 and a sample report |

---

## PHIÊN 1 (16/11/2026): Chọn skill và lên kế hoạch cho §3.1, §3.3, §3.4, §3.5

### MỤC ĐÍCH
- Tìm các skill phù hợp để thiết kế hệ thống và viết các mục kiến trúc được giao.
- Lập kế hoạch: mỗi mục dùng skill nào, tạo ra sản phẩm gì và dựa vào tài liệu nào.

### KẾT QUẢ ĐẠT ĐƯỢC
- AI đề xuất 3 skill mới (C4, clean architecture, deployment diagrams) và cài cùng 3 skill cũ vào thư mục skill chung.
- Kế hoạch theo từng mục. Tôi chốt các quyết định: dùng **polling** cho cập nhật thời gian thực, viết bằng **tiếng Anh**, ảnh chưa vẽ thì để placeholder kèm caption.

---

## PHIÊN 2 (16/11/2026): Vẽ Container, Component, Deployment theo chuẩn C4

### MỤC ĐÍCH
- Tạo ba sơ đồ kiến trúc và viết phần mô tả §3.5, dựa trên PA1, PA2.

### KẾT QUẢ ĐẠT ĐƯỢC
- Thử vài công cụ (Excalidraw, Mermaid, draw.io), cuối cùng dùng draw.io để có layout kiểm soát được, rồi xoá các file thử.
- Vẽ lại ba sơ đồ theo quy tắc trên c4model.com: có tiêu đề và phạm vi, ghi rõ kiểu phần tử và công nghệ, mỗi mũi tên có nhãn ý định và giao thức. Container chỉ còn 3 container, NGINX/Docker/AWS chuyển sang §3.5.
- **Tôi kiểm tra:** xem ảnh render và chỉ ra layout chưa tốt, yêu cầu AI tìm skill hướng dẫn layout trước khi sửa tiếp.
- **Hạn chế:** AI ghi rõ phiên này chưa chạy lint cho các hình.

---

## PHIÊN 3 (16/11/2026): Đổi style sơ đồ theo ảnh mẫu, review bằng sub-agent

### MỤC ĐÍCH
- Đưa Component, Container và Deployment về cùng một style (theo ảnh mẫu tôi cung cấp) và làm chữ dễ đọc hơn.

### KẾT QUẢ ĐẠT ĐƯỢC
- AI dùng skill OOP và kiến trúc để review Component Diagram hiện tại, rồi sửa. Một sub-agent review độc lập sau khi vẽ xong.
- Chữ trong hình nhỏ vì canvas rộng 2400 – 2700 px: AI tăng cỡ chữ khoảng 1.3 lần, thu hẹp bề ngang canvas, dời hệ thống ngoài xuống dưới. Ảnh xuất PNG 2x, không còn nhãn đè nhau.

---

## PHIÊN 4 (17/11/2026): Sửa §3.1 theo peer review và đồng bộ với Google Docs

### MỤC ĐÍCH
- Sửa §3.1 theo peer review của Hiếu trên GitHub Issue, sau đó đưa nội dung từ Google Docs của nhóm về file PA3 local.

### KẾT QUẢ ĐẠT ĐƯỢC
- AI đọc issue và sửa §3.1. Tôi tự trả lời Hiếu trên issue.
- Đồng bộ chỉ phần chữ và bảng; ảnh thay bằng `[IMAGE]`.
- AI báo các chỗ khác biệt: Doc không có đoạn mở đầu và ghi chú dependency rules của §3.3/§3.4, §3.5 chỉ còn dòng gợi ý của template, có thêm §3.6 (5 ADR). Bản cũ được sao lưu trước khi ghi đè.

---

## PHIÊN 5 (17/11/2026): Chuẩn bị công cụ và viết bản nháp §4 Object-Oriented Design

### MỤC ĐÍCH
- Có đủ skill và công cụ cho UML/OOP, rồi viết bản nháp §4 từ PA1, PA2 và các phần §3 đã có.

### KẾT QUẢ ĐẠT ĐƯỢC
- Cài skill UML, OOP, kiến trúc; PlantUML, Graphviz; extension xem PlantUML và draw.io trong VS Code.
- AI soạn domain model và các class diagram (4.1, 4.2a – 4.2c…) bằng PlantUML trên một nhánh riêng.
- Bố cục PlantUML rối, nên AI chuyển 4 sơ đồ rối nhất sang file `.drawio` gốc (12 / 24 / 29 / 41 class), kiểm tra bằng script: đủ class, không đường nối trỏ vào khối không tồn tại, không khối đè nhau.
- **Lưu ý của AI:** chèn PlantUML thẳng vào draw.io không tách được từng khối nên không dùng được.

---

## PHIÊN 6 (17/11 – 18/11/2026): So sánh §4 với nhánh khác, review nguyên tắc OOP, class diagram tổng hợp

### MỤC ĐÍCH
- So sánh bản §4 của tôi với bản của một agent khác (nhánh WIP), chọn phần tốt hơn.
- Review hệ thống class theo các nguyên tắc OOP; tạo một class diagram bao trùm toàn bộ class.

### KẾT QUẢ ĐẠT ĐƯỢC
- Bảng khác biệt giữa hai bản, nơi nào tốt hơn, lý do, đề xuất sửa. Tôi duyệt rồi mới áp dụng.
- Review OOP (7 nhóm vấn đề kèm phương án). Tôi cũng dán một bản review của agent khác để AI đối chiếu.
- AI thừa nhận không tự nhìn được layout, gợi ý skill về layout và visual review; vẽ class diagram tổng hợp với đầy đủ thuộc tính và hàm.
- **Sự cố:** khi tôi bảo checkout nhánh mới nhất, AI xoá một worktree đang được VS Code mở, gây lỗi "unable to resolve workspace". AI tạo lại thư mục và hướng dẫn mở lại; sau đó tôi dặn AI không xoá worktree để checkout. Một lần tôi gõ nhầm "Resume" ở sai session và yêu cầu rollback; AI kiểm tra và xác nhận chưa có thay đổi nào.

---

## PHIÊN 7 (18/11/2026): Vẽ lại Component/Container, caption và nội dung Deployment

### MỤC ĐÍCH
- Làm Component và Container Diagram chi tiết hơn theo ảnh mẫu; viết caption; viết §3.5 và kiểm tra nhất quán giữa PA1, PA2, PA3.

### KẾT QUẢ ĐẠT ĐƯỢC
- Container Diagram vẽ lại có thêm Reverse Proxy, Static Content, Certbot, Let's Encrypt. (Về sau §3.3 chốt lại còn 3 container, xem phiên 11.)
- Caption cho Component Diagram.
- Nội dung §3.5 viết trực tiếp vào file PA3 (đã bỏ VPC theo yêu cầu).
- **Kiểm tra nhất quán:** PA1 có nhắc EBS (20 – 30 GiB gp3), PA2 không nhắc EBS, ECR, Systems Manager; PA3 vẽ EBS thành node riêng. AI thêm ghi chú "Changes from PA1 and PA2" ở cuối §3.5 (EBS, backup, ECR/SSM, Let's Encrypt).

---

## PHIÊN 8 (20/11/2026): Review của Khang cho §3.3 – §3.5, review §3.6, kết nối Penpot MCP

### MỤC ĐÍCH
- Sửa §3.3 – §3.5 theo review của Khang, review §3.6 (ADR) của Hiếu, và chuyển cách vẽ sơ đồ sang Penpot tự host.

### KẾT QUẢ ĐẠT ĐƯỢC
- Cập nhật file PA3 theo review; tạo bản review §3.6.
- Quyết định mới của nhóm: **mọi sơ đồ vẽ qua Penpot MCP, dạng SVG, có nhóm component rõ ràng.**
- AI kết nối MCP tích hợp sẵn của Penpot 2.18.7 (thay cho bản MCP cũ bị lệch phiên bản), gỡ cấu hình cũ. AI nhắc không đưa token vào repo.

---

## PHIÊN 9 (20/11/2026): Đưa 4 sơ đồ C4 lên Penpot

### MỤC ĐÍCH
- Đưa Component, Deployment, Container và System Context lên Penpot với một style chung (lấy theo Component Diagram).

### KẾT QUẢ ĐẠT ĐƯỢC
- 4 page `ContainerDiagram`, `ComponentDiagram`, `DeploymentDiagram`, `SystemContextDiagram` vẽ bằng shape native, text sửa được, group theo component và đường nối.
- Container vẽ lại theo style Component; System Context vẽ mới từ ảnh tôi gửi.
- AI export từng sơ đồ để xem lại. Các file cũ trong `docs/design/diagrams/` được xoá sau đó theo yêu cầu của tôi.

---

## PHIÊN 10 (20/11/2026): Chuyển class diagram sang Penpot, tạo bộ asset và tài liệu cho các phiên AI sau

### MỤC ĐÍCH
- Đưa toàn bộ class diagram (SVG) lên Penpot, đặt tên page theo PascalCase, tách diagram và bảng thành hai page, tạo asset dùng lại.

### KẾT QUẢ ĐẠT ĐƯỢC
- Thư viện asset `UmlKit` (màu, typography, badge, mũi tên) dùng chung cho các sơ đồ.
- Phiên này mất nhiều lượt thử vì kết nối MCP bị ngắt, tôi phải reload và cấp lại link nhiều lần.
- AI viết `CLAUDE.md` và `docs/design/PENPOT.md`: thông tin file Penpot, bảng 15 page, quy ước hình, các bẫy kỹ thuật, quy trình thêm sơ đồ. Hai file đã được kiểm tra không chứa token.
- **Lưu ý:** khi xoá worktree tạm theo yêu cầu, các file nằm trong đó bị mất; AI tạo lại hai file ngay trên main.

---

## PHIÊN 11 (20/11/2026): Sửa theo review GitHub Issue, viết lại §4, review §3.6 của Hiếu

### MỤC ĐÍCH
- Đọc review ở các issue #130 – #132, đối chiếu §3 với thiết kế OOP, viết lại §4 và ghép vào file PA3, review §3.6 và đăng lên issue.

### KẾT QUẢ ĐẠT ĐƯỢC
- **Review issue:** tôi cho phép AI không làm đúng từng chữ (ví dụ bỏ legend trong ảnh, chuyển thành đoạn "Key" trong nội dung). Fig 3.1 – 3.4 sửa theo hướng này.
- **Đồng bộ §3 và §4:** BookingService tách thành 3 lớp, StatusScheduler gọi `BookingMaintenanceService`, bỏ `PriceCalculator`, CourtService/UserAdminService hỏi booking qua `BookingQueryService`.
- **§4:** domain model, class diagram (4.2, 4.2a – 4.2g), 8 class spec (C1 – C8), design principles và patterns. Sequence và State Machine để placeholder cho Tú. AI thêm bảng đặc tả 6 rule (`check(ctx)`).
- **§3.6:** review của Hiếu đăng lên issue #129, không sửa trực tiếp nội dung của Hiếu.
- **Chưa xong / cần người kiểm tra:**
  - Mã BR trong bảng 6 rule do AI suy ra từ bản nháp cũ, cần đối chiếu lại với PA2.
  - FullClassDiagram chưa thêm 2 thao tác của `BookingQueryService`; bảng CrossRing chưa sửa; chưa xem lại ảnh sau khi đổi màu.
- Dọn dẹp git: AI xoá 7 branch local (chỉ giữ `main`, không đụng remote) và ghi lại SHA của từng nhánh để khôi phục được.

---

## PHIÊN 12 (23/11/2026): Review bản PA3 v2 (§2 – §5) và sơ đồ Penpot

### MỤC ĐÍCH
- Làm "referee review": thẩm định bản v2 (§2 – §5) và các sơ đồ Penpot, đối chiếu với PA1, PA2, thư mục ảnh trên Drive và một bài mẫu. Chỉ đọc, không sửa tài liệu gốc.

### KẾT QUẢ ĐẠT ĐƯỢC
- File `pa/PA3/PA3-review-v2.md`: kết luận **Needs minor fixes**, 30 finding theo mức Critical/Major/Minor/Cosmetic, bảng Pass/Fail theo checklist.
- **2 lỗi chặn:**
  - C1: mã HTTP trong `ErrorMapper` và 5 sequence diagram (422/409) mâu thuẫn với 6 Acceptance Criteria của PA2 (HTTP 400).
  - C2: §7 Traceability còn nguyên placeholder.
- **Major:** chữ trong sơ đồ in ra chỉ còn khoảng 3 pt; NFR-16 còn ghi "pending"; sequence diagram thiếu lifeline `UnitOfWork`, `UserRepository.lockForUpdate`, `WalkInCustomer`; fragment `alt` đè ra ngoài khung `tx`.
- Lần đầu AI không đọc được bản v2 (quyền truy cập), đã dừng và báo tôi chia sẻ rồi mới audit.
- **Lưu ý:** điểm ước lượng (khoảng 8.0 → 9.0 – 9.5/10) là chủ quan của AI, không dựa trên barem chính thức.

---

## CÁCH TÔI KIỂM CHỨNG VÀ SỬ DỤNG KẾT QUẢ CỦA AI

- Các quyết định thiết kế là của tôi và nhóm (polling thay vì SSE, 3 container, vẽ bằng Penpot, quy ước hình A4); AI đề xuất và thực hiện.
- Tôi xem ảnh render từng sơ đồ, nhiều lần yêu cầu sửa layout. AI không tự thấy layout tốt, nên mỗi lần đều export ảnh để xem lại.
- Nội dung có nguồn (PA1, PA2, issue review, Google Docs) được đối chiếu; chỗ AI tự suy ra (mã BR của 6 rule, điểm ước lượng) đã được đánh dấu cần kiểm tra.
- Không đưa token, thông tin cá nhân hay bí mật vào repo, commit hay prompt; token Penpot chỉ nằm trong cấu hình cục bộ.

## HẠN CHẾ VÀ ĐIỀU CẦN LƯU Ý

- AI từng xoá worktree đang mở và làm mất file chưa commit; sau đó tôi dặn dùng detach thay vì xoá, và tạo các file hướng dẫn trên main.
- Một số sơ đồ (FullClassDiagram, CrossRing) chưa khớp hoàn toàn với nội dung §4.
- Bản review v2 có 2 lỗi chặn (C1, C2) và 4 lỗi Major chưa được sửa tại thời điểm viết log này.
