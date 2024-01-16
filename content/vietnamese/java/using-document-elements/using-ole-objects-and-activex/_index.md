---
title: Sử dụng đối tượng OLE và điều khiển ActiveX trong Aspose.Words cho Java
linktitle: Sử dụng đối tượng OLE và điều khiển ActiveX
second_title: API xử lý tài liệu Java Aspose.Words
description: Tìm hiểu cách sử dụng các đối tượng OLE và điều khiển ActiveX trong Aspose.Words cho Java. Tạo tài liệu tương tác một cách dễ dàng. Bắt đầu ngay bây giờ!
type: docs
weight: 21
url: /vi/java/using-document-elements/using-ole-objects-and-activex/
---
Trong hướng dẫn này, chúng ta sẽ khám phá cách làm việc với các đối tượng OLE (Liên kết và nhúng đối tượng) và các điều khiển ActiveX trong Aspose.Words cho Java. Đối tượng OLE và điều khiển ActiveX là những công cụ mạnh mẽ cho phép bạn nâng cao tài liệu của mình bằng cách nhúng hoặc liên kết nội dung bên ngoài, chẳng hạn như bảng tính, tệp đa phương tiện hoặc điều khiển tương tác. Hãy theo dõi khi chúng tôi đi sâu vào các ví dụ về mã và tìm hiểu cách sử dụng các tính năng này một cách hiệu quả.

### Điều kiện tiên quyết

Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

1.  Aspose.Words for Java : Đảm bảo bạn đã cài đặt thư viện Aspose.Words trong dự án Java của mình. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/words/java/).

2. Môi trường phát triển Java : Bạn nên thiết lập một môi trường phát triển Java đang hoạt động trên hệ thống của mình.

### Chèn một đối tượng OLE

Hãy bắt đầu bằng cách chèn một đối tượng OLE vào tài liệu Word. Chúng ta sẽ tạo một tài liệu Word đơn giản rồi chèn một đối tượng OLE đại diện cho một trang web.

```java
string outPath = "Your Output Directory";
public void insertOleObject() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.insertOleObject("http://www.aspose.com", "htmlfile", đúng, đúng, null);
    doc.save("Your Directory Path" + "WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
}
```

Trong mã này, chúng tôi tạo một tài liệu mới và chèn một đối tượng OLE hiển thị trang web Aspose. Bạn có thể thay thế URL bằng nội dung mong muốn.

### Chèn một đối tượng OLE bằng OlePackage

Tiếp theo, hãy khám phá cách chèn một đối tượng OLE bằng OlePackage. Điều này cho phép bạn nhúng các tệp bên ngoài dưới dạng đối tượng OLE trong tài liệu của mình.

```java
@Test
public void insertOleObjectWithOlePackage() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    byte[] bs = FileUtils.readFileToByteArray(new File("Your Directory Path" + "Zip file.zip"));
    try (ByteArrayInputStream stream = new ByteArrayInputStream(bs))
    {
        Shape shape = builder.insertOleObject(stream, "Package", true, null);
        OlePackage olePackage = shape.getOleFormat().getOlePackage();
        olePackage.setFileName("filename.zip");
        olePackage.setDisplayName("displayname.zip");
        doc.save(outPath + "WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
    }
}
```

Trong ví dụ này, chúng tôi chèn một đối tượng OLE bằng cách sử dụng OlePackage, cho phép bạn bao gồm các tệp bên ngoài dưới dạng đối tượng được nhúng.

### Chèn đối tượng OLE làm biểu tượng

Bây giờ, hãy xem cách chèn đối tượng OLE làm biểu tượng. Điều này rất hữu ích khi bạn muốn hiển thị biểu tượng đại diện cho một tệp được nhúng.

```java
@Test
public void insertOleObjectAsIcon() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.insertOleObjectAsIcon("Your Directory Path" + "Presentation.pptx", false, getImagesDir() + "Logo icon.ico", "My embedded file");
    doc.save(outPath + "WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
}
```

Trong mã này, chúng tôi chèn một đối tượng OLE làm biểu tượng, cung cấp cách trình bày nội dung được nhúng trực quan hấp dẫn hơn.

### Đọc thuộc tính điều khiển ActiveX

Bây giờ, hãy chuyển trọng tâm sang điều khiển ActiveX. Chúng ta sẽ tìm hiểu cách đọc các thuộc tính của điều khiển ActiveX trong tài liệu Word.

```java
@Test
public void readActiveXControlProperties() throws Exception
{
    Document doc = new Document("Your Directory Path" + "ActiveX controls.docx");
    String properties = "";
    for (Shape shape : (Iterable<Shape>) doc.getChildNodes(NodeType.SHAPE, true))
    {
        if (shape.getOleFormat() == null) break;
        OleControl oleControl = shape.getOleFormat().getOleControl();
        if (oleControl.isForms2OleControl())
        {
            Forms2OleControl checkBox = (Forms2OleControl) oleControl;
            properties = properties + "\nCaption: " + checkBox.getCaption();
            properties = properties + "\nValue: " + checkBox.getValue();
            properties = properties + "\nEnabled: " + checkBox.getEnabled();
            properties = properties + "\nType: " + checkBox.getType();
            if (checkBox.getChildNodes() != null)
            {
                properties = properties + "\nChildNodes: " + checkBox.getChildNodes();
            }
            properties += "\n";
        }
    }
    properties = properties + "\nTotal ActiveX Controls found: " + doc.getChildNodes(NodeType.SHAPE, true).getCount();
    System.out.println("\n" + properties);
}
```

Trong mã này, chúng tôi lặp qua các hình dạng trong tài liệu Word, xác định các điều khiển ActiveX và truy xuất các thuộc tính của chúng.

### Phần kết luận

Chúc mừng! Bạn đã học cách làm việc với các đối tượng OLE và điều khiển ActiveX trong Aspose.Words cho Java. Những tính năng này mở ra vô số khả năng tạo tài liệu động và tương tác.

### Câu hỏi thường gặp

### Mục đích của đối tượng OLE trong tài liệu Word là gì? 
   - Đối tượng OLE cho phép bạn nhúng hoặc liên kết nội dung bên ngoài, chẳng hạn như tệp hoặc trang web, trong tài liệu Word.

### Tôi có thể tùy chỉnh giao diện của đối tượng OLE trong tài liệu của mình không? 
   - Có, bạn có thể tùy chỉnh giao diện của các đối tượng OLE, bao gồm cài đặt biểu tượng và tên tệp.

### Điều khiển ActiveX là gì và chúng có thể cải thiện tài liệu của tôi như thế nào? 
   - Điều khiển ActiveX là các thành phần tương tác có thể thêm chức năng vào tài liệu Word của bạn, chẳng hạn như điều khiển biểu mẫu hoặc trình phát đa phương tiện.

### Aspose.Words cho Java có phù hợp với việc tự động hóa tài liệu cấp doanh nghiệp không? 
   - Có, Aspose.Words for Java là một thư viện mạnh mẽ để tự động hóa việc tạo và thao tác tài liệu trong các ứng dụng Java.

### Tôi có thể truy cập Aspose.Words cho Java ở đâu? 
   -  Bạn có thể tải xuống Aspose.Words cho Java từ[đây](https://releases.aspose.com/words/java/).

Hãy bắt đầu với Aspose.Words cho Java ngay hôm nay và khám phá toàn bộ tiềm năng của việc tự động hóa và tùy chỉnh tài liệu!
