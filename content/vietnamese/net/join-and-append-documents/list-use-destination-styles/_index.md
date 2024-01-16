---
title: Danh sách sử dụng kiểu đích
linktitle: Danh sách sử dụng kiểu đích
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách nối và nối các tài liệu Word trong khi vẫn giữ nguyên kiểu danh sách của tài liệu đích bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/join-and-append-documents/list-use-destination-styles/
---

Hướng dẫn này sẽ hướng dẫn bạn trong quá trình sử dụng tính năng Kiểu đích sử dụng danh sách của Aspose.Words cho .NET. Tính năng này cho phép bạn nối và nối các tài liệu Word trong khi sử dụng kiểu danh sách của tài liệu đích.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

1. Đã cài đặt Aspose.Words cho .NET. Bạn có thể tải xuống từ trang web Aspose hoặc cài đặt nó qua NuGet.
2. Visual Studio hoặc bất kỳ môi trường phát triển C# nào khác.

## Bước 1: Khởi tạo thư mục tài liệu

 Đầu tiên, bạn cần đặt đường dẫn đến thư mục tài liệu của mình. Sửa đổi giá trị của`dataDir` có thể thay đổi đường dẫn chứa tài liệu của bạn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tải tài liệu nguồn và đích

 Tiếp theo, bạn cần tải tài liệu nguồn và đích bằng Aspose.Words`Document` lớp học. Cập nhật tên tập tin trong`Document` hàm tạo theo tên tài liệu của bạn.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Bước 3: Đặt Tài liệu Nguồn thành Tiếp tục sau Tài liệu Đích

 Để đảm bảo rằng nội dung từ tài liệu nguồn tiếp tục sau khi kết thúc tài liệu đích, bạn cần đặt`SectionStart` thuộc tính của phần đầu tiên trong tài liệu nguồn để`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Bước 4: Xử lý định dạng danh sách

Để xử lý định dạng danh sách, bạn sẽ lặp qua từng đoạn trong tài liệu nguồn và kiểm tra xem đó có phải là một mục danh sách hay không. Nếu đúng như vậy, bạn sẽ so sánh ID danh sách với các danh sách hiện có trong tài liệu đích. Nếu tồn tại một danh sách có cùng ID, bạn sẽ tạo một bản sao của danh sách trong tài liệu nguồn và cập nhật định dạng danh sách của đoạn văn để sử dụng danh sách đã sao chép.

```csharp
Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();

foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    if (para.IsListItem)
    {
        int listId = para.ListFormat.List.ListId;
        if (dstDoc.Lists.GetListByListId(listId) != null)
        {
            Aspose.Words.Lists.List currentList;
            if (newLists.ContainsKey(listId))
            {
                currentList = newLists[listId];
            }
            else
            {
                currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
                newLists.Add(listId, currentList);
            }
            para.ListFormat.List = currentList;
        }
    }
}
```

## Bước 5: Nối tài liệu nguồn vào tài liệu đích

 Bây giờ, bạn có thể nối tài liệu nguồn vào tài liệu đích bằng cách sử dụng`AppendDocument` phương pháp của`Document` lớp học. Các`ImportFormatMode.UseDestinationStyles` tham số đảm bảo rằng kiểu danh sách của tài liệu đích được sử dụng trong thao tác chắp thêm.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## Bước 6: Lưu tài liệu cuối cùng

Cuối cùng, lưu tài liệu đã hợp nhất với tính năng List Use Destination Styles được bật bằng cách sử dụng`Save` phương pháp của`Document` lớp học.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

### Mã nguồn ví dụ cho Danh sách Sử dụng Kiểu Đích bằng Aspose.Words cho .NET 

Đây là mã nguồn đầy đủ cho tính năng "Danh sách sử dụng kiểu đích" trong C# bằng cách sử dụng Aspose.Words cho .NET:


```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Đặt tài liệu nguồn tiếp tục ngay sau khi kết thúc tài liệu đích.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Theo dõi các danh sách được tạo.
	Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		if (para.IsListItem)
		{
			int listId = para.ListFormat.List.ListId;
			// Kiểm tra xem tài liệu đích có chứa danh sách có ID này chưa. Nếu có thì điều này có thể
			// làm cho hai danh sách chạy cùng nhau. Thay vào đó, hãy tạo một bản sao của danh sách trong tài liệu nguồn.
			if (dstDoc.Lists.GetListByListId(listId) != null)
			{
				Aspose.Words.Lists.List currentList;
				// Danh sách mới sao chép đã tồn tại cho ID này, hãy truy xuất danh sách đã lưu trữ,
				// và sử dụng nó trên đoạn văn hiện tại.
				if (newLists.ContainsKey(listId))
				{
					currentList = newLists[listId];
				}
				else
				{
					// Thêm một bản sao của danh sách này vào tài liệu và lưu trữ nó để tham khảo sau này.
					currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
					newLists.Add(listId, currentList);
				}
				// Đặt danh sách đoạn này vào danh sách đã sao chép.
				para.ListFormat.List = currentList;
			}
		}
	}
	// Nối tài liệu nguồn vào cuối tài liệu đích.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

Đó là nó! Bạn đã triển khai thành công tính năng Kiểu đích sử dụng danh sách bằng Aspose.Words cho .NET. Tài liệu cuối cùng sẽ chứa nội dung đã hợp nhất với các kiểu danh sách từ tài liệu đích.