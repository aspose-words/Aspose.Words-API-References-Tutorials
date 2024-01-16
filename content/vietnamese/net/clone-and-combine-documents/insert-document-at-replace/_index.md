---
title: Chèn tài liệu vào thay thế
linktitle: Chèn tài liệu vào thay thế
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chèn tài liệu thay thế bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/clone-and-combine-documents/insert-document-at-replace/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn cách chèn tài liệu vào tài liệu khác khi thay thế bằng tính năng Chèn tài liệu khi thay thế của Aspose.Words cho .NET. Thực hiện theo các bước bên dưới để hiểu mã nguồn và thực hiện chèn tài liệu.

## Bước 1: Tải tài liệu chính

Để bắt đầu, hãy chỉ định thư mục cho tài liệu của bạn và tải tài liệu chính vào đối tượng Tài liệu. Đây là cách thực hiện:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## Bước 2: Định cấu hình tùy chọn tìm kiếm và thay thế

Bây giờ chúng ta sẽ định cấu hình các tùy chọn tìm và thay thế bằng cách chỉ định hướng tìm kiếm và gọi lại thay thế để chèn tài liệu vào tài liệu khác. Đây là cách thực hiện:

```csharp
// Định cấu hình tùy chọn tìm kiếm và thay thế.
FindReplaceOptions options = new FindReplaceOptions
{
Direction = FindReplaceDirection.Backward,
ReplacingCallback = new InsertDocumentAtReplaceHandler()
};
```

## Bước 3: Gọi phương thức thay thế

Bây giờ chúng ta sẽ gọi phương thức thay thế để tìm và thay thế văn bản đã chỉ định bằng một chuỗi trống, sử dụng các tùy chọn đã định cấu hình. Đây là cách thực hiện:

```csharp
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

### Mã nguồn ví dụ cho Chèn tài liệu tại Thay thế bằng Aspose.Words cho .NET

Đây là mã nguồn hoàn chỉnh cho tính năng Chèn Tài liệu khi thay thế Aspose.Words cho .NET:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

// Đặt tùy chọn tìm và thay thế.
FindReplaceOptions options = new FindReplaceOptions
{
	Direction = FindReplaceDirection.Backward, 
	ReplacingCallback = new InsertDocumentAtReplaceHandler()
};

// Gọi phương thức thay thế.
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã khám phá cách chèn tài liệu vào tài liệu khác trong quá trình thay thế bằng cách sử dụng tính năng Chèn Tài liệu Khi Thay thế của Aspose.Words cho .NET. Bằng cách định cấu hình các tùy chọn tìm và thay thế cũng như cung cấp dữ liệu cần thiết, bạn có thể tập hợp các tài liệu một cách linh hoạt bằng cách thay thế các phần giữ chỗ cụ thể bằng nội dung của các phần hoặc mẫu tài liệu khác. Aspose.Words for .NET cung cấp một cách mạnh mẽ và linh hoạt để quản lý các tác vụ thao tác tài liệu phức tạp, biến nó thành một công cụ có giá trị để tự động hóa các kịch bản tạo tài liệu và chèn nội dung.

### Câu hỏi thường gặp

#### Hỏi: Mục đích của việc chèn tài liệu vào tài liệu khác trong quá trình thay thế là gì?

Đáp: Việc chèn tài liệu vào một tài liệu khác trong quá trình thay thế cho phép bạn thay thế động một trình giữ chỗ cụ thể bằng nội dung của một tài liệu riêng biệt. Tính năng này đặc biệt hữu ích khi bạn muốn tập hợp một tài liệu lớn hơn bằng cách kết hợp nhiều mẫu hoặc phần tài liệu được xác định trước vào các phần giữ chỗ cụ thể.

#### Câu hỏi: Làm cách nào để chèn tài liệu vào tài liệu khác trong khi thay thế bằng Aspose.Words cho .NET?

Trả lời: Để chèn tài liệu vào tài liệu khác trong quá trình thay thế bằng Aspose.Words cho .NET, hãy làm theo các bước sau:
1. Tải tài liệu chính chứa phần giữ chỗ vào đối tượng Tài liệu.
2. Định cấu hình các tùy chọn tìm và thay thế, bao gồm lệnh gọi lại hướng tìm kiếm và thay thế để xử lý việc chèn tài liệu.
3. Gọi phương thức thay thế bằng mẫu tìm kiếm thích hợp, thay thế phần giữ chỗ bằng một chuỗi trống, sử dụng các tùy chọn đã định cấu hình.

#### Câu hỏi: Tôi có thể tùy chỉnh hành vi chèn trong khi thay thế không?

Trả lời: Có, bạn có thể tùy chỉnh hành vi chèn trong quá trình thay thế bằng cách triển khai ReplacingCallback tùy chỉnh. Bằng cách kế thừa từ giao diện IReplacesCallback, bạn có thể kiểm soát cách các tài liệu được chèn và hợp nhất dựa trên các yêu cầu cụ thể của bạn khi thay thế phần giữ chỗ.

#### Câu hỏi: Tôi có thể thay thế nhiều phần giữ chỗ bằng các tài liệu khác nhau không?

Đáp: Có, bạn có thể thay thế nhiều phần giữ chỗ bằng các tài liệu khác nhau bằng cách chỉ định các mẫu tìm kiếm thích hợp cho từng phần giữ chỗ và cung cấp các tài liệu tương ứng để chèn vào.