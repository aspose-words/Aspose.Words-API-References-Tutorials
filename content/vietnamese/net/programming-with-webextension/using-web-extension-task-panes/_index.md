---
title: Sử dụng ngăn tác vụ mở rộng web
linktitle: Sử dụng ngăn tác vụ mở rộng web
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách thêm và định cấu hình Ngăn tác vụ mở rộng web trong tài liệu Word bằng Aspose.Words cho .NET trong hướng dẫn chi tiết từng bước này.
type: docs
weight: 10
url: /vi/net/programming-with-webextension/using-web-extension-task-panes/
---
## Giới thiệu

Chào mừng bạn đến với hướng dẫn chuyên sâu này về cách sử dụng Ngăn tác vụ mở rộng web trong tài liệu Word bằng Aspose.Words cho .NET. Nếu bạn từng muốn cải thiện tài liệu Word của mình bằng các ngăn tác vụ tương tác thì bạn đã đến đúng nơi. Hướng dẫn này sẽ hướng dẫn bạn từng bước để đạt được điều này một cách liền mạch.

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào, hãy đảm bảo bạn có mọi thứ bạn cần:

-  Aspose.Words for .NET: Bạn có thể tải xuống[đây](https://releases.aspose.com/words/net/).
- Môi trường phát triển .NET: Visual Studio hoặc bất kỳ IDE nào khác mà bạn thích.
- Kiến thức cơ bản về C#: Điều này sẽ giúp bạn theo dõi các ví dụ về mã.
-  Giấy phép cho Aspose.Words: Bạn có thể mua một cái[đây](https://purchase.aspose.com/buy) hoặc lấy giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).

## Nhập không gian tên

Trước khi chúng ta bắt đầu viết mã, hãy đảm bảo bạn đã nhập các không gian tên sau vào dự án của mình:

```csharp
using Aspose.Words;
using Aspose.Words.WebExtensions;
```

## Hướng dẫn từng bước một

Bây giờ, hãy chia quy trình thành các bước dễ thực hiện.

### Bước 1: Thiết lập thư mục tài liệu của bạn

Trước tiên, chúng ta cần thiết lập đường dẫn đến thư mục tài liệu của bạn. Đây là nơi tài liệu Word của bạn sẽ được lưu.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

### Bước 2: Tạo một tài liệu mới

Tiếp theo, chúng ta sẽ tạo một tài liệu Word mới bằng Aspose.Words.

```csharp
Document doc = new Document();
```

 Dòng này khởi tạo một phiên bản mới của`Document` lớp, đại diện cho một tài liệu Word.

### Bước 3: Thêm ngăn tác vụ

Bây giờ, chúng ta sẽ thêm Ngăn tác vụ vào tài liệu của mình. Ngăn tác vụ rất hữu ích trong việc cung cấp các chức năng và công cụ bổ sung trong tài liệu Word.

```csharp
TaskPane taskPane = new TaskPane();
doc.WebExtensionTaskPanes.Add(taskPane);
```

 Ở đây chúng ta tạo một cái mới`TaskPane` đối tượng và thêm nó vào tài liệu`WebExtensionTaskPanes` bộ sưu tập.

### Bước 4: Cấu hình ngăn tác vụ

Để hiển thị Ngăn tác vụ của chúng tôi và đặt các thuộc tính của nó, chúng tôi sử dụng đoạn mã sau:

```csharp
taskPane.DockState = TaskPaneDockState.Right;
taskPane.IsVisible = true;
taskPane.Width = 300;
```

- `DockState` đặt nơi Ngăn tác vụ sẽ xuất hiện. Trong trường hợp này, nó ở bên phải.
- `IsVisible` đảm bảo Ngăn Tác vụ có thể nhìn thấy được.
- `Width` đặt độ rộng của Ngăn tác vụ.

### Bước 5: Thiết lập tham chiếu tiện ích mở rộng web

Tiếp theo, chúng tôi thiết lập Tham chiếu tiện ích mở rộng web bao gồm ID, phiên bản, loại cửa hàng và cửa hàng.

```csharp
taskPane.WebExtension.Reference.Id = "wa102923726";
taskPane.WebExtension.Reference.Version = "1.0.0.0";
taskPane.WebExtension.Reference.StoreType = WebExtensionStoreType.OMEX;
taskPane.WebExtension.Reference.Store = "th-TH";
```

- `Id`là mã định danh duy nhất cho tiện ích mở rộng web.
- `Version` chỉ định phiên bản của tiện ích mở rộng.
- `StoreType` cho biết loại cửa hàng (trong trường hợp này là OMEX).
- `Store` chỉ định mã ngôn ngữ/văn hóa của cửa hàng.

### Bước 6: Thêm thuộc tính vào tiện ích mở rộng web

Bạn có thể thêm thuộc tính vào tiện ích mở rộng web của mình để xác định hành vi hoặc nội dung của nó.

```csharp
taskPane.WebExtension.Properties.Add(new WebExtensionProperty("mailchimpCampaign", "mailchimpCampaign"));
```

 Ở đây, chúng tôi thêm một thuộc tính có tên`mailchimpCampaign`.

### Bước 7: Liên kết tiện ích mở rộng web

Cuối cùng, chúng tôi thêm các ràng buộc vào tiện ích mở rộng web của mình. Các ràng buộc cho phép bạn liên kết phần mở rộng với các phần cụ thể của tài liệu.

```csharp
taskPane.WebExtension.Bindings.Add(new WebExtensionBinding("UnnamedBinding_0_1506535429545", WebExtensionBindingType.Text, "194740422"));
```

- `UnnamedBinding_0_1506535429545` là tên của ràng buộc.
- `WebExtensionBindingType.Text` chỉ ra rằng ràng buộc là loại văn bản.
- `194740422` là ID của phần tài liệu mà tiện ích mở rộng được liên kết.

### Bước 8: Lưu tài liệu

Sau khi thiết lập mọi thứ, hãy lưu tài liệu của bạn.

```csharp
doc.Save(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");
```

Dòng này lưu tài liệu vào thư mục được chỉ định với tên tệp đã cho.

### Bước 9: Tải và hiển thị thông tin ngăn tác vụ

Để xác minh và hiển thị thông tin ngăn tác vụ, chúng tôi tải tài liệu và lặp qua các ngăn tác vụ.

```csharp
doc = new Document(dataDir + "WorkingWithWebExtension.UsingWebExtensionTaskPanes.docx");

Console.WriteLine("Task panes sources:\n");

foreach (TaskPane taskPaneInfo in doc.WebExtensionTaskPanes)
{
    WebExtensionReference reference = taskPaneInfo.WebExtension.Reference;
    Console.WriteLine($"Provider: \"{reference.Store}\", version: \"{reference.Version}\", catalog identifier: \"{reference.Id}\";");
}
```

Mã này tải tài liệu và in mã định danh nhà cung cấp, phiên bản và danh mục của từng ngăn tác vụ trong bảng điều khiển.

## Phần kết luận

Và thế là xong! Bạn đã thêm và định cấu hình thành công Ngăn tác vụ tiện ích mở rộng web trong tài liệu Word bằng Aspose.Words cho .NET. Tính năng mạnh mẽ này có thể nâng cao đáng kể tài liệu Word của bạn bằng cách cung cấp các chức năng bổ sung trực tiếp trong tài liệu. 

## Câu hỏi thường gặp

### Ngăn tác vụ trong Word là gì?
Ngăn tác vụ là một thành phần giao diện cung cấp các công cụ và chức năng bổ sung trong tài liệu Word, nâng cao năng suất và tương tác của người dùng.

### Tôi có thể tùy chỉnh giao diện của Ngăn tác vụ không?
 Có, bạn có thể tùy chỉnh giao diện của Ngăn tác vụ bằng cách đặt các thuộc tính như`DockState`, `IsVisible` , Và`Width`.

### Thuộc tính tiện ích mở rộng web là gì?
Thuộc tính tiện ích mở rộng web là thuộc tính tùy chỉnh mà bạn có thể thêm vào tiện ích mở rộng web để xác định hành vi hoặc nội dung của nó.

### Làm cách nào để liên kết Tiện ích mở rộng Web với một phần của tài liệu?
 Bạn có thể liên kết Tiện ích mở rộng Web với một phần của tài liệu bằng cách sử dụng`WebExtensionBinding` lớp, chỉ định loại liên kết và ID mục tiêu.

### Tôi có thể tìm thêm thông tin về Aspose.Words cho .NET ở đâu?
 Bạn có thể tìm tài liệu chi tiết[đây](https://reference.aspose.com/words/net/).