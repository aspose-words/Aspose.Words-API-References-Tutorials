---
title: Tùy chọn lưu tài liệu HTML nâng cao với Aspose.Words Java
linktitle: Lưu tài liệu HTML với
second_title: API xử lý tài liệu Java Aspose.Words
description: Trong hướng dẫn này, chúng tôi đã đề cập đến nhiều tùy chọn lưu tài liệu HTML nâng cao với Aspose.Words for Java. Các tùy chọn này cho phép bạn tạo HTML chất lượng cao
type: docs
weight: 16
url: /vi/java/document-loading-and-saving/advance-html-documents-saving-options/
---

Trong hướng dẫn này, chúng ta sẽ khám phá các tùy chọn lưu tài liệu HTML nâng cao do Aspose.Words for Java cung cấp. Aspose.Words là một API Java mạnh mẽ để làm việc với các tài liệu Word và cung cấp nhiều tính năng để thao tác và chuyển đổi tài liệu.

## 1. Giới thiệu
Aspose.Words for Java cho phép bạn làm việc với các tài liệu Word theo chương trình. Trong hướng dẫn này, chúng tôi sẽ tập trung vào các tùy chọn lưu tài liệu HTML nâng cao, cho phép bạn kiểm soát cách các tài liệu Word được chuyển đổi thành HTML.

## 2. Xuất thông tin khứ hồi
Các`exportRoundtripInformation` phương pháp này cho phép bạn xuất tài liệu Word sang HTML trong khi vẫn giữ nguyên thông tin khứ hồi. Thông tin này có thể hữu ích khi bạn muốn chuyển đổi HTML trở lại định dạng Word mà không làm mất bất kỳ chi tiết cụ thể nào của tài liệu.

```java
public void exportRoundtripInformation() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportRoundtripInformation(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
}
```

## 3. Xuất Phông chữ dưới dạng Base64
 Với`exportFontsAsBase64` phương pháp, bạn có thể xuất phông chữ được sử dụng trong tài liệu dưới dạng dữ liệu được mã hóa Base64 trong HTML. Điều này đảm bảo rằng biểu diễn HTML giữ nguyên cùng kiểu phông chữ như tài liệu Word gốc.

```java
@Test
public void exportFontsAsBase64() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportFontsAsBase64(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
}
```

## 4. Xuất tài nguyên
Các`exportResources` phương pháp này cho phép bạn chỉ định loại CSS stylesheet và xuất tài nguyên phông chữ. Bạn cũng có thể thiết lập thư mục tài nguyên và bí danh cho tài nguyên trong HTML.

```java
@Test
public void exportResources() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
    saveOptions.setExportFontResources(true);
    saveOptions.setResourceFolder("Your Directory Path" + "Resources");
    saveOptions.setResourceFolderAlias("http://example.com/resources");
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
}
```

## 5. Chuyển đổi Metafiles sang EMF hoặc WMF
Các`convertMetafilesToEmfOrWmf`Phương pháp này cho phép bạn chuyển đổi các siêu tệp trong tài liệu sang định dạng EMF hoặc WMF, đảm bảo khả năng tương thích và hiển thị mượt mà trong HTML.

```java
@Test
public void convertMetafilesToEmfOrWmf() throws Exception {
    // Đoạn mã không được hiển thị vì lý do ngắn gọn.
}
```

## 6. Chuyển đổi Metafiles sang SVG
 Sử dụng`convertMetafilesToSvg` phương pháp chuyển đổi tệp meta sang định dạng SVG. Định dạng này lý tưởng để hiển thị đồ họa vector trong tài liệu HTML.

```java
@Test
public void convertMetafilesToSvg() throws Exception {
    // Đoạn mã không được hiển thị vì lý do ngắn gọn.
}
```

## 7. Thêm tiền tố tên lớp CSS
 Với`addCssClassNamePrefix` phương pháp, bạn có thể thêm tiền tố vào tên lớp CSS trong HTML đã xuất. Điều này giúp ngăn ngừa xung đột với các kiểu hiện có.

```java
@Test
public void addCssClassNamePrefix() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
    saveOptions.setCssClassNamePrefix("pfx_");
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
}
```

## 8. Xuất URL CID cho Tài nguyên MHTML
Các`exportCidUrlsForMhtmlResources` phương pháp này được sử dụng khi lưu tài liệu ở định dạng MHTML. Nó cho phép xuất URL Content-ID cho các tài nguyên.

```java
@Test
public void exportCidUrlsForMhtmlResources() throws Exception {
    // Đoạn mã không được hiển thị vì lý do ngắn gọn.
}
```

## 9. Giải quyết tên phông chữ
Các`resolveFontNames` Phương pháp này giúp giải quyết tên phông chữ khi lưu tài liệu ở định dạng HTML, đảm bảo hiển thị nhất quán trên các nền tảng khác nhau.

```java
@Test
public void resolveFontNames() throws Exception {
    // Đoạn mã không được hiển thị vì lý do ngắn gọn.
}
```

## 10. Xuất trường biểu mẫu nhập văn bản dưới dạng văn bản
Các`exportTextInputFormFieldAsText` phương pháp này xuất các trường biểu mẫu dưới dạng văn bản thuần túy trong HTML, giúp chúng dễ đọc và chỉnh sửa.

```java
@Test
public void exportTextInputFormFieldAsText() throws Exception {
    // Đoạn mã không được hiển thị vì lý do ngắn gọn.
}
```

## 11. Kết luận
Trong hướng dẫn này, chúng tôi đã khám phá các tùy chọn lưu tài liệu HTML nâng cao do Aspose.Words for Java cung cấp. Các tùy chọn này cung cấp cho bạn quyền kiểm soát chi tiết đối với quá trình chuyển đổi, cho phép bạn tạo các tài liệu HTML gần giống với tài liệu Word gốc.

## 12. Câu hỏi thường gặp
Sau đây là một số câu hỏi thường gặp về cách sử dụng Aspose.Words cho Java và các tùy chọn lưu tài liệu HTML:

### Câu hỏi 1: Làm thế nào tôi có thể chuyển đổi HTML trở lại định dạng Word bằng Aspose.Words cho Java?
 Để chuyển đổi HTML trở lại định dạng Word, bạn có thể sử dụng API Aspose.Words`load` phương pháp tải tài liệu HTML và sau đó lưu ở định dạng Word.

### Câu hỏi 2: Tôi có thể tùy chỉnh kiểu CSS khi xuất sang HTML không?
 Có, bạn có thể tùy chỉnh các kiểu CSS bằng cách sửa đổi các bảng định kiểu được sử dụng trong HTML hoặc bằng cách sử dụng`addCssClassNamePrefix` phương pháp thêm tiền tố vào tên lớp CSS.

### Câu hỏi 3: Có cách nào để tối ưu hóa đầu ra HTML để hiển thị trên web không?
Có, bạn có thể tối ưu hóa đầu ra HTML để hiển thị trên web bằng cách cấu hình các tùy chọn như xuất phông chữ dưới dạng Base64 và chuyển đổi siêu tệp sang SVG.

### Câu hỏi 4: Có hạn chế nào khi chuyển đổi các tài liệu Word phức tạp sang HTML không?
Mặc dù Aspose.Words for Java cung cấp khả năng chuyển đổi mạnh mẽ nhưng các tài liệu Word phức tạp với bố cục phức tạp có thể cần xử lý hậu kỳ bổ sung để đạt được đầu ra HTML mong muốn.
