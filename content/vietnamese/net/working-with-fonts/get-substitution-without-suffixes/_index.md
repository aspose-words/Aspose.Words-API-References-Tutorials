---
title: Nhận thay thế không có hậu tố
linktitle: Nhận thay thế không có hậu tố
second_title: API xử lý tài liệu Aspose.Words
description: Trong hướng dẫn này, hãy tìm hiểu cách ghi đè không có hậu tố trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/working-with-fonts/get-substitution-without-suffixes/
---

Trong hướng dẫn này, chúng tôi sẽ chỉ cho bạn cách lấy phần ghi đè không có hậu tố trong tài liệu Word bằng thư viện Aspose.Words cho .NET. Việc thay thế không có hậu tố được sử dụng để giải quyết các vấn đề về thay thế phông chữ khi hiển thị hoặc in tài liệu. Chúng tôi sẽ hướng dẫn bạn từng bước để giúp bạn hiểu và triển khai mã trong dự án .NET của mình.

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

## Bước 2: Tải tài liệu và định cấu hình các thay thế không có hậu tố
 Tiếp theo, chúng ta sẽ tải tài liệu bằng cách sử dụng`Document` lớp và định cấu hình các thay thế không có hậu tố bằng cách sử dụng`DocumentSubstitutionWarnings` lớp học. Chúng tôi cũng sẽ thêm nguồn phông chữ bằng cách chỉ định thư mục chứa phông chữ.

```csharp
// Tải tài liệu và định cấu hình các thay thế không có hậu tố
Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;

List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
```

## Bước 3: Lưu tài liệu
Cuối cùng, chúng tôi sẽ lưu tài liệu với các phần ghi đè không có hậu tố được áp dụng.

```csharp
// Lưu tài liệu
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");
```

### Mã nguồn mẫu cho Nhận thay thế không có hậu tố bằng Aspose.Words cho .NET 
```csharp

// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;
List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");

```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã biết cách lấy phần ghi đè không có hậu tố trong tài liệu Word bằng Aspose.Words cho .NET. Việc thay thế không có hậu tố rất hữu ích trong việc giải quyết các vấn đề về thay thế phông chữ. Hãy thoải mái sử dụng tính năng này để cải thiện việc hiển thị và in tài liệu của bạn.

### Câu hỏi thường gặp

#### Câu hỏi: Tại sao Aspose.Words thêm hậu tố vào việc thay thế phông chữ?

Trả lời: Aspose.Words thêm hậu tố vào việc thay thế phông chữ để tránh xung đột giữa phông chữ gốc và phông chữ được thay thế. Điều này giúp đảm bảo khả năng tương thích tối đa khi chuyển đổi và thao tác với tài liệu.

#### Câu hỏi: Làm cách nào tôi có thể truy xuất các thay thế phông chữ không có hậu tố trong Aspose.Words?

 Trả lời: Để truy xuất các thay thế phông chữ không có hậu tố trong Aspose.Words, bạn có thể sử dụng`FontSubstitutionSettings` lớp học và`RemoveSuffixes` tài sản. Đặt thuộc tính này thành`true` sẽ nhận được sự thay thế phông chữ mà không cần thêm hậu tố.

#### Câu hỏi: Có thể tắt tính năng thêm hậu tố vào tính năng thay thế phông chữ trong Aspose.Words không?

Trả lời: Không, không thể tắt việc thêm hậu tố vào việc thay thế phông chữ trong Aspose.Words. Hậu tố được thêm theo mặc định để đảm bảo tính tương thích và nhất quán của tài liệu.

#### Câu hỏi: Làm cách nào tôi có thể lọc các hậu tố không mong muốn khi thay thế phông chữ trong Aspose.Words?

 Trả lời: Để lọc các hậu tố không mong muốn khi thay thế phông chữ trong Aspose.Words, bạn có thể sử dụng các kỹ thuật xử lý chuỗi, chẳng hạn như sử dụng`Replace` hoặc`Substring` phương pháp loại bỏ các hậu tố cụ thể mà bạn không muốn đưa vào.