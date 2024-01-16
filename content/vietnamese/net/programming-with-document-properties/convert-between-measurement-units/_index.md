---
title: Chuyển đổi giữa các đơn vị đo lường
linktitle: Chuyển đổi giữa các đơn vị đo lường
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để chuyển đổi giữa các đơn vị đo lường trong tài liệu bằng Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/programming-with-document-properties/convert-between-measurement-units/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn mã nguồn C# để chuyển đổi giữa các đơn vị đo lường bằng Aspose.Words cho .NET. Tính năng này cho phép bạn chỉ định lề, khoảng cách đầu trang và chân trang, v.v. theo các đơn vị đo lường khác nhau.

## Bước 1: Thiết lập dự án

Để bắt đầu, hãy tạo một dự án C# mới trong IDE yêu thích của bạn. Đảm bảo thư viện Aspose.Words for .NET được tham chiếu trong dự án của bạn.

## Bước 2: Tạo tài liệu và hàm tạo

Trong bước này, chúng ta sẽ tạo một tài liệu mới và khởi tạo hàm tạo. Sử dụng mã sau đây:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 3: Cấu hình đơn vị đo

Bây giờ chúng ta sẽ chuyển đổi các giá trị về khoảng cách lề, đầu trang và chân trang, v.v. theo các đơn vị đo lường khác nhau. Sử dụng đoạn mã sau để chỉ định giá trị theo đơn vị đo lường cụ thể:

```csharp
PageSetup pageSetup = builder.PageSetup;
pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
```

 Mã này sử dụng`ConvertUtil` lớp Aspose.Words để chuyển đổi các giá trị được chỉ định thành inch (`InchToPoint` ). Bạn cũng có thể sử dụng các phương pháp chuyển đổi khác có sẵn trong`ConvertUtil` lớp để chuyển đổi giá trị sang các đơn vị đo lường khác.

### Mã nguồn ví dụ về Chuyển đổi giữa các đơn vị đo lường bằng Aspose.Words cho .NET

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	PageSetup pageSetup = builder.PageSetup;
	pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
	pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
	pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
	pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
	pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
	pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
  
```

Bây giờ bạn đã học cách chuyển đổi giữa các đơn vị đo lường khi chỉ định khoảng cách lề, đầu trang và chân trang, v.v. trong tài liệu bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước được cung cấp trong hướng dẫn này, bạn có thể dễ dàng chỉ định các giá trị trong đơn vị đo lường mong muốn trong tài liệu của riêng mình.