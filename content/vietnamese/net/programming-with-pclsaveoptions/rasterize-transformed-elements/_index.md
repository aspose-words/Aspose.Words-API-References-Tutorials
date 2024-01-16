---
title: Rasterize các phần tử đã chuyển đổi
linktitle: Rasterize các phần tử đã chuyển đổi
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách tắt tính năng rasterization của các phần tử đã chuyển đổi khi chuyển đổi sang định dạng PCL bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-pclsaveoptions/rasterize-transformed-elements/
---

Aspose.Words for .NET là một thư viện mạnh mẽ để tạo, thao tác và chuyển đổi tài liệu Word trong ứng dụng C#. Trong số các tính năng được Aspose.Words cung cấp là khả năng rasterize các phần tử đã chuyển đổi khi chuyển đổi tài liệu sang các định dạng khác nhau. Trong hướng dẫn này, chúng tôi sẽ chỉ cho bạn cách sử dụng mã nguồn C# của Aspose.Words cho .NET để tắt tính năng rasterization của các phần tử đã chuyển đổi khi chuyển đổi tài liệu sang định dạng PCL.

## Tìm hiểu thư viện Aspose.Words

Trước khi đi sâu vào mã, điều quan trọng là phải hiểu thư viện Aspose.Words cho .NET. Aspose.Words là một thư viện phổ biến giúp việc Xử lý văn bản bằng tài liệu Word trở nên dễ dàng và hiệu quả. Nó cung cấp nhiều tính năng để tạo, chỉnh sửa và chuyển đổi tài liệu Word, bao gồm hỗ trợ rasterize các phần tử đã chuyển đổi trong quá trình chuyển đổi.

## Đang tải tài liệu Word

Bước đầu tiên là tải tài liệu Word bạn muốn chuyển đổi sang định dạng PCL. Sử dụng lớp Tài liệu để tải tài liệu từ tệp nguồn. Đây là một ví dụ :

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

Trong ví dụ này, chúng tôi đang tải tài liệu "Rendering.docx" nằm trong thư mục tài liệu.

## Định cấu hình tùy chọn sao lưu

Bước tiếp theo là định cấu hình các tùy chọn lưu để chuyển đổi sang định dạng PCL. Sử dụng lớp PclSaveOptions và đặt thuộc tính RasterizeTransformedElements thành false. Đây là cách thực hiện:

```csharp
PclSaveOptions saveOptions = new PclSaveOptions
{
     SaveFormat = SaveFormat.Pcl,
     RasterizeTransformedElements = false
};
```

Chúng tôi tạo một đối tượng PclSaveOptions mới và đặt thuộc tính SaveFormat thành SaveFormat.Pcl để chỉ định rằng chúng tôi muốn lưu tài liệu ở định dạng PCL. Tiếp theo, chúng tôi đặt thuộc tính RasterizeTransformedElements thành false để tắt quá trình rasterization các phần tử đã chuyển đổi.

## Chuyển đổi tài liệu sang định dạng PCL

Bây giờ chúng ta đã định cấu hình các tùy chọn lưu, chúng ta có thể tiến hành chuyển đổi tài liệu sang định dạng PCL. Sử dụng phương thức Lưu của lớp Tài liệu để lưu tài liệu đã chuyển đổi ở định dạng PCL bằng cách chỉ định các tùy chọn lưu. Đây là một ví dụ :

```csharp
doc.Save(dataDir + "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl", saveOptions);
```

Trong ví dụ này, chúng tôi lưu tài liệu đã chuyển đổi dưới dạng "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl" bằng cách sử dụng các tùy chọn lưu đã chỉ định.

### Mã nguồn mẫu cho tính năng "Rasterize Transformed Elements" với Aspose.Words for .NET

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tải tài liệu Word


Document doc = new Document(dataDir + "Rendering.docx");

// Định cấu hình các tùy chọn sao lưu để chuyển đổi sang định dạng PCL
PclSaveOptions saveOptions = new PclSaveOptions
{
     SaveFormat = SaveFormat.Pcl,
     RasterizeTransformedElements = false
};

// Chuyển đổi tài liệu sang định dạng PCL
doc.Save(dataDir + "WorkingWithPclSaveOptions.RasterizeTransformedElements.pcl", saveOptions);
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã trình bày cách sử dụng Aspose.Words cho .NET để vô hiệu hóa quá trình rasterization của các phần tử đã chuyển đổi khi chuyển đổi tài liệu sang định dạng PCL bằng mã nguồn C# được cung cấp. Bằng cách làm theo các bước được cung cấp, bạn có thể dễ dàng kiểm soát hành vi rasterization của các phần tử được chuyển đổi khi chuyển đổi tài liệu Word của mình sang các định dạng khác nhau. Aspose.Words cung cấp tính linh hoạt và sức mạnh to lớn để làm việc với các phần tử được chuyển đổi, cho phép bạn tạo các tài liệu được chuyển đổi một cách chính xác theo nhu cầu cụ thể của mình.