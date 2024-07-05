---
title: Sử dụng Trường trong Aspose.Words cho Java
linktitle: Sử dụng trường
second_title: API xử lý tài liệu Java Aspose.Words
description: Tìm hiểu cách sử dụng Aspose.Words cho các trường Java một cách hiệu quả trong hướng dẫn từng bước này. Tạo tài liệu Word động một cách dễ dàng.
type: docs
weight: 11
url: /vi/java/using-document-elements/using-fields/
---

Trong hướng dẫn từng bước này, chúng tôi sẽ hướng dẫn bạn cách sử dụng các trường trong Aspose.Words cho Java để thao tác tài liệu một cách dễ dàng. Aspose.Words for Java là một API mạnh mẽ cho phép bạn làm việc với các tài liệu Word theo chương trình, cung cấp cho bạn toàn quyền kiểm soát nội dung và định dạng của chúng.

## 1. Giới thiệu

Aspose.Words for Java là một công cụ cần thiết cho bất kỳ ai xử lý tài liệu Word trong các ứng dụng Java. Các trường là phần giữ chỗ có thể lưu trữ dữ liệu động trong tài liệu của bạn. Hướng dẫn này sẽ chỉ cho bạn cách làm việc với các trường một cách hiệu quả.

## 2. Thiết lập môi trường của bạn

 Trước khi bắt đầu, hãy đảm bảo bạn đã cài đặt Aspose.Words for Java. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/words/java/). Ngoài ra, hãy đảm bảo rằng bạn đã cài đặt Java và môi trường phát triển tích hợp (IDE) như Eclipse hoặc IntelliJ IDEA trên hệ thống của mình.

## 3. Tải tài liệu Word

Trong ứng dụng Java của bạn, bạn cần tải tài liệu Word mà bạn muốn làm việc. Đây là một đoạn mã để giúp bạn bắt đầu:

```java
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
Document doc = new Document(dataDir + "Mail merge destinations - Fax.docx");
```

 Thay thế`"Your Document Directory"` Và`"Your Output Directory"` bằng những con đường phù hợp.

## 4. Tùy chỉnh trộn thư

Aspose.Words for Java cung cấp sự hỗ trợ tuyệt vời cho các hoạt động trộn thư. Bạn có thể tùy chỉnh quy trình trộn thư bằng cách thiết lập trình xử lý sự kiện trộn thư. Đây là cách thực hiện:

```java
// Thiết lập trình xử lý sự kiện trộn thư để thực hiện công việc tùy chỉnh.
doc.getMailMerge().setFieldMergingCallback(new HandleMergeField());

// Cắt bớt các giá trị hợp nhất thư ở cuối và khoảng trắng ở đầu.
doc.getMailMerge().setTrimWhitespaces(false);

String[] fieldNames = {
    "RecipientName", "SenderName", "FaxNumber", "PhoneNumber",
    "Subject", "Body", "Urgent", "ForReview", "PleaseComment"
};

Object[] fieldValues = {
    "Josh", "Jenny", "123456789", "", "Hello",
    "<b>HTML Body Test message 1</b>", true, false, true
};

doc.getMailMerge().execute(fieldNames, fieldValues);
```

## 5. Lưu tài liệu

Sau khi tùy chỉnh tài liệu của bạn, bạn có thể lưu nó bằng mã sau:

```java
doc.save(outPath + "WorkingWithFields.MailMergeFormFields.docx");
```

 Thay thế`"Your Output Directory"` với đường dẫn đầu ra mong muốn.

## Mã nguồn hoàn chỉnh
```java
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
Document doc = new Document(dataDir + "Mail merge destinations - Fax.docx");
// Thiết lập trình xử lý sự kiện trộn thư để thực hiện công việc tùy chỉnh.
doc.getMailMerge().setFieldMergingCallback(new HandleMergeField());
// Cắt bớt các giá trị hợp nhất thư ở cuối và khoảng trắng ở đầu.
doc.getMailMerge().setTrimWhitespaces(false);
String[] fieldNames = {
	"RecipientName", "SenderName", "FaxNumber", "PhoneNumber",
	"Subject", "Body", "Urgent", "ForReview", "PleaseComment"
};
Object[] fieldValues = {
	"Josh", "Jenny", "123456789", "", "Hello",
	"<b>HTML Body Test message 1</b>", true, false, true
};
doc.getMailMerge().execute(fieldNames, fieldValues);
doc.save(outPath + "WorkingWithFields.MailMergeFormFields.docx");
```
Mã nguồn của Lớp HandleMergeField

```java
    private static class HandleMergeField implements IFieldMergingCallback
    {
        /// <tóm tắt>
        /// Trình xử lý này được gọi cho mọi trường trộn thư được tìm thấy trong tài liệu,
        /// cho mọi bản ghi được tìm thấy trong nguồn dữ liệu.
        /// </tóm tắt>
        public void /*IFieldMergingCallback.*/fieldMerging(FieldMergingArgs e) throws Exception
        {
            if (mBuilder == null)
                mBuilder = new DocumentBuilder(e.getDocument());
            // Chúng tôi quyết định rằng chúng tôi muốn tất cả các giá trị boolean được xuất ra dưới dạng trường biểu mẫu hộp kiểm.
            if (e.getFieldValue() instanceof /*boolean*/Boolean)
            {
                // Di chuyển "con trỏ" đến trường hợp nhất hiện tại.
                mBuilder.moveToMergeField(e.getFieldName());
                String checkBoxName = MessageFormat.format("{0}{1}", e.getFieldName(), e.getRecordIndex());
                mBuilder.insertCheckBox(checkBoxName, (Boolean) e.getFieldValue(), 0);
                return;
            }
            switch (e.getFieldName())
            {
                case "Body":
                    mBuilder.moveToMergeField(e.getFieldName());
                    mBuilder.insertHtml((String) e.getFieldValue());
                    break;
                case "Subject":
                {
                    mBuilder.moveToMergeField(e.getFieldName());
                    String textInputName = MessageFormat.format("{0}{1}", e.getFieldName(), e.getRecordIndex());
                    mBuilder.insertTextInput(textInputName, TextFormFieldType.REGULAR, "", (String) e.getFieldValue(), 0);
                    break;
                }
            }
        }
        public void imageFieldMerging(ImageFieldMergingArgs args)
        {
            args.setImageFileName("Image.png");
            args.getImageWidth().setValue(200.0);
            args.setImageHeight(new MergeFieldImageDimension(200.0, MergeFieldImageDimensionUnit.PERCENT));
        }
        private DocumentBuilder mBuilder;
    }
    @Test
    public void mailMergeImageField() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.writeln("{{#foreach example}}");
        builder.writeln("{{Image(126pt;126pt):stempel}}");
        builder.writeln("{{/foreach example}}");
        doc.getMailMerge().setUseNonMergeFields(true);
        doc.getMailMerge().setTrimWhitespaces(true);
        doc.getMailMerge().setUseWholeParagraphAsRegion(false);
        doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_TABLE_ROWS
                | MailMergeCleanupOptions.REMOVE_CONTAINING_FIELDS
                | MailMergeCleanupOptions.REMOVE_UNUSED_REGIONS
                | MailMergeCleanupOptions.REMOVE_UNUSED_FIELDS);
        doc.getMailMerge().setFieldMergingCallback(new ImageFieldMergingHandler());
        doc.getMailMerge().executeWithRegions(new DataSourceRoot());
        doc.save("Your Directory Path" + "WorkingWithFields.MailMergeImageField.docx");
    }
    private static class ImageFieldMergingHandler implements IFieldMergingCallback
    {
        public void fieldMerging(FieldMergingArgs args)
        {
            // Việc thực hiện là không cần thiết.
        }
        public void imageFieldMerging(ImageFieldMergingArgs args) throws Exception
        {
            Shape shape = new Shape(args.getDocument(), ShapeType.IMAGE);
            {
                shape.setWidth(126.0); shape.setHeight(126.0); shape.setWrapType(WrapType.SQUARE);
            }
            shape.getImageData().setImage("Your Directory Path" + "Mail merge image.png");
            args.setShape(shape);
        }
    }
    public static class DataSourceRoot implements IMailMergeDataSourceRoot
    {
        public IMailMergeDataSource getDataSource(String s)
        {
            return new DataSource();
        }
        private static class DataSource implements IMailMergeDataSource
        {
            private boolean next = true;
            private String tableName()
            {
                return "example";
            }
            @Override
            public String getTableName() {
                return tableName();
            }
            public boolean moveNext()
            {
                boolean result = next;
                next = false;
                return result;
            }
            public IMailMergeDataSource getChildDataSource(String s)
            {
                return null;
            }
            public boolean getValue(String fieldName, Ref<Object> fieldValue)
            {
                fieldValue.set(null);
                return false;
            }
        }
    }
    @Test
    public void mailMergeAndConditionalField() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // Chèn MERGEFIELD lồng bên trong trường IF.
        // Vì câu lệnh trường IF là sai nên kết quả của MERGEFIELD bên trong sẽ không được hiển thị,
        //và MERGEFIELD sẽ không nhận được bất kỳ dữ liệu nào trong quá trình trộn thư.
        FieldIf fieldIf = (FieldIf)builder.insertField(" IF 1 = 2 ");
        builder.moveTo(fieldIf.getSeparator());
        builder.insertField(" MERGEFIELD  FullName ");
        // Chúng tôi vẫn có thể đếm MERGEFIELD bên trong các trường IF câu lệnh sai nếu chúng tôi đặt cờ này thành true.
        doc.getMailMerge().setUnconditionalMergeFieldsAndRegions(true);
        DataTable dataTable = new DataTable();
        dataTable.getColumns().add("FullName");
        dataTable.getRows().add("James Bond");
        doc.getMailMerge().execute(dataTable);
        // Kết quả sẽ không hiển thị trong tài liệu vì trường IF sai,
        // nhưng MERGEFIELD bên trong thực sự đã nhận được dữ liệu.
        doc.save("Your Directory Path" + "WorkingWithFields.MailMergeAndConditionalField.docx");
    }
    @Test
    public void mailMergeImageFromBlob() throws Exception
    {
        Document doc = new Document("Your Directory Path" + "Mail merge destination - Northwind employees.docx");
        doc.getMailMerge().setFieldMergingCallback(new HandleMergeImageFieldFromBlob());
        Class.forName("net.ucanaccess.jdbc.UcanaccessDriver");
        String connString = "jdbc:ucanaccess://" + getDatabaseDir() + "Northwind.mdb";
        Connection connection = DriverManager.getConnection(connString, "Admin", "");
        Statement statement = connection.createStatement();
        ResultSet resultSet = statement.executeQuery("SELECT * FROM Employees");
        DataTable dataTable = new DataTable(resultSet, "Employees");
        IDataReader dataReader = new DataTableReader(dataTable);
        doc.getMailMerge().executeWithRegions(dataReader, "Employees");
        connection.close();
        doc.save("Your Directory Path" + "WorkingWithFields.MailMergeImageFromBlob.docx");
    }
    public static class HandleMergeImageFieldFromBlob implements IFieldMergingCallback
    {
        public void /*IFieldMergingCallback.*/fieldMerging(FieldMergingArgs args)
        {
            // Không làm gì cả.
        }
        /// <tóm tắt>
        /// Điều này được gọi khi công cụ trộn thư gặp trường hợp nhất Hình ảnh:XXX trong tài liệu.
        /// Bạn có cơ hội trả về một đối tượng Hình ảnh, tên tệp hoặc luồng chứa hình ảnh.
        /// </tóm tắt>
        public void /*IFieldMergingCallback.*/imageFieldMerging(ImageFieldMergingArgs e) throws Exception
        {
            // Giá trị trường là một mảng byte, chỉ cần truyền nó và tạo luồng trên đó.
            ByteArrayInputStream imageStream = new ByteArrayInputStream((byte[]) e.getFieldValue());
            // Bây giờ công cụ trộn thư sẽ truy xuất hình ảnh từ luồng.
            e.setImageStream(imageStream);
        }
    }
    @Test
    public void handleMailMergeSwitches() throws Exception
    {
        Document doc = new Document("Your Directory Path" + "Field sample - MERGEFIELD.docx");
        doc.getMailMerge().setFieldMergingCallback(new MailMergeSwitches());
        final String HTML = "<html>\r\n                    <h1>Hello world!</h1>\r\n            </html>";
        doc.getMailMerge().execute(new String[] { "htmlField1" }, new Object[] { HTML });
        doc.save("Your Directory Path" + "WorkingWithFields.HandleMailMergeSwitches.docx");
    }
    public static class MailMergeSwitches implements IFieldMergingCallback
    {
        public void /*IFieldMergingCallback.*/fieldMerging(FieldMergingArgs e) throws Exception
        {
            if (e.getFieldName().startsWith("HTML"))
            {
                if (e.getField().getFieldCode().contains("\\b"))
                {
                    FieldMergeField field = e.getField();
                    DocumentBuilder builder = new DocumentBuilder(e.getDocument());
                    builder.moveToMergeField(e.getDocumentFieldName(), true, false);
                    builder.write(field.getTextBefore());
                    builder.insertHtml(e.getFieldValue().toString());
                    e.setText("");
                }
            }
        }
        public void /*IFieldMergingCallback.*/imageFieldMerging(ImageFieldMergingArgs args)
        {
        }
    }
    @Test
    public void alternatingRows() throws Exception
    {
        Document doc = new Document("Your Directory Path" + "Mail merge destination - Northwind suppliers.docx");
        doc.getMailMerge().setFieldMergingCallback(new HandleMergeFieldAlternatingRows());
        DataTable dataTable = getSuppliersDataTable();
        doc.getMailMerge().executeWithRegions(dataTable);
        doc.save("Your Directory Path" + "WorkingWithFields.AlternatingRows.doc");
    }
    private static class HandleMergeFieldAlternatingRows implements IFieldMergingCallback
    {
        /// <tóm tắt>
        /// Được gọi cho mọi trường hợp nhất gặp phải trong tài liệu.
        /// Chúng tôi có thể trả lại một số dữ liệu cho công cụ trộn thư hoặc thực hiện thao tác khác với tài liệu.
        /// Trong trường hợp này chúng tôi sửa đổi định dạng ô.
        /// </tóm tắt>
        public void /*IFieldMergingCallback.*/fieldMerging(FieldMergingArgs e)
        {
            if (mBuilder == null)
                mBuilder = new DocumentBuilder(e.getDocument());
            if ("CompanyName".equals(e.getFieldName()))
            {
                // Chọn màu tùy theo số hàng là chẵn hay lẻ.
                Color rowColor = isOdd(mRowIdx) 
                    ? new Color((213), (227), (235)) 
                    : new Color((242), (242), (242));
                //Hiện tại không có cách nào để đặt thuộc tính ô cho toàn bộ hàng, vì vậy chúng ta phải lặp lại tất cả các ô trong hàng.
                for (int colIdx = 0; colIdx < 4; colIdx++)
                {
                    mBuilder.moveToCell(0, mRowIdx, colIdx, 0);
                    mBuilder.getCellFormat().getShading().setBackgroundPatternColor(rowColor);
                }
                mRowIdx++;
            }
        }
        public void /*IFieldMergingCallback.*/imageFieldMerging(ImageFieldMergingArgs args)
        {
            // Không làm gì cả.
        }
        private DocumentBuilder mBuilder;
        private int mRowIdx;
    }
    /// <tóm tắt>
    /// Trả về true nếu giá trị là số lẻ; sai nếu giá trị là số chẵn.
    /// </tóm tắt>
    private static boolean isOdd(int value)
    {
        return (value / 2 * 2) == value;
    }
    /// <tóm tắt>
    /// Tạo DataTable và điền dữ liệu vào.
    /// Trong thực tế, DataTable này phải được điền từ cơ sở dữ liệu.
    /// </tóm tắt>
    private DataTable getSuppliersDataTable()
    {
        DataTable dataTable = new DataTable("Suppliers");
        dataTable.getColumns().add("CompanyName");
        dataTable.getColumns().add("ContactName");
        for (int i = 0; i < 10; i++)
        {
            DataRow datarow = dataTable.newRow();
            dataTable.getRows().add(datarow);
            datarow.set(0, "Company " + i);
            datarow.set(1, "Contact " + i);
        }
        return dataTable;
	}
}
```

## 6. Kết luận

Chúc mừng! Bạn đã học cách sử dụng các trường trong Aspose.Words dành cho Java để thao tác linh hoạt với tài liệu Word. API mạnh mẽ này cung cấp cho bạn toàn quyền kiểm soát tài liệu của mình, khiến nó trở thành tài sản quý giá cho các nhà phát triển Java.

## 7. Câu hỏi thường gặp

### Câu hỏi 1: Tôi có thể tải xuống Aspose.Words cho Java ở đâu?
 Bạn có thể tải xuống Aspose.Words cho Java từ[đây](https://releases.aspose.com/words/java/).

### Câu hỏi 2: Làm cách nào tôi có thể nhận được giấy phép tạm thời cho Aspose.Words cho Java?
 Bạn có thể xin giấy phép tạm thời từ[đây](https://purchase.aspose.com/temporary-license/).

### Câu hỏi 3: Tôi có thể nhận hỗ trợ cho Aspose.Words cho Java ở đâu?
 Để được hỗ trợ, bạn có thể truy cập diễn đàn Aspose.Words[đây](https://forum.aspose.com/).

### Câu hỏi 4: Aspose.Words dành cho Java có phù hợp để xử lý nội dung HTML trong tài liệu Word không?
Có, Aspose.Words for Java cung cấp hỗ trợ tuyệt vời để xử lý nội dung HTML trong tài liệu Word.

### Câu hỏi 5: Tôi có thể sử dụng Aspose.Words cho Java miễn phí không?
 Aspose.Words for Java là một sản phẩm thương mại, nhưng bạn có thể khám phá các tính năng của nó bằng bản dùng thử miễn phí có sẵn[đây](https://releases.aspose.com/).

Hãy bắt đầu với Aspose.Words cho Java ngay hôm nay và kiểm soát các tài liệu Word của bạn hơn bao giờ hết!

