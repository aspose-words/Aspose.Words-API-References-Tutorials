---
title: Chèn tài liệu vào thay thế
linktitle: Chèn tài liệu vào thay thế
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chèn liền mạch một tài liệu Word vào một tài liệu Word khác bằng Aspose.Words cho .NET với hướng dẫn từng bước chi tiết của chúng tôi. Hoàn hảo cho các nhà phát triển muốn hợp lý hóa việc xử lý tài liệu.
type: docs
weight: 10
url: /vi/net/clone-and-combine-documents/insert-document-at-replace/
---
## Giới thiệu

Này, các chuyên gia tài liệu! Bạn đã bao giờ thấy mình đắm chìm trong mã nguồn, cố gắng tìm ra cách chèn một tài liệu Word vào một tài liệu Word khác một cách liền mạch chưa? Đừng lo, vì hôm nay chúng ta sẽ đi sâu vào thế giới Aspose.Words dành cho .NET để thực hiện công việc đó một cách dễ dàng. Chúng tôi sẽ hướng dẫn chi tiết từng bước về cách sử dụng thư viện mạnh mẽ này để chèn tài liệu vào các điểm cụ thể trong quá trình tìm và thay thế. Bạn đã sẵn sàng trở thành chuyên gia Aspose.Words chưa? Hãy bắt đầu!

## Điều kiện tiên quyết

Trước khi chúng ta bắt đầu viết mã, có một số điều bạn cần phải chuẩn bị sẵn:

-  Visual Studio: Đảm bảo bạn đã cài đặt Visual Studio trên máy của mình. Nếu bạn chưa có nó, bạn có thể tải xuống từ[đây](https://visualstudio.microsoft.com/).
-  Aspose.Words for .NET: Bạn sẽ cần thư viện Aspose.Words. Bạn có thể lấy nó từ[trang web giả định](https://releases.aspose.com/words/net/).
- Kiến thức cơ bản về C#: Hiểu biết cơ bản về C# và .NET sẽ giúp bạn làm theo hướng dẫn này.

Được rồi, bỏ những thứ đó đi, hãy bắt tay vào thực hiện một số mã!

## Nhập không gian tên

Trước tiên, chúng ta cần nhập các không gian tên cần thiết để hoạt động với Aspose.Words. Điều này giống như thu thập tất cả các công cụ của bạn trước khi bắt đầu một dự án. Thêm các lệnh sử dụng này vào đầu tệp C# của bạn:

```csharp
using System;
using System.Text.RegularExpressions;
using Aspose.Words;
using Aspose.Words.Replacing;
using Aspose.Words.Tables;
```

Bây giờ chúng ta đã có các điều kiện tiên quyết, hãy chia quy trình thành các bước vừa phải. Mỗi bước đều quan trọng và sẽ đưa chúng ta đến gần hơn với mục tiêu của mình.

## Bước 1: Thiết lập thư mục tài liệu

Đầu tiên, chúng ta cần chỉ định thư mục lưu trữ tài liệu của chúng ta. Điều này giống như việc chuẩn bị sân khấu trước buổi biểu diễn lớn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn đến thư mục của bạn. Đây là nơi tài liệu của bạn sẽ sống và thở.

## Bước 2: Tải tài liệu chính

Tiếp theo, chúng tôi tải tài liệu chính mà chúng tôi muốn chèn tài liệu khác vào. Hãy coi đây là giai đoạn chính của chúng ta, nơi tất cả hành động sẽ diễn ra.

```csharp
Document mainDoc = new Document(dataDir + "Document insertion 1.docx");
```

Mã này tải tài liệu chính từ thư mục được chỉ định.

## Bước 3: Đặt tùy chọn tìm và thay thế

Để tìm vị trí cụ thể mà chúng tôi muốn chèn tài liệu của mình, chúng tôi sử dụng chức năng tìm và thay thế. Điều này giống như sử dụng bản đồ để tìm vị trí chính xác cho phần bổ sung mới của chúng tôi.

```csharp
FindReplaceOptions options = new FindReplaceOptions
{
    Direction = FindReplaceDirection.Backward,
    ReplacingCallback = new InsertDocumentAtReplaceHandler()
};
```

Ở đây, chúng tôi đang đặt hướng lùi và chỉ định trình xử lý gọi lại tùy chỉnh mà chúng tôi sẽ xác định tiếp theo.

## Bước 4: Thực hiện thao tác Thay thế

Bây giờ, chúng tôi yêu cầu tài liệu chính của mình tìm kiếm một văn bản giữ chỗ cụ thể và không thay thế nó bằng gì, trong khi sử dụng lệnh gọi lại tùy chỉnh của chúng tôi để chèn một tài liệu khác.

```csharp
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

Mã này thực hiện thao tác tìm và thay thế, sau đó lưu tài liệu đã cập nhật.

## Bước 5: Tạo Trình xử lý gọi lại thay thế tùy chỉnh

Trình xử lý gọi lại tùy chỉnh của chúng tôi là nơi điều kỳ diệu xảy ra. Trình xử lý này sẽ xác định cách thực hiện chèn tài liệu trong quá trình tìm và thay thế.

```csharp
private class InsertDocumentAtReplaceHandler : IReplacingCallback
{
    ReplaceAction IReplacingCallback.Replacing(ReplacingArgs args)
    {
        Document subDoc = new Document(dataDir + "Document insertion 2.docx");

        // Chèn tài liệu sau đoạn văn có chứa văn bản trùng khớp.
        Paragraph para = (Paragraph)args.MatchNode.ParentNode;
        InsertDocument(para, subDoc);

        // Xóa đoạn văn có văn bản trùng khớp.
        para.Remove();
        return ReplaceAction.Skip;
    }
}
```

Ở đây, chúng ta tải tài liệu cần chèn và sau đó gọi một phương thức trợ giúp để thực hiện thao tác chèn.

## Bước 6: Xác định phương pháp chèn tài liệu

Phần cuối cùng của câu đố của chúng ta là phương pháp thực sự chèn tài liệu vào vị trí đã chỉ định.

```csharp
private static void InsertDocument(Node insertionDestination, Document docToInsert)
{
	if (insertionDestination.NodeType == NodeType.Paragraph || insertionDestination.NodeType == NodeType.Table)
	{
		CompositeNode destinationParent = insertionDestination.ParentNode;

		NodeImporter importer =
			new NodeImporter(docToInsert, insertionDestination.Document, ImportFormatMode.KeepSourceFormatting);

		// Lặp qua tất cả các nút cấp khối trong phần thân của phần,
		// sau đó sao chép và chèn mọi nút không phải là đoạn trống cuối cùng của một phần.
		foreach (Section srcSection in docToInsert.Sections.OfType<Section>())
		foreach (Node srcNode in srcSection.Body)
		{
			if (srcNode.NodeType == NodeType.Paragraph)
			{
				Paragraph para = (Paragraph)srcNode;
				if (para.IsEndOfSection && !para.HasChildNodes)
					continue;
			}

			Node newNode = importer.ImportNode(srcNode, true);

			destinationParent.InsertAfter(newNode, insertionDestination);
			insertionDestination = newNode;
		}
	}
	else
	{
		throw new ArgumentException("The destination node should be either a paragraph or table.");
	}
}
```

Phương pháp này đảm nhiệm việc nhập các nút từ tài liệu cần chèn và đặt chúng vào đúng vị trí trong tài liệu chính.

## Phần kết luận

Và bạn có nó! Hướng dẫn toàn diện để chèn tài liệu này vào tài liệu khác bằng Aspose.Words cho .NET. Bằng cách làm theo các bước này, bạn có thể dễ dàng tự động hóa các tác vụ thao tác và lắp ráp tài liệu. Cho dù bạn đang xây dựng một hệ thống quản lý tài liệu hay chỉ cần hợp lý hóa quy trình xử lý tài liệu của mình, Aspose.Words là người bạn đồng hành đáng tin cậy của bạn.

## Câu hỏi thường gặp

### Aspose.Words cho .NET là gì?
Aspose.Words for .NET là một thư viện mạnh mẽ để thao tác các tài liệu Word theo chương trình. Nó cho phép bạn tạo, sửa đổi, chuyển đổi và xử lý tài liệu Word một cách dễ dàng.

### Tôi có thể chèn nhiều tài liệu cùng một lúc không?
Có, bạn có thể sửa đổi trình xử lý gọi lại để xử lý nhiều phần chèn bằng cách lặp lại một tập hợp tài liệu.

### Có bản dùng thử miễn phí không?
 Tuyệt đối! Bạn có thể tải xuống bản dùng thử miễn phí từ[đây](https://releases.aspose.com/).

### Làm cách nào để nhận được hỗ trợ cho Aspose.Words?
Bạn có thể nhận được hỗ trợ bằng cách truy cập[Diễn đàn Aspose.Words](https://forum.aspose.com/c/words/8).

### Tôi có thể giữ nguyên định dạng của tài liệu được chèn không?
 Vâng, cái`NodeImporter` lớp cho phép bạn chỉ định cách xử lý định dạng khi nhập các nút từ tài liệu này sang tài liệu khác.