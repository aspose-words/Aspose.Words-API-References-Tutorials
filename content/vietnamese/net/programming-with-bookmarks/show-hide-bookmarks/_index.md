---
title: Hiển thị Ẩn dấu trang trong tài liệu Word
linktitle: Hiển thị Ẩn dấu trang trong tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách hiển thị hoặc ẩn dấu trang cụ thể trong tài liệu word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-bookmarks/show-hide-bookmarks/
---

Trong bài viết này, chúng ta sẽ khám phá mã nguồn C# ở trên để hiểu cách sử dụng chức năng Hiển thị Ẩn Dấu trang trong thư viện Aspose.Words cho .NET. Tính năng này cho phép bạn hiển thị hoặc ẩn một dấu trang cụ thể trong tài liệu word.

## Điều kiện tiên quyết

- Kiến thức cơ bản về ngôn ngữ C#.
- Môi trường phát triển .NET có cài đặt thư viện Aspose.Words.

## Bước 1: Tải tài liệu

 Chúng tôi sử dụng`Document` lớp để tải tài liệu hiện có từ một tệp:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## Bước 2: Hiển thị hoặc ẩn dấu trang cụ thể

 Chúng tôi sử dụng`ShowHideBookmarkedContent`chức năng hiển thị hoặc ẩn một dấu trang cụ thể trong tài liệu. Hàm này lấy các tham số của tài liệu, tên của dấu trang và boolean để cho biết nên hiển thị hay ẩn dấu trang:

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", false);
```

## Bước 3: Lưu tài liệu đã sửa đổi

 Chúng tôi sử dụng`Save` phương pháp lưu tài liệu đã sửa đổi vào một tệp:

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

### Mã nguồn ví dụ cho Hiển thị Ẩn Dấu trang bằng Aspose.Words cho .NET

Đây là mã nguồn ví dụ đầy đủ để minh họa việc hiển thị hoặc ẩn một dấu trang cụ thể bằng Aspose.Words cho .NET:

```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");

	ShowHideBookmarkedContent(doc, "MyBookmark1", false);
	
	doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");

```

#### ShowHideBookmarkedMã nguồn nội dung

```csharp

public void ShowHideBookmarkedContent(Document doc, string bookmarkName, bool showHide)
        {
            Bookmark bm = doc.Range.Bookmarks[bookmarkName];

            DocumentBuilder builder = new DocumentBuilder(doc);
            builder.MoveToDocumentEnd();

            // {IF "{Dấu trang MERGEFIELD}" = "true" "" ""}
            Field field = builder.InsertField("IF \"", null);
            builder.MoveTo(field.Start.NextSibling);
            builder.InsertField("MERGEFIELD " + bookmarkName + "", null);
            builder.Write("\" = \"true\" ");
            builder.Write("\"");
            builder.Write("\"");
            builder.Write(" \"\"");

            Node currentNode = field.Start;
            bool flag = true;
            while (currentNode != null && flag)
            {
                if (currentNode.NodeType == NodeType.Run)
                    if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
                        flag = false;

                Node nextNode = currentNode.NextSibling;

                bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
                currentNode = nextNode;
            }

            Node endNode = bm.BookmarkEnd;
            flag = true;
            while (currentNode != null && flag)
            {
                if (currentNode.NodeType == NodeType.FieldEnd)
                    flag = false;

                Node nextNode = currentNode.NextSibling;

                bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
                endNode = currentNode;
                currentNode = nextNode;
            }

            doc.MailMerge.Execute(new[] { bookmarkName }, new object[] { showHide });
        }
		
```
## Phần kết luận

Trong bài viết này, chúng ta đã khám phá mã nguồn C# để hiểu cách sử dụng tính năng Hiển thị Ẩn Dấu trang của Aspose.Words cho .NET. Chúng tôi đã làm theo hướng dẫn từng bước để hiển thị hoặc ẩn dấu trang cụ thể trong tài liệu.

### Câu hỏi thường gặp về ẩn dấu trang trong tài liệu word

#### Hỏi: Tôi có thể hiển thị hoặc ẩn nhiều dấu trang trong cùng một tài liệu không?

Đáp: Có, bạn có thể hiển thị hoặc ẩn nhiều dấu trang trong cùng một tài liệu bằng cách lặp lại bước 2 và 3 cho mỗi dấu trang bạn muốn xử lý.

#### Hỏi: Mã được cung cấp có hoạt động với các định dạng tài liệu Word khác, chẳng hạn như .doc hoặc .docm không?

Đáp: Có, mã được cung cấp hoạt động với nhiều định dạng tài liệu Word khác nhau được Aspose.Words hỗ trợ, chẳng hạn như .doc và .docm. Chỉ cần đảm bảo sử dụng đúng tên tệp và đường dẫn khi tải và lưu tài liệu.

#### Hỏi: Làm cách nào tôi có thể hiển thị lại dấu trang bị ẩn?

 Đáp: Để hiển thị lại dấu trang bị ẩn, bạn cần sử dụng cùng một`ShowHideBookmarkedContent` hàm truyền giá trị`true` đối với tham số boolean cho biết hiển thị hay ẩn dấu trang.

#### Câu hỏi: Tôi có thể sử dụng các điều kiện để hiển thị hoặc ẩn dấu trang dựa trên giá trị trường hợp nhất trong tài liệu không?

 Đáp: Có, bạn có thể sử dụng các điều kiện và hợp nhất các giá trị trường để xác định xem dấu trang sẽ được hiển thị hay ẩn. Bạn có thể tùy chỉnh mã của`ShowHideBookmarkedContent` có tính đến các điều kiện và giá trị thích hợp.

#### Hỏi: Làm cách nào tôi có thể xóa dấu trang trong tài liệu Word bằng Aspose.Words cho .NET?

 Trả lời: Để xóa dấu trang trong tài liệu Word bằng Aspose.Words cho .NET, bạn có thể sử dụng`RemoveBookmarks` phương pháp của`Document` lớp học. Đây là một mã mẫu:

```csharp
doc.RemoveBookmarks("BookmarkName");
```