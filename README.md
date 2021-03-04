# Yêu cầu

#### 1. Dựng trang collection như mẫu (bỏ qua header, footer)
> Link mẫu: https://juno.vn/collections/happy-sale
- [x] Hoàn chỉnh giao diện trang như mẫu
 - [x] Sử dụng collections.template: https://rec.egany.com/sxLKVn
 - [x] Responsive trên các breakpoints: `375px`, `768px`, `1440px`
 - [x] Hiển thị tuỳ chọn màu sắc theo variant Màu sắc: https://rec.egany.com/4wfKQw
--> Không cần đổi hình sản phẩm khi hover vào hình variant
 - [ ] Load Ajax | Viewmore *(điểm cộng)*

#### 2. Document bao gồm:
- [x] Trình bày giải pháp triển khai
- [x] Hướng dẫn cách thiết lập / nhập liệu dữ liệu cho trang demo trên


# Phân tích và Giải pháp 
Dựa theo layout mẫu được giao, có các thành phần chính:
### 1. Banner
**- Phân tích:** Bao gồm ảnh + link khi click vào ảnh
**- Giải pháp:** Lấy từ setting (thiết lập giao diện) bao gồm: `Setting ảnh` & `Setting Link`

### 2. Các tab tương ứng với nhóm sản phẩm
**- Phân tích:** https://rec.egany.com/T4xCHf

 - **[Tính năng 1]** Mỗi tab là một collection, có mô tả của collection đó (collection description)
 - **[Tính năng 2]** Trong mỗi collection sẽ có các tab con dùng để filter sản phẩm (filter theo loại sản phẩm hoặc tag của sản phẩm)

**- Giải pháp:**

**[Tính năng 1]** Để lấy danh sách các link collection, có 2 cách làm:
 ##### **Cách 1:**
> - Thiết lập menu, mỗi menu item trỏ về collection tương ứng
> - Dùng liquid để get menu
--> Search `linklist` trong cheatsheet liquid để biết cách sử dụng: http://cheat.markdunkley.com/
> - Lúc này sẽ lấy được title và link menu tương ứng với collection được thiết lập (`link.title`, `link.url`)

--> *Ưu điểm:* Không bị giới hạn nhóm sản phẩm được thiết lập, khi cần tạo thêm tab collection thì chỉ cần vào phần thiết lập menu, tạo thêm menu là xong
--> *Nhược điểm:* Tốn nhiều thời gian để triển khai. Chỉ phù hợp với nhu cầu thực tế cần tạo vô hạn tab collection

 ##### **Cách 2:**
 > - Lấy từ setting, mỗi setting tương ứng với mỗi tab bao gồm: Tên collection, link collection
 > --> Ví dụ setting cho 1 collection bao gồm tên hiển thị và collection tương ứng: https://rec.egany.com/M0lGvG

--> *Ưu điểm:* Nhanh, đơn giản
--> *Nhược điểm:* Không linh động do số lượng tối đa phụ thuộc vào setting, không tuỳ ý thêm nhiều collection như giải pháp tạo menu

**[Tính năng 2]** Các tab con dùng để filter trong mỗi tab collection:
**Gợi ý:** 
> --> Có thể dùng `loại sản phẩm` hoặc `tag sản phẩm` để làm filter. Trường hợp này dùng loại sản phẩm sẽ đơn giản và phù hợp hơn.

### 3. Variant màu sắc cho mỗi sản phẩm
**Gợi ý:** 
> - Mỗi chấm tròn tương ứng với hình ảnh của variant Màu Sắc
> - Để lấy hình ảnh của variant, search `variant.image` trong checklist [http://cheat.markdunkley.com/](http://cheat.markdunkley.com/)

### 4. Tính năng Xem thêm (Viewmore) 
> Tự phân tích và lên giải pháp 
