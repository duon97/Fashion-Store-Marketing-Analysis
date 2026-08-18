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

<img width="1032" height="685" alt="image" src="https://github.com/user-attachments/assets/55ed8707-7279-46bc-9103-e4da74fa216f" />
<img width="1037" height="682" alt="image" src="https://github.com/user-attachments/assets/909051d6-7fe1-409f-aea0-20c6e7aeca42" />
<img width="1072" height="678" alt="image" src="https://github.com/user-attachments/assets/ba7c52bb-1cbd-4765-8756-7364ca6d0ada" />

## PRODUCT ANALYSIS

<img width="1103" height="695" alt="image" src="https://github.com/user-attachments/assets/836f4472-1dc7-4f05-aaff-21d26e0a93b9" />



## IV. INSIGHT AND RECOMENDATION

I. Insight

I. Insight

1. Campaign Insight: Lookalike

Tổng quan: Lookalike ghi nhận khoản lỗ khoảng 107.9 tỷ. Nguyên nhân chính không đến từ chi phí quảng cáo cao hay giá vốn cao mà do Lookalike đang tập trung vào các sản phẩm có giá trị đơn hàng thấp hơn khoảng 200K so với hai nhóm còn lại. AOV chỉ đạt 1.17M trong khi giá vốn mỗi đơn khoảng 1.14M, khiến gross margin mỗi đơn chỉ còn khoảng 30 đến 50K, không đủ bù chi phí quảng cáo 130 đến 180K mỗi đơn. Vì vậy, càng scale ngân sách càng làm gia tăng mức lỗ.

AUDREY SHIRT: Ghi nhận khoản lỗ khoảng 108M trong 4 tuần liên tiếp và là campaign có ảnh hưởng lớn nhất đến toàn bộ segment. Spend tăng từ W2 đến W3 thay vì được tắt, cho thấy campaign có thể đang được tối ưu theo revenue thay vì profit.

NALANI & MIRENA SKIRT: Ghi nhận khoản lỗ khoảng 15M trong W2 và W3, với margin mỗi đơn âm từ 50K đến 139K. Campaign đã được tắt sau W3, đây là quyết định phù hợp.

Các campaign có profit dương ổn định: FLOWERS MAKE MY DAY đạt 2.57M ở W1, 2.36M ở W2 và 4.69M ở W3, cho thấy hiệu quả bền vững nhất. YOU DESERVE THE MOST BEAUTIFUL THINGS cũng duy trì lợi nhuận dương trong W1 đến W3. DELIA SET, MACY JUMPSUIT, MELI DRESS và KATY DRESS đều ghi nhận lợi nhuận trong W4 đến W5.

Kết luận: Lookalike không hoàn toàn kém hiệu quả mà bị kéo xuống bởi một số campaign có mức lỗ lớn. AUDREY SHIRT là vấn đề chính do giá vốn không phù hợp, khiến mỗi đơn hàng tạo ra lợi nhuận âm. Việc tiếp tục scale campaign làm mức lỗ tăng nhanh hơn.

Vấn đề hệ thống: Margin mỗi đơn âm khoảng 140K là vấn đề liên quan đến cấu trúc giá sản phẩm và không phụ thuộc trực tiếp vào quảng cáo. Ngoài ra, campaign đã có ROAS dưới ngưỡng hòa vốn từ W2 nhưng vẫn tiếp tục scale trong ba tuần. Việc thiết lập cảnh báo tự động khi ROAS dưới ngưỡng hoặc Profit âm có thể giúp hạn chế khoản lỗ đáng kể.

2. Campaign Insight: Open/Cold

AUDREY SHIRT không chỉ ảnh hưởng đến Lookalike mà còn tác động tiêu cực đến Open/Cold.

Một số campaign có mức lỗ lớn khác gồm TH 5.5 NEW ARRIVAL, STAY ELEGANT, FABRIC FOR SUMMER, NEVA SHIRT & ZUZIE SHORT và SERINA & MANDY OUTFIT OF TODAY. Pattern chung là các campaign mới được launch với margin âm, sau đó được scale mạnh trước khi phát hiện vấn đề về profitability.

Hero campaign nổi bật: AVIAN DRESS đạt 9.79M, KATY DRESS đạt 7.49M và DANICA DRESS đạt 5.65M trong W3. MARGNET DRESS đạt 15.67M trong W4. LISA DRESS đạt 9.94M và 5.24M, trong khi NEVIN DRESS đạt 6.37M trong W5.

Kết luận: Open/Cold có khả năng tạo lợi nhuận cao khi kết hợp đúng sản phẩm, nhưng hiệu quả tổng thể bị ảnh hưởng bởi các campaign có margin âm chạy đồng thời.

3. Campaign Insight: Retargeting

AUDREY SHIRT xuất hiện ở cả ba segment và ảnh hưởng tiêu cực đến toàn bộ hệ thống. TH 5.5 NEW ARRIVAL là campaign có mức ảnh hưởng lớn thứ hai, đặc biệt đáng chú ý trong Retargeting.

Trong W3, các Hero campaign gồm AVIAN, KATY, DANICA ở Open/Cold và SENSE OF ELEGANCE, LUCIE DRESS, VERENA SET ở Retargeting. Open/Cold có nhiều Hero campaign mạnh hơn nên có khả năng bù đắp khoản lỗ tốt hơn.

Nghịch lý Retargeting: Về lý thuyết, Retargeting có khả năng mang lại lợi nhuận cao hơn Open/Cold do conversion cao, chi phí quảng cáo trên mỗi đơn thấp và AOV tương đương. Tuy nhiên, thực tế Retargeting lại chịu mức lỗ lớn do tập trung retarget các sản phẩm có margin âm.

TH 5.5 NEW ARRIVAL là ví dụ điển hình khi ghi nhận khoản lỗ 8.36M trong W2 Retargeting, trong khi Open/Cold của cùng campaign chỉ lỗ 4.38M.

4. Product Insight

Danh mục cần dừng: Áo Tách Set và Chân Váy Tách Set có margin âm và là nguyên nhân chính khiến Lookalike ghi nhận mức lỗ lớn.

Danh mục nên scale: Set Váy Áo có margin cao nhất ở mức 0.37 và AOV 1.9M. Váy Chiết Eo Xoè có margin 0.25 và revenue cao nhất trong Open/Cold. Đây là hai danh mục có tiềm năng tạo lợi nhuận tốt.

Thương hiệu: Hoa là brand duy nhất có profit dương. Trừu Tượng ghi nhận khoản lỗ khoảng 0.2bn dù margin gần bằng 0, cho thấy chiến lược sử dụng volume để bù đắp margin thấp không bền vững.

SKU Retargeting: Green Flower Set có margin cao nhất ở mức 0.35 nhưng chưa được khai thác đúng mức. Nelia Set và Delia Set là hai SKU có hiệu quả tốt nhất.

II. Recommendation theo ROAS/ROI
ROAS cao, ROI dương → Scale ngân sách có kiểm soát (tăng 10–20%), duy trì creative và target hiện tại.
ROAS cao, ROI âm → Tối ưu CPM/CPC, thử A/B test creative, hoặc điều chỉnh giá sản phẩm trước khi scale.
ROAS thấp, ROI dương → Mở rộng tệp khách hàng hoặc tăng ngân sách nhẹ để kiểm tra tiềm năng tăng trưởng.
ROAS thấp, ROI âm → Tạm dừng hoặc giảm mạnh ngân sách, phân tích lại target và creative, chỉ tiếp tục khi có cải thiện rõ rệt.



