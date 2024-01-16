---
title: Tính năng loại mở
linktitle: Tính năng loại mở
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách bật và sử dụng các tính năng Loại mở trong Aspose.Words cho .NET
type: docs
weight: 10
url: /vi/net/enable-opentype-features/open-type-features/
---

Trong hướng dẫn toàn diện này, bạn sẽ tìm hiểu cách bật và sử dụng các tính năng Open Type trong Aspose.Words for .NET. Chúng tôi sẽ hướng dẫn bạn thực hiện quy trình và cung cấp cho bạn các đoạn mã C# cần thiết. Đến cuối hướng dẫn này, bạn sẽ có thể làm việc với các tính năng Loại mở trong tài liệu Word của mình.

## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo rằng bạn có các điều kiện tiên quyết sau:
- Thư viện Aspose.Words for .NET được cài đặt trên hệ thống của bạn.

## Bước 1: Tải tài liệu
Để bắt đầu, hãy tải tài liệu bằng lớp Document:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");
```

## Bước 2: Kích hoạt tính năng loại mở
Để bật các tính năng Loại mở, hãy đặt thuộc tính TextShaperFactory của lớp LayoutOptions thành một phiên bản của nhà máy tạo hình văn bản mong muốn. Trong ví dụ này, chúng tôi sử dụng HarfBuzzTextShaperFactory:

```csharp
doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;
```

## Bước 3: Lưu tài liệu
Sau khi bật tính năng Loại mở, hãy lưu tài liệu ở định dạng đầu ra mong muốn, chẳng hạn như PDF:

```csharp
doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

### Mã nguồn ví dụ cho các tính năng loại mở bằng Aspose.Words cho .NET
Đây là mã nguồn hoàn chỉnh để sử dụng các tính năng Open Type trong Aspose.Words for .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");

doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;

doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

## Phần kết luận
Chúc mừng! Bạn đã học thành công cách bật và sử dụng các tính năng Loại mở trong Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước và sử dụng mã nguồn được cung cấp, giờ đây bạn có thể làm việc với các tính năng Loại mở trong tài liệu Word của mình.

Các tính năng của Open Type cung cấp khả năng tạo kiểu chữ và định hình văn bản nâng cao, cho phép bạn tạo các tài liệu trông hấp dẫn và chuyên nghiệp về mặt trực quan. Thử nghiệm với các nhà máy tạo hình văn bản khác nhau và khám phá khả năng của các tính năng Kiểu mở trong dự án của bạn.

### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào để bật tính năng OpenType trong Aspose.Words cho .NET?

Trả lời: Để bật các tính năng OpenType trong Aspose.Words cho .NET, bạn cần làm theo các bước được đề cập trong hướng dẫn.

#### Câu hỏi: Những tính năng OpenType nào được hỗ trợ trong Aspose.Words cho .NET?

Đáp: Aspose.Words for .NET hỗ trợ một số tính năng OpenType, chẳng hạn như chữ ghép, biến thể hình tượng, thay thế theo ngữ cảnh, v.v.

#### Câu hỏi: Làm cách nào để kiểm tra xem tính năng OpenType có được hỗ trợ ở một phông chữ cụ thể không?

Đáp: Bạn có thể kiểm tra xem tính năng OpenType có được hỗ trợ ở một phông chữ cụ thể hay không bằng cách sử dụng`Font.OpenTypeFeatures` phương thức trong Aspose.Words cho .NET.

#### Câu hỏi: Aspose.Words for .NET hỗ trợ những tính năng định dạng văn bản nào khác?

Trả lời: Ngoài các tính năng OpenType, Aspose.Words for .NET còn hỗ trợ các tính năng định dạng văn bản khác như định dạng đoạn văn, tạo bảng, thêm hình ảnh, v.v.

#### Câu hỏi: Tôi có thể sử dụng các tính năng OpenType trong tất cả các phiên bản Aspose.Words cho .NET không?

Trả lời: Các tính năng OpenType được hỗ trợ trong các phiên bản mới hơn của Aspose.Words cho .NET. Đảm bảo bạn đang sử dụng phiên bản tương thích để hưởng lợi từ các tính năng này.