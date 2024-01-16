---
title: Đơn vị đo lường
linktitle: Đơn vị đo lường
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chỉ định đơn vị đo khi chuyển đổi tài liệu Word sang ODT bằng Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/programming-with-odtsaveoptions/measure-unit/
---

Khi bạn chuyển đổi tài liệu Word sang định dạng Văn bản OpenDocument (ODT) trong ứng dụng C#, bạn có thể muốn chỉ định đơn vị đo lường được sử dụng cho các thuộc tính nội dung và định dạng có thể đo lường được. Với thư viện Aspose.Words dành cho .NET, bạn có thể dễ dàng chỉ định chức năng này bằng cách sử dụng các tùy chọn lưu OdtSaveOptions. Trong hướng dẫn từng bước này, chúng tôi sẽ hướng dẫn bạn cách sử dụng mã nguồn Aspose.Words for .NET C# để chuyển đổi tài liệu Word sang ODT bằng cách chỉ định đơn vị đo bằng OdtSaveOptions.

## Tìm hiểu thư viện Aspose.Words

Trước khi đi sâu vào mã, điều quan trọng là phải hiểu thư viện Aspose.Words cho .NET. Aspose.Words là một thư viện mạnh mẽ để tạo, chỉnh sửa, chuyển đổi và bảo vệ tài liệu Word trên các nền tảng khác nhau bao gồm .NET. Nó cung cấp nhiều tính năng để thao tác với tài liệu, chẳng hạn như chèn văn bản, thay đổi định dạng, thêm phần và hơn thế nữa.

## Đang tải tài liệu Word

Bước đầu tiên là tải tài liệu Word bạn muốn chuyển đổi sang ODT. Sử dụng lớp Tài liệu để tải tài liệu từ tệp nguồn. Đây là một ví dụ :

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

Trong ví dụ này, chúng tôi tải tài liệu "Document.docx" nằm trong thư mục tài liệu.

## Định cấu hình tùy chọn sao lưu

Bước tiếp theo là định cấu hình các tùy chọn sao lưu để chuyển đổi sang ODT. Sử dụng lớp OdtSaveOptions và đặt thuộc tính MeasureUnit thành giá trị mong muốn. Ví dụ: nếu bạn muốn sử dụng inch làm đơn vị đo, hãy đặt MeasureUnit thành OdtSaveMeasureUnit.Inches. Đây là cách thực hiện:

```csharp
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };
```

Chúng tôi tạo một đối tượng OdtSaveOptions mới và đặt thuộc tính MeasureUnit thành giá trị mong muốn, trong trường hợp của chúng tôi là OdtSaveMeasureUnit.Inches để sử dụng inch làm đơn vị đo lường.

## Chuyển đổi tài liệu sang ODT

Bây giờ chúng ta đã định cấu hình các tùy chọn lưu, chúng ta có thể tiến hành chuyển đổi tài liệu sang ODT. Sử dụng phương thức Lưu của lớp Tài liệu để lưu tài liệu đã chuyển đổi ở định dạng ODT bằng cách chỉ định các tùy chọn lưu. Đây là một ví dụ :

```csharp
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

Trong ví dụ này, chúng tôi lưu tài liệu đã chuyển đổi dưới dạng "WorkingWithOdtSaveOptions.MeasureUnit.odt" bằng cách sử dụng các tùy chọn lưu đã chỉ định.

### Mã nguồn mẫu cho OdtSaveOptions với chức năng "Đơn vị đo lường" sử dụng Aspose.Words cho .NET



```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tải tài liệu Word
Document doc = new Document(dataDir + "Document.docx");

// Cấu hình các tùy chọn dự phòng với tính năng “Đơn vị đo lường”
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };

// Chuyển đổi tài liệu sang ODT
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã giải thích cách chuyển đổi tài liệu Word sang ODT bằng cách chỉ định đơn vị đo bằng cách sử dụng tùy chọn lưu OdtSaveOptions với thư viện Aspose.Words cho .NET. Bằng cách làm theo các bước được cung cấp và sử dụng mã nguồn C# được cung cấp, bạn có thể dễ dàng áp dụng chức năng này trong ứng dụng C# của mình. Việc chỉ định đơn vị đo khi chuyển đổi sang ODT cho phép bạn kiểm soát định dạng và kích thước của tài liệu thu được theo nhu cầu cụ thể của mình.