---
title: Gỡ rối các dấu trang hàng trong tài liệu Word
linktitle: Gỡ rối các dấu trang hàng trong tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách gỡ rối các dấu trang hàng lồng nhau trong tài liệu word để xóa các hàng cụ thể mà không ảnh hưởng đến các dấu trang khác.
type: docs
weight: 10
url: /vi/net/programming-with-bookmarks/untangle-row-bookmarks/
---

Trong bài viết này, chúng ta sẽ khám phá mã nguồn C# ở trên để hiểu cách sử dụng hàm Untangle Row Bookmarks trong thư viện Aspose.Words for .NET. Chức năng này cho phép đặt phần cuối của dấu trang trong cùng một dòng với phần đầu của dấu trang.

## Điều kiện tiên quyết

- Kiến thức cơ bản về ngôn ngữ C#.
- Môi trường phát triển .NET có cài đặt thư viện Aspose.Words.

## Bước 1: Tải tài liệu

 Chúng tôi sử dụng`Document` lớp để tải tài liệu hiện có từ một tệp:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Table column bookmarks.docx");
```

## Bước 2: Làm sáng tỏ dấu trang dòng

 Chúng tôi sử dụng`Untangle` chức năng gỡ rối dấu trang từ các hàng. Hàm này thực hiện nhiệm vụ tùy chỉnh là đặt dấu trang cuối dòng vào cùng dòng khi dấu trang bắt đầu:

```csharp
Untangle(doc);
```

## Bước 3: Xóa dòng theo dấu trang

 Chúng tôi sử dụng`DeleteRowByBookmark` chức năng xóa một hàng cụ thể bằng dấu trang của nó:

```csharp
DeleteRowByBookmark(doc, "ROW2");
```

## Bước 4: Kiểm tra tính toàn vẹn của các dấu trang khác

Chúng tôi xác minh rằng các dấu trang khác không bị hỏng bằng cách kiểm tra xem phần cuối của dấu trang có còn tồn tại hay không:

```csharp
if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
throw new Exception("Wrong, the end of the bookmark was deleted.");

doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");
```

### Mã nguồn mẫu cho Dấu trang gỡ rối hàng bằng Aspose.Words cho .NET

Đây là mã nguồn mẫu đầy đủ để gỡ rối dấu trang khỏi các dòng bằng Aspose.Words cho .NET:


```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Table column bookmarks.docx");

	//Điều này thực hiện nhiệm vụ tùy chỉnh là đặt các đầu dấu trang của hàng vào cùng một hàng với phần đầu dấu trang bắt đầu.
	Untangle(doc);

	// Bây giờ chúng ta có thể dễ dàng xóa các hàng bằng dấu trang mà không làm hỏng dấu trang của bất kỳ hàng nào khác.
	DeleteRowByBookmark(doc, "ROW2");

	// Việc này chỉ để kiểm tra xem dấu trang kia có bị hỏng hay không.
	if (doc.Range.Bookmarks["ROW1"].BookmarkEnd == null)
		throw new Exception("Wrong, the end of the bookmark was deleted.");

	doc.Save(dataDir + "WorkingWithBookmarks.UntangleRowBookmarks.docx");

```

#### Gỡ rối mã nguồn
```csharp

private void Untangle(Document doc)
        {
            foreach (Bookmark bookmark in doc.Range.Bookmarks)
            {
                // Lấy hàng cha của cả nút đánh dấu và nút cuối dấu trang.
                Row row1 = (Row) bookmark.BookmarkStart.GetAncestor(typeof(Row));
                Row row2 = (Row) bookmark.BookmarkEnd.GetAncestor(typeof(Row));

                // Nếu cả hai hàng đều ổn và dấu trang bắt đầu và kết thúc được chứa trong các hàng liền kề,
                // di chuyển nút cuối dấu trang đến cuối đoạn cuối cùng trong ô cuối cùng của hàng trên cùng.
                if (row1 != null && row2 != null && row1.NextSibling == row2)
                    row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
            }
        }

```

#### Mã nguồn DeleteRowByBookmark
```csharp

 private void DeleteRowByBookmark(Document doc, string bookmarkName)
        {
            Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

            Row row = (Row) bookmark?.BookmarkStart.GetAncestor(typeof(Row));
            row?.Remove();
        }

```
## Phần kết luận

Trong bài viết này, chúng ta đã khám phá mã nguồn C# để hiểu cách sử dụng tính năng Untangle Row Bookmarks của Aspose.Words cho .NET. Chúng tôi đã làm theo hướng dẫn từng bước để gỡ rối các dấu trang hàng và xóa một hàng cụ thể mà không làm hỏng các dấu trang khác.

### Câu hỏi thường gặp về gỡ rối dấu trang trong tài liệu word

#### Câu hỏi: Dấu trang sắp xếp lại hàng có chỉ hoạt động với dấu trang hàng trong bảng không?

Trả lời: Có, tính năng Gỡ rối dấu trang hàng được thiết kế đặc biệt để gỡ rối các dấu trang hàng trong bảng. Chức năng này có thể được sử dụng để xử lý dấu trang dòng trong mảng và đảm bảo rằng phần cuối của dấu trang ở cùng dòng khi dấu trang bắt đầu.

#### Câu hỏi: Chức năng Đánh dấu dòng sắp xếp lại có sửa đổi nội dung của tài liệu gốc không?

Trả lời: Có, chức năng Dấu trang dòng sắp xếp lại sẽ sửa đổi tài liệu gốc bằng cách di chuyển phần cuối của dấu trang để đặt chúng vào cùng dòng với phần đầu của dấu trang. Đảm bảo lưu bản sao lưu của tài liệu trước khi áp dụng tính năng này.

#### Hỏi: Làm cách nào tôi có thể xác định dấu trang dòng trong tài liệu Word của mình?

Đáp: Dấu trang hàng thường được sử dụng trong bảng để đánh dấu các phần cụ thể. Bạn có thể xác định dấu trang hàng bằng cách duyệt qua dấu trang trong tài liệu và kiểm tra xem dấu trang có nằm trong các hàng của bảng hay không.

#### Câu hỏi: Có thể gỡ rối các dấu trang hàng trong các bảng không liền kề không?

Trả lời: Chức năng Gỡ rối Dấu trang hàng như được trình bày trong bài viết này được thiết kế để gỡ rối dấu trang hàng trong các bảng liền kề. Để gỡ rối các dấu trang hàng trong các bảng không liền kề, có thể cần phải điều chỉnh thêm mã tùy thuộc vào cấu trúc của tài liệu.

#### Câu hỏi: Tôi có thể thực hiện những thao tác nào khác trên dấu trang hàng sau khi chúng đã được làm sáng tỏ?

Trả lời: Sau khi các dấu trang dòng được tách ra, bạn có thể thực hiện các thao tác khác nhau nếu cần. Điều này có thể bao gồm chỉnh sửa, xóa hoặc thêm nội dung vào các dòng được đánh dấu. Hãy đảm bảo xử lý các dấu trang một cách cẩn thận để tránh mọi tác động không mong muốn đến phần còn lại của tài liệu.