---
title: Hiển thị ẩn nội dung được đánh dấu trong tài liệu Word
linktitle: Hiển thị ẩn nội dung được đánh dấu trong tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách hiển thị và ẩn nội dung được đánh dấu trong tài liệu Word bằng Aspose.Words cho .NET với hướng dẫn chi tiết từng bước này.
type: docs
weight: 10
url: /vi/net/programming-with-bookmarks/show-hide-bookmarked-content/
---
## Giới thiệu

Bạn đã sẵn sàng bước vào thế giới thao tác tài liệu với Aspose.Words cho .NET chưa? Cho dù bạn là nhà phát triển đang tìm cách tự động hóa các tác vụ tài liệu hay chỉ là người tò mò về cách xử lý tệp Word theo chương trình thì bạn đã đến đúng nơi. Hôm nay, chúng ta sẽ khám phá cách hiển thị và ẩn nội dung được đánh dấu trong tài liệu Word bằng Aspose.Words cho .NET. Hướng dẫn từng bước này sẽ giúp bạn trở thành chuyên gia trong việc kiểm soát khả năng hiển thị nội dung dựa trên dấu trang. Hãy bắt đầu!

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào vấn đề chi tiết, có một số điều bạn cần:

1. Visual Studio: Bất kỳ phiên bản nào tương thích với .NET.
2.  Aspose.Words cho .NET: Tải xuống[đây](https://releases.aspose.com/words/net/).
3. Hiểu biết cơ bản về C#: Nếu bạn có thể viết một chương trình "Xin chào thế giới" đơn giản thì bạn đã sẵn sàng.
4. Tài liệu Word có dấu trang: Chúng tôi sẽ sử dụng tài liệu mẫu có dấu trang cho hướng dẫn này.

## Nhập không gian tên

Trước tiên, hãy nhập các không gian tên cần thiết. Điều này đảm bảo chúng tôi có tất cả các công cụ cần thiết cho nhiệm vụ của mình.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Bookmark;
```

Với những không gian tên này, tất cả chúng ta đã sẵn sàng bắt đầu hành trình của mình.

## Bước 1: Thiết lập dự án của bạn

Được rồi, hãy bắt đầu mọi thứ bằng cách thiết lập dự án của chúng ta trong Visual Studio.

### Tạo một dự án mới

Mở Visual Studio và tạo dự án Console App (.NET Core) mới. Đặt tên gì đó hấp dẫn, chẳng hạn như "BookmarkVisibilityManager".

### Thêm Aspose.Words cho .NET

Bạn sẽ cần thêm Aspose.Words for .NET vào dự án của mình. Bạn có thể thực hiện việc này thông qua Trình quản lý gói NuGet.

1. Đi tới Công cụ > Trình quản lý gói NuGet > Quản lý gói NuGet cho Giải pháp.
2. Tìm kiếm "Aspose.Words".
3. Cài đặt gói.

Tuyệt vời! Bây giờ dự án của chúng ta đã được thiết lập, hãy chuyển sang tải tài liệu của chúng ta.

## Bước 2: Tải tài liệu

Chúng ta cần tải tài liệu Word có chứa dấu trang. Đối với hướng dẫn này, chúng tôi sẽ sử dụng tài liệu mẫu có tên "Bookmarks.docx".

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

 Đoạn mã này đặt đường dẫn đến thư mục tài liệu của bạn và tải tài liệu vào thư mục`doc` sự vật.

## Bước 3: Hiển thị/Ẩn nội dung được đánh dấu

Bây giờ đến phần thú vị – hiển thị hoặc ẩn nội dung dựa trên dấu trang. Chúng ta sẽ tạo một phương thức gọi là`ShowHideBookmarkedContent` để xử lý việc này.

Đây là phương pháp sẽ chuyển đổi khả năng hiển thị của nội dung được đánh dấu:

```csharp
public void ShowHideBookmarkedContent(Document doc, string bookmarkName, bool isHidden)
{
    Bookmark bm = doc.Range.Bookmarks[bookmarkName];

    Node currentNode = bm.BookmarkStart;
    while (currentNode != null && currentNode.NodeType != NodeType.BookmarkEnd)
    {
        if (currentNode.NodeType == NodeType.Run)
        {
            Run run = currentNode as Run;
            run.Font.Hidden = isHidden;
        }
        currentNode = currentNode.NextSibling;
    }
}
```

### Phân tích phương pháp

-  Truy xuất dấu trang:`Bookmark bm = doc.Range.Bookmarks[bookmarkName];` tìm nạp dấu trang.
- Truyền tải nút: Chúng tôi duyệt qua các nút trong dấu trang.
-  Chuyển đổi mức độ hiển thị: Nếu nút là một`Run` (một dòng văn bản liền kề), chúng tôi đặt nó`Hidden` tài sản.

## Bước 4: Áp dụng phương pháp

Với phương pháp của chúng tôi đã sẵn sàng, hãy áp dụng nó để hiển thị hoặc ẩn nội dung dựa trên dấu trang.

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", true);
```

Dòng mã này sẽ ẩn nội dung trong dấu trang có tên "MyBookmark1".

## Bước 5: Lưu tài liệu

Cuối cùng, hãy lưu tài liệu đã sửa đổi của chúng tôi.

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

Thao tác này sẽ lưu tài liệu với những thay đổi mà chúng tôi đã thực hiện.

## Phần kết luận

Và bạn có nó! Bạn vừa học cách hiển thị và ẩn nội dung được đánh dấu trong tài liệu Word bằng Aspose.Words for .NET. Công cụ mạnh mẽ này giúp thao tác tài liệu trở nên dễ dàng, cho dù bạn đang tự động hóa báo cáo, tạo mẫu hay chỉ mày mò các tệp Word. Chúc mừng mã hóa!

## Câu hỏi thường gặp

### Tôi có thể chuyển đổi nhiều dấu trang cùng một lúc không?
 Có, bạn có thể gọi`ShowHideBookmarkedContent` phương pháp cho mỗi dấu trang bạn muốn chuyển đổi.

### Việc ẩn nội dung có ảnh hưởng đến cấu trúc của tài liệu không?
Không, việc ẩn nội dung chỉ ảnh hưởng đến khả năng hiển thị của nội dung đó. Nội dung vẫn còn trong tài liệu.

### Tôi có thể sử dụng phương pháp này cho các loại nội dung khác không?
Phương pháp này đặc biệt chuyển đổi việc chạy văn bản. Đối với các loại nội dung khác, bạn sẽ cần sửa đổi logic truyền tải nút.

### Aspose.Words cho .NET có miễn phí không?
 Aspose.Words cung cấp bản dùng thử miễn phí[đây](https://releases.aspose.com/) , nhưng cần có giấy phép đầy đủ để sử dụng sản xuất. Bạn có thể mua nó[đây](https://purchase.aspose.com/buy).

### Làm cách nào tôi có thể nhận được hỗ trợ nếu gặp sự cố?
 Bạn có thể nhận được hỗ trợ từ cộng đồng Aspose[đây](https://forum.aspose.com/c/words/8).