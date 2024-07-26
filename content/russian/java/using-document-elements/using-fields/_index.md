---
title: Использование полей в Aspose.Words для Java
linktitle: Использование полей
second_title: API обработки Java-документов Aspose.Words
description: Научитесь эффективно использовать поля Aspose.Words для Java в этом пошаговом руководстве. С легкостью создавайте динамические документы Word.
type: docs
weight: 11
url: /ru/java/using-document-elements/using-fields/
---

В этом пошаговом руководстве мы покажем вам, как использовать поля в Aspose.Words для Java для удобного управления документами. Aspose.Words for Java — это мощный API, который позволяет вам программно работать с документами Word, предоставляя вам полный контроль над их содержимым и форматированием.

## 1. Введение

Aspose.Words for Java — это важный инструмент для всех, кто работает с документами Word в приложениях Java. Поля — это заполнители, которые могут хранить динамические данные в вашем документе. Из этого туториала вы узнаете, как эффективно работать с полями.

## 2. Настройка среды

 Прежде чем начать, убедитесь, что у вас установлен Aspose.Words для Java. Вы можете скачать его с[здесь](https://releases.aspose.com/words/java/). Кроме того, убедитесь, что в вашей системе установлена Java и интегрированная среда разработки (IDE), такая как Eclipse или IntelliJ IDEA.

## 3. Загрузка документа Word

В вашем Java-приложении вам необходимо загрузить документ Word, с которым вы хотите работать. Вот фрагмент кода, который поможет вам начать:

```java
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
Document doc = new Document(dataDir + "Mail merge destinations - Fax.docx");
```

 Заменять`"Your Document Directory"`и`"Your Output Directory"` с соответствующими путями.

## 4. Настройка слияния почты

Aspose.Words для Java обеспечивает отличную поддержку операций слияния почты. Вы можете настроить процесс слияния почты, настроив обработчик событий слияния почты. Вот как это сделать:

```java
// Настройте обработчик событий слияния почты для выполнения индивидуальной работы.
doc.getMailMerge().setFieldMergingCallback(new HandleMergeField());

// Обрезать конечные и ведущие пробелы в значениях слияния почты.
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

## 5. Сохранение документа

После настройки документа вы можете сохранить его, используя следующий код:

```java
doc.save(outPath + "WorkingWithFields.MailMergeFormFields.docx");
```

 Заменять`"Your Output Directory"` с желаемым выходным путем.

## Полный исходный код
```java
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
Document doc = new Document(dataDir + "Mail merge destinations - Fax.docx");
// Настройте обработчик событий слияния почты для выполнения индивидуальной работы.
doc.getMailMerge().setFieldMergingCallback(new HandleMergeField());
// Обрезать конечные и ведущие пробелы в значениях слияния почты.
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
Исходный код класса HandleMergeField

```java
    private static class HandleMergeField implements IFieldMergingCallback
    {
        /// <сводка>
        /// Этот обработчик вызывается для каждого поля слияния почты, найденного в документе,
        /// для каждой записи, найденной в источнике данных.
        /// </сводка>
        public void /*IFieldMergingCallback.*/fieldMerging(FieldMergingArgs e) throws Exception
        {
            if (mBuilder == null)
                mBuilder = new DocumentBuilder(e.getDocument());
            // Мы решили, что хотим, чтобы все логические значения выводились в виде полей формы флажков.
            if (e.getFieldValue() instanceof /*boolean*/Boolean)
            {
                // Переместите «курсор» в текущее поле слияния.
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
            // Реализация не требуется.
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
        // Вставьте MERGEFIELD, вложенный в поле IF.
        // Поскольку оператор поля IF является ложным, результат внутреннего MERGEFIELD не будет отображаться.
        //и MERGEFIELD не будет получать никаких данных во время слияния почты.
        FieldIf fieldIf = (FieldIf)builder.insertField(" IF 1 = 2 ");
        builder.moveTo(fieldIf.getSeparator());
        builder.insertField(" MERGEFIELD  FullName ");
        // Мы по-прежнему можем считать поля MERGEFIELD внутри полей IF с ложным оператором, если установим для этого флага значение true.
        doc.getMailMerge().setUnconditionalMergeFieldsAndRegions(true);
        DataTable dataTable = new DataTable();
        dataTable.getColumns().add("FullName");
        dataTable.getRows().add("James Bond");
        doc.getMailMerge().execute(dataTable);
        // Результат не будет виден в документе, поскольку поле IF имеет значение false.
        // но внутренний MERGEFILD действительно получил данные.
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
            // Ничего не делать.
        }
        /// <сводка>
        /// Это вызывается, когда механизм слияния почты обнаруживает в документе поле слияния Image:XXX.
        /// У вас есть возможность вернуть объект изображения, имя файла или поток, содержащий изображение.
        /// </сводка>
        public void /*IFieldMergingCallback.*/imageFieldMerging(ImageFieldMergingArgs e) throws Exception
        {
            // Значение поля представляет собой массив байтов, просто приведите его и создайте на нем поток.
            ByteArrayInputStream imageStream = new ByteArrayInputStream((byte[]) e.getFieldValue());
            // Теперь механизм слияния почты будет извлекать изображение из потока.
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
        /// <сводка>
        /// Вызывается для каждого поля слияния, встречающегося в документе.
        /// Мы можем либо вернуть некоторые данные в механизм слияния почты, либо сделать с документом что-то еще.
        /// В этом случае мы изменяем форматирование ячеек.
        /// </сводка>
        public void /*IFieldMergingCallback.*/fieldMerging(FieldMergingArgs e)
        {
            if (mBuilder == null)
                mBuilder = new DocumentBuilder(e.getDocument());
            if ("CompanyName".equals(e.getFieldName()))
            {
                // Выберите цвет в зависимости от того, четный или нечетный номер строки.
                Color rowColor = isOdd(mRowIdx) 
                    ? new Color((213), (227), (235)) 
                    : new Color((242), (242), (242));
                //На данный момент нет возможности установить свойства ячейки для всей строки, поэтому нам приходится перебирать все ячейки в строке.
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
            // Ничего не делать.
        }
        private DocumentBuilder mBuilder;
        private int mRowIdx;
    }
    /// <сводка>
    /// Возвращает true, если значение нечетное; false, если значение четное.
    /// </сводка>
    private static boolean isOdd(int value)
    {
        return (value / 2 * 2) == value;
    }
    /// <сводка>
    /// Создать DataTable и заполнить ее данными.
    /// В реальной жизни этот DataTable должен заполняться из базы данных.
    /// </сводка>
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

## 6. Заключение

Поздравляем! Вы узнали, как использовать поля в Aspose.Words для Java для динамического управления документами Word. Этот мощный API дает вам полный контроль над вашими документами, что делает его ценным активом для разработчиков Java.

## 7. Часто задаваемые вопросы

### Вопрос 1: Где я могу скачать Aspose.Words для Java?
 Вы можете скачать Aspose.Words для Java с сайта[здесь](https://releases.aspose.com/words/java/).

### В2: Как я могу получить временную лицензию на Aspose.Words для Java?
 Вы можете получить временную лицензию[здесь](https://purchase.aspose.com/temporary-license/).

### Вопрос 3. Где я могу получить поддержку Aspose.Words для Java?
 Для поддержки вы можете посетить форум Aspose.Words.[здесь](https://forum.aspose.com/).

### Вопрос 4. Подходит ли Aspose.Words для Java для обработки HTML-содержимого в документах Word?
Да, Aspose.Words for Java обеспечивает отличную поддержку обработки HTML-содержимого в документах Word.

### Вопрос 5: Могу ли я использовать Aspose.Words для Java бесплатно?
 Aspose.Words for Java — это коммерческий продукт, но вы можете изучить его возможности, воспользовавшись бесплатной пробной версией.[здесь](https://releases.aspose.com/).

Начните работу с Aspose.Words для Java сегодня и возьмите под контроль свои документы Word, как никогда раньше!

