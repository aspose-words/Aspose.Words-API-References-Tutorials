---
title: Đặt hệ thống thư mục phông chữ và thư mục tùy chỉnh
linktitle: Đặt hệ thống thư mục phông chữ và thư mục tùy chỉnh
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để thiết lập hệ thống và thư mục phông chữ tùy chỉnh khi hiển thị tài liệu bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/working-with-fonts/set-fonts-folders-system-and-custom-folder/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình từng bước để đặt thư mục phông chữ hệ thống và thư mục tùy chỉnh khi hiển thị tài liệu bằng Aspose.Words cho .NET. Chúng tôi sẽ giải thích mã nguồn C# đi kèm và cung cấp cho bạn hướng dẫn toàn diện để giúp bạn hiểu và triển khai tính năng này trong các dự án của riêng bạn. Đến cuối hướng dẫn này, bạn sẽ biết cách chỉ định nhiều thư mục phông chữ, bao gồm thư mục hệ thống và thư mục tùy chỉnh, để sử dụng khi hiển thị tài liệu của mình bằng Aspose.Words cho .NET.

## Bước 1: Xác định thư mục tài liệu
Đầu tiên, bạn cần đặt đường dẫn đến thư mục tài liệu của mình. Đây là vị trí bạn muốn lưu tài liệu được hiển thị đã chỉnh sửa của mình. Thay thế "THƯ VIỆN TÀI LIỆU CỦA BẠN" bằng đường dẫn thích hợp.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Load tài liệu cần render
 Sau đó, bạn có thể tải tài liệu để kết xuất bằng cách sử dụng`Document` lớp học. Đảm bảo chỉ định đường dẫn tài liệu chính xác.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Bước 3: Đặt thư mục hệ thống và phông chữ tùy chỉnh
 Bây giờ bạn có thể đặt thư mục phông chữ hệ thống và thư mục tùy chỉnh bằng cách sử dụng`FontSettings` lớp học và`SetFontsSources()` phương pháp. Trước tiên, bạn cần truy xuất danh sách các nguồn phông chữ phụ thuộc vào môi trường bằng cách sử dụng`GetFontsSources()` và lưu trữ nó trong một danh sách. Sau đó, bạn có thể tạo một phiên bản mới của`FolderFontSource` chỉ định đường dẫn đến thư mục tùy chỉnh chứa phông chữ của bạn. Thêm phiên bản này vào danh sách các nguồn phông chữ hiện có. Cuối cùng, sử dụng`SetFontsSources()` để cập nhật nguồn phông chữ với danh sách mới.

```csharp
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
```

## Bước 4: Áp dụng cài đặt phông chữ
 Tiếp theo, bạn cần áp dụng cài đặt phông chữ cho tài liệu của mình bằng cách sử dụng`FontSettings` tài sản của`Document` lớp học.

```csharp
doc.FontSettings = fontSettings;
```

## Bước 5: Lưu tài liệu được kết xuất
Cuối cùng, bạn có thể lưu tài liệu được kết xuất vào một tệp bằng cách

   sử dụng`Save()` phương pháp của`Document` lớp học. Đảm bảo chỉ định đúng đường dẫn và tên tệp.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

### Mã nguồn mẫu cho Đặt hệ thống thư mục phông chữ và thư mục tùy chỉnh bằng Aspose.Words cho .NET 

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Truy xuất mảng nguồn phông chữ phụ thuộc vào môi trường được tìm kiếm theo mặc định.
// Ví dụ: phần này sẽ chứa nguồn "Windows\Fonts\" trên máy Windows.
// Chúng tôi thêm mảng này vào Danh sách mới để giúp việc thêm hoặc xóa các mục phông chữ dễ dàng hơn nhiều.
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
// Thêm nguồn thư mục mới sẽ hướng dẫn Aspose.Words tìm kiếm phông chữ trong thư mục sau.
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
//Thêm thư mục tùy chỉnh chứa phông chữ của chúng tôi vào danh sách các nguồn phông chữ hiện có.
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã tìm hiểu cách đặt thư mục phông chữ hệ thống và thư mục tùy chỉnh khi hiển thị tài liệu bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước này, bạn có thể dễ dàng chỉ định nhiều thư mục phông chữ, bao gồm thư mục hệ thống và thư mục tùy chỉnh, để sử dụng khi hiển thị tài liệu của mình. Aspose.Words cung cấp API mạnh mẽ và linh hoạt để Xử lý văn bản với phông chữ trong tài liệu của bạn. Với kiến thức này, bạn có thể kiểm soát và tùy chỉnh các nguồn phông chữ được sử dụng khi hiển thị tài liệu theo nhu cầu cụ thể của mình.

### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào tôi có thể đặt thư mục phông chữ hệ thống trong Aspose.Words?

Trả lời: Để đặt thư mục phông chữ hệ thống trong Aspose.Words, bạn không phải làm gì cả. Aspose.Words tự động sử dụng phông chữ hệ thống được cài đặt trên hệ điều hành của bạn.

#### Câu hỏi: Làm cách nào tôi có thể đặt thư mục phông chữ tùy chỉnh trong Aspose.Words?

 Trả lời: Để đặt các thư mục phông chữ tùy chỉnh trong Aspose.Words, bạn có thể sử dụng`SetFontsFolders` phương pháp của`Fonts` lớp chỉ định vị trí của các thư mục phông chữ tùy chỉnh.

#### Câu hỏi: Tôi có thể chỉ định nhiều thư mục phông chữ tùy chỉnh trong Aspose.Words không?

 Trả lời: Có, bạn có thể chỉ định nhiều thư mục phông chữ tùy chỉnh trong Aspose.Words bằng cách sử dụng`SetFontsFolders` phương pháp của`Fonts` class với danh sách các vị trí thư mục.

#### Câu hỏi: Làm cách nào tôi có thể kiểm tra các thư mục phông chữ được xác định trong Aspose.Words?

 Để kiểm tra các thư mục phông chữ được xác định trong Aspose.Words, bạn có thể sử dụng`GetFolders` phương pháp của`Fonts` class để lấy danh sách các thư mục phông chữ được cấu hình.

#### Câu hỏi: Phông chữ thư mục tùy chỉnh có được ưu tiên hơn phông chữ hệ thống trong Aspose.Words không?

Trả lời: Có, phông chữ thư mục tùy chỉnh được ưu tiên hơn phông chữ hệ thống trong Aspose.Words. Nếu phông chữ xuất hiện trong cả thư mục tùy chỉnh và phông chữ hệ thống, Aspose.Words sẽ sử dụng phiên bản từ thư mục tùy chỉnh.