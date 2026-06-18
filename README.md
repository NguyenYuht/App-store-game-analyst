# App-store Game Analyst
Dự án này phân tích thị trường Game Mobile dựa trên bộ dữ liệu trên App Store xuyên suốt 10 năm từ 2008-2019. Từ đó đưa ra các insights để cung cấp lời khuyên cho các nhà phát hành game về thể loại, dung lượng, ngôn ngữ phù hợp cho game mới muốn phát hành ra thị trường.
* **Author:** Nguyễn Thủy | International Business Administration | Foreign Trade University (FTU)
* **Tools:** Excel, Power Query, Microsoft Power BI, DAX
* **Domain:** Game Analyst
---
<details>
<summary><b> ENGLISH VERSION (Click to view details)</b></summary>

<br>

### 1. Project Background & Objective
The dataset contains information on games released on the App Store from 2008 to 2019, a period marked by the rapid growth of smartphones and the App Store ecosystem.

This project aims to identify the characteristics of successful and highly rated games by analyzing factors such as supported languages, app size, download price, genres, and other attributes. Based on these findings, the project provides recommendations for publishers and developers who plan to enter the mobile gaming market.

### 2. Dashboard Overview
*(Download the `.pbix` file in the `Dashboard Image` folder to interact with the report directly.)*

*(Images of all report pages are available in the `Dashboard Image` folder.)*

The dashboard consists of five report pages:

* **Page 1:** OVERVIEW OF THE GAME MARKET (2008–2019)
* **Page 2:** ANALYSIS OF SUPPORTED LANGUAGES IN GAMES
* **Page 3:** GENRE DISTRIBUTION ANALYSIS AND PRICE–GENRE CORRELATION
* **Page 4:** TRENDS IN PRICE AND USER RATINGS FROM 2008 TO 2019
* **Page 5:** TOP 5 GAMES DURING THE TECHNOLOGY BOOM PERIOD (2016–2019)

### 3. Data Processing Workflow & Methodology

* **Excel Processing:**
    * Created two additional tables for in-depth analysis of Languages and Genres by separating multi-value fields.
    * Removed duplicate records based on App ID.

* **Data Cleaning with Power Query:**
    * **Handling 1NF violations:** Used *Split Column by Delimiter* and expanded the `Languages` and `Genres` columns (which contain comma-separated values) into individual rows.
    * **Fixing corrupted text values:** Added a new column named `Name Clear` and applied `Text.Trim`, `Text.Clean`, and `Text.Replace` functions to remove unwanted characters and formatting issues.
    * **Creating analytical columns:** Added a new column named `Languages More` using `if...else` conditions and `Text.Contains` to classify language support into three categories:
        * English
        * English and Other Languages
        * Other Languages
    * Removed rows containing errors.

* **Data Modeling & DAX:**
    * Built dynamic measures using `SUMX`, including the `Profit` measure.

### 4. Key Findings

* Games supporting multiple languages, particularly English combined with other languages, tend to attract more users.
* The top three leading genres remained consistent throughout the years: **Strategy**, **Entertainment**, and **Puzzle**. Other genres such as **Simulation**, **Action**, and **Casual** also ranked among the most popular categories.
* No significant correlation was found between game size and price.
* User satisfaction with game quality has increased over time, as reflected in rising ratings.
* The **Free-to-Play** model has become increasingly dominant. Users are less willing to pay upfront for games and prefer trying them for free. Therefore, developers are encouraged to release games at no cost and generate revenue through **In-App Purchases (IAPs)** and advertisements.
  
</details>

<details>
<summary><b> PHIÊN BẢN TIẾNG VIỆT (Nhấn vào để xem chi tiết)</b></summary>

<br>
### 1. Bối cảnh & Mục tiêu
Bộ dữ liệu bao gồm các game có mặt trên App Store từ năm 2008-2019, giai đoạn Smartphone và App Store bắt đầu bùng nổ. Đi sâu nhằm khai thác để trả lời câu hỏi những game thành công và được đánh giá cao trên App Store sẽ có những đặc điểm gì về Ngôn ngữ sử dụng, Dung lượng, Chi phí để tải app, Thể loại,... Từ đó đưa ra những lời khuyên cho những nhà phát hành muốn gia nhập vào thị trường này.
### 2. Hình ảnh Dashboard
*(Tải file `.pbix` trong thư mục `dashboard Image` để tương tác trực tiếp).*

*(Hình ảnh của các trang báo cáo nằm trong thư mục 'Dashboard Image')*

* Dashboard bao gồm 5 trang:
   * Trang 1: TỔNG QUAN THỊ TRƯỜNG GAME TỪ NĂM 2008-2019
   * Trang 2: PHÂN TÍCH NGÔN NGỮ HỖ TRỢ TRONG GAME
   * Trang 3: PHÂN TÍCH BIẾN THIÊN GENRE VÀ TƯƠNG QUAN PRICE-GENRE
   * Trang 4: XU HƯỚNG GIÁ VÀ RATING BIẾN THIÊN TỪ NĂM 2008 ĐẾN NĂM 2019
   * Trang 5: PHÂN TÍCH TOP 5 GAME TRONG GIAI ĐOẠN BÙNG NỔ CÔNG NGHỆ (2016-2019)

### 3. Quy trình & Phương pháp xử lý dữ liệu
* **Xử lý bằng Excel:**
    * Tạo thêm các 2 bảng đi sâu vào phân tích Languages và Genres để lấy data rã cột cho bước tiếp theo
    * Xóa đi những cột có App ID bị trùng lặp
* **Làm sạch bằng Power Query:**
    * **Xử lý vi phạm 1NF:** Sử dụng *Split Column by Delimiter*, rã thành hàng để rã cột `Languages` và cột Genres (chứa các giá trị ngăn cách bằng dấu phẩy `,`) thành từng dòng độc lập
    * **Xử lý cột bị lỗi dữ liệu:** Add New Column 'Name Clear', dùng hàm Text.Trim, Text.Clean, Text.Replace xử lý các ký tự tạo thành lỗi trong tên
    * **Thêm cột để phân tích:** Tạo thêm cột 'Languages more', sử dụng hàm If else, Text.Contains để biến dữ liệu trong cột 'Languages' thành 3 giá trị (English, English and Others Languages; Others)
    * Remove Error Column
* **Mô hình hóa & DAX:**
    * Xây dựng các Measure động sử dụng `SUMX` ('Profit')
### 4. Kết quả phân tích cốt lõi
    * Ngôn ngữ hỗ trợ trong các game được chơi phổ biến là Đa ngôn ngữ (Tiếng Anh kết hợp với các ngôn ngữ khác)
    * Top 3 thể loại game dẫn đầu không đổi theo từng năm: Strategy, Entertainment và Puzzle. Ngoài ra, các thể loại game như Simulation, Action, Casual,... cũng nằm trong top các thể loại game phổ biến với người dùng.
    * Không có mối tương quan giữa dung lượng và giá cả của game
    * Người dùng ngày càng hài lòng về chất lượng của các game
    * Xu hướng Free-to-play phát triển mạnh, người dùng ngày càng không muốn chi trước để trải nghiệm game. Thay vào đó, các nhà làm game nên phát hành game miễn phí và tập trung vào thu được lợi nhuận từ người dùng thông qua In-app Purchase và Ads.
</details>
