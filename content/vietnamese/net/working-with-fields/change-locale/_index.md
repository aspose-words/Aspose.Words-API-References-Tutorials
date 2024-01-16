---
title: Thay đổi ngôn ngữ
linktitle: Thay đổi ngôn ngữ
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách thay đổi ngôn ngữ cho định dạng ngày và số trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/working-with-fields/change-locale/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình thay đổi ngôn ngữ trong tài liệu Word bằng Aspose.Words cho .NET. Bằng cách sửa đổi ngôn ngữ, bạn có thể kiểm soát định dạng ngày và số trong quá trình phối thư. Chúng tôi sẽ cung cấp cho bạn mã nguồn C# cần thiết và hướng dẫn từng bước để đạt được điều này.

## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo rằng bạn có các điều kiện tiên quyết sau:
- Thư viện Aspose.Words for .NET được cài đặt trên hệ thống của bạn.

## Bước 1: Tạo Tài liệu và DocumentBuilder
Để bắt đầu, hãy tạo một thể hiện của lớp Document và đối tượng DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 2: Chèn một trường
Tiếp theo, chèn trường hợp nhất vào tài liệu bằng phương thức InsertField:

```csharp
builder.InsertField("MERGEFIELD Date");
```

Trong đoạn mã trên, chúng tôi chèn trường hợp nhất có tên "Ngày" vào tài liệu.

## Bước 3: Thay đổi ngôn ngữ
Để thay đổi ngôn ngữ cho định dạng ngày và số, bạn có thể sửa đổi văn hóa hiện tại của chuỗi. Trong ví dụ này, chúng tôi sẽ đặt ngôn ngữ thành tiếng Đức ("de-DE"):

```csharp
CultureInfo currentCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("de-DE");
```

Trong đoạn mã trên, chúng tôi lưu trữ văn bản hiện tại và sau đó đặt văn hóa của luồng hiện tại thành tiếng Đức.

## Bước 4: Thực hiện trộn thư
Thực hiện thao tác trộn thư và cung cấp giá trị ngày cho trường "Ngày":

```csharp
doc.MailMerge.Execute(new[] { "Date" }, new object[] { DateTime.Now });
```

Trong đoạn mã này, chúng tôi thực hiện thao tác trộn thư và cung cấp ngày hiện tại làm giá trị cho trường "Ngày".

## Bước 5: Khôi phục ngôn ngữ gốc
Sau khi phối thư hoàn tất, hãy khôi phục văn bản ban đầu cho chuỗi:

```csharp
Thread.CurrentThread.CurrentCulture = currentCulture;
```

Trong đoạn mã trên, chúng tôi khôi phục văn hóa ban đầu của luồng.

## Bước 6: Lưu tài liệu
Lưu tài liệu đã sửa đổi vào một tệp bằng phương thức Lưu của lớp Tài liệu:

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeLocale.docx");
```

### Mã nguồn ví dụ để thay đổi ngôn ngữ bằng Aspose.Words cho .NET
Đây là mã nguồn hoàn chỉnh để thay đổi ngôn ngữ trong tài liệu Word bằng Aspose.Words cho .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField("MERGEFIELD Date");

CultureInfo currentCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("de-DE");

doc.MailMerge.Execute(new[] { "Date" }, new object[] { DateTime.Now });

Thread.CurrentThread.CurrentCulture = currentCulture;

doc.Save(dataDir + "WorkingWithFields.ChangeLocale.docx");
```

## Phần kết luận
Chúc mừng! Bạn đã học thành công cách thay đổi ngôn ngữ trong tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước và sử dụng mã nguồn được cung cấp, giờ đây bạn có thể kiểm soát định dạng ngày và số trong quá trình trộn thư. Tùy chỉnh ngôn ngữ theo yêu cầu của bạn để đảm bảo định dạng chính xác và nhất quán trong tài liệu của bạn.

### Câu hỏi thường gặp

#### Hỏi: Aspose.Words có tương thích với các phiên bản Microsoft Word khác nhau không?

Trả lời: Có, Aspose.Words tương thích với các phiên bản Microsoft Word khác nhau bao gồm Word 2003, Word 2007, Word 2010, Word 2013, Word 2016 và Word 2019.

#### Câu hỏi: Aspose.Words có hỗ trợ các cấu trúc trường phức tạp không?

Đ: Chắc chắn rồi! Aspose.Words cung cấp hỗ trợ rộng rãi cho các cấu trúc trường phức tạp, bao gồm các trường lồng nhau, các phép tính và biểu thức điều kiện. Bạn có thể sử dụng API mạnh mẽ này để làm việc với bất kỳ loại cấu trúc trường nào.

#### Câu hỏi: Aspose.Words có hỗ trợ các hoạt động cập nhật trường không?

Trả lời: Có, Aspose.Words cho phép bạn cập nhật các trường theo lịch trình. Bạn có thể dễ dàng cập nhật giá trị trường, làm mới các phép tính và thực hiện các hoạt động khác liên quan đến trường bằng API.

#### Câu hỏi: Có thể chuyển đổi các trường thành văn bản thuần túy bằng Aspose.Words không?

Đ: Chắc chắn rồi! Aspose.Words cung cấp các phương thức để chuyển đổi các trường thành văn bản thuần túy. Điều này có thể hữu ích khi bạn cần trích xuất nội dung mà không có bất kỳ định dạng hoặc chức năng nào liên quan đến trường.

#### Câu hỏi: Có thể tạo tài liệu Word có trường động bằng Aspose.Words không?

Đ: Chắc chắn rồi! Aspose.Words cung cấp chức năng mạnh mẽ để tạo tài liệu Word với các trường động. Bạn có thể tạo mẫu với các trường được xác định trước và điền dữ liệu vào chúng một cách linh hoạt, cung cấp giải pháp linh hoạt và hiệu quả để tạo tài liệu.