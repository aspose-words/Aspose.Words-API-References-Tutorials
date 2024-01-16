---
title: Đặt thư mục phông chữ
linktitle: Đặt thư mục phông chữ
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách đặt thư mục phông chữ trong Aspose.Words cho .NET và đảm bảo tính khả dụng của phông chữ được sử dụng trong tài liệu của bạn.
type: docs
weight: 10
url: /vi/net/working-with-fonts/set-fonts-folder/
---
Trong hướng dẫn này, chúng tôi sẽ chỉ cho bạn cách đặt thư mục phông chữ trong Aspose.Words cho .NET. Bạn sẽ học cách chỉ định thư mục chứa các phông chữ được sử dụng trong tài liệu Word của mình.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có các mục sau:
- Kiến thức làm việc về ngôn ngữ lập trình C#
- Thư viện Aspose.Words cho .NET được cài đặt trong dự án của bạn

## Bước 1: Xác định thư mục tài liệu
 Bắt đầu bằng cách đặt đường dẫn thư mục đến vị trí tài liệu Word của bạn. Thay thế`"YOUR DOCUMENT DIRECTORY"` trong mã với đường dẫn thích hợp.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Đặt thư mục phông chữ
 Tạo một thể hiện của`FontSettings` lớp và sử dụng`SetFontsFolder` phương pháp chỉ định thư mục chứa phông chữ. Thay thế`"Fonts"` với tên của thư mục phông chữ thực tế.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
```

## Bước 3: Tải tài liệu với cài đặt phông chữ
 Sử dụng`LoadOptions` lớp để chỉ định cài đặt phông chữ trong`FontSettings` lựa chọn. Sau đó sử dụng`Document` class để tải tài liệu bằng các tùy chọn này.

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

### Mã nguồn mẫu cho Đặt thư mục phông chữ bằng Aspose.Words cho .NET 

```csharp

// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## Phần kết luận
Xin chúc mừng! Bây giờ bạn đã biết cách đặt thư mục phông chữ trong Aspose.Words cho .NET. Bạn có thể sử dụng tính năng này để đảm bảo tính sẵn có của phông chữ được sử dụng trong tài liệu của bạn và đảm bảo tính nhất quán trong việc hiển thị phông chữ.

### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào tôi có thể đặt thư mục phông chữ tùy chỉnh trong Aspose.Words?

 Trả lời: Để đặt thư mục phông chữ tùy chỉnh trong Aspose.Words, bạn có thể sử dụng`FontsFolder` lớp học và`SetFontsFolders` phương pháp chỉ định đường dẫn đến thư mục chứa phông chữ của bạn.

#### Câu hỏi: Tôi có thể đặt nhiều thư mục phông chữ trong Aspose.Words không?

 Trả lời: Có, bạn có thể đặt nhiều thư mục phông chữ trong Aspose.Words bằng cách gọi hàm`SetFontsFolders` nhiều lần với đường dẫn của các thư mục phông chữ khác nhau mà bạn muốn sử dụng.

#### Hỏi: Điều gì sẽ xảy ra nếu phông chữ được sử dụng trong tài liệu không có trong các thư mục phông chữ đã xác định?

Trả lời: Nếu phông chữ được sử dụng trong tài liệu không có trong các thư mục phông chữ được xác định trong Aspose.Words, thì phông chữ thay thế sẽ được sử dụng thay thế. Điều này đảm bảo rằng văn bản trong tài liệu sẽ luôn được hiển thị chính xác, ngay cả khi không có phông chữ gốc.

#### Câu hỏi: Các thư mục phông chữ được xác định trong Aspose.Words có được ưu tiên hơn các phông chữ được cài đặt trên hệ thống không?

Trả lời: Có, các thư mục phông chữ được xác định trong Aspose.Words được ưu tiên hơn các phông chữ được cài đặt trên hệ thống. Điều này có nghĩa là nếu một phông chữ có cùng tên xuất hiện cả trong các thư mục phông chữ đã xác định và trong phông chữ hệ thống, phiên bản trong thư mục phông chữ sẽ được sử dụng khi xử lý tài liệu Word.