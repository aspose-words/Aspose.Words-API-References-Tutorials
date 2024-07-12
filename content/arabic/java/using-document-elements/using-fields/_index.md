---
title: استخدام الحقول في Aspose.Words لجافا
linktitle: استخدام الحقول
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة مستندات جافا
description: تعلم كيفية استخدام Aspose.Words لحقول Java بشكل فعال في هذا البرنامج التعليمي خطوة بخطوة. قم بإنشاء مستندات Word ديناميكية بسهولة.
type: docs
weight: 11
url: /ar/java/using-document-elements/using-fields/
---

في هذا البرنامج التعليمي خطوة بخطوة، سنرشدك حول كيفية استخدام الحقول في Aspose.Words for Java للتعامل مع المستندات بسهولة. Aspose.Words for Java عبارة عن واجهة برمجة تطبيقات قوية تتيح لك العمل مع مستندات Word برمجيًا، مما يمنحك التحكم الكامل في محتواها وتنسيقها.

## 1 المقدمة

Aspose.Words for Java هي أداة أساسية لأي شخص يتعامل مع مستندات Word في تطبيقات Java. الحقول عبارة عن عناصر نائبة يمكنها تخزين البيانات الديناميكية في مستندك. سيوضح لك هذا البرنامج التعليمي كيفية العمل مع الحقول بفعالية.

## 2. إعداد بيئتك

 قبل أن تبدأ، تأكد من تثبيت Aspose.Words for Java. يمكنك تنزيله من[هنا](https://releases.aspose.com/words/java/). تأكد أيضًا من تثبيت Java وبيئة التطوير المتكاملة (IDE) مثل Eclipse أو IntelliJ IDEA على نظامك.

## 3. تحميل مستند Word

في تطبيق Java الخاص بك، تحتاج إلى تحميل مستند Word الذي تريد العمل معه. إليك مقتطف من التعليمات البرمجية للبدء:

```java
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
Document doc = new Document(dataDir + "Mail merge destinations - Fax.docx");
```

 يستبدل`"Your Document Directory"`و`"Your Output Directory"` بالطرق المناسبة .

## 4. تخصيص دمج البريد

يوفر Aspose.Words for Java دعمًا ممتازًا لعمليات دمج البريد. يمكنك تخصيص عملية دمج المراسلات عن طريق إعداد معالج حدث دمج المراسلات. هيريس كيفية القيام بذلك:

```java
// قم بإعداد معالج حدث دمج البريد للقيام بالعمل المخصص.
doc.getMailMerge().setFieldMergingCallback(new HandleMergeField());

// قم بقص قيم دمج المراسلات اللاحقة والمسافات البيضاء البادئة.
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

## 5. حفظ الوثيقة

بعد تخصيص المستند الخاص بك، يمكنك حفظه باستخدام الكود التالي:

```java
doc.save(outPath + "WorkingWithFields.MailMergeFormFields.docx");
```

 يستبدل`"Your Output Directory"` مع مسار الإخراج المطلوب.

## كود المصدر الكامل
```java
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
Document doc = new Document(dataDir + "Mail merge destinations - Fax.docx");
// قم بإعداد معالج حدث دمج البريد للقيام بالعمل المخصص.
doc.getMailMerge().setFieldMergingCallback(new HandleMergeField());
// قم بقص قيم دمج المراسلات اللاحقة والمسافات البيضاء البادئة.
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
كود المصدر لفئة HandleMergeField

```java
    private static class HandleMergeField implements IFieldMergingCallback
    {
        /// <الملخص>
        /// يتم استدعاء هذا المعالج لكل حقل دمج بريدي موجود في المستند،
        /// لكل سجل موجود في مصدر البيانات.
        /// </ملخص>
        public void /*IFieldMergingCallback.*/fieldMerging(FieldMergingArgs e) throws Exception
        {
            if (mBuilder == null)
                mBuilder = new DocumentBuilder(e.getDocument());
            // قررنا أننا نريد أن يتم إخراج جميع القيم المنطقية كحقول نموذج خانة اختيار.
            if (e.getFieldValue() instanceof /*boolean*/Boolean)
            {
                // انقل "المؤشر" إلى حقل الدمج الحالي.
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
            // التنفيذ غير مطلوب.
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
        // قم بإدراج MERGEFIELD متداخل داخل حقل IF.
        // نظرًا لأن عبارة الحقل IF خاطئة، فلن يتم عرض نتيجة MERGEFIELD الداخلي،
        //ولن يتلقى MERGEFIELD أية بيانات أثناء عملية دمج المراسلات.
        FieldIf fieldIf = (FieldIf)builder.insertField(" IF 1 = 2 ");
        builder.moveTo(fieldIf.getSeparator());
        builder.insertField(" MERGEFIELD  FullName ");
        // لا يزال بإمكاننا حساب MERGEFIELDs داخل حقول IF الخاصة بالبيانات الخاطئة إذا قمنا بتعيين هذه العلامة على "صحيح".
        doc.getMailMerge().setUnconditionalMergeFieldsAndRegions(true);
        DataTable dataTable = new DataTable();
        dataTable.getColumns().add("FullName");
        dataTable.getRows().add("James Bond");
        doc.getMailMerge().execute(dataTable);
        // لن تكون النتيجة مرئية في المستند لأن حقل IF خطأ،
        // لكن MERGEFIELD الداخلي تلقى البيانات بالفعل.
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
            // لا تفعل شيئا.
        }
        /// <الملخص>
        /// يتم استدعاء هذا عندما يواجه محرك دمج البريد حقل دمج الصورة:XXX في المستند.
        /// لديك فرصة لإرجاع كائن صورة أو اسم ملف أو دفق يحتوي على الصورة.
        /// </ملخص>
        public void /*IFieldMergingCallback.*/imageFieldMerging(ImageFieldMergingArgs e) throws Exception
        {
            // قيمة الحقل عبارة عن مصفوفة بايت، ما عليك سوى إرسالها وإنشاء دفق عليها.
            ByteArrayInputStream imageStream = new ByteArrayInputStream((byte[]) e.getFieldValue());
            // الآن سيقوم مشغل دمج المراسلات باسترداد الصورة من الدفق.
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
        /// <الملخص>
        /// يتم استدعاؤه لكل حقل دمج موجود في المستند.
        /// يمكننا إما إرجاع بعض البيانات إلى محرك دمج المراسلات أو القيام بشيء آخر بالمستند.
        /// في هذه الحالة نقوم بتعديل تنسيق الخلية.
        /// </ملخص>
        public void /*IFieldMergingCallback.*/fieldMerging(FieldMergingArgs e)
        {
            if (mBuilder == null)
                mBuilder = new DocumentBuilder(e.getDocument());
            if ("CompanyName".equals(e.getFieldName()))
            {
                // حدد اللون بناءً على ما إذا كان رقم الصف زوجيًا أم فرديًا.
                Color rowColor = isOdd(mRowIdx) 
                    ? new Color((213), (227), (235)) 
                    : new Color((242), (242), (242));
                //لا توجد طريقة لتعيين خصائص الخلية للصف بأكمله في الوقت الحالي، لذلك يتعين علينا التكرار على جميع الخلايا في الصف.
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
            // لا تفعل شيئا.
        }
        private DocumentBuilder mBuilder;
        private int mRowIdx;
    }
    /// <الملخص>
    /// إرجاع صحيح إذا كانت القيمة غريبة؛ كاذبة إذا كانت القيمة زوجية.
    /// </ملخص>
    private static boolean isOdd(int value)
    {
        return (value / 2 * 2) == value;
    }
    /// <الملخص>
    /// قم بإنشاء DataTable واملأه بالبيانات.
    /// في الواقع، يجب ملء DataTable هذا من قاعدة بيانات.
    /// </ملخص>
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

## 6. الاستنتاج

تهانينا! لقد تعلمت كيفية استخدام الحقول في Aspose.Words for Java لمعالجة مستندات Word ديناميكيًا. تمنحك واجهة برمجة التطبيقات القوية هذه تحكمًا كاملاً في مستنداتك، مما يجعلها رصيدًا قيمًا لمطوري Java.

## 7. الأسئلة الشائعة

### س1: أين يمكنني تنزيل Aspose.Words لـ Java؟
 يمكنك تنزيل Aspose.Words for Java من[هنا](https://releases.aspose.com/words/java/).

### س2: كيف يمكنني الحصول على ترخيص مؤقت لبرنامج Aspose.Words لـ Java؟
 يمكنك الحصول على ترخيص مؤقت من[هنا](https://purchase.aspose.com/temporary-license/).

### س3: أين يمكنني الحصول على الدعم لـ Aspose.Words لـ Java؟
 للحصول على الدعم، يمكنك زيارة منتدى Aspose.Words[هنا](https://forum.aspose.com/).

### س 4: هل Aspose.Words for Java مناسب للتعامل مع محتوى HTML في مستندات Word؟
نعم، يوفر Aspose.Words for Java دعمًا ممتازًا للتعامل مع محتوى HTML في مستندات Word.

### س5: هل يمكنني استخدام Aspose.Words لـ Java مجانًا؟
 يعد Aspose.Words for Java منتجًا تجاريًا، ولكن يمكنك استكشاف ميزاته من خلال الإصدار التجريبي المجاني المتاح[هنا](https://releases.aspose.com/).

ابدأ استخدام Aspose.Words for Java اليوم وتحكم في مستندات Word الخاصة بك كما لم يحدث من قبل!

