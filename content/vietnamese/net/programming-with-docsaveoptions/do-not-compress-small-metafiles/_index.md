---
title: Không nén các siêu tệp nhỏ
linktitle: Không nén các siêu tệp nhỏ
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách sử dụng Aspose.Words cho .NET để bật tính năng Không nén siêu tệp nhỏ khi lưu tài liệu.
type: docs
weight: 10
url: /vi/net/programming-with-docsaveoptions/do-not-compress-small-metafiles/
---

Nén siêu dữ liệu trong tài liệu là một tính năng phổ biến khi Xử lý văn bản với các tệp trong ứng dụng C#. Tuy nhiên, có thể không cần thiết phải nén siêu dữ liệu của các tệp nhỏ để duy trì chất lượng của chúng. Trong hướng dẫn từng bước này, chúng tôi sẽ chỉ cho bạn cách sử dụng mã nguồn C# của Aspose.Words cho .NET để bật tính năng "Không nén siêu tệp nhỏ" trong tùy chọn lưu tài liệu.

## Tìm hiểu thư viện Aspose.Words

Trước khi đi sâu vào mã, điều quan trọng là phải hiểu thư viện Aspose.Words cho .NET. Aspose.Words là một thư viện mạnh mẽ để tạo, chỉnh sửa, chuyển đổi và bảo vệ tài liệu Word trên các nền tảng khác nhau bao gồm .NET. Nó cung cấp nhiều tính năng để thao tác với tài liệu, chẳng hạn như chèn văn bản, thay đổi định dạng, thêm phần và hơn thế nữa.

## Bước 1: Đặt thư mục tài liệu

Bước đầu tiên là xác định thư mục nơi bạn muốn lưu tài liệu. Bạn phải chỉ định đường dẫn thư mục đầy đủ. Ví dụ :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Đảm bảo thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 2: Chèn phần và văn bản

Sau đó, bạn có thể chèn các phần và văn bản vào tài liệu của mình. Sử dụng lớp DocumentBuilder do Aspose.Words cung cấp để xây dựng nội dung tài liệu của bạn. Đây là một ví dụ đơn giản:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");
```

Trong ví dụ này, chúng tôi tạo một tài liệu trống mới và sau đó sử dụng DocumentBuilder để thêm một dòng văn bản.

## Bước 3: Tùy chọn thiết lập

'sự đăng ký

Bây giờ hãy định cấu hình các tùy chọn lưu cho tài liệu của chúng tôi. Sử dụng lớp DocSaveOptions để chỉ định cài đặt lưu. Ví dụ :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions();
```

Trong ví dụ này, chúng tôi đang tạo một đối tượng DocSaveOptions mới để đặt các tùy chọn lưu.

## Bước 4: Kích hoạt tính năng "Không nén siêu tệp nhỏ"

 Để bật tính năng "Không nén siêu tệp nhỏ", bạn phải đặt`Compliance` thuộc tính của đối tượng DocSaveOptions với giá trị`PdfCompliance.PdfA1a`. Đây là cách thực hiện:

```csharp
saveOptions.Compliance = PdfCompliance.PdfA1a;
```

Cấu hình này đảm bảo rằng siêu dữ liệu tệp nhỏ không bị nén khi tài liệu được lưu.

## Bước 5: Lưu tài liệu

Cuối cùng, bạn có thể lưu tài liệu bằng cách sử dụng`Save` phương thức của lớp Document. Chỉ định đường dẫn đầy đủ đến tệp và tên tệp mong muốn. Ví dụ :

```csharp
doc.Save(dataDir + "DocumentWithDoNotCompressMetafiles.pdf", saveOptions);
```

Đảm bảo thay thế "dataDir" bằng đường dẫn đến thư mục tài liệu của bạn.

### Mã nguồn ví dụ cho DocSaveOptions có tính năng Không nén siêu tệp nhỏ bằng Aspose.Words cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Chèn hai phần với một số văn bản.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");

// Định cấu hình tùy chọn lưu với tính năng "Không nén siêu tệp nhỏ"
DocSaveOptions saveOptions = new DocSaveOptions();
saveOptions.Compliance = PdfCompliance.PdfA1a;

// Lưu tài liệu với các tùy chọn được chỉ định
doc.Save(dataDir + "DocumentWithDoNotCompressMetafiles.pdf", saveOptions);
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã giải thích cách sử dụng thư viện Aspose.Words cho .NET để bật tính năng "Không nén siêu tệp nhỏ" khi lưu tài liệu. Bằng cách làm theo các bước được cung cấp và sử dụng mã nguồn C# được cung cấp, bạn có thể dễ dàng áp dụng chức năng này trong ứng dụng C# của mình. Việc bảo quản siêu dữ liệu tệp nhỏ không nén có thể rất quan trọng để duy trì chất lượng và tính toàn vẹn của tài liệu.