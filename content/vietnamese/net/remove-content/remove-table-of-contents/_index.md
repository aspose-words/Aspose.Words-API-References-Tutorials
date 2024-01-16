---
title: Xóa mục lục trong tài liệu Word
linktitle: Xóa mục lục trong tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách xóa mục lục trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/remove-content/remove-table-of-contents/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn cách xóa mục lục trong tài liệu Word bằng thư viện Aspose.Words cho .NET. Mục lục đôi khi có thể dư thừa hoặc không cần thiết, đoạn mã này sẽ giúp bạn loại bỏ nó một cách hiệu quả. Chúng tôi sẽ cung cấp hướng dẫn từng bước để giúp bạn hiểu và triển khai mã trong dự án .NET của riêng bạn.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có các mục sau:
- Kiến thức làm việc về ngôn ngữ lập trình C#
- Thư viện Aspose.Words cho .NET được cài đặt trong dự án của bạn
- Một tài liệu Word chứa mục lục mà bạn muốn xóa

## Bước 1: Xác định thư mục tài liệu
 Trước tiên, bạn cần đặt đường dẫn thư mục đến vị trí tài liệu Word của mình. Thay thế`"YOUR DOCUMENT DIRECTORY"` trong mã với đường dẫn thích hợp.

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Tải tài liệu lên
 Tiếp theo, chúng ta sẽ tải tài liệu Word vào một phiên bản của`Document` lớp sử dụng`Load` phương pháp.

```csharp
// Tải tài liệu
Document doc = new Document(dataDir + "your-document.docx");
```

## Bước 3: Xóa mục lục
 Để loại bỏ mục lục, chúng ta sẽ lặp qua kiểu TOC (mục lục)`FieldStart` các nút trong tài liệu. Chúng ta sẽ lưu trữ các nút này để có thể truy cập nhanh và tạo danh sách các nút cần xóa.

```csharp
// Lưu trữ các nút FieldStart của trường TOC trong tài liệu để truy cập nhanh.
List<FieldStart> fieldStarts = new List<FieldStart>();
// Đây là danh sách lưu trữ các nút được tìm thấy bên trong TOC được chỉ định. Chúng sẽ bị xóa khi kết thúc phương pháp này.
List<Node> nodeList = new List<Node>();

foreach(FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
     if (start.FieldType == FieldType.FieldTOC)
     {
         fieldStarts.Add(start);
     }
}

// Kiểm tra xem chỉ số TOC đã chỉ định có tồn tại hay không.
if (index > fieldStarts.Count - 1)
     throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
     // Sẽ an toàn hơn nếu lưu trữ các nút này và xóa tất cả chúng ở cuối.
     nodeList.Add(currentNode);
     currentNode = currentNode.NextPreOrder(doc);

     // Khi chúng tôi gặp nút FieldEnd thuộc loại FieldTOC,
     //chúng tôi biết chúng tôi đang ở cuối TOC hiện tại và chúng tôi dừng lại ở đây.
     if (currentNode.NodeType == NodeType.FieldEnd)
     {
         FieldEnd fieldEnd = (FieldEnd)currentNode;
         if (fieldEnd.FieldType == FieldType.FieldTOC)


             isRemoving = false;
     }
}

foreach(Node node in nodeList)
{
     node. Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```


### Mã nguồn mẫu để Xóa mục lục bằng Aspose.Words cho .NET 
```csharp

// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
// Tải tài liệu
Document doc = new Document(dataDir + "your-document.docx");

// Lưu trữ các nút FieldStart của trường TOC trong tài liệu để truy cập nhanh.
List<FieldStart> fieldStarts = new List<FieldStart>();
// Đây là danh sách lưu trữ các nút được tìm thấy bên trong TOC được chỉ định. Chúng sẽ bị xóa khi kết thúc phương pháp này.
List<Node> nodeList = new List<Node>();

foreach (FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
	if (start.FieldType == FieldType.FieldTOC)
	{
		fieldStarts.Add(start);
	}
}

// Đảm bảo tồn tại TOC được chỉ định bởi chỉ mục được thông qua.
if (index > fieldStarts.Count - 1)
	throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
	// Sẽ an toàn hơn nếu lưu trữ các nút này và xóa tất cả chúng cùng một lúc sau đó.
	nodeList.Add(currentNode);
	currentNode = currentNode.NextPreOrder(doc);

	// Khi chúng tôi gặp nút FieldEnd thuộc loại FieldTOC,
	// chúng tôi biết chúng tôi đang ở cuối TOC hiện tại và dừng ở đây.
	if (currentNode.NodeType == NodeType.FieldEnd)
	{
		FieldEnd fieldEnd = (FieldEnd) currentNode;
		if (fieldEnd.FieldType == FieldType.FieldTOC)
			isRemoving = false;
	}
}

foreach (Node node in nodeList)
{
	node.Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
        
```

## Phần kết luận
Trong hướng dẫn này, chúng tôi đã trình bày hướng dẫn từng bước để xóa mục lục khỏi tài liệu Word bằng thư viện Aspose.Words cho .NET. Bằng cách làm theo mã và hướng dẫn được cung cấp, bạn có thể dễ dàng loại bỏ mục lục và cải thiện bố cục tài liệu của mình. Hãy nhớ điều chỉnh đường dẫn thư mục và tên tệp cho phù hợp với nhu cầu cụ thể của bạn.

### Câu hỏi thường gặp

#### Hỏi: Tại sao tôi nên sử dụng Aspose.Words để xóa mục lục trong tài liệu Word?

Trả lời: Aspose.Words là một thư viện lớp mạnh mẽ và linh hoạt để thao tác các tài liệu Word trong các ứng dụng .NET. Bằng cách sử dụng Aspose.Words, bạn có thể xóa mục lục khỏi tài liệu của mình một cách hiệu quả, điều này có thể hữu ích nếu mục lục dư thừa hoặc không cần thiết. Điều này cho phép bạn tùy chỉnh nội dung tài liệu của mình và cải thiện cách trình bày tổng thể của nó.

#### Câu hỏi: Làm cách nào để tải lên tài liệu trong Aspose.Words cho .NET?

Trả lời: Để xóa mục lục trong tài liệu Word, trước tiên bạn phải tải tài liệu vào bộ nhớ bằng phương thức Load() của Aspose.Words. Đây là mã mẫu để tải tài liệu từ một thư mục cụ thể:

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tải tài liệu
Document doc = new Document(dataDir + "your-document.docx");
```

 Thay thế`"YOUR DOCUMENTS DIRECTORY"` với đường dẫn thực tế đến tài liệu của bạn.

#### Câu hỏi: Làm cách nào để xóa mục lục trong tài liệu bằng Aspose.Words?

 Đáp: Để loại bỏ TOC, bạn cần lặp qua`FieldStart` gõ các nút của TOC trong tài liệu. Bạn có thể lưu trữ các nút này để truy cập nhanh và tạo danh sách các nút để xóa. Đây là một mã mẫu:

```csharp
// Lưu trữ các nút FieldStart của trường TOC trong tài liệu để truy cập nhanh.
List<FieldStart> fieldStarts = new List<FieldStart>();
//Đây là danh sách lưu trữ các nút được tìm thấy bên trong TOC được chỉ định. Chúng sẽ bị xóa khi kết thúc phương pháp này.
List<Node> nodeList = new List<Node>();

foreach(FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
if (start.FieldType == FieldType.FieldTOC)
{
fieldStarts.Add(start);
}
}

// Kiểm tra xem chỉ mục mục lục đã chỉ định có tồn tại hay không.
if (index > fieldStarts.Count - 1)
throw new ArgumentOutOfRangeException("Table of contents index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
// Sẽ an toàn hơn nếu lưu trữ các nút này và xóa tất cả chúng ở cuối.
nodeList.Add(currentNode);
currentNode = currentNode.NextPreOrder(doc);

// Khi chúng tôi gặp nút FieldEnd thuộc loại FieldTOC,
//chúng tôi biết chúng tôi đang ở cuối TOC hiện tại và chúng tôi dừng lại ở đây.
if (currentNode.NodeType == NodeType.FieldEnd)
{
FieldEnd fieldEnd = (FieldEnd)currentNode;
if (fieldEnd.FieldType == FieldType.FieldTOC)
isRemoving = false;
}
}

foreach(Node node in nodeList)
{
node. Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```

#### Hỏi: Làm cách nào để lưu tài liệu đã chỉnh sửa trong Aspose.Words cho .NET?

Đáp: Sau khi xóa mục lục, bạn phải lưu tài liệu đã sửa đổi bằng phương thức Save(). Chỉ định đường dẫn và định dạng tệp đầu ra mong muốn (ví dụ: DOCX) cho tài liệu đã chỉnh sửa. Đây là một mã mẫu:

```csharp
doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```