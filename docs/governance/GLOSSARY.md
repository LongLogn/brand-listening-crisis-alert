# Project Glossary — Brand Listening and Crisis Alert

| Thuộc tính | Nội dung |
| --- | --- |
| Bộ tài liệu | BRD 2.0 — sản phẩm v0.1 |
| Cập nhật | 08/10/2026 |
| Nguồn | [BRD](BRD.md), [PROJECT_SPEC](PROJECT_SPEC.md), [DATA_SOURCE](DATA_SOURCE.md) |
| Phạm vi | Dữ liệu mock, AI giám sát/DM, Event Contract, vai trò/SLA và AWS |
| Mã thuật ngữ | Giữ GL khi cùng khái niệm; mã không liên tục do giới hạn phạm vi |

## I. Abbreviations and Identifiers

*Chữ viết tắt chỉ mở rộng từ tiếng Anh; tên sản phẩm dùng nguyên tên.*

### 1. Abbreviations — Chữ viết tắt

| Ký hiệu | English expansion | Ý nghĩa |
| --- | --- | --- |
| BRD | Business Requirements Document | Yêu cầu nghiệp vụ |
| AI / LLM | Artificial Intelligence / Large Language Model | Trí tuệ nhân tạo / mô hình ngôn ngữ lớn |
| API / HTTP | Application Programming Interface / Hypertext Transfer Protocol | Giao diện / giao thức API |
| JSON / JSONL | JavaScript Object Notation / JSON Lines | Dữ liệu JSON / mỗi dòng JSON |
| JWT | JSON Web Token | Token xác thực |
| DM | Direct Message | Tin nhắn riêng |
| SME | Small and Medium-sized Enterprise | Doanh nghiệp vừa và nhỏ |
| CS | Customer Service | Chăm sóc khách hàng |
| CMO / CEO | Chief Marketing Officer / Chief Executive Officer | Giám đốc Marketing / Giám đốc điều hành |
| SLA / SLO / SLI | Service Level Agreement / Service Level Objective / Service Level Indicator | Mức dịch vụ / mục tiêu / chỉ số đo |
| P95 | 95th Percentile | Phân vị 95 |
| ID | Identifier | Định danh |
| AWS / IAM | Amazon Web Services / Identity and Access Management | Đám mây / quyền AWS |
| S3 | Simple Storage Service | Lưu đối tượng |
| SQS / SNS | Simple Queue Service / Simple Notification Service | Hàng đợi / thông báo |
| FIFO / DLQ | First In, First Out / Dead-Letter Queue | Thứ tự / hàng đợi lỗi |
| SHA | Secure Hash Algorithm | Thuật toán băm; SHA-256 cho định danh nhóm/sự kiện |
| UTC | Coordinated Universal Time | Chuẩn thời gian |
| USD | United States Dollar | Ngân sách |
| MCP | Model Context Protocol | Kết nối công cụ, hướng tương lai |
| PIC / WBS | Person in Charge / Work Breakdown Structure | Phụ trách / phân rã công việc |

### 2. Identifiers — Mã tài liệu

| Tiền tố | English expansion | Cách dùng |
| --- | --- | --- |
| GL | Glossary Entry | Thuật ngữ |
| BO-S | Business Objective — Simplified Scope | Mục tiêu nghiệp vụ |
| BR-S / AC-S | Business Requirement / Acceptance Criterion — Simplified Scope | Yêu cầu / nghiệm thu |
| DG-S | Diagram — Simplified Scope | Sơ đồ BRD |
| PS-DL / PS-DG | Project Specification Deliverable / Diagram | Sản phẩm / sơ đồ PROJECT_SPEC |
| TC / DS-DG | Test Case / Data Source Diagram | Tình huống / sơ đồ DATA_SOURCE |

## II. Business and Roles

*Đối tượng nghiệp vụ và trách nhiệm; nhân viên doanh nghiệp khác khách mock và khác nhóm sinh viên.*

### 1. Core Business Terms — Thuật ngữ cốt lõi

| ID | English term | Tiếng Việt | Cách hiểu trong v0.1 nhỏ |
| --- | --- | --- | --- |
| GL-001 | Brand listening | Lắng nghe thương hiệu | Theo dõi phản ánh về một thương hiệu demo; dữ liệu nguồn hoàn toàn mô phỏng. |
| GL-002 | Brand | Thương hiệu | Đối tượng được nhắc/giám sát. Demo một thương hiệu giả, không triển khai nhiều khách hàng doanh nghiệp. |
| GL-252 | Small and Medium-sized Enterprise — SME | Doanh nghiệp vừa và nhỏ | Bối cảnh tổ chức có thể kiêm nhiệm và không có CMO; quyền vẫn theo chức năng. |
| GL-014 | Adverse feedback | Phản hồi bất lợi | Ý kiến/trải nghiệm xấu hướng thương hiệu; đơn lẻ không tự là khủng hoảng. |
| GL-016 | Reputational crisis | Khủng hoảng truyền thông | Tình huống cần con người đánh giá ảnh hưởng uy tín. Cảnh báo chỉ là dấu hiệu cần xem xét. |
| GL-044 | Alert | Cảnh báo | Bản ghi phát hiện có mức/lý do/thời điểm/bằng chứng; không đồng nhất email hoặc hồ sơ. |
| GL-045 | Case | Vụ việc | Hồ sơ nhận, xác minh, xử lý, chuyển cấp và đóng; có thể gom nhiều cảnh báo cùng vấn đề. |
| GL-046 | Notification | Thông báo | Lần truyền thông tin về cảnh báo/vụ việc; dịch vụ chấp nhận khác email đến inbox hoặc người nhận nhận việc. |
| GL-109 | Severity | Mức cảnh báo/vụ việc | LOW đơn lẻ, MEDIUM tập thể, CRITICAL nghiêm trọng; không là xác suất cáo buộc đúng. |
| GL-118 | Sentiment analysis | Phân tích sắc thái | POSITIVE/NEGATIVE/NEUTRAL/MIXED; không tự xác định đối tượng bị cáo buộc hoặc sinh reply. |
| GL-024 | Verification | Xác minh | Con người kiểm tra dữ kiện và phần thiếu, không lấy kết quả AI thay sự thật. |
| GL-027 | Verification outcome | Kết quả xác minh | Có cơ sở / Không phù hợp sau xác minh / Chưa đủ thông tin; độc lập trạng thái và mức. |
| GL-029 | Escalation | Chuyển cấp | Quá hạn chưa nhận tự chuyển tới cấp tiếp theo đang có; chuyển vượt thẩm quyền có lý do. CEO là điểm cuối. |
| GL-048 | Acknowledgement | Xác nhận nhận xử lý | Người đúng quyền xác nhận nhận vụ việc; khác mở email hoặc xem màn hình. |
| GL-034 | Case closure | Đóng vụ việc | Có kết luận/hành động và người đúng quyền; chatbot đã trả lời không tự đóng hồ sơ. |
| GL-253 | Automatic customer reply | Tự động trả lời | Bedrock soạn phản hồi từ chính sách mock, backend kiểm tra rồi tự gửi vào đúng hội thoại. |
| GL-254 | Human handoff | Bàn giao con người | Đưa câu hỏi ngoài phạm vi/nhạy cảm/lỗi tới người có trách nhiệm, lưu lý do và trạng thái. |

### 2. Roles — Các vai trò

| ID | English term | Tiếng Việt | Cách hiểu trong v0.1 nhỏ |
| --- | --- | --- | --- |
| GL-255 | Communications specialist | Chuyên viên | Theo dõi, nhận và xử lý ban đầu; không tự thay chính sách hoặc vượt thẩm quyền. |
| GL-256 | Communications expert | Chuyên gia | Xác minh/đánh giá chuyên môn, đề xuất biện pháp và chuyển Trưởng phòng khi cần. |
| GL-257 | Head of Communications | Trưởng phòng truyền thông | Điều phối/phê duyệt trong quyền, giao lại/đóng/mở lại, duyệt mẫu; xin cấp trên khi vượt quyền. |
| GL-258 | Chief Marketing Officer — CMO | Giám đốc Marketing | Cấp trên Trưởng phòng khi doanh nghiệp có; không có thì bỏ qua để tới CEO. |
| GL-259 | Chief Executive Officer — CEO | Giám đốc điều hành | Cấp cuối của chuỗi; quá hạn vẫn giữ nghĩa vụ, không vòng lặp hoặc tự đóng. |
| GL-037 | Admin | Admin kỹ thuật | Vận hành tài khoản/cấu hình kỹ thuật; ngoài chuỗi truyền thông, không tự có quyền nghiệp vụ. |
| GL-260 | Mock customer | Khách hàng giả lập | Người viết bài/bình luận/tin nhắn; thuộc tập 10–20 user, không phải tài khoản nhân viên. |
| GL-043 | Assignee | Người được giao | Người/cấp chịu trách nhiệm hiện hành, có mốc giao/nhận/hạn và lịch sử. |
| GL-021 | As-Is | Quy trình hiện tại tham chiếu | Mô hình SME thủ công giả định; chưa khảo sát doanh nghiệp thật. |
| GL-022 | To-Be | Quy trình mong muốn | Hai luồng tự động và trách nhiệm/SLA được hệ thống hỗ trợ, con người vẫn quyết định chuyên môn. |

## III. Data, AI and Time

*Định danh, cơ chế phân tích và phép đo phải giữ đúng đơn vị.*

### 1. Data and Reply Terms — Dữ liệu và phản hồi

| ID | English term | Tiếng Việt | Cách hiểu trong v0.1 nhỏ |
| --- | --- | --- | --- |
| GL-053 | Content | Nội dung | Bài hoặc bình luận gốc; 10 bài+100 bình luận=110. 10 DM đầu vào là tập riêng; tổng 120 đầu vào, reply là dữ liệu phát sinh. |
| GL-054 | Post | Bài đăng | Một trong 10 bài hardcode, có tác giả/thời gian/ID. |
| GL-055 | Top-level comment | Bình luận cấp đầu | Một trong 10 bình luận trực tiếp mỗi bài, có parent và tác giả thuộc tập user. |
| GL-261 | Direct Message — DM | Tin nhắn riêng | 10 DM đầu vào từ 10 khách; tách bình luận công khai và reply hệ thống. |
| GL-262 | Webhook | Sự kiện đẩy tới backend | Simulator chủ động gửi bài/comment/tin; không chứng minh kết nối nền tảng thật. |
| GL-263 | Hardcoded source data | Dữ liệu nguồn hardcode | Câu chữ/người dùng/từ khóa chuẩn bị sẵn; kết quả AI/reply vẫn phải xử lý runtime theo cơ chế công bố. |
| GL-061 | Event | Sự kiện | Một thao tác tạo/sửa/tương tác/DM; event_id nhận diện thao tác, retry giữ nguyên event_id/request. |
| GL-072 | Run | Lần chạy | Phạm vi demo/phát lại/reset, tách lịch sử và chống lặp giữa các lần. |
| GL-063 | Payload | Dữ liệu nội dung | Bốn trường time/user_id/msg_id/msg_content nằm trong payload; metadata và loại thao tác nằm ở envelope. |
| GL-064 | Schema | Cấu trúc dữ liệu | Trường/kiểu/ràng buộc Event Contract tại BRD VII; khác thiết kế vật lý DynamoDB. |
| GL-264 | Conversation identifier | Định danh hội thoại | Ngữ cảnh để reply đúng cuộc chat, khác ID riêng của từng tin. |
| GL-080 | Deduplication | Chống trùng | Ngăn tác động lặp theo run/event và nội dung/phiên bản; khôi phục bước dang dở, không tạo reply mới. |
| GL-082 | Audit trail | Lịch sử tác nghiệp | Ai làm gì, khi nào, lý do; giữ quá hạn/chuyển cấp/điều chỉnh/đóng. |
| GL-070 | Real AI result | Kết quả AI thật | Kết quả gọi cơ chế AI thực tế, lưu input/output. Đáp án gán sẵn phải ghi là giả lập. |
| GL-265 | Response template | Mẫu phản hồi | Câu tiếp nhận/giới hạn được duyệt, dùng fallback và bàn giao; khác phản hồi do LLM soạn. |
| GL-266 | Generative response | Phản hồi sinh bằng mô hình | Nova Lite soạn câu từ dữ kiện/chính sách; backend kiểm tra trước gửi, ngoài phạm vi chuyển người. |
| GL-124 | Ground truth / gold label | Đáp án tình huống | Hành vi mong đợi để đối chiếu demo; không đưa đáp án vào đầu vào để giả AI phát hiện. |
| GL-104 | Sliding window | Cửa sổ trượt | Khoảng (T−10 phút,T]; T là mốc nghiệp vụ lớn nhất trong run, không lùi khi sự kiện cũ tới. |
| GL-105 | Eligible total count — N | Tổng đủ điều kiện | Bài/comment duy nhất có phân tích thành công, phiên bản hiện hành, cùng run/brand/topic/cửa sổ; không gồm DM/reply/lỗi. |
| GL-106 | Qualified negative count — K | Số tiêu cực đủ ngưỡng | Phần của N có NEGATIVE với score Comprehend ≥0,85; không là xác suất khủng hoảng. |
| GL-107 | Negative ratio | Tỷ lệ tiêu cực | K/N khi N>0; MEDIUM cần đồng thời N≥10, K≥5, tỷ lệ≥50%. |
| GL-270 | Large Language Model — LLM | Mô hình ngôn ngữ lớn | Hiểu yêu cầu và sinh văn bản; v0.1 dùng Nova Lite qua Bedrock, không giao quyền nghiệp vụ cho model. |
| GL-271 | Converse API | API hội thoại Bedrock | Giao diện gọi Nova Lite; lưu model, phiên bản prompt, token và trạng thái xử lý. |
| GL-272 | Event Contract | Hợp đồng sự kiện | Cấu trúc, định danh, thao tác, phiên bản, đồng hồ, kết quả và lỗi tại BRD VII. |
| GL-273 | Event envelope | Metadata sự kiện | schema_version/event_id/event_type/run và quan hệ; bao quanh payload bốn trường nội dung. |
| GL-274 | Content version | Phiên bản văn bản | Version nguyên ≥1 của cùng nội dung; sửa tăng version, không tăng N hoặc đổi mốc tiếp nhận đầu. |
| GL-275 | Engagement revision | Phiên bản tương tác | Revision riêng cho likes/shares tuyệt đối; resend không cộng lại, không gọi AI văn bản. |
| GL-279 | Dead-Letter Queue — DLQ | Hàng đợi lỗi | Sự kiện hết lượt xử lý tự động, có lỗi và cơ chế xem/phát lại có kiểm soát. |
| GL-281 | Policy reference | Tham chiếu chính sách | policy_refs dẫn tới dữ kiện được duyệt; backend kiểm tra và dùng đánh giá nội dung phản hồi. |
| GL-282 | JSON validation | Kiểm tra đầu ra JSON | Parse/schema và kiểm tra nghiệp vụ tại backend; yêu cầu JSON trong prompt không tự bảo đảm schema. |
| GL-283 | Idempotent reply | Phản hồi chống lặp | Reply_id ổn định, lưu trước gửi; retry dùng cùng nội dung/ID sau đối soát. |
| GL-284 | HTTP 202 Accepted | Đã tiếp nhận bất đồng bộ | Sự kiện đã lưu bền vững và xếp hàng; chưa đồng nghĩa AI/reply hoàn tất. |
| GL-285 | Policy version | Phiên bản chính sách | Bản dữ kiện/mẫu có người duyệt, lưu cùng kết quả để truy vết. |
| GL-286 | Input and output tokens | Token vào/ra | Đơn vị tính phí model; input gồm hướng dẫn/chính sách/ngữ cảnh và tin khách. |
| GL-287 | First In, First Out — FIFO | Thứ tự trong nhóm | SQS giữ thứ tự tiếp nhận theo MessageGroupId; không thay chống trùng ứng dụng. |

### 2. SLA and Clocks — Thời gian và mức dịch vụ

| ID | English term | Tiếng Việt | Cách hiểu trong v0.1 nhỏ |
| --- | --- | --- | --- |
| GL-145 | Service Level Agreement — SLA | Thỏa thuận mức dịch vụ | Hạn nhận theo cấp 5/10/15/30/60 phút thực; quá hạn chưa nhận tự chuyển. Hạn xử lý do quản lý đặt riêng. |
| GL-146 | Service Level Objective — SLO | Mục tiêu dịch vụ | Giá trị mong muốn, chưa là kết quả đạt. |
| GL-147 | Service Level Indicator — SLI | Chỉ số thực đo | Đo có start/end, phạm vi, số mẫu và lỗi để so mục tiêu. |
| GL-085 | Wall clock | Đồng hồ thực | Đo backend/gửi/reply; không lấy time nguồn hardcode làm mốc nhận thực. |
| GL-084 | Simulation clock | Đồng hồ mô phỏng | Business clock cho cửa sổ; timer demo tăng tốc có nhãn. Không dùng làm số đo hiệu năng thực. |
| GL-094 | Due time | Mốc đến hạn | ack_due_at cho nhận; resolution_due_at cho xử lý. Thay hạn giữ mốc cũ/lý do. |
| GL-095 | Overdue | Đang quá hạn | Đã tới hạn chưa hoàn tất; chuyển cấp không xóa vi phạm. |
| GL-152 | 95th percentile — P95 | Phân vị 95 | Sắp lượt thành công tăng dần, phần tử ceil(0,95×n), đếm từ 1; báo số mẫu/lỗi/chưa xong. |
| GL-093 | Operating session | Phiên vận hành | Khoảng chạy có lịch, mặc định 2 giờ; không là cam kết 24/7. |
| GL-179 | Cleanup | Dọn tài nguyên | Sau xuất bằng chứng/nghiệm thu cuối/nhóm xác nhận không cần demo lại; không tự xóa từ việc duyệt tài liệu. |
| GL-276 | First business received time | Mốc tiếp nhận nghiệp vụ đầu | first_business_received_at bất biến qua sửa; quyết định nội dung còn nằm trong cửa sổ hay không. |

## IV. Cloud Services

*Core serverless và tác vụ minh chứng bổ sung cùng thuộc phạm vi dự án.*

### 1. Core Services — Dịch vụ core

| ID | English term | Tiếng Việt | Vai trò |
| --- | --- | --- | --- |
| GL-267 | Serverless | Dịch vụ không quản lý máy chủ | Hướng core Lambda/DynamoDB/S3; vẫn quản lý quyền, lỗi và chi phí. |
| GL-211 | AWS Lambda | Backend hàm | Ingest/API, worker AI và xử lý SLA. |
| GL-220 | Amazon DynamoDB | Dữ liệu khóa–giá trị/tài liệu | Trạng thái event/content/case/chat/SLA và kiểm tra có điều kiện. |
| GL-214 | Amazon Simple Storage Service — S3 | Lưu trữ đối tượng | Mock, dữ liệu xuất và bằng chứng. |
| GL-268 | Amazon API Gateway | API được quản lý | HTTP API nhận sự kiện và thao tác nhân viên. |
| GL-225 | Amazon Comprehend | Phân tích văn bản | Sentiment sau Translate; không sinh câu trả lời. |
| GL-228 | Amazon Translate | Dịch máy | Việt→Anh trước Comprehend; giữ bản gốc. |
| GL-269 | Amazon Bedrock | Nền tảng model | Nova Lite On-Demand hiểu yêu cầu và soạn phản hồi DM từ chính sách. |
| GL-226 | Amazon Simple Queue Service — SQS | Hàng đợi | FIFO cho giám sát/hội thoại, DLQ cho sự kiện lỗi. |
| GL-227 | Amazon Simple Notification Service — SNS | Thông báo | Email hộp thư demo; chấp nhận gửi khác email tới inbox hoặc nhận việc. |
| GL-277 | Amazon Cognito | Định danh ứng dụng | Đăng nhập nhân viên; API dùng JWT và kiểm tra quyền nghiệp vụ. |
| GL-278 | JSON Web Token — JWT | Token xác thực | API Gateway kiểm tra token; backend kiểm tra quyền và đối tượng. |
| GL-280 | Amazon EventBridge | Lịch/tác vụ nền | Kích hoạt kiểm tra SLA mỗi phút, độc lập người mở dashboard. |

### 2. Additional Catalogue — Danh mục minh chứng bổ sung

| Tên / English expansion | Vai trò minh chứng |
| --- | --- |
| IAM — Identity and Access Management | Quyền AWS cho module/tài nguyên |
| AWS Organizations | Quản trị tài khoản/chính sách |
| AWS Pricing Calculator | Dự toán core và toàn bộ minh chứng |
| VPC — Virtual Private Cloud | Mạng phần minh chứng |
| Amazon Route 53 / Amazon CloudFront | Định tuyến/phân phối frontend |
| EC2 — Elastic Compute Cloud / Auto Scaling Group | Tác vụ replay/worker và co giãn mẫu |
| AWS Elastic Beanstalk / ECS — Elastic Container Service | Tác vụ ứng dụng/container có đầu vào/đầu ra |
| EBS — Elastic Block Store / EFS — Elastic File System | Lưu và chia sẻ gói dữ liệu/bằng chứng |
| Amazon S3 Glacier | Lớp lưu trữ gói bằng chứng |
| RDS — Relational Database Service / Amazon Aurora | Nhập dữ liệu xuất và truy vấn đối soát |
| Amazon Redshift | Tổng hợp/truy vấn dữ liệu mẫu |
| ELB — Elastic Load Balancing / ALB — Application Load Balancer | Cân bằng tải cho tác vụ compute |
| Amazon CloudWatch | Log, metric và đối soát |
| NAT — Network Address Translation Gateway | Outbound cho phần minh chứng mạng |
| AWS Step Functions | Điều phối tùy chọn, không là điều kiện luồng chính |

## V. Usage and Maintenance

*Dùng khái niệm nhất quán trong yêu cầu, API, giao diện và báo cáo.*

### 1. Distinctions — Phân biệt nhanh

| Dễ nhầm | Quy định |
| --- | --- |
| Nội dung / sự kiện / phiên bản | 120 nội dung cơ sở; resend/edit không tạo nội dung mới |
| Comment / DM / reply | Comment giám sát; DM khách vào; reply hệ thống không đưa trở lại như tin khách |
| Alert / case / notification | Phát hiện / hồ sơ tác nghiệp / thông tin gửi |
| Sentiment / cáo buộc | Sắc thái khác nguy cơ và khác kết luận xác minh |
| Mock input / mock AI | Nguồn giả lập vẫn được phân tích bằng dịch vụ thật trong demo chính |
| Business / server / demo clock | Cửa sổ / hiệu năng và SLA / trình diễn tăng tốc |
| Nhận / giải quyết | Ack dừng timeout nhận; hạn xử lý và kết luận theo dõi riêng |
| Mục tiêu / kết quả | SLO là yêu cầu; PASS/FAIL cần phép đo và bằng chứng |

### 2. Maintenance — Cập nhật

| Nội dung | Quy tắc |
| --- | --- |
| Thuật ngữ mới | Định nghĩa ngắn, một nghĩa chung; giữ mã GL khi khái niệm không đổi |
| Nguồn chuẩn | BRD nghiệp vụ, DATA_SOURCE dữ liệu, PROJECT_SPEC tổ chức thực hiện |
| Thay đổi | Đồng bộ nghĩa với API/UI và tài liệu; không lưu lịch sử trao đổi trong glossary |
