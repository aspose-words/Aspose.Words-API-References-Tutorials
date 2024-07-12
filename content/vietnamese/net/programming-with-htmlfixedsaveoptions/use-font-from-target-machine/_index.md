---
title: Sử dụng phông chữ từ máy mục tiêu
linktitle: Sử dụng phông chữ từ máy mục tiêu
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chuyển đổi tài liệu Word sang HTML cố định bằng cách sử dụng phông chữ của máy mục tiêu với Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-htmlfixedsaveoptions/use-font-from-target-machine/
---

Khi chuyển đổi tài liệu Word sang HTML cố định trong ứng dụng C#, bạn có thể muốn sử dụng phông chữ của máy đích để đảm bảo rằng HTML được hiển thị vẫn giữ nguyên giao diện và kiểu dáng ban đầu của tài liệu. Với thư viện Aspose.Words dành cho .NET, bạn có thể dễ dàng chỉ định chức năng này bằng cách sử dụng tùy chọn lưu HtmlFixedSaveOptions. Trong hướng dẫn từng bước này, chúng tôi sẽ hướng dẫn bạn cách sử dụng mã nguồn C# của Aspose.Words cho .NET để chuyển đổi tài liệu Word sang HTML cố định bằng cách sử dụng phông chữ của máy mục tiêu bằng cách sử dụng HtmlFixedSaveOptions.

## Tìm hiểu thư viện Aspose.Words

Trước khi đi sâu vào mã, điều quan trọng là phải hiểu thư viện Aspose.Words cho .NET. Aspose.Words là một thư viện mạnh mẽ để tạo, chỉnh sửa, chuyển đổi và bảo vệ tài liệu Word trên các nền tảng khác nhau bao gồm .NET. Nó cung cấp nhiều tính năng để thao tác với tài liệu, chẳng hạn như chèn văn bản, thay đổi định dạng, thêm phần và hơn thế nữa.

## Đang tải tài liệu Word

Bước đầu tiên là tải tài liệu Word bạn muốn chuyển đổi sang HTML cố định. Sử dụng lớp Tài liệu để tải tài liệu từ tệp nguồn. Đây là một ví dụ :

```csharp
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");
```

Trong ví dụ này, chúng tôi tải tài liệu "Dấu đầu dòng với phông chữ thay thế.docx" nằm trong thư mục tài liệu.

## Định cấu hình tùy chọn sao lưu

Bước tiếp theo là định cấu hình các tùy chọn lưu để chuyển đổi sang HTML cố định. Sử dụng lớp HtmlFixedSaveOptions và đặt thuộc tính UseTargetMachineFonts thành true để báo cho Aspose.Words sử dụng phông chữ từ máy đích. Đây là cách thực hiện:

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };
```

Chúng tôi tạo một đối tượng HtmlFixedSaveOptions mới và đặt thuộc tính UseTargetMachineFonts thành true để sử dụng phông chữ của máy đích khi chuyển đổi.

## Đã sửa lỗi chuyển đổi tài liệu HTML

Bây giờ chúng ta đã định cấu hình các tùy chọn lưu, chúng ta có thể tiến hành chuyển đổi tài liệu sang HTML cố định. Sử dụng phương thức Lưu của lớp Tài liệu để lưu tài liệu đã chuyển đổi ở định dạng HTML cố định bằng cách chỉ định các tùy chọn lưu. Đây là một ví dụ :

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

Trong ví dụ này, chúng tôi lưu tài liệu đã chuyển đổi dưới dạng "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html" bằng cách sử dụng các tùy chọn lưu đã chỉ định.

### Mã nguồn ví dụ cho HtmlFixedSaveOptions với tính năng "Sử dụng phông chữ từ máy đích" bằng Aspose.Words cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tải tài liệu Word
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");

// Định cấu hình các tùy chọn sao lưu với tính năng "Sử dụng phông chữ từ máy đích"
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };

// Chuyển đổi tài liệu sang HTML cố định
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã giải thích cách chuyển đổi tài liệu Word sang HTML cố định bằng cách sử dụng phông chữ của máy mục tiêu với thư viện Aspose.Words cho .NET. Bằng cách làm theo các bước được cung cấp và sử dụng mã nguồn C# được cung cấp, bạn có thể dễ dàng áp dụng chức năng này trong ứng dụng C# của mình. Việc chuyển đổi sang HTML cố định với phông chữ của máy đích đảm bảo hiển thị tài liệu trung thực và nhất quán ở định dạng HTML.
