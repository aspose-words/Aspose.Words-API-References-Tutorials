---
title: Hiển thị các bản sửa đổi trong bong bóng
linktitle: Hiển thị các bản sửa đổi trong bong bóng
second_title: API xử lý tài liệu Aspose.Words
description: Hiển thị các bản sửa đổi trong bong bóng với Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/working-with-revisions/show-revisions-in-balloons/
---

Trong hướng dẫn từng bước này, chúng tôi sẽ chỉ cho bạn cách hiển thị các bản sửa đổi dưới dạng bong bóng trong tài liệu Word bằng Aspose.Words cho .NET. Chúng tôi sẽ cung cấp cho bạn mã nguồn hoàn chỉnh và chỉ cho bạn cách định dạng đầu ra đánh dấu.

## Bước 1: Tải tài liệu

Bước đầu tiên là tải lên tài liệu có chứa các bản sửa đổi.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## Bước 2: Định cấu hình tùy chọn hiển thị đánh giá

Chúng tôi sẽ định cấu hình các tùy chọn hiển thị để hiển thị các bản sửa đổi trong bong bóng.

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;
```

## Bước 3: Lưu tài liệu ở định dạng PDF

Cuối cùng, chúng tôi sẽ lưu tài liệu dưới dạng PDF với các bản sửa đổi được hiển thị trong bong bóng.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## Định dạng đầu ra đánh dấu

Đầu ra có thể được định dạng trong markdown để cải thiện khả năng đọc. Ví dụ :

```markdown
- Revisions are Showed in bubbles with revision bars on the right side.
```

### Mã nguồn ví dụ cho Hiển thị các bản sửa đổi trong bong bóng bằng Aspose.Words cho .NET

Đây là mã nguồn hoàn chỉnh để hiển thị các bản sửa đổi dưới dạng bong bóng trong tài liệu bằng Aspose.Words cho .NET:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(MyDir + "Revisions.docx");

// Trình kết xuất chèn các bản sửa đổi nội tuyến, xóa và định dạng các bản sửa đổi trong bóng chú thích.
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
// Hiển thị các thanh sửa đổi ở phía bên phải của trang.
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;

doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách hiển thị các bản sửa đổi dưới dạng bong bóng trong tài liệu Word bằng Aspose.Words cho .NET. Bằng cách sử dụng các tùy chọn hiển thị thích hợp, chúng tôi có thể hiển thị các bản sửa đổi trong bong bóng với các thanh sửa đổi ở bên phải. Aspose.Words for .NET cung cấp nhiều tính năng mạnh mẽ để thao tác với tài liệu Word, bao gồm cả quản lý sửa đổi. Giờ đây, bạn có thể sử dụng kiến thức này để hiển thị các bản sửa đổi dưới dạng bong bóng trong tài liệu Word của riêng mình bằng cách sử dụng Aspose.Words for .NET.


### Câu hỏi thường gặp

#### Hỏi: Làm cách nào để tải lên tài liệu trong Aspose.Words cho .NET?

 Đáp: Hãy sử dụng`Document` lớp Aspose.Words dành cho .NET để tải tài liệu từ một tệp. Bạn có thể chỉ định đường dẫn tài liệu đầy đủ.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Hỏi: Làm cách nào để hiển thị các bản sửa đổi trong bong bóng bằng Aspose.Words cho .NET?

 Đáp: Hãy sử dụng`ShowInBalloons` tài sản của`RevisionOptions` đối tượng để định cấu hình hiển thị các bản sửa đổi trong bong bóng. Bạn có thể đặt thuộc tính này trên`ShowInBalloons.FormatAndDelete` để hiển thị các bản sửa đổi trong bong bóng với các bản sửa đổi bị xóa và định dạng.

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
```

#### Hỏi: Làm cách nào để lưu tài liệu ở định dạng PDF bằng Aspose.Words cho .NET?

 Đáp: Hãy sử dụng`Save` phương pháp của`Document` đối tượng để lưu tài liệu ở định dạng PDF. Bạn phải chỉ định đường dẫn đích đầy đủ có phần mở rộng ".pdf".

```csharp
doc.Save("path/to/destination/document.pdf");
```