# **Cách viết một Lab Guide**

## **I. Phần 1: Chuẩn bị**

### 1. **Tải Hugo Theme**
- Sử dụng [**Theme Hugo**](https://gohugo.io/) cho Lab guide. Cài đặt Hugo theo hướng dẫn [tại đây](https://gohugo.io/getting-started/installing/).
- Kiểm tra cài đặt bằng cách gõ lệnh sau trong **Terminal/CMD/PowerShell**:
  ```bash
  hugo version
  ```

### 2. **Tải IDE**
- Cài đặt [Visual Studio Code](https://code.visualstudio.com/download) hoặc bất kỳ IDE nào bạn thích.
- Đảm bảo IDE có plug-ins hỗ trợ Markdown như **Markdown All in One**, **Markdown TOC**, v.v.

### 3. **Tải Snagit 2019**
- Sử dụng Snagit 2019 để chụp màn hình và chỉnh sửa hình ảnh cho Lab Guide.

### 4. **Tải Active Presenter**
- Tải về [Active Presenter](https://atomisystems.com/download/) để quay video các bước thực hiện trong Lab.

### 5. **Tải Draw.io**
- Vẽ diagram với [Draw.io](https://www.diagrams.net/). Tải về bộ icon AWS [tại đây](https://aws.amazon.com/vi/architecture/icons/).

**Lưu ý:** Tuân thủ format và style của sư phụ Gia Hưng khi vẽ diagrams.

## **II. Phần 2: Nội dung**

### 1. **Cấu trúc file**

#### **Thư mục *content***
- Tổ chức bài Lab với 2 cấp độ (VD: **2. -> 2.1.**).
- Mỗi thư mục chứa:
  - Các thư mục thứ cấp.
  - Tập tin **_index.md** (Tiếng Anh) và **_index.vi.md** (Tiếng Việt).
  
  *Nếu chỉ viết guide tiếng Việt, sao chép **_index.vi.md** và đổi tên thành **_index.md**.*

#### **Thư mục *static/images***
- Chứa ảnh cho Lab Guide.
- Sử dụng thẻ gán ảnh trong Markdown như sau:
  ```md
  ![Tên ảnh](/images/2.1/SNAG001.png?width=90pc)
  ```
  - Dùng `?width=90pc` cho ảnh toàn màn hình, `?width=40pc` hoặc `?width=50pc` cho ảnh crop.

#### **Thư mục *public***
- Thư mục này sẽ được tạo bởi Hugo khi bạn build project.
- Để build project, sử dụng lệnh:
  ```bash
  hugo
  ```
- Để xem guide trên server, chạy lệnh sau:
  ```bash
  hugo server
  ```

### 2. **Nội dung**

1. **Thực hiện bài Hand-on Lab** một lần để nắm các bước.
2. **Lên cấu trúc** Lab Guide và thư mục tương ứng.
3. **Clean up** và **thực hiện lại** bài Lab, quay phim hoặc screenshot từng bước.
4. **Viết nội dung** cho Lab Guide và đặt placeholder cho hình ảnh.
5. **Trích xuất hình ảnh** từ video nếu có và đặt vào vị trí xác định.
6. **Crop hình ảnh**, loại bỏ khung viền browser.
7. **Kiểm tra** và **format** lại nội dung với [Notice](https://learn.netlify.app/en/shortcodes/notice/) và bổ sung các [Tập tin đính kèm](https://learn.netlify.app/en/shortcodes/attachments/).

#### **Phần tiêu đề**
```yaml
+++
title = "Viết nội dung"
date = 2020
weight = 2
chapter = false
pre = "<b>2. </b>"
+++
```

#### **Phần heading**
- Sử dụng h4 (`####`) cho các tiêu đề section.

#### **Phần Table of Contents (TOC)**
- Sử dụng plug-in **Markdown All in One** để tạo TOC tự động:
  - `Ctrl + Shift + P` -> **Create Table of Contents**

#### **Phần ghi chú**
- Sử dụng shortcode cho các đoạn ghi chú, cảnh báo, etc.:
  ```yaml
  {{% notice note %}} Đây là Note {{% /notice %}}
  {{% notice info %}} Đây là Info {{% /notice %}}
  {{% notice tip %}} Đây là Tip {{% /notice %}}
  {{% notice warning %}} Đây là Warning {{% /notice %}}
  ```

#### **Phần tập tin đính kèm**
- Tạo tập tin đính kèm với shortcode:
  ```yaml
  {{% attachments title="Dockerfile" pattern="Dockerfile" %}}
  ```

#### **Phần vẽ bảng**
- Sử dụng [Tables Generator](https://www.tablesgenerator.com/markdown_tables) để tạo bảng trong Markdown.

#### **Phần hình ảnh**
1. **Phần mềm chụp màn hình:** Sử dụng SnagIt (2019/2020).
2. **Thiết kế hình ảnh:**
   - **Trình duyệt:** Chrome, tắt Bookmark bar.
   - **Zoom:** 100%.
   - **Độ phân giải:** FullHD (1920 x 1080).
   - **Font:** Arial Black, Size: 18, không bật Shadow.
   - **Khung đánh dấu:** Màu trùng với màu chữ, độ dày 1 px, độ mờ 100%.

### **Update config.toml**

```toml
[Languages.en]
title = "How to Write a Lab Guide"
weight = 1
languageName = "English"

[Languages.vi]
title = "Cách viết một Lab Guide"
weight = 2
languageName = "Tiếng Việt"
```

# **Cre:** Sư Huynh Minh Lê, Sư Huynh Thanh Hiệp.

