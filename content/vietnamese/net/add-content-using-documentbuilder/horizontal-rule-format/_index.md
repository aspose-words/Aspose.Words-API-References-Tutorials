---
title: Định dạng thước kẻ ngang trong tài liệu Word
linktitle: Định dạng thước kẻ ngang trong tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách định dạng quy tắc ngang trong tài liệu Word bằng Aspose.Words cho .NET. Hướng dẫn từng bước một.
type: docs
weight: 10
url: /vi/net/add-content-using-documentbuilder/horizontal-rule-format/
---
Trong ví dụ toàn diện này, bạn sẽ tìm hiểu cách định dạng quy tắc ngang trong tài liệu Word bằng Aspose.Words cho .NET. Chúng tôi sẽ hướng dẫn bạn thực hiện quy trình và cung cấp cho bạn các đoạn mã C# cần thiết. Đến cuối hướng dẫn này, bạn sẽ có thể tùy chỉnh căn chỉnh, chiều rộng, chiều cao, màu sắc và các thuộc tính khác của quy tắc ngang.

## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo rằng bạn có các điều kiện tiên quyết sau:
- Thư viện Aspose.Words for .NET được cài đặt trên hệ thống của bạn.

## Bước 1: Tạo DocumentBuilder và chèn quy tắc ngang
Để bắt đầu, hãy tạo một đối tượng DocumentBuilder và sử dụng phương thức InsertHorizontalRule để chèn quy tắc ngang:

```csharp
DocumentBuilder builder = new DocumentBuilder();
Shape shape = builder.InsertHorizontalRule();
```

## Bước 2: Truy cập Định dạng quy tắc ngang
Tiếp theo, truy cập thuộc tính HorizontalRuleFormat của đối tượng Shape để lấy các tùy chọn định dạng:

```csharp
HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
```

## Bước 3: Tùy chỉnh các tùy chọn định dạng
Bây giờ, bạn có thể tùy chỉnh các tùy chọn định dạng khác nhau cho quy tắc ngang. Ví dụ: bạn có thể điều chỉnh căn chỉnh, chiều rộng, chiều cao, màu sắc và bóng đổ:

```csharp
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;
```

## Bước 4: Lưu tài liệu
Sau khi định dạng quy tắc ngang, lưu tài liệu vào file bằng phương thức Save của đối tượng Document:

```csharp
builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

### Mã nguồn ví dụ cho định dạng quy tắc ngang bằng cách sử dụng Aspose.Words cho .NET
Đây là mã nguồn hoàn chỉnh để định dạng quy tắc ngang bằng Aspose.Words cho .NET:

```csharp
DocumentBuilder builder = new DocumentBuilder();

Shape shape = builder.InsertHorizontalRule();

HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;

builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

Hãy nhớ điều chỉnh mã theo yêu cầu cụ thể của bạn và nâng cao nó bằng chức năng bổ sung nếu cần.

## Phần kết luận
Chúc mừng! Bạn đã học thành công cách định dạng thước ngang trong tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước và sử dụng mã nguồn được cung cấp, giờ đây bạn có thể tùy chỉnh giao diện của các quy tắc ngang để nâng cao bố cục trực quan của tài liệu.

Thử nghiệm với các tùy chọn định dạng khác nhau để đạt được phong cách và hiệu ứng mong muốn cho các quy tắc ngang của bạn.

### Câu hỏi thường gặp về định dạng quy tắc ngang trong tài liệu word

#### Câu hỏi: Tôi có thể áp dụng các màu khác nhau cho thước kẻ ngang không?

Đ: Chắc chắn rồi! Với Aspose.Words for .NET, bạn có thể dễ dàng tùy chỉnh màu của thước ngang bằng cách đặt thuộc tính Color thành giá trị màu mong muốn. Điều này cho phép bạn khớp quy tắc ngang với thiết kế tổng thể của tài liệu.

#### Hỏi: Có thể điều chỉnh độ rộng và chiều cao của thước ngang được không?

Đáp: Có, bạn có toàn quyền kiểm soát chiều rộng và chiều cao của thước ngang. Bằng cách sửa đổi thuộc tính Chiều rộng và Chiều cao, bạn có thể đạt được kích thước mong muốn cho quy tắc ngang.

#### Câu hỏi: Tôi có thể thay đổi cách căn chỉnh của thước ngang trong tài liệu không?

Đ: Chắc chắn rồi! Aspose.Words for .NET cho phép bạn chỉ định căn chỉnh của quy tắc ngang bằng thuộc tính Alignment. Bạn có thể chọn từ nhiều tùy chọn khác nhau như Giữa, Trái, Phải và Căn đều.

#### Câu hỏi: Tôi có thể áp dụng màu nền hoặc màu nền cho quy tắc ngang không?

Trả lời: Có, bạn có thể thêm màu nền hoặc màu nền cho quy tắc ngang. Theo mặc định, thuộc tính NoShade được đặt thành true, nhưng bạn có thể đặt nó thành false và xác định độ bóng bằng các phương pháp thích hợp.

#### Câu hỏi: Tôi có thể chèn nhiều quy tắc ngang vào một tài liệu không?

Đ: Chắc chắn rồi! Bạn có thể chèn nhiều quy tắc ngang trong tài liệu Word bằng Aspose.Words for .NET. Chỉ cần lặp lại các bước trong hướng dẫn nếu cần để thêm bao nhiêu quy tắc ngang theo yêu cầu của bạn.