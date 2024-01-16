---
title: Không lưu dấu đầu dòng ảnh
linktitle: Không lưu dấu đầu dòng ảnh
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách tắt tính năng lưu dấu đầu dòng hình ảnh trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-docsaveoptions/do-not-save-picture-bullet/
---

Dấu đầu dòng hình ảnh là tính năng thường được sử dụng trong tài liệu Word để thêm dấu đầu dòng tùy chỉnh. Tuy nhiên, trong một số trường hợp, có thể cần phải tắt đăng ký dấu đầu dòng hình ảnh khi thao tác với tài liệu bằng Thư viện Aspose.Words cho .NET. Trong hướng dẫn từng bước này, chúng tôi sẽ giải thích cách sử dụng mã nguồn Aspose.Words C# cho .NET để tắt tính năng lưu dấu đầu dòng hình ảnh bằng các tùy chọn lưu DocSaveOptions.

## Tìm hiểu thư viện Aspose.Words

Trước khi đi sâu vào mã, điều quan trọng là phải hiểu thư viện Aspose.Words cho .NET. Aspose.Words là một thư viện mạnh mẽ để tạo, chỉnh sửa, chuyển đổi và bảo vệ tài liệu Word trên các nền tảng khác nhau bao gồm .NET. Nó cung cấp nhiều tính năng để thao tác với tài liệu, chẳng hạn như chèn văn bản, thay đổi định dạng, thêm phần và hơn thế nữa.

## Bước 1: Thiết lập thư mục tài liệu

Bước đầu tiên là xác định thư mục chứa tài liệu của bạn. Bạn phải chỉ định đường dẫn thư mục đầy đủ. Ví dụ :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Đảm bảo thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 2: Tải tài liệu có dấu đầu dòng hình ảnh

Tiếp theo, bạn cần tải tài liệu có dấu đầu dòng hình ảnh. Sử dụng lớp Tài liệu để tải tài liệu từ một tệp. Ví dụ :

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

Trong ví dụ này, chúng tôi đang tải tài liệu từ tệp "Hình ảnh dấu đầu dòng.docx"

  nằm trong thư mục tài liệu.

## Bước 3: Định cấu hình tùy chọn ghi

Bây giờ hãy định cấu hình các tùy chọn lưu cho tài liệu của chúng tôi. Sử dụng lớp DocSaveOptions để chỉ định cài đặt lưu. Ví dụ :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };
```

Trong ví dụ này, chúng tôi tạo một đối tượng DocSaveOptions mới và đặt thuộc tính SavePictureBullet thành false để vô hiệu hóa việc lưu dấu đầu dòng ảnh.

## Bước 4: Kích hoạt tính năng “Không lưu dấu đầu dòng ảnh”

Để bật tính năng "Không lưu dấu đầu dòng ảnh", chúng tôi đã định cấu hình các tùy chọn lưu với SavePictureBullet được đặt thành sai. Điều này đảm bảo rằng dấu đầu dòng hình ảnh không được lưu trong tài liệu cuối cùng.

## Bước 5: Lưu tài liệu

Cuối cùng, bạn có thể lưu tài liệu bằng phương thức Save của lớp Document. Chỉ định đường dẫn đầy đủ đến tệp và tên tệp mong muốn. Ví dụ :

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

Đảm bảo thay thế "dataDir" bằng đường dẫn thư mục tới tài liệu của bạn.

## Mã nguồn ví dụ cho các tùy chọn lưu DocSaveOptions với chức năng "Không lưu dấu đầu dòng ảnh" bằng Aspose.Words cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tải tài liệu có dấu đầu dòng hình ảnh
Document doc = new Document(dataDir + "Image bullet points.docx");

// Định cấu hình tùy chọn lưu với tính năng "Không lưu dấu đầu dòng ảnh"
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };

// Lưu tài liệu với các tùy chọn được chỉ định
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã trình bày cách tắt tính năng lưu dấu đầu dòng hình ảnh trong tài liệu bằng thư viện Aspose.Words cho .NET. Bằng cách làm theo các bước được cung cấp và sử dụng mã nguồn C# được cung cấp, bạn có thể dễ dàng áp dụng chức năng này trong ứng dụng C# của mình. Việc tắt tính năng lưu dấu đầu dòng hình ảnh có thể hữu ích trong một số trường hợp để giữ nguyên cấu trúc và định dạng tài liệu mà không lưu dấu đầu dòng hình ảnh.