---
title: Nhận danh sách các phông chữ có sẵn
linktitle: Nhận danh sách các phông chữ có sẵn
second_title: API xử lý tài liệu Aspose.Words
description: Khám phá cách lấy danh sách các phông chữ có sẵn bằng Aspose.Words cho .NET trong hướng dẫn từng bước chi tiết này. Tăng cường kỹ năng quản lý phông chữ của bạn.
type: docs
weight: 10
url: /vi/net/working-with-fonts/get-list-of-available-fonts/
---
## Giới thiệu

Bạn đã bao giờ gặp khó khăn trong việc quản lý phông chữ trong tài liệu Word của mình chưa? Nếu bạn là nhà phát triển .NET, Aspose.Words for .NET sẵn sàng giải cứu bạn! Thư viện mạnh mẽ này không chỉ giúp bạn tạo và thao tác với tài liệu Word theo chương trình mà còn cung cấp khả năng quản lý phông chữ mở rộng. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước về cách lấy danh sách các phông chữ có sẵn bằng Aspose.Words cho .NET. Chúng tôi sẽ chia nó thành các bước dễ hiểu để đảm bảo bạn có thể thực hiện dễ dàng. Vì vậy, hãy đi sâu vào và làm cho việc quản lý phông chữ trở nên dễ dàng!

## Điều kiện tiên quyết

Trước khi chúng ta bắt đầu, có một số điều bạn cần:

-  Aspose.Words for .NET: Đảm bảo bạn đã cài đặt thư viện Aspose.Words for .NET. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/words/net/).
- Visual Studio: Ví dụ này sử dụng Visual Studio làm môi trường phát triển.
- .NET Framework: Đảm bảo bạn đã cài đặt .NET Framework trên máy của mình.
- Thư mục tài liệu: Đường dẫn thư mục nơi tài liệu của bạn được lưu trữ.

## Nhập không gian tên

Đầu tiên, nhập các không gian tên cần thiết vào dự án của bạn:

```csharp
using System;
using System.Collections.Generic;
using Aspose.Words;
using Aspose.Words.Fonts;
```

## Bước 1: Khởi tạo cài đặt phông chữ

Bước đầu tiên là khởi tạo cài đặt phông chữ. Điều này sẽ cho phép bạn quản lý nguồn phông chữ cho tài liệu của mình.

```csharp
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
```

- FontSettings: Lớp này được sử dụng để chỉ định các cài đặt cho nguồn phông chữ và thay thế phông chữ.
- fontSources: Chúng tôi tạo danh sách các nguồn phông chữ hiện có từ cài đặt phông chữ hiện tại.

## Bước 2: Xác định thư mục tài liệu

Tiếp theo, chỉ định đường dẫn đến thư mục tài liệu của bạn. Đây là nơi Aspose.Words sẽ tìm kiếm phông chữ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

-  dataDir: Biến chuỗi này chứa đường dẫn đến thư mục chứa phông chữ của bạn. Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế.

## Bước 3: Thêm thư mục phông chữ tùy chỉnh

Bây giờ, hãy thêm nguồn thư mục mới để hướng dẫn Aspose.Words tìm kiếm phông chữ trong thư mục này.

```csharp
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
```

- FolderFontSource: Lớp này đại diện cho nguồn phông chữ thư mục. Tham số thứ hai (`true`) cho biết có nên tìm kiếm phông chữ đệ quy trong các thư mục con hay không.

## Bước 4: Cập nhật nguồn phông chữ

Thêm thư mục phông chữ tùy chỉnh vào danh sách nguồn phông chữ hiện có và cập nhật cài đặt phông chữ.

```csharp
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
```

- fontSources.Add(folderFontSource): Thêm thư mục phông chữ tùy chỉnh vào các nguồn phông chữ hiện có.
- đã cập nhậtFontSources: Chuyển đổi danh sách nguồn phông chữ thành một mảng.

## Bước 5: Truy xuất và hiển thị phông chữ

Cuối cùng, lấy các phông chữ có sẵn và hiển thị chi tiết của chúng.

```csharp
foreach (PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
    Console.WriteLine("FontFamilyName : " + fontInfo.FontFamilyName);
    Console.WriteLine("FullFontName  : " + fontInfo.FullFontName);
    Console.WriteLine("Version  : " + fontInfo.Version);
    Console.WriteLine("FilePath : " + fontInfo.FilePath);
}
```

- GetAvailableFonts(): Truy xuất danh sách các phông chữ có sẵn từ nguồn phông chữ đầu tiên trong danh sách cập nhật.
-  fontInfo: Một thể hiện của`PhysicalFontInfo` chứa thông tin chi tiết về từng phông chữ.

## Phần kết luận

Chúc mừng! Bạn đã truy xuất thành công danh sách các phông chữ có sẵn bằng Aspose.Words cho .NET. Hướng dẫn này đã hướng dẫn bạn từng bước, từ khởi tạo cài đặt phông chữ đến hiển thị chi tiết phông chữ. Với kiến thức này, giờ đây bạn có thể quản lý phông chữ trong tài liệu Word của mình một cách dễ dàng. Hãy nhớ rằng Aspose.Words for .NET là một công cụ mạnh mẽ có thể nâng cao đáng kể khả năng xử lý tài liệu của bạn. Vì vậy, hãy tiếp tục và khám phá thêm nhiều tính năng để giúp quá trình phát triển của bạn hiệu quả hơn nữa.

## Câu hỏi thường gặp

### Tôi có thể sử dụng Aspose.Words cho .NET với các khung .NET khác không?
Có, Aspose.Words for .NET tương thích với nhiều khung .NET khác nhau bao gồm .NET Core và .NET 5+.

### Làm cách nào để cài đặt Aspose.Words cho .NET?
Bạn có thể cài đặt nó thông qua Trình quản lý gói NuGet trong Visual Studio bằng cách tìm kiếm "Aspose.Words".

### Có thể thêm nhiều thư mục phông chữ tùy chỉnh?
 Có, bạn có thể thêm nhiều thư mục phông chữ tùy chỉnh bằng cách tạo nhiều`FolderFontSource` các phiên bản và thêm chúng vào danh sách nguồn phông chữ.

### Tôi có thể truy xuất chi tiết phông chữ từ một nguồn phông chữ cụ thể không?
 Có, bạn có thể truy xuất chi tiết phông chữ từ bất kỳ nguồn phông chữ nào bằng cách chỉ định chỉ mục của nguồn phông chữ trong`updatedFontSources` mảng.

### Aspose.Words for .NET có hỗ trợ thay thế phông chữ không?
Có, nó hỗ trợ thay thế phông chữ để đảm bảo văn bản được hiển thị chính xác ngay cả khi phông chữ gốc không có sẵn.