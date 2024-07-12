---
title: Nhận danh sách các phông chữ có sẵn
linktitle: Nhận danh sách các phông chữ có sẵn
second_title: API xử lý tài liệu Aspose.Words
description: Trong hướng dẫn này, hãy tìm hiểu cách lấy danh sách phông chữ có sẵn trong Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/working-with-fonts/get-list-of-available-fonts/
---
Trong hướng dẫn này, chúng tôi sẽ giải thích cách lấy danh sách phông chữ có sẵn trong Aspose.Words cho .NET. Danh sách các phông chữ có sẵn cho bạn biết những phông chữ nào bạn có thể sử dụng trong tài liệu của mình. Chúng tôi sẽ hướng dẫn bạn từng bước để giúp bạn hiểu và triển khai mã trong dự án .NET của mình.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có các mục sau:
- Kiến thức làm việc về ngôn ngữ lập trình C#
- Thư viện Aspose.Words cho .NET được cài đặt trong dự án của bạn

## Bước 1: Xác định thư mục tài liệu
 Trước tiên, bạn cần đặt đường dẫn thư mục đến vị trí tài liệu Word của mình. Thay thế`"YOUR DOCUMENT DIRECTORY"` trong mã với đường dẫn thích hợp.

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Định cấu hình nguồn phông chữ
Tiếp theo, chúng ta sẽ tạo một thể hiện của`FontSettings` và lấy các nguồn phông chữ hiện có bằng cách sử dụng`GetFontsSources()` phương pháp. Chúng tôi cũng sẽ thêm nguồn phông chữ mới bằng cách chỉ định thư mục chứa phông chữ.

```csharp
// Định cấu hình nguồn phông chữ
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());

// Thêm nguồn phông chữ mới
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
fontSources.Add(folderFontSource);

FontSourceBase[] updatedFontSources = fontSources.ToArray();
```

## Bước 3: Lấy danh sách font chữ có sẵn
 Bây giờ chúng ta sẽ duyệt các phông chữ có sẵn bằng cách sử dụng`GetAvailableFonts()` phương pháp trên nguồn phông chữ được cập nhật đầu tiên.

```csharp
// Lấy danh sách các phông chữ có sẵn
foreach(PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
Console.WriteLine("Font Family Name: " + fontInfo.FontFamilyName);
Console.WriteLine("Full font name: " + fontInfo.FullFontName);
Console.WriteLine("Version: " + fontInfo.Version);
Console.WriteLine("Path: " + fontInfo.FilePath);
}
```


### Mã nguồn mẫu để Nhận danh sách các phông chữ có sẵn bằng Aspose.Words cho .NET 

```csharp

// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
// Thêm nguồn thư mục mới sẽ hướng dẫn Aspose.Words tìm kiếm phông chữ trong thư mục sau.
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
// Thêm thư mục tùy chỉnh chứa phông chữ của chúng tôi vào danh sách các nguồn phông chữ hiện có.
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
foreach (PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
	Console.WriteLine("FontFamilyName : " + fontInfo.FontFamilyName);
	Console.WriteLine("FullFontName  : " + fontInfo.FullFontName);
	Console.WriteLine("Version  : " + fontInfo.Version);
	Console.WriteLine("FilePath : " + fontInfo.FilePath);
}

```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã biết cách lấy danh sách phông chữ có sẵn trong Aspose.Words cho .NET. Điều này cho bạn biết bạn có thể sử dụng phông chữ nào trong tài liệu của mình. Hãy sử dụng tính năng này để chọn phông chữ phù hợp với nhu cầu của bạn.

### Câu hỏi thường gặp

#### Hỏi: Làm cách nào tôi có thể truy xuất danh sách phông chữ có sẵn trong Aspose.Words?

 Trả lời: Để truy xuất danh sách phông chữ có sẵn trong Aspose.Words, bạn có thể sử dụng`FontsProvider` lớp học và`GetAvailableFonts` phương pháp. Phương pháp này sẽ trả về danh sách tất cả các phông chữ được cài đặt trên hệ thống của bạn.

#### Câu hỏi: Tôi có thể lọc danh sách phông chữ có sẵn theo tiêu chí nhất định trong Aspose.Words không?

Trả lời: Có, bạn có thể lọc danh sách phông chữ có sẵn trong Aspose.Words bằng các tiêu chí cụ thể. Ví dụ: bạn có thể lọc phông chữ theo họ, kiểu hoặc ngôn ngữ.

#### Hỏi: Làm cách nào tôi có thể sử dụng danh sách phông chữ có sẵn trong tài liệu Word của mình?

 Trả lời: Để sử dụng danh sách phông chữ có sẵn trong tài liệu Word của bạn, bạn có thể duyệt qua danh sách và chọn phông chữ thích hợp bằng cách sử dụng các phương pháp và thuộc tính của`FontSettings` lớp trong Aspose.Words.