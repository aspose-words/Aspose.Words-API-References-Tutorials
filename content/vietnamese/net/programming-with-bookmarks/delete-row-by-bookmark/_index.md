---
title: Xóa hàng theo dấu trang trong tài liệu Word
linktitle: Xóa hàng theo dấu trang trong tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách xóa một hàng trong bảng dựa trên một dấu trang cụ thể trong tài liệu word bằng Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/programming-with-bookmarks/delete-row-by-bookmark/
---

Trong bài viết này, chúng ta sẽ khám phá mã nguồn C# ở trên để hiểu cách sử dụng hàm Xóa hàng theo dấu trang trong thư viện Aspose.Words cho .NET. Tính năng này cho phép bạn xóa một hàng trong bảng dựa trên một dấu trang cụ thể trong tài liệu word.

## Điều kiện tiên quyết

- Kiến thức cơ bản về ngôn ngữ C#.
- Môi trường phát triển .NET có cài đặt thư viện Aspose.Words.

## Bước 1: Lấy dấu trang

 Chúng tôi sử dụng`Bookmarks` thuộc tính của phạm vi tài liệu để lấy dấu trang cụ thể mà chúng tôi muốn sử dụng để xóa hàng trong bảng:

```csharp
Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];
```

## Bước 2: Xóa hàng của bảng

 Chúng tôi sử dụng`GetAncestor` phương pháp để có được`Row` gõ phần tử cha của dấu trang. Tiếp theo, chúng tôi sử dụng`Remove` phương pháp để loại bỏ hàng bảng:

```csharp
Row row = (Row)bookmark?.BookmarkStart.GetAncestor(typeof(Row));
row?.Remove();
```

### Mã nguồn mẫu cho Xóa hàng theo dấu trang bằng Aspose.Words cho .NET

Đây là mã nguồn mẫu đầy đủ để minh họa việc xóa một hàng trong bảng dựa trên một dấu trang cụ thể bằng Aspose.Words cho .NET:

```csharp

	Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

	Row row = (Row) bookmark?.BookmarkStart.GetAncestor(typeof(Row));
	row?.Remove();
        
```

## Phần kết luận

Trong bài viết này, chúng ta đã khám phá mã nguồn C# để hiểu cách sử dụng chức năng Xóa hàng theo dấu trang của Aspose.Words cho .NET. Chúng tôi đã làm theo hướng dẫn từng bước để xóa một hàng trong bảng dựa trên một dấu trang cụ thể trong tài liệu.

### Câu hỏi thường gặp về xóa hàng theo dấu trang trong tài liệu word

#### Câu hỏi: Tôi có thể xóa nhiều hàng bằng cùng một dấu trang không?

Đáp: Có, bạn có thể xóa nhiều hàng bằng cùng một dấu trang. Tuy nhiên, bạn cần xử lý logic trong mã của mình để xác định số hàng cần xóa và thực hiện các điều chỉnh cần thiết đối với đoạn mã được cung cấp.

#### Hỏi: Điều gì xảy ra nếu dấu trang không tồn tại trong tài liệu?

Đáp: Nếu dấu trang được chỉ định không tồn tại trong tài liệu thì đoạn mã sẽ trả về giá trị rỗng cho đối tượng dấu trang. Do đó, bạn cần xử lý tình huống này trong mã của mình bằng cách thêm các bước kiểm tra thích hợp trước khi cố gắng xóa hàng của bảng.

#### Câu hỏi: Thư viện Aspose.Words có được sử dụng miễn phí không?

 Trả lời: Thư viện Aspose.Words là thư viện thương mại và bạn có thể cần có giấy phép hợp lệ để sử dụng nó trong các dự án của mình. Bạn có thể ghé thăm[Aspose.Words cho tài liệu tham khảo API .NET](https://reference.aspose.com/words/net/) để tìm hiểu thêm về các tùy chọn cấp phép và giá cả của họ.

#### Hỏi: Tôi có thể xóa các hàng khỏi bảng trong một phần cụ thể của tài liệu Word không?

Đáp: Có, bạn có thể xóa các hàng khỏi bảng trong một phần cụ thể của tài liệu Word. Bạn có thể sửa đổi đoạn mã được cung cấp để nhắm mục tiêu một phần cụ thể bằng cách sử dụng phạm vi hoặc dấu trang thích hợp trong phần đó.