---
title: Giữ ký tự kiểm soát kế thừa
linktitle: Giữ ký tự kiểm soát kế thừa
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách giữ nguyên các ký tự điều khiển cũ khi lưu tài liệu bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-ooxmlsaveoptions/keep-legacy-control-chars/
---

Trong hướng dẫn này, chúng ta sẽ khám phá mã nguồn C# được cung cấp để giữ nguyên các ký tự điều khiển cũ khi lưu tài liệu bằng Aspose.Words cho .NET. Tính năng này cho phép bạn giữ lại các ký tự điều khiển đặc biệt khi chuyển đổi hoặc lưu tài liệu.

## Bước 1: Thiết lập môi trường

Trước khi bắt đầu, hãy đảm bảo bạn đã thiết lập môi trường phát triển của mình với Aspose.Words for .NET. Đảm bảo bạn đã thêm các tham chiếu cần thiết và nhập các không gian tên thích hợp.

## Bước 2: Tải tài liệu

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Legacy control character.doc");
```

 Ở bước này, chúng ta tải tài liệu bằng cách sử dụng`Document` phương thức và chuyển đường dẫn đến tệp chứa các ký tự điều khiển được kế thừa.

## Bước 3: Định cấu hình tùy chọn sao lưu OOXML

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };
```

 Trong bước này, chúng tôi định cấu hình các tùy chọn lưu OOXML bằng cách tạo một`OoxmlSaveOptions` sự vật. Chúng tôi chỉ định định dạng lưu mong muốn (ở đây,`FlatOpc` ) và kích hoạt`KeepLegacyControlChars` tùy chọn để giữ các ký tự điều khiển kế thừa.

## Bước 4: Lưu tài liệu với các ký tự điều khiển kế thừa

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
```

 Ở bước cuối cùng này, chúng tôi lưu tài liệu bằng cách sử dụng`Save` phương thức và chuyển đường dẫn đến tệp đầu ra bằng`.docx` tiện ích mở rộng, cùng với các tùy chọn lưu được chỉ định.

Bây giờ bạn có thể chạy mã nguồn để giữ nguyên các ký tự điều khiển cũ khi lưu tài liệu. Tệp kết quả sẽ được lưu trong thư mục được chỉ định với tên "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx".

### Mã nguồn mẫu cho Keep Legacy Control Chars bằng Aspose.Words for .NET 
```csharp

// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Legacy control character.doc");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
            
        
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã khám phá chức năng giữ nguyên các ký tự điều khiển cũ khi lưu tài liệu bằng Aspose.Words cho .NET. Chúng tôi đã học cách giữ lại các ký tự đặc biệt có thể quan trọng để định dạng hoặc hiển thị tài liệu phù hợp.

 Việc giữ nguyên các ký tự điều khiển kế thừa đặc biệt hữu ích khi Xử lý văn bản bằng các tài liệu sử dụng các tính năng cũ hơn hoặc cụ thể, chẳng hạn như các ký tự điều khiển đặc biệt. Bằng cách kích hoạt`KeepLegacyControlChars` tùy chọn khi lưu tài liệu, bạn đảm bảo rằng các ký tự này được giữ nguyên.

Aspose.Words for .NET cung cấp nhiều tùy chọn sao lưu linh hoạt và mạnh mẽ để đáp ứng nhu cầu thao tác tài liệu của bạn. Bằng cách sử dụng các tùy chọn thích hợp, bạn có thể tùy chỉnh quy trình sao lưu để duy trì các đặc điểm cụ thể của tài liệu của mình.

Vui lòng kết hợp chức năng này vào các dự án Aspose.Words for .NET để đảm bảo tính toàn vẹn và bảo toàn các ký tự điều khiển kế thừa trong tài liệu của bạn.