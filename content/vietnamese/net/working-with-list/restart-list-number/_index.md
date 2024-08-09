---
title: Khởi động lại số danh sách
linktitle: Khởi động lại số danh sách
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách khởi động lại số danh sách trong tài liệu Word bằng Aspose.Words for .NET. Hướng dẫn chi tiết, 2000 từ này bao gồm mọi thứ bạn cần biết, từ thiết lập đến tùy chỉnh nâng cao.
type: docs
weight: 10
url: /vi/net/working-with-list/restart-list-number/
---
## Giới thiệu

Bạn đang muốn nắm vững nghệ thuật thao tác danh sách trong tài liệu Word của mình bằng Aspose.Words cho .NET? Vâng, bạn đang ở đúng nơi! Trong hướng dẫn này, chúng ta sẽ đi sâu vào việc khởi động lại số danh sách, một tính năng tiện lợi sẽ nâng kỹ năng tự động hóa tài liệu của bạn lên một tầm cao mới. Hãy thắt dây an toàn và bắt đầu nào!

## Điều kiện tiên quyết

Trước khi chúng ta chuyển sang mã, hãy đảm bảo bạn có mọi thứ bạn cần:

1.  Aspose.Words for .NET: Bạn cần cài đặt Aspose.Words for .NET. Nếu bạn chưa cài đặt nó, bạn có thể[tải nó ở đây](https://releases.aspose.com/words/net/).
2. Môi trường phát triển: Đảm bảo bạn có môi trường phát triển phù hợp như Visual Studio.
3. Kiến thức cơ bản về C#: Hiểu biết cơ bản về C# sẽ giúp bạn làm theo hướng dẫn.

## Nhập không gian tên

Trước tiên, hãy nhập các không gian tên cần thiết. Đây là những điều quan trọng để truy cập các tính năng của Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Lists;
using System.Drawing;
```

Bây giờ, hãy chia quy trình thành các bước dễ thực hiện. Chúng tôi sẽ đề cập đến mọi thứ từ việc tạo danh sách đến bắt đầu lại việc đánh số.

## Bước 1: Thiết lập tài liệu và trình tạo của bạn

Trước khi có thể bắt đầu thao tác với danh sách, bạn cần có tài liệu và DocumentBuilder. DocumentBuilder là công cụ dùng để thêm nội dung vào tài liệu của bạn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 2: Tạo và tùy chỉnh danh sách đầu tiên của bạn

Tiếp theo, chúng tôi sẽ tạo một danh sách dựa trên mẫu và tùy chỉnh giao diện của nó. Trong ví dụ này, chúng tôi đang sử dụng định dạng số Ả Rập có dấu ngoặc đơn.

```csharp
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;
```

Ở đây, chúng ta đã thiết lập màu chữ thành màu đỏ và căn chỉnh văn bản về bên phải.

## Bước 3: Thêm các mục vào danh sách đầu tiên của bạn

 Với danh sách của bạn đã sẵn sàng, đã đến lúc thêm một số mục. Trình tạo tài liệu`ListFormat.List` thuộc tính giúp áp dụng định dạng danh sách cho văn bản.

```csharp
builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();
```

## Bước 4: Khởi động lại việc đánh số danh sách

Để sử dụng lại danh sách và bắt đầu lại việc đánh số, bạn cần tạo một bản sao của danh sách gốc. Điều này cho phép bạn sửa đổi danh sách mới một cách độc lập.

```csharp
List list2 = doc.Lists.AddCopy(list1);
list2.ListLevels[0].StartAt = 10;
```

Trong ví dụ này, danh sách mới bắt đầu ở số 10.

## Bước 5: Thêm mục vào danh sách mới

Cũng giống như trước đây, hãy thêm các mục vào danh sách mới của bạn. Điều này thể hiện danh sách khởi động lại ở số được chỉ định.

```csharp
builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();
```

## Bước 6: Lưu tài liệu của bạn

Cuối cùng, lưu tài liệu của bạn vào thư mục được chỉ định.

```csharp
builder.Document.Save(dataDir + "WorkingWithList.RestartListNumber.docx");
```

## Phần kết luận

Việc khởi động lại số danh sách trong tài liệu Word bằng Aspose.Words cho .NET rất đơn giản và cực kỳ hữu ích. Cho dù bạn đang tạo báo cáo, tạo tài liệu có cấu trúc hay chỉ cần kiểm soát tốt hơn danh sách của mình, kỹ thuật này đều có thể đáp ứng được nhu cầu của bạn.

## Câu hỏi thường gặp

### Tôi có thể sử dụng các mẫu danh sách khác ngoài NumberArabicParenthesis không?

Tuyệt đối! Aspose.Words cung cấp nhiều mẫu danh sách khác nhau như dấu đầu dòng, chữ cái, chữ số La Mã, v.v. Bạn có thể chọn một trong những phù hợp nhất với nhu cầu của bạn.

### Làm cách nào để thay đổi cấp độ danh sách?

 Bạn có thể thay đổi cấp độ danh sách bằng cách sửa đổi`ListLevels` tài sản. Ví dụ,`list1.ListLevels[1]` sẽ đề cập đến cấp độ thứ hai của danh sách.

### Tôi có thể bắt đầu lại việc đánh số ở số bất kỳ không?

 Có, bạn có thể đặt số bắt đầu thành bất kỳ giá trị số nguyên nào bằng cách sử dụng`StartAt` thuộc tính của cấp danh sách.

### Có thể có định dạng khác nhau cho các cấp độ danh sách khác nhau không?

Thực vậy! Mỗi cấp độ danh sách có thể có cài đặt định dạng riêng, chẳng hạn như phông chữ, căn chỉnh và kiểu đánh số.

### Nếu tôi muốn tiếp tục đánh số từ danh sách trước đó thay vì khởi động lại thì sao?

Nếu muốn tiếp tục đánh số, bạn không cần tạo bản sao của danh sách. Đơn giản chỉ cần tiếp tục thêm các mục vào danh sách ban đầu.


