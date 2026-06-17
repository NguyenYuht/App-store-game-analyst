# App-store Game Analyst
Dự án này phân tích thị trường Game Mobile dựa trên bộ dữ liệu trên App Store xuyên suốt 10 năm từ 2008-2019. Từ đó đưa ra các insights để cung cấp lời khuyên cho các nhà phát hành game về thể loại, dung lượng, ngôn ngữ phù hợp cho game mới muốn phát hành ra thị trường.
* **Author:** Nguyễn Thủy | International Business Administration | Foreign Trade University (FTU)
* **Tools:** Excel, Power Query, Microsoft Power BI, DAX
* **Domain:** Game Analyst
---
### 1. Bối cảnh & Mục tiêu
Bộ dữ liệu bao gồm các game có mặt trên App Store từ năm 2008-2019, giai đoạn Smartphone và App Store bắt đầu bùng nổ. Đi sâu nhằm khai thác để trả lời câu hỏi những game thành công và được đánh giá cao trên App Store sẽ có những đặc điểm gì về Ngôn ngữ sử dụng, Dung lượng, Chi phí để tải app, Thể loại,... Từ đó đưa ra những lời khuyên cho những nhà phát hành muốn gia nhập vào thị trường này.
### 2. Hình ảnh Dashboard
*(Tải file `.pbix` trong thư mục `dashboard_ASGA` để tương tác trực tiếp).*

*(Dưới đây là hình ảnh của các trang báo cáo)*

**Trang 1: TỔNG QUAN THỊ TRƯỜNG GAME TỪ NĂM 2008-2019**

**Trang 2: PHÂN TÍCH NGÔN NGỮ HỖ TRỢ TRONG GAME**

**Trang 3: PHÂN TÍCH BIẾN THIÊN GENRE VÀ TƯƠNG QUAN PRICE-GENRE**

**Trang 4: XU HƯỚNG GIÁ VÀ RATING BIẾN THIÊN TỪ NĂM 2008 ĐẾN NĂM 2019**

**Trang 5: PHÂN TÍCH TOP 5 GAME TRONG GIAI ĐOẠN BÙNG NỔ CÔNG NGHỆ (2016-2019)**

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
  
