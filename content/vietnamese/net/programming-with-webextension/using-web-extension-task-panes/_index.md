---
title: Sử dụng ngăn tác vụ mở rộng web
linktitle: Sử dụng ngăn tác vụ mở rộng web
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước cách sử dụng Ngăn tác vụ mở rộng web với Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-webextension/using-web-extension-task-panes/
---

Bài viết này cung cấp hướng dẫn từng bước về cách sử dụng ngăn tác vụ tiện ích mở rộng web với Aspose.Words cho .NET. Chúng tôi sẽ giải thích chi tiết từng phần của mã. Khi kết thúc hướng dẫn này, bạn sẽ có thể hiểu cách thêm và định cấu hình bảng tác vụ cho tiện ích mở rộng web.

Trước khi bắt đầu, hãy đảm bảo bạn đã cài đặt và định cấu hình thư viện Aspose.Words cho .NET trong dự án của mình. Bạn có thể tìm thấy thư viện và hướng dẫn cài đặt trên trang web Aspose.

## Bước 1: Xác định thư mục tài liệu

 Để bắt đầu, bạn cần xác định đường dẫn đến thư mục mà bạn muốn lưu tài liệu đã tạo. Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tạo và đặt cấu hình ngăn tác vụ

 Chúng tôi tạo ra một`TaskPane` đối tượng và thêm nó vào tài liệu`s `Bộ sưu tập WebExtensionTaskPanes`. Tiếp theo, chúng tôi định cấu hình các thuộc tính của ngăn tác vụ, chẳng hạn như trạng thái gắn đế, khả năng hiển thị và chiều rộng của nó.

```csharp
Document doc = new Document();

TaskPane taskPane = new TaskPane();
doc.WebExtensionTaskPanes.Add(taskPane);

taskPane.DockState = TaskPaneDockState.Right;
taskPane.IsVisible = true;
taskPane.Width = 300;
```

Chúng tôi cũng đặt thông tin xác thực của tiện ích mở rộng web bao gồm id danh mục, phiên bản và loại cửa hàng.

```csharp
taskPane.WebExtension.Reference.Id = "wa102923726";
taskPane.WebExtension.Reference.Version = "1.0.0.0";
taskPane.WebExtension.Reference.StoreType = WebExtensionStoreType.OMEX;
taskPane.WebExtension.Reference.Store = "th-TH";
```

Cuối cùng, chúng tôi thêm các thuộc tính và liên kết vào tiện ích mở rộng web.

```csharp
taskPane.WebExtension.Properties.Add(new WebExtensionProperty("mailchimpCampaign", "mailchimpCampaign"));
taskPane.WebExtension.Bindings.Add(new WebExtensionBinding("UnnamedBinding_0_1506535429545",
	WebExtensionBindingType.Text, "194740422"));
```

## Bước 3: Lưu và tải tài liệu

Chúng tôi lưu tài liệu với các ngăn tác vụ được định cấu hình trong thư mục đã chỉ định.

```csharp
doc.Save(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
```

## Bước 4: Hiển thị thông tin các task pane

Tiếp theo, chúng tôi tải tài liệu và hiển thị thông tin nguồn của khung tác vụ.

```csharp
doc = new Document(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
Console.WriteLine("Task Panes Sources:\n");

foreach(TaskPane taskPaneInfo in doc.WebExtensionTaskPanes)
{
WebExtensionReference reference = taskPaneInfo.WebExtension.Reference;


Console.WriteLine($"Vendor: \"{reference.Store}\", version: \"{reference.Version}\", catalog id: \"{reference.Id}\";");
}
```

Đó là tất cả ! Bạn đã sử dụng thành công bảng tác vụ tiện ích mở rộng web với Aspose.Words cho .NET.

### Mã nguồn ví dụ để sử dụng các ngăn tác vụ mở rộng web với Aspose.Words cho .NET


```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();

	TaskPane taskPane = new TaskPane();
	doc.WebExtensionTaskPanes.Add(taskPane);

	taskPane.DockState = TaskPaneDockState.Right;
	taskPane.IsVisible = true;
	taskPane.Width = 300;

	taskPane.WebExtension.Reference.Id = "wa102923726";
	taskPane.WebExtension.Reference.Version = "1.0.0.0";
	taskPane.WebExtension.Reference.StoreType = WebExtensionStoreType.OMEX;
	taskPane.WebExtension.Reference.Store = "th-TH";
	taskPane.WebExtension.Properties.Add(new WebExtensionProperty("mailchimpCampaign", "mailchimpCampaign"));
	taskPane.WebExtension.Bindings.Add(new WebExtensionBinding("UnnamedBinding_0_1506535429545",
		WebExtensionBindingType.Text, "194740422"));

	doc.Save(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
	
	
	
	doc = new Document(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
	
	Console.WriteLine("Task panes sources:\n");

	foreach (TaskPane taskPaneInfo in doc.WebExtensionTaskPanes)
	{
		WebExtensionReference reference = taskPaneInfo.WebExtension.Reference;
		Console.WriteLine($"Provider: \"{reference.Store}\", version: \"{reference.Version}\", catalog identifier: \"{reference.Id}\";");
	}
 
```
