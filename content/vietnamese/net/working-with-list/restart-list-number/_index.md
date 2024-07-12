---
title: Khởi động lại số danh sách
linktitle: Khởi động lại số danh sách
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách đặt lại số danh sách trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/working-with-list/restart-list-number/
---
Trong hướng dẫn từng bước này, chúng tôi sẽ chỉ cho bạn cách đặt lại số danh sách trong tài liệu Word bằng Aspose.Words cho .NET. Chúng tôi sẽ giải thích mã nguồn C# được cung cấp và chỉ cho bạn cách triển khai nó trong các dự án của riêng bạn.

 Để bắt đầu, hãy đảm bảo bạn đã cài đặt và định cấu hình Aspose.Words for .NET trong môi trường phát triển của mình. Nếu bạn chưa có, hãy tải xuống và cài đặt thư viện từ[Aspose.Releases]https://releases.aspose.com/words/net/.

## Bước 1: Tạo tài liệu và trình tạo tài liệu

Đầu tiên, tạo một tài liệu mới và trình tạo tài liệu liên quan:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 2: Tạo và tùy chỉnh danh sách đầu tiên

Tiếp theo, tạo danh sách dựa trên mẫu hiện có, sau đó tùy chỉnh các cấp độ của mẫu đó:

```csharp
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;
```

## Bước 3: Thêm các mục vào danh sách đầu tiên

Sử dụng trình tạo tài liệu để thêm các mục vào danh sách đầu tiên và xóa số danh sách:

```csharp
builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## Bước 4: Tạo và tùy chỉnh danh sách thứ hai

Để sử dụng lại danh sách đầu tiên bằng cách đặt lại số, hãy tạo bản sao bố cục danh sách gốc:

```csharp
List list2 = doc.Lists.AddCopy(list1);
list2.ListLevels[0].StartAt = 10;
```

Bạn cũng có thể thực hiện các thay đổi bổ sung cho danh sách thứ hai nếu cần.

## Bước 5: Thêm các mục vào danh sách thứ hai

Sử dụng lại trình tạo tài liệu để thêm các mục vào danh sách thứ hai và xóa số danh sách:

```csharp
builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## Bước 6: Lưu tài liệu đã sửa đổi

Cuối cùng, lưu tài liệu đã sửa đổi:

```csharp
builder.Document.Save(dataDir + "ResetListNumber.docx");
```

Vì thế ! Bạn đã đặt lại thành công số danh sách trong tài liệu Word bằng Aspose.Words for .NET.

### Mã nguồn mẫu để đặt lại số danh sách

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Tạo một danh sách dựa trên một mẫu.
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;

builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

// Để sử dụng lại danh sách đầu tiên, chúng ta cần bắt đầu lại việc đánh số bằng cách tạo bản sao của định dạng danh sách ban đầu.
List list2 = doc.Lists.AddCopy(list1);

// Chúng tôi có thể sửa đổi danh sách mới theo bất kỳ cách nào, bao gồm cả việc đặt số bắt đầu mới.
list2.ListLevels[0].StartAt = 10;

builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

builder.Document.Save(dataDir + "WorkingWithList.RestartListNumber.docx");
            
```

### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào tôi có thể bắt đầu lại việc đánh số danh sách trong Aspose.Words?

 Trả lời: Để khởi động lại việc đánh số danh sách trong Aspose.Words, bạn có thể sử dụng`ListRestartAtNumber` phương pháp của`List` lớp học. Phương pháp này cho phép bạn đặt một giá trị quay số mới để khởi động lại danh sách. Ví dụ, bạn có thể sử dụng`list.ListRestartAtNumber(1)` để bắt đầu lại việc đánh số từ 1.

#### Câu hỏi: Có thể tùy chỉnh tiền tố và hậu tố của việc đánh số danh sách được khởi động lại trong Aspose.Words không?

 Trả lời: Có, bạn có thể tùy chỉnh tiền tố và hậu tố của việc đánh số danh sách được khởi động lại trong Aspose.Words. Các`ListLevel` lớp cung cấp các thuộc tính như`ListLevel.NumberPrefix`Và`ListLevel.NumberSuffix`cho phép bạn chỉ định tiền tố và hậu tố cho từng cấp độ trong danh sách. Bạn có thể sử dụng các thuộc tính này để tùy chỉnh tiền tố và hậu tố nếu cần.

#### Câu hỏi: Làm cách nào tôi có thể chỉ định một giá trị đánh số cụ thể mà từ đó danh sách sẽ được khởi động lại?

 Đáp: Để chỉ định một giá trị số cụ thể mà từ đó danh sách sẽ được khởi động lại, bạn có thể sử dụng`ListRestartAtNumber` phương thức truyền giá trị mong muốn làm đối số. Ví dụ: để bắt đầu lại việc đánh số từ 5, bạn có thể sử dụng`list.ListRestartAtNumber(5)`.

#### Câu hỏi: Có thể khởi động lại việc đánh số danh sách nhiều cấp trong Aspose.Words không?

 Trả lời: Có, Aspose.Words hỗ trợ khởi động lại việc đánh số nhiều cấp độ danh sách. Bạn có thể áp dụng`ListRestartAtNumber` ở mỗi cấp danh sách để bắt đầu lại việc đánh số riêng lẻ. Ví dụ, bạn có thể sử dụng`list.Levels[0].ListRestartAtNumber(1)` để khởi động lại cấp danh sách đầu tiên từ 1 và`list.Levels[1].ListRestartAtNumber(1)` để khởi động lại danh sách cấp độ thứ hai bắt đầu từ 1, v.v.



