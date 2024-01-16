---
title: Đặt phiên bản Ms Word
linktitle: Đặt phiên bản Ms Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách tải tài liệu bằng phiên bản MS Word được chỉ định bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-loadoptions/set-ms-word-version/
---
Khi Xử lý văn bản bằng tài liệu Word trong ứng dụng C#, có thể cần phải chỉ định phiên bản Microsoft Word sẽ sử dụng khi tải tài liệu. Với thư viện Aspose.Words cho .NET, bạn có thể dễ dàng đặt phiên bản MS Word nào sẽ sử dụng bằng LoadOptions. Trong hướng dẫn từng bước này, chúng tôi sẽ hướng dẫn bạn cách sử dụng mã nguồn Aspose.Words for .NET C# để tải tài liệu có phiên bản MS Word được chỉ định bằng cách sử dụng tùy chọn tải LoadOptions.

## Tìm hiểu thư viện Aspose.Words

Trước khi đi sâu vào mã, điều quan trọng là phải hiểu thư viện Aspose.Words cho .NET. Aspose.Words là một thư viện mạnh mẽ để tạo, chỉnh sửa, chuyển đổi và bảo vệ tài liệu Word trên các nền tảng khác nhau bao gồm .NET. Nó cung cấp nhiều tính năng để thao tác với tài liệu, chẳng hạn như chèn văn bản, thay đổi định dạng, thêm phần và hơn thế nữa.

## Định cấu hình tùy chọn tải

Bước đầu tiên là định cấu hình các tùy chọn tải cho tài liệu của chúng tôi. Sử dụng lớp LoadOptions để chỉ định các tham số tải. Trong trường hợp của chúng tôi, chúng tôi cần đặt thuộc tính MswVersion thành phiên bản MS Word mong muốn. Ví dụ: chúng tôi đang sử dụng phiên bản Microsoft Word 2010. Đây là cách làm:

```csharp
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };
```

Chúng tôi tạo một đối tượng LoadOptions mới và đặt thuộc tính MswVersion thành MsWordVersion.Word2010 để chỉ định phiên bản MS Word 2010.

## Tải tài liệu với phiên bản MS Word được chỉ định

Bây giờ chúng ta đã định cấu hình các tùy chọn tải, chúng ta có thể tải tài liệu bằng lớp Tài liệu và chỉ định các tùy chọn tải. Đây là một ví dụ :

```csharp
Document doc = new Document(dataDir + "Document.docx", loadOptions);
```

Trong ví dụ này, chúng tôi tải tài liệu "Document.docx" nằm trong thư mục tài liệu bằng các tùy chọn tải đã chỉ định.

### Mã nguồn mẫu cho LoadOptions với chức năng "Đặt phiên bản MS Word" bằng Aspose.Words cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Định cấu hình tùy chọn tải với tính năng "Đặt phiên bản MS Word"
LoadOptions loadOptions = new LoadOptions { MswVersion = MsWordVersion.Word2010 };

// Tải tài liệu với phiên bản MS Word được chỉ định
Document doc = new Document(dataDir + "Document.docx", loadOptions);

// Lưu tài liệu
doc.Save(dataDir + "WorkingWithLoadOptions.SetMsWordVersion.docx");
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã giải thích cách tải lên tài liệu chỉ định một phiên bản MS Word cụ thể bằng thư viện Aspose.Words cho .NET. Bằng cách làm theo các bước được cung cấp và sử dụng mã nguồn C# được cung cấp, bạn có thể dễ dàng áp dụng chức năng này trong ứng dụng C# của mình. Tải tài liệu bằng phiên bản MS Word được chỉ định cho phép bạn đảm bảo khả năng tương thích và xử lý tài liệu phù hợp trong ứng dụng của bạn.


### Câu hỏi thường gặp

#### Hỏi: Tại sao tôi cần chỉ định phiên bản MS Word khi tải tài liệu trong ứng dụng C#?

Việc chỉ định phiên bản MS Word đảm bảo rằng tài liệu được tải và xử lý chính xác, đặc biệt khi xử lý các định dạng hoặc tính năng cụ thể có thể khác nhau giữa các phiên bản khác nhau.

#### Hỏi: Aspose.Words hỗ trợ những phiên bản MS Word nào?

Đáp: Aspose.Words for .NET hỗ trợ nhiều phiên bản MS Word khác nhau, bao gồm Word 97, Word 2003, Word 2007, Word 2010, Word 2013, Word 2016, Word 2019, v.v.

#### Hỏi: Tôi có thể tải tài liệu bằng phiên bản MS Word khác với phiên bản được cài đặt trên hệ thống của tôi không?

Trả lời: Có, Aspose.Words cho phép bạn chỉ định một phiên bản MS Word khác khi tải tài liệu, đảm bảo tính tương thích ngay cả khi hệ thống đích có phiên bản MS Word khác.

#### Hỏi: Việc cài đặt phiên bản MS Word mang lại lợi ích như thế nào cho ứng dụng C# của tôi?

Trả lời: Việc đặt phiên bản MS Word đảm bảo rằng tài liệu được xử lý theo định dạng và tính năng dự định của phiên bản cụ thể đó, mang lại kết quả nhất quán.

#### Câu hỏi: Aspose.Words có bị giới hạn chỉ xử lý các tài liệu DOCX không?

Trả lời: Không, Aspose.Words hỗ trợ nhiều định dạng tài liệu khác nhau, bao gồm DOC, RTF, HTML, PDF, v.v., khiến nó trở thành một công cụ linh hoạt để xử lý các loại tài liệu khác nhau.