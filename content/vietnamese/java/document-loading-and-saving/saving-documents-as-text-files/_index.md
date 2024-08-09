---
title: Lưu tài liệu dưới dạng tệp văn bản trong Aspose.Words cho Java
linktitle: Lưu tài liệu dưới dạng tệp văn bản
second_title: API xử lý tài liệu Java Aspose.Words
description: Tìm hiểu cách lưu tài liệu dưới dạng tệp văn bản trong Aspose.Words cho Java. Hãy làm theo hướng dẫn từng bước của chúng tôi với các ví dụ về mã Java.
type: docs
weight: 24
url: /vi/java/document-loading-and-saving/saving-documents-as-text-files/
---

## Giới thiệu về Lưu tài liệu dưới dạng tệp văn bản trong Aspose.Words cho Java

Trong hướng dẫn này, chúng ta sẽ khám phá cách lưu tài liệu dưới dạng tệp văn bản bằng thư viện Aspose.Words cho Java. Aspose.Words là một API Java mạnh mẽ để làm việc với các tài liệu Word và nó cung cấp nhiều tùy chọn khác nhau để lưu tài liệu ở các định dạng khác nhau, bao gồm cả văn bản thuần túy. Chúng tôi sẽ đề cập đến các bước để đạt được điều này và cung cấp mã Java mẫu trong quá trình thực hiện.

## Điều kiện tiên quyết

Trước khi chúng ta bắt đầu, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

- Bộ công cụ phát triển Java (JDK) được cài đặt trên hệ thống của bạn.
-  Thư viện Aspose.Words for Java được tích hợp vào dự án của bạn. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/words/java/).
- Kiến thức cơ bản về lập trình Java.

## Bước 1: Tạo tài liệu

Để lưu tài liệu dưới dạng tệp văn bản, trước tiên chúng ta cần tạo tài liệu bằng Aspose.Words. Đây là đoạn mã Java đơn giản để tạo một tài liệu có một số nội dung:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.writeln("Hello world!");
builder.getParagraphFormat().setBidi(true);
builder.writeln("שלום עולם!");
builder.writeln("مرحبا بالعالم!");
```

Trong mã này, chúng tôi tạo một tài liệu mới và thêm một số văn bản vào đó, bao gồm cả văn bản bằng các ngôn ngữ khác nhau.

## Bước 2: Xác định tùy chọn lưu văn bản

Tiếp theo, chúng ta cần xác định các tùy chọn lưu văn bản chỉ định cách lưu tài liệu dưới dạng tệp văn bản. Chúng tôi có thể định cấu hình các cài đặt khác nhau như thêm dấu giá thầu, thụt lề danh sách, v.v. Chúng ta hãy xem hai ví dụ:

### Ví dụ 1: Thêm nhãn hiệu Bidi

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.setAddBidiMarks(true);
doc.save("output.txt", saveOptions);
```

 Trong ví dụ này, chúng ta tạo một`TxtSaveOptions` đối tượng và thiết lập`AddBidiMarks`tài sản để`true` để bao gồm các dấu bidi trong đầu ra văn bản.

### Ví dụ 2: Sử dụng ký tự tab để thụt lề danh sách

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.getListIndentation().setCount(1);
saveOptions.getListIndentation().setCharacter('\t');
doc.save("output.txt", saveOptions);
```

Ở đây, chúng tôi định cấu hình các tùy chọn lưu để sử dụng ký tự tab để thụt lề danh sách với số lượng là 1.

## Bước 3: Lưu tài liệu dưới dạng văn bản

Bây giờ chúng ta đã xác định các tùy chọn lưu văn bản, chúng ta có thể lưu tài liệu dưới dạng tệp văn bản. Đoạn mã sau đây minh họa cách thực hiện việc này:

```java
doc.save("output.txt", saveOptions);
```

 Thay thế`"output.txt"` với đường dẫn tệp mong muốn nơi bạn muốn lưu tệp văn bản.

## Mã nguồn hoàn chỉnh để lưu tài liệu dưới dạng tệp văn bản trong Aspose.Words cho Java

```java
    public void addBidiMarks() throws Exception
    {        
		Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.writeln("Hello world!");
        builder.getParagraphFormat().setBidi(true);
        builder.writeln("שלום עולם!");
        builder.writeln("مرحبا بالعالم!");
        TxtSaveOptions saveOptions = new TxtSaveOptions(); { saveOptions.setAddBidiMarks(true); }
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
    }
    @Test
    public void useTabCharacterPerLevelForListIndentation() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // Tạo một danh sách có ba mức thụt lề.
        builder.getListFormat().applyNumberDefault();
        builder.writeln("Item 1");
        builder.getListFormat().listIndent();
        builder.writeln("Item 2");
        builder.getListFormat().listIndent(); 
        builder.write("Item 3");
        TxtSaveOptions saveOptions = new TxtSaveOptions();
        saveOptions.getListIndentation().setCount(1);
        saveOptions.getListIndentation().setCharacter('\t');
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt", saveOptions);
    }
    @Test
    public void useSpaceCharacterPerLevelForListIndentation() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // Tạo một danh sách có ba mức thụt lề.
        builder.getListFormat().applyNumberDefault();
        builder.writeln("Item 1");
        builder.getListFormat().listIndent();
        builder.writeln("Item 2");
        builder.getListFormat().listIndent(); 
        builder.write("Item 3");
        TxtSaveOptions saveOptions = new TxtSaveOptions();
        saveOptions.getListIndentation().setCount(3);
        saveOptions.getListIndentation().setCharacter(' ');
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
	}
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách lưu tài liệu dưới dạng tệp văn bản trong Aspose.Words cho Java. Chúng tôi đã trình bày các bước để tạo tài liệu, xác định các tùy chọn lưu văn bản và lưu tài liệu ở định dạng văn bản. Aspose.Words cung cấp tính linh hoạt cao khi lưu tài liệu, cho phép bạn điều chỉnh đầu ra theo yêu cầu cụ thể của mình.

## Câu hỏi thường gặp

### Làm cách nào để thêm dấu bidi vào đầu ra văn bản?

 Để thêm dấu bidi vào đầu ra văn bản, hãy đặt`AddBidiMarks` tài sản của`TxtSaveOptions` ĐẾN`true`. Ví dụ:

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.setAddBidiMarks(true);
```

### Tôi có thể tùy chỉnh ký tự thụt lề danh sách không?

 Có, bạn có thể tùy chỉnh ký tự thụt lề danh sách bằng cách định cấu hình`ListIndentation` tài sản của`TxtSaveOptions`. Ví dụ: để sử dụng ký tự tab để thụt lề danh sách, bạn có thể làm như sau:

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.getListIndentation().setCount(1);
saveOptions.getListIndentation().setCharacter('\t');
```

### Aspose.Words for Java có phù hợp để xử lý văn bản đa ngôn ngữ không?

Có, Aspose.Words for Java phù hợp để xử lý văn bản đa ngôn ngữ. Nó hỗ trợ nhiều ngôn ngữ và mã hóa ký tự khác nhau, khiến nó trở thành lựa chọn linh hoạt để làm việc với các tài liệu bằng các ngôn ngữ khác nhau.

### Làm cách nào tôi có thể truy cập thêm tài liệu và tài nguyên cho Aspose.Words cho Java?

 Bạn có thể tìm thấy tài liệu và tài nguyên toàn diện về Aspose.Words cho Java trên trang web tài liệu Aspose:[Aspose.Words cho tài liệu Java](https://reference.aspose.com/words/java/).

### Tôi có thể tải xuống Aspose.Words cho Java ở đâu?

 Bạn có thể tải xuống thư viện Aspose.Words cho Java từ trang web Aspose:[Tải xuống Aspose.Words cho Java](https://releases.aspose.com/words/java/).