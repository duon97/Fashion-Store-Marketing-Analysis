# Fashion-Store-Marketing-Analysis
Phân tích hiệu quả marketing, hành vi khách hàng và doanh thu để tìm kiếm cơ hội tăng trưởng và hỗ trợ ra quyết định dựa trên dữ liệu.
# Market-Expansion-and-Product-Strategy
Use Power BI to analyze business data to find new market opportunities, and find  strategic product
## I. Giới thiệu
### 1. Bộ dữ liệu
#### Orders Table

## 🧩 Dim_danh_sach_san_pham

| Tên cột               | Kiểu dữ liệu | Mô tả |
|------------------------|--------------|-------|
| Chất liệu              | STRING       | Chất liệu cấu thành sản phẩm (vải, nhựa, kim loại, v.v.) |
| Danh mục               | STRING       | Nhóm sản phẩm theo phân loại kinh doanh |
| Giá vốn                | FLOAT        | Chi phí sản xuất hoặc nhập hàng của sản phẩm |
| Giá bán                | FLOAT        | Giá bán niêm yết của sản phẩm |
| Giá bán + VAT          | FLOAT        | Giá bán đã bao gồm thuế VAT |
| Giá nhập               | FLOAT        | Giá nhập hàng từ nhà cung cấp |
| ID                     | INTEGER      | Mã định danh duy nhất của sản phẩm |
| Loại sản phẩm          | STRING       | Phân loại sản phẩm (ví dụ: thời trang, điện tử, gia dụng) |
| Mã danh mục            | STRING       | Mã định danh của danh mục sản phẩm |
| Mã danh mục nội bộ     | STRING       | Mã danh mục dùng trong hệ thống nội bộ |
| Mã sản phẩm            | STRING       | Mã SKU hoặc mã sản phẩm duy nhất |
| Mã vạch                | STRING       | Barcode sản phẩm |
| margin % new           | FLOAT        | Tỷ suất lợi nhuận mới được tính theo giá vốn và giá bán |
| Màu sắc                | STRING       | Màu sắc của sản phẩm |
| Tên sản phẩm           | STRING       | Tên hiển thị của sản phẩm |
| Thương hiệu            | STRING       | Tên thương hiệu hoặc nhà sản xuất |
| Trạng thái             | STRING       | Tình trạng sản phẩm (đang bán, ngừng bán, hết hàng) |

---

### 💡 **Mục đích**
> Bảng này lưu trữ thông tin chi tiết về **sản phẩm**, bao gồm giá, danh mục, thương hiệu, và đặc tính vật lý.  
> Giúp phân tích **hiệu quả kinh doanh**, **biên lợi nhuận**, và **xu hướng sản phẩm

## 📊 Dim_mkt_camp_cost

| Tên cột                 | Kiểu dữ liệu | Mô tả |
|--------------------------|--------------|-------|
| Campaign id              | STRING       | Mã định danh chiến dịch marketing |
| Click                    | INTEGER      | Số lượt click trên quảng cáo |
| CPC                      | FLOAT        | Chi phí trung bình cho mỗi lượt click |
| CPM                      | FLOAT        | Chi phí trung bình cho mỗi 1.000 lượt hiển thị |
| CustomerType             | STRING       | Loại khách hàng mục tiêu của chiến dịch |
| Loại ngân sách chiến dịch | STRING       | Phân loại ngân sách (Branding, Conversion, Retargeting, v.v.) |
| Lượt hiển thị            | INTEGER      | Tổng số lượt hiển thị quảng cáo |
| Ngân sách chiến dịch     | FLOAT        | Tổng ngân sách được phân bổ cho chiến dịch |
| Ngày                     | DATE         | Ngày diễn ra hoặc ghi nhận dữ liệu chiến dịch |
| Phân phối chiến dịch     | STRING       | Kênh phân phối quảng cáo (Facebook, Google, TikTok, v.v.) |
| Số tiền đã chi tiêu      | FLOAT        | Tổng chi phí đã sử dụng trong chiến dịch |
| Tên chiến dịch           | STRING       | Tên chiến dịch marketing |

---

### 💡 **Mục đích**
> Bảng này lưu trữ thông tin tổng quan về **chiến dịch marketing**, bao gồm ngân sách, chi phí, lượt hiển thị và hiệu quả tương tác.  
> Giúp phân tích **hiệu suất quảng cáo**, **chi phí theo kênh**, và **hiệu quả đầu tư (ROI)**.

---
# 💰 Fact_order

| Column Name          | Data Type | Description |
|-----------------------|-----------|--------------|
| Ad/direct sales       | STRING    | Kênh bán hàng (quảng cáo hoặc trực tiếp) |
| Cấp độ khách hàng     | STRING    | Phân loại khách hàng (VIP, thân thiết, mới, etc.) |
| Chiết khấu            | FLOAT     | Giá trị chiết khấu áp dụng cho đơn hàng |
| Danh mục sản phẩm     | STRING    | Nhóm sản phẩm theo phân loại kinh doanh |
| factData.Mã Sản phẩm  | STRING    | Mã sản phẩm liên kết với bảng factData |
| Giá                   | FLOAT     | Giá bán thực tế của sản phẩm |
| Giá vốn               | FLOAT     | Giá vốn hoặc chi phí sản xuất của sản phẩm |
| ID                    | INTEGER   | Mã định danh duy nhất cho đơn hàng |
| Lý do hủy             | STRING    | Nguyên nhân hủy đơn hàng (nếu có) |
| Mã khách hàng         | STRING    | Mã định danh khách hàng |
| Mã sản phẩm           | STRING    | Mã SKU sản phẩm trong đơn hàng |
| Mã sản phẩm cha       | STRING    | Mã sản phẩm chính (nếu là biến thể hoặc phiên bản con) |
| Mã vạch               | STRING    | Barcode sản phẩm |
| margin new            | FLOAT     | Tỷ suất lợi nhuận mới được tính theo giá vốn và giá bán |
| Nguồn                 | STRING    | Nguồn đơn hàng (website, Facebook, Shopee, etc.) |
| Phường xã             | STRING    | Địa chỉ chi tiết của khách hàng (phường/xã) |
| Quận huyện            | STRING    | Địa chỉ quận/huyện khách hàng |
| Sản phẩm              | STRING    | Tên sản phẩm trong đơn hàng |
| Sinh nhật             | DATE      | Ngày sinh khách hàng (nếu có) |
| Số lượng              | INTEGER   | Số lượng sản phẩm được mua |
| Tên khách hàng        | STRING    | Họ và tên khách hàng |
| Tên sản phẩm cha      | STRING    | Tên sản phẩm chính (nếu là biến thể) |
| Thành phố             | STRING    | Thành phố khách hàng sinh sống |
| Thời gian             | DATE      | Ngày và giờ đặt đơn hàng |
| Trạng thái            | STRING    | Tình trạng đơn hàng (đã giao, đang xử lý, đã hủy, etc.) |

---

### 💡  **Mục đích**
> Bảng này lưu trữ dữ liệu chi tiết về **đơn hàng và khách hàng**, bao gồm thông tin sản phẩm, giá, chiết khấu, địa chỉ, và trạng thái.  
> Giúp phân tích **doanh thu, lợi nhuận, hành vi mua hàng**, và **hiệu quả kênh bán 

---
## 📈 Fact_mkt_camp_by_sku_cost

| Column Name                | Data Type | Description |
|-----------------------------|-----------|--------------|
| CommentsTheo AM             | INTEGER   | Số lượng bình luận theo Account Manager |
| Inbox + CommentsTheo AM     | INTEGER   | Tổng số tin nhắn và bình luận theo Account Manager |
| InboxTheo AM                | INTEGER   | Số tin nhắn theo Account Manager |
| Tiền đã chạy Theo Sản phẩm  | FLOAT     | Chi phí quảng cáo cho từng sản phẩm |
| Bài chạy theo ngày          | DATE      | Ngày chạy quảng cáo theo bài viết |
| Bình luận về bài viết       | INTEGER   | Tổng bình luận trên bài viết quảng cáo |
| Campaign id                 | STRING    | Mã chiến dịch marketing |
| Click                       | INTEGER   | Số lượt click trên quảng cáo |
| Click theo AM               | INTEGER   | Số click theo Account Manager |
| CP/KQTheo AM                | FLOAT     | Chi phí trên kết quả theo Account Manager |
| CPC                         | FLOAT     | Cost Per Click – Chi phí trên mỗi lượt click |
| CPCTheo AM                  | FLOAT     | CPC theo Account Manager |
| CPM                         | FLOAT     | Cost Per Mille – Chi phí trên 1.000 lượt hiển thị |
| CPMTheo AM                  | FLOAT     | CPM theo Account Manager |
| CTR                         | FLOAT     | Click‑Through Rate – Tỷ lệ click trên hiển thị |
| CTRTheo AM                  | FLOAT     | CTR theo Account Manager |
| Đơn vị tiền tệ              | STRING    | Loại tiền tệ sử dụng (VND, USD, etc.) |
| Giá bán                     | FLOAT     | Giá bán sản phẩm liên quan đến chiến dịch |
| Khách cũTheo AM             | INTEGER   | Số khách hàng cũ theo Account Manager |
| Khách mớiTheo AM            | INTEGER   | Số khách hàng mới theo Account Manager |
| Lần bắt đầu cuộc trò chuyện | INTEGER   | Số cuộc trò chuyện được khởi tạo qua quảng cáo |
| Loại ngân sách chiến dịch   | STRING    | Phân loại ngân sách (Branding, Conversion, etc.) |
| Lượt hiển thị               | INTEGER   | Tổng số lượt hiển thị quảng cáo |
| Lượt hiển thịTheo AM        | INTEGER   | Lượt hiển thị theo Account Manager |
| Mã Sản phẩm                 | STRING    | Mã SKU sản phẩm liên quan đến chiến dịch |
| Ngân sách chiến dịch        | FLOAT     | Tổng ngân sách chiến dịch marketing |
| Ngân sáchTheo sản phẩm      | FLOAT     | Ngân sách phân bổ cho từng sản phẩm |
| Ngày                        | DATE      | Ngày ghi nhận chi phí hoặc hiệu quả chiến dịch |
| Phân phối chiến dịch        | STRING    | Kênh phân phối quảng cáo (Facebook, Google, etc.) |
| SL bán được phân bổ theo t... | INTEGER   | Số lượng bán được phân bổ theo từng chiến dịch |
| SL bán tổng                 | INTEGER   | Tổng số lượng sản phẩm bán ra |
| SL tồn                      | INTEGER   | Số lượng tồn kho liên quan đến chiến dịch |
| Số tiền đã chi tiêu (VND)   | FLOAT     | Tổng chi phí đã chi cho chiến dịch (VND) |
| Tên Bài Chạy                | STRING    | Tên bài viết quảng cáo được chạy |
| Tên chiến dịch              | STRING    | Tên chiến dịch marketing |
| Tên Sản Phẩm                | STRING    | Tên sản phẩm liên quan đến chiến dịch |
| Tên Sản phẩm 2              | STRING    | Tên sản phẩm phụ hoặc phiên bản khác |
| Tin nhắn mới                | INTEGER   | Số tin nhắn mới phát sinh từ chiến dịch |
| Tổng CMT trên SP            | INTEGER   | Tổng bình luận trên sản phẩm |
| Tổng SL bán theo Campaign   | INTEGER   | Tổng số lượng bán theo chiến dịch |

---

### 💡  **Mục đích**
> Bảng này lưu trữ dữ liệu chi tiết về **hiệu quả chiến dịch marketing theo từng SKU**, bao gồm chi phí, lượt hiển thị, tương tác, và doanh số.  
> Giúp phân tích **hiệu suất quảng cáo** và **tối ưu ngân sách** cho từng sản phẩm.

### 🔗 **Liên kết dữ liệu**
<img width="1112" height="343" alt="image" src="https://github.com/user-attachments/assets/a01be390-3388-4ef3-8790-bf0b9e75ed09" />
### 🔗 **Cấu trúc quan hệ**
- **Dim_mkt_camp_cost (1)** → **Fact_mkt_camp_by_sku_cost (*)**  
  → Quan hệ theo `Campaign id` để phân tích chi phí và hiệu quả từng chiến dịch.  
- **Dim_danh_sach_san_pham (1)** → **Fact_mkt_camp_by_sku_cost (*)**  
  → Quan hệ theo `Mã Sản phẩm` để đối chiếu hiệu quả quảng cáo theo sản phẩm.  
- **Dim_danh_sach_san_pham (1)** → **Fact_order (*)**  
  → Quan hệ theo `Mã Sản phẩm` để phân tích doanh thu và lợi nhuận thực tế.  

---
### 2. Vấn đề cần giải quyết 
Xây dựng báo cáo chiến thuật để giúp lãnh đạo công ty hiểu quá trình chi tiêu ngân sách và hiệu suất của các chiến dịch marketing, liên kết doanh thu bán hàng với các chi tiêu marketing, tối ưu hiệu suất ngân sách marketing dựa trên KPIs. Từ đó đề xuất các chiến thuật cải thiện hiệu suất.

## II. Design Thinking ( Tư duy thiết kế )
## STEP 1: Empathyze (Thấu cảm)

<img width="1176" height="627" alt="image" src="https://github.com/user-attachments/assets/1df5b4e0-bc87-4230-b910-310893790a87" />
<img width="1060" height="643" alt="image" src="https://github.com/user-attachments/assets/c748daeb-b301-4a46-b95c-d2907f2bdfcd" />

## STEP 2: Define POV (Nhìn sâu)

<img width="1344" height="639" alt="image" src="https://github.com/user-attachments/assets/4c8497b9-c58f-4937-9d02-61bb25af4fde" />
<img width="1266" height="584" alt="image" src="https://github.com/user-attachments/assets/14e01408-42f4-4b40-97be-790169b44ed4" />

## STEP 3: Ideate (Lên ý tưởng)

<img width="1792" height="570" alt="image" src="https://github.com/user-attachments/assets/e34ba597-d8b6-4f19-8e44-dd4d947f3411" />

## STEP 4:  Prototype and review (tạo mẫu thữ nghiệm và đánh giá)

Choose the type of chart suitable for the questions
Presentation, layout of each part of the report(size, chart arrangement...)
Choose the color of the report
Self-review and edit my report
## III. VISUALIZATION (TRỰC QUAN)
## OVERVIEW 

<img width="1325" height="719" alt="image" src="https://github.com/user-attachments/assets/1e99c1ca-2ae9-4541-8f7e-b25b0c4c7d2a" />

## CAMPAIGN

<img width="1277" height="723" alt="image" src="https://github.com/user-attachments/assets/425305a5-e003-4351-8069-3e8bb94cfbfc" />
<img width="1278" height="723" alt="image" src="https://github.com/user-attachments/assets/b9cedf27-b359-478d-b2d4-a58eabb86d12" />
<img width="1286" height="726" alt="image" src="https://github.com/user-attachments/assets/e1f7cfd1-83cc-4daf-8056-83da5cd7ccd0" />

## PRODUCT ANALYSIS

<img width="1292" height="627" alt="image" src="https://github.com/user-attachments/assets/a8c1deb8-0364-4b0d-8b0c-329343b3be10" />



## IV. INSIGHT AND RECOMENDATION

<img width="1105" height="609" alt="image" src="https://github.com/user-attachments/assets/a65746d6-96be-4aa6-bbd5-84a75879d5c0" />



