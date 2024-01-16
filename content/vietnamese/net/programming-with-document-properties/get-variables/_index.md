---
title: Nhận biến
linktitle: Nhận biến
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để truy xuất các biến tài liệu bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-document-properties/get-variables/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn mã nguồn C# để truy xuất các biến từ tài liệu bằng Aspose.Words cho .NET. Tính năng này cho phép bạn truy cập các biến được xác định trong tài liệu.

## Bước 1: Thiết lập dự án

Để bắt đầu, hãy tạo một dự án C# mới trong IDE yêu thích của bạn. Đảm bảo thư viện Aspose.Words for .NET được tham chiếu trong dự án của bạn.

## Bước 2: Tải tài liệu

Trong bước này, chúng tôi sẽ tải tài liệu Word mà chúng tôi muốn truy xuất các biến. Sử dụng đoạn mã sau để tải tài liệu:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Thay thế`"YOUR DOCUMENTS DIRECTORY"` với đường dẫn thực tế của thư mục chứa tài liệu của bạn.

## Bước 3: Truy xuất biến

Bây giờ chúng ta sẽ truy xuất các biến được xác định trong tài liệu. Sử dụng mã sau đây:

```csharp
string variables = "";
foreach(KeyValuePair<string, string> entry in doc.Variables)
{
     string name = entry.Key;
     string value = entry.Value;
     if (variables == "")
     {
         variables = "Name: " + name + ", " + "Value: " + value;
     }
     else
     {
         variables = variables + "\nName: " + name + ", " + "Value: " + value;
     }
}

Console.WriteLine("\nThe document contains the following variables:\n" + variables);
```

Mã này lặp lại từng cặp khóa-giá trị trong các biến tài liệu và truy xuất tên cũng như giá trị của từng biến. Các biến sau đó được nối để hiển thị thông tin cho từng biến.

### Mã nguồn mẫu cho Nhận biến bằng Aspose.Words cho .NET

```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	string variables = "";
	foreach (KeyValuePair<string, string> entry in doc.Variables)
	{
		string name = entry.Key;
		string value = entry.Value;
		if (variables == "")
		{
			variables = "Name: " + name + "," + "Value: {1}" + value;
		}
		else
		{
			variables = variables + "Name: " + name + "," + "Value: {1}" + value;
		}
	}
	

	Console.WriteLine("\nDocument have following variables " + variables);

```

 Đảm bảo chỉ định đường dẫn tài liệu chính xác trong`dataDir` Biến đổi.

Bây giờ bạn đã học cách truy xuất các biến từ tài liệu bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước được cung cấp trong hướng dẫn này, bạn có thể dễ dàng truy cập và xem các biến từ tài liệu của riêng mình.