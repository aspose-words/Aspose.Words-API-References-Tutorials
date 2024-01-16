---
title: Viết tất cả các quy tắc Css trong một tệp
linktitle: Viết tất cả các quy tắc Css trong một tệp
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chuyển đổi tài liệu Word sang HTML cố định bằng cách viết tất cả các quy tắc CSS vào một tệp duy nhất với Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-htmlfixedsaveoptions/write-all-css-rules-in-single-file/
---

Khi chuyển đổi tài liệu Word sang HTML cố định trong ứng dụng C#, bạn có thể muốn hợp nhất tất cả các quy tắc CSS thành một tệp duy nhất để tổ chức tốt hơn và có tính linh hoạt hơn. Với thư viện Aspose.Words dành cho .NET, bạn có thể dễ dàng chỉ định chức năng này bằng cách sử dụng tùy chọn lưu HtmlFixedSaveOptions. Trong hướng dẫn từng bước này, chúng tôi sẽ hướng dẫn bạn cách sử dụng mã nguồn Aspose.Words for .NET C# để chuyển đổi tài liệu Word sang HTML cố định bằng cách viết tất cả các quy tắc CSS trong một tệp bằng cách sử dụng tùy chọn lưu HtmlFixedSaveOptions.

## Tìm hiểu thư viện Aspose.Words

Trước khi đi sâu vào mã, điều quan trọng là phải hiểu thư viện Aspose.Words cho .NET. Aspose.Words là một thư viện mạnh mẽ để tạo, chỉnh sửa, chuyển đổi và bảo vệ tài liệu Word trên các nền tảng khác nhau bao gồm .NET. Nó cung cấp nhiều tính năng để thao tác với tài liệu, chẳng hạn như chèn văn bản, thay đổi định dạng, thêm phần và hơn thế nữa.

## Đang tải tài liệu Word

Bước đầu tiên là tải tài liệu Word bạn muốn chuyển đổi sang HTML cố định. Sử dụng lớp Tài liệu để tải tài liệu từ tệp nguồn. Đây là một ví dụ :

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

Trong ví dụ này, chúng tôi tải tài liệu "Document.docx" nằm trong thư mục tài liệu.

## Định cấu hình tùy chọn sao lưu

Bước tiếp theo là định cấu hình các tùy chọn lưu để chuyển đổi sang HTML cố định. Sử dụng lớp HtmlFixedSaveOptions và đặt thuộc tính SaveFontFaceCssSeparately thành false để ghi tất cả quy tắc CSS vào một tệp duy nhất. Đây là cách thực hiện:

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };
```

Chúng tôi tạo một đối tượng HtmlFixedSaveOptions mới và đặt thuộc tính SaveFontFaceCssSeparately thành false để ghi tất cả các quy tắc CSS vào một tệp duy nhất.

## Đã sửa lỗi chuyển đổi tài liệu HTML

Bây giờ chúng ta đã định cấu hình các tùy chọn lưu, chúng ta có thể tiến hành chuyển đổi tài liệu sang HTML cố định. Sử dụng phương thức Lưu của lớp Tài liệu để lưu tài liệu đã chuyển đổi ở định dạng HTML cố định bằng cách chỉ định các tùy chọn lưu. Đây là một ví dụ :

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

Trong ví dụ này, chúng tôi lưu tài liệu đã chuyển đổi dưới dạng "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html" bằng cách sử dụng các tùy chọn lưu đã chỉ định.

### Mã nguồn mẫu cho HtmlFixedSaveOptions với tính năng "Viết tất cả quy tắc CSS trong một tệp" bằng Aspose.Words cho .NET

```csharp
// Đường dẫn truy cập vào thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tải tài liệu Word
Document doc = new Document(dataDir + "Document.docx");

// Định cấu hình các tùy chọn sao lưu với tính năng "Viết tất cả các quy tắc CSS trong một tệp"
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };

// Chuyển đổi tài liệu sang HTML cố định
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã đề cập đến cách chuyển đổi tài liệu Word sang HTML cố định bằng cách viết tất cả các quy tắc CSS trong một tệp bằng cách sử dụng HtmlFixedSaveOptions với thư viện Aspose.Words cho .NET. Bằng cách làm theo các bước được cung cấp và sử dụng mã nguồn C# được cung cấp, bạn có thể dễ dàng áp dụng chức năng này trong ứng dụng C# của mình. Viết tất cả các quy tắc CSS vào một tệp giúp việc tổ chức và quản lý mã HTML được tạo trong quá trình chuyển đổi tài liệu trở nên dễ dàng hơn.