---
title: Đọc thuộc tính XControl hoạt động từ tệp Word
linktitle: Đọc thuộc tính XControl hoạt động từ tệp Word
second_title: API xử lý tài liệu Aspose.Words
description: Đọc thuộc tính của điều khiển ActiveX trong tệp Word bằng Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---

Trong hướng dẫn từng bước này, chúng tôi sẽ chỉ cho bạn cách đọc các thuộc tính của điều khiển ActiveX trong tệp Word bằng Aspose.Words cho .NET. Chúng tôi sẽ cung cấp cho bạn mã nguồn hoàn chỉnh và chỉ cho bạn cách định dạng đầu ra đánh dấu.

## Bước 1: Khởi tạo tài liệu

 Bước đầu tiên là khởi tạo`Document` đối tượng bằng cách tải tài liệu Word có chứa các điều khiển ActiveX. Hãy chắc chắn để thay thế`MyDir` với đường dẫn thực tế đến thư mục chứa tài liệu.

```csharp
Document doc = new Document(MyDir + "ActiveX controls.docx");
```

## Bước 2: Khôi phục điều khiển ActiveX

 Trong bước này, chúng ta sẽ lặp lại từng`Shape` của tài liệu để truy xuất các điều khiển ActiveX và đọc các thuộc tính của chúng.

```csharp
string properties = "";
foreach(Shape shape in doc.GetChildNodes(NodeType.Shape, true))
{
     if (shape.OleFormat is null) break;

     OleControl oleControl = shape.OleFormat.OleControl;
     if (oleControl.IsForms2OleControl)
     {
         Forms2OleControl checkBox = (Forms2OleControl)oleControl;
         properties = properties + "\nCaption: " + checkBox.Caption;
         properties = properties + "\nValue: " + checkBox.Value;
         properties = properties + "\nEnabled: " + checkBox.Enabled;
         properties = properties + "\nType: " + checkBox.Type;
         if (checkBox. ChildNodes != null)
         {
             properties = properties + "\nChildNodes: " + checkBox.ChildNodes;
         }

         properties += "\n";
     }
}

properties = properties + "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
Console.WriteLine("\n" + properties);
```

### Mã nguồn ví dụ để đọc Thuộc tính XControl hoạt động bằng Aspose.Words cho .NET

Đây là mã nguồn hoàn chỉnh để đọc các thuộc tính của điều khiển ActiveX bằng Aspose.Words cho .NET:

```csharp
	Document doc = new Document(MyDir + "ActiveX controls.docx");

	string properties = "";
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
	{
		if (shape.OleFormat is null) break;

		OleControl oleControl = shape.OleFormat.OleControl;
		if (oleControl.IsForms2OleControl)
		{
			Forms2OleControl checkBox = (Forms2OleControl) oleControl;
			properties = properties + "\nCaption: " + checkBox.Caption;
			properties = properties + "\nValue: " + checkBox.Value;
			properties = properties + "\nEnabled: " + checkBox.Enabled;
			properties = properties + "\nType: " + checkBox.Type;
			if (checkBox.ChildNodes != null)
			{
				properties = properties + "\nChildNodes: " + checkBox.ChildNodes;
			}

			properties += "\n";
		}
	}

	properties = properties + "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
	Console.WriteLine("\n" + properties);
```

## Phần kết luận

Hướng dẫn này đã chỉ cho bạn cách đọc các thuộc tính của điều khiển ActiveX trong tệp Word bằng Aspose.Words cho .NET. Bằng cách làm theo các bước được mô tả, bạn có thể khởi tạo tài liệu, truy xuất các điều khiển ActiveX và đọc các thuộc tính của chúng. Sử dụng mã mẫu được cung cấp làm điểm bắt đầu và tùy chỉnh mã đó theo nhu cầu cụ thể của bạn.

Việc đọc các thuộc tính của điều khiển ActiveX cho phép bạn trích xuất thông tin quan trọng từ tệp Word có chứa các điều khiển này. Aspose.Words for .NET cung cấp các tính năng mạnh mẽ để Xử lý Từ với các điều khiển ActiveX và tự động hóa quá trình xử lý tài liệu của bạn.

### Câu hỏi thường gặp

#### Hỏi: Bước đầu tiên để đọc thuộc tính của điều khiển ActiveX trong tệp Word là gì?

 A: Bước đầu tiên là khởi tạo`Document` đối tượng bằng cách tải tài liệu Word có chứa các điều khiển ActiveX. Hãy chắc chắn để thay thế`MyDir` với đường dẫn thực tế đến thư mục chứa tài liệu.

#### Câu hỏi: Làm cách nào để đưa các điều khiển ActiveX vào tài liệu?

 Đáp: Để truy xuất các điều khiển ActiveX, bạn cần lặp qua từng`Shape` của tài liệu và kiểm tra xem đó có phải là điều khiển ActiveX hay không. Sử dụng`OleFormat` tài sản của`Shape` để truy cập`OleControl` đối tượng và lấy các thuộc tính cần thiết.

#### Câu hỏi: Tôi có thể đọc được những thuộc tính nào của điều khiển ActiveX?

Trả lời: Bạn có thể đọc các thuộc tính khác nhau của điều khiển ActiveX, chẳng hạn như chú thích, giá trị, trạng thái được bật hoặc tắt, loại và các Mã con được liên kết với điều khiển.

#### Câu hỏi: Làm cách nào để có được tổng số điều khiển ActiveX trong tài liệu?

 Đáp: Để có được tổng số điều khiển ActiveX trong tài liệu, bạn có thể sử dụng`GetChildNodes` phương pháp của`Document` đối tượng chỉ định`NodeType.Shape` loại và bao gồm các nút con.