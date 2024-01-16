---
title: การใช้ฟิลด์ใน Aspose.Words สำหรับ Java
linktitle: การใช้ฟิลด์
second_title: Aspose.Words Java การประมวลผลเอกสาร API
description: เรียนรู้การใช้ฟิลด์ Aspose.Words สำหรับ Java อย่างมีประสิทธิภาพในบทช่วยสอนทีละขั้นตอนนี้ สร้างเอกสาร Word แบบไดนามิกได้อย่างง่ายดาย
type: docs
weight: 11
url: /th/java/using-document-elements/using-fields/
---

ในบทช่วยสอนทีละขั้นตอนนี้ เราจะแนะนำคุณเกี่ยวกับวิธีใช้ฟิลด์ใน Aspose.Words สำหรับ Java เพื่อจัดการเอกสารได้อย่างง่ายดาย Aspose.Words สำหรับ Java เป็น API ที่ทรงพลังที่ช่วยให้คุณทำงานกับเอกสาร Word โดยทางโปรแกรม ทำให้คุณควบคุมเนื้อหาและการจัดรูปแบบได้อย่างเต็มที่

## 1. บทนำ

Aspose.Words for Java เป็นเครื่องมือสำคัญสำหรับทุกคนที่เกี่ยวข้องกับเอกสาร Word ในแอปพลิเคชัน Java ช่องคือตัวยึดตำแหน่งที่สามารถจัดเก็บข้อมูลแบบไดนามิกในเอกสารของคุณได้ บทช่วยสอนนี้จะแสดงวิธีการทำงานกับฟิลด์อย่างมีประสิทธิภาพ

## 2. การตั้งค่าสภาพแวดล้อมของคุณ

 ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.Words สำหรับ Java แล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/words/java/). นอกจากนี้ ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java และสภาพแวดล้อมการพัฒนาแบบรวม (IDE) เช่น Eclipse หรือ IntelliJ IDEA บนระบบของคุณ

## 3. การโหลดเอกสาร Word

ในแอปพลิเคชัน Java ของคุณ คุณต้องโหลดเอกสาร Word ที่คุณต้องการใช้งาน ต่อไปนี้เป็นตัวอย่างโค้ดสำหรับการเริ่มต้น:

```java
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
Document doc = new Document(dataDir + "Mail merge destinations - Fax.docx");
```

 แทนที่`"Your Document Directory"` และ`"Your Output Directory"` ด้วยแนวทางที่เหมาะสม

## 4. การปรับแต่งจดหมายเวียน

Aspose.Words for Java ให้การสนับสนุนที่ดีเยี่ยมสำหรับการดำเนินการจดหมายเวียน คุณสามารถปรับแต่งกระบวนการจดหมายเวียนได้ด้วยการตั้งค่าตัวจัดการเหตุการณ์จดหมายเวียน ต่อไปนี้เป็นวิธีดำเนินการ:

```java
// ตั้งค่าตัวจัดการเหตุการณ์จดหมายเวียนเพื่อทำงานแบบกำหนดเอง
doc.getMailMerge().setFieldMergingCallback(new HandleMergeField());

// ตัดค่าจดหมายเวียนต่อท้ายและช่องว่างนำหน้า
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

## 5. การบันทึกเอกสาร

หลังจากปรับแต่งเอกสารของคุณแล้ว คุณสามารถบันทึกโดยใช้โค้ดต่อไปนี้:

```java
doc.save(outPath + "WorkingWithFields.MailMergeFormFields.docx");
```

 แทนที่`"Your Output Directory"` ด้วยเส้นทางขาออกที่ต้องการ

## กรอกซอร์สโค้ดให้สมบูรณ์
```java
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
Document doc = new Document(dataDir + "Mail merge destinations - Fax.docx");
// ตั้งค่าตัวจัดการเหตุการณ์จดหมายเวียนเพื่อทำงานแบบกำหนดเอง
doc.getMailMerge().setFieldMergingCallback(new HandleMergeField());
// ตัดค่าจดหมายเวียนต่อท้ายและช่องว่างนำหน้า
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
ซอร์สโค้ดของคลาส HandleMergeField

```java
    private static class HandleMergeField implements IFieldMergingCallback
    {
        /// <สรุป>
        /// ตัวจัดการนี้ถูกเรียกสำหรับทุกฟิลด์จดหมายเวียนที่พบในเอกสาร
        /// สำหรับทุกบันทึกที่พบในแหล่งข้อมูล
        /// </สรุป>
        public void /*IFieldMergingCallback.*/fieldMerging(FieldMergingArgs e) throws Exception
        {
            if (mBuilder == null)
                mBuilder = new DocumentBuilder(e.getDocument());
            // เราตัดสินใจว่าเราต้องการให้ค่าบูลีนทั้งหมดส่งออกเป็นช่องแบบฟอร์มช่องทำเครื่องหมาย
            if (e.getFieldValue() instanceof /*boolean*/Boolean)
            {
                // ย้าย "เคอร์เซอร์" ไปยังช่องผสานปัจจุบัน
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
            // ไม่จำเป็นต้องมีการดำเนินการ
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
        // แทรก MERGEFIELD ที่ซ้อนกันภายในฟิลด์ IF
        // เนื่องจากคำสั่งฟิลด์ IF เป็นเท็จ ผลลัพธ์ของ MERGEFIELD ภายในจะไม่แสดงขึ้นมา
        //และ MERGEFIELD จะไม่ได้รับข้อมูลใด ๆ ในระหว่างการรวมจดหมาย
        FieldIf fieldIf = (FieldIf)builder.insertField(" IF 1 = 2 ");
        builder.moveTo(fieldIf.getSeparator());
        builder.insertField(" MERGEFIELD  FullName ");
        // เรายังคงสามารถนับ MERGEFIELD ในช่อง IF ที่เป็นข้อความเท็จได้ หากเราตั้งค่าสถานะนี้เป็นจริง
        doc.getMailMerge().setUnconditionalMergeFieldsAndRegions(true);
        DataTable dataTable = new DataTable();
        dataTable.getColumns().add("FullName");
        dataTable.getRows().add("James Bond");
        doc.getMailMerge().execute(dataTable);
        // ผลลัพธ์จะไม่ปรากฏในเอกสารเนื่องจากฟิลด์ IF เป็นเท็จ
        // แต่ MERGEFIELD ภายในได้รับข้อมูลจริงๆ
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
            // ไม่ทำอะไร.
        }
        /// <สรุป>
        /// สิ่งนี้เรียกว่าเมื่อกลไกจัดการจดหมายเวียนพบฟิลด์รูปภาพ:XXX ผสานในเอกสาร
        /// คุณมีโอกาสที่จะส่งคืนออบเจ็กต์รูปภาพ ชื่อไฟล์ หรือสตรีมที่มีรูปภาพนั้น
        /// </สรุป>
        public void /*IFieldMergingCallback.*/imageFieldMerging(ImageFieldMergingArgs e) throws Exception
        {
            // ค่าของฟิลด์เป็นอาร์เรย์ไบต์ เพียงแค่ส่งและสร้างสตรีมบนนั้น
            ByteArrayInputStream imageStream = new ByteArrayInputStream((byte[]) e.getFieldValue());
            // ขณะนี้กลไกจัดการจดหมายเวียนจะดึงข้อมูลรูปภาพจากกระแสข้อมูล
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
        /// <สรุป>
        /// เรียกทุกช่องผสานที่พบในเอกสาร
        /// เราสามารถส่งคืนข้อมูลบางส่วนไปยังโปรแกรมจดหมายเวียนหรือดำเนินการอย่างอื่นกับเอกสารได้
        /// ในกรณีนี้ เราแก้ไขการจัดรูปแบบเซลล์
        /// </สรุป>
        public void /*IFieldMergingCallback.*/fieldMerging(FieldMergingArgs e)
        {
            if (mBuilder == null)
                mBuilder = new DocumentBuilder(e.getDocument());
            if ("CompanyName".equals(e.getFieldName()))
            {
                // เลือกสีขึ้นอยู่กับว่าหมายเลขแถวเป็นเลขคู่หรือคี่
                Color rowColor = isOdd(mRowIdx) 
                    ? new Color((213), (227), (235)) 
                    : new Color((242), (242), (242));
                //ขณะนี้ยังไม่มีวิธีตั้งค่าคุณสมบัติของเซลล์สำหรับทั้งแถว ดังนั้นเราจึงต้องวนซ้ำเซลล์ทั้งหมดในแถว
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
            // ไม่ทำอะไร.
        }
        private DocumentBuilder mBuilder;
        private int mRowIdx;
    }
    /// <สรุป>
    /// คืนค่าเป็นจริงหากค่าเป็นเลขคี่ เท็จถ้าค่าเป็นเลขคู่
    /// </สรุป>
    private static boolean isOdd(int value)
    {
        return (value / 2 * 2) == value;
    }
    /// <สรุป>
    /// สร้าง DataTable แล้วกรอกข้อมูล
    /// ในชีวิตจริง DataTable นี้ควรถูกเติมจากฐานข้อมูล
    /// </สรุป>
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

## 6. บทสรุป

ยินดีด้วย! คุณได้เรียนรู้วิธีใช้ฟิลด์ใน Aspose.Words สำหรับ Java เพื่อจัดการเอกสาร Word แบบไดนามิก API อันทรงพลังนี้ช่วยให้คุณควบคุมเอกสารของคุณได้อย่างสมบูรณ์ ทำให้เป็นทรัพย์สินที่มีค่าสำหรับนักพัฒนา Java

## 7. คำถามที่พบบ่อย

### คำถามที่ 1: ฉันจะดาวน์โหลด Aspose.Words สำหรับ Java ได้ที่ไหน
 คุณสามารถดาวน์โหลด Aspose.Words สำหรับ Java ได้จาก[ที่นี่](https://releases.aspose.com/words/java/).

### คำถามที่ 2: ฉันจะรับใบอนุญาตชั่วคราวสำหรับ Aspose.Words สำหรับ Java ได้อย่างไร
 คุณสามารถขอรับใบอนุญาตชั่วคราวได้จาก[ที่นี่](https://purchase.aspose.com/temporary-license/).

### คำถามที่ 3: ฉันจะรับการสนับสนุนสำหรับ Aspose.Words สำหรับ Java ได้ที่ไหน
 หากต้องการการสนับสนุน คุณสามารถไปที่ฟอรัม Aspose.Words[ที่นี่](https://forum.aspose.com/).

### คำถามที่ 4: Aspose.Words สำหรับ Java เหมาะสำหรับการจัดการเนื้อหา HTML ในเอกสาร Word หรือไม่
ใช่ Aspose.Words สำหรับ Java ให้การสนับสนุนที่ยอดเยี่ยมสำหรับการจัดการเนื้อหา HTML ในเอกสาร Word

### คำถามที่ 5: ฉันสามารถใช้ Aspose.Words สำหรับ Java ได้ฟรีหรือไม่
 Aspose.Words for Java เป็นผลิตภัณฑ์เชิงพาณิชย์ แต่คุณสามารถสำรวจฟีเจอร์ต่างๆ ของมันได้ด้วยการทดลองใช้ฟรี[ที่นี่](https://releases.aspose.com/).

เริ่มต้นใช้งาน Aspose.Words สำหรับ Java วันนี้และควบคุมเอกสาร Word ของคุณอย่างที่ไม่เคยมีมาก่อน!

