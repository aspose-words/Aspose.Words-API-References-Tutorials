---
title: Använda fält i Aspose.Words för Java
linktitle: Använda fält
second_title: Aspose.Words Java Document Processing API
description: Lär dig att använda Aspose.Words för Java-fält effektivt i denna steg-för-steg handledning. Skapa dynamiska Word-dokument med lätthet.
type: docs
weight: 11
url: /sv/java/using-document-elements/using-fields/
---

denna steg-för-steg handledning kommer vi att guida dig om hur du använder fält i Aspose.Words för Java för att enkelt manipulera dokument. Aspose.Words för Java är ett kraftfullt API som låter dig arbeta med Word-dokument programmatiskt, vilket ger dig full kontroll över deras innehåll och formatering.

## 1. Introduktion

Aspose.Words för Java är ett viktigt verktyg för alla som arbetar med Word-dokument i Java-applikationer. Fält är platshållare som kan lagra dynamisk data i ditt dokument. Denna handledning visar dig hur du arbetar med fält effektivt.

## 2. Ställa in din miljö

 Innan du börjar, se till att du har Aspose.Words för Java installerat. Du kan ladda ner den från[här](https://releases.aspose.com/words/java/). Se också till att du har Java och en integrerad utvecklingsmiljö (IDE) som Eclipse eller IntelliJ IDEA installerad på ditt system.

## 3. Ladda ett Word-dokument

I din Java-applikation måste du ladda Word-dokumentet du vill arbeta med. Här är ett kodavsnitt för att komma igång:

```java
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
Document doc = new Document(dataDir + "Mail merge destinations - Fax.docx");
```

 Byta ut`"Your Document Directory"`och`"Your Output Directory"` med lämpliga vägar.

## 4. Anpassa Mail Merge

Aspose.Words för Java ger utmärkt stöd för kopplingsoperationer. Du kan anpassa kopplingsprocessen genom att konfigurera en kopplingshändelsehanterare. Så här gör du:

```java
// Konfigurera kopplingshändelsehanteraren för att göra det anpassade arbetet.
doc.getMailMerge().setFieldMergingCallback(new HandleMergeField());

// Trimma efterföljande och ledande blankstegs kopplingsvärden.
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

## 5. Spara dokumentet

När du har anpassat ditt dokument kan du spara det med följande kod:

```java
doc.save(outPath + "WorkingWithFields.MailMergeFormFields.docx");
```

 Byta ut`"Your Output Directory"` med önskad utgångsväg.

## Komplett källkod
```java
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
Document doc = new Document(dataDir + "Mail merge destinations - Fax.docx");
// Konfigurera kopplingshändelsehanteraren för att göra det anpassade arbetet.
doc.getMailMerge().setFieldMergingCallback(new HandleMergeField());
// Trimma efterföljande och ledande blankstegs kopplingsvärden.
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
Källkod för Class HandleMergeField

```java
    private static class HandleMergeField implements IFieldMergingCallback
    {
        /// <sammanfattning>
        /// Den här hanteraren anropas för varje kopplingsfält som finns i dokumentet,
        /// för varje post som finns i datakällan.
        /// </summary>
        public void /*IFieldMergingCallback.*/fieldMerging(FieldMergingArgs e) throws Exception
        {
            if (mBuilder == null)
                mBuilder = new DocumentBuilder(e.getDocument());
            // Vi beslutade att vi vill att alla booleska värden ska matas ut som kryssrutaformulär.
            if (e.getFieldValue() instanceof /*boolean*/Boolean)
            {
                // Flytta "markören" till det aktuella sammanslagningsfältet.
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
            // Implementering krävs inte.
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
        // Infoga ett MERGEFIELD kapslat i ett IF-fält.
        // Eftersom IF-fältsatsen är falsk kommer resultatet av det inre MERGEFIELD inte att visas,
        //och MERGEFIELD kommer inte att ta emot några data under en e-postsammanfogning.
        FieldIf fieldIf = (FieldIf)builder.insertField(" IF 1 = 2 ");
        builder.moveTo(fieldIf.getSeparator());
        builder.insertField(" MERGEFIELD  FullName ");
        // Vi kan fortfarande räkna MERGEFIELDs i falska IF-fält om vi ställer in denna flagga på sant.
        doc.getMailMerge().setUnconditionalMergeFieldsAndRegions(true);
        DataTable dataTable = new DataTable();
        dataTable.getColumns().add("FullName");
        dataTable.getRows().add("James Bond");
        doc.getMailMerge().execute(dataTable);
        // Resultatet kommer inte att synas i dokumentet eftersom IF-fältet är falskt,
        // men det inre MERGEFIELD fick verkligen data.
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
            // Göra ingenting.
        }
        /// <sammanfattning>
        /// Detta kallas när kopplingsmotorn stöter på Image:XXX kopplingsfält i dokumentet.
        /// Du har en chans att returnera ett bildobjekt, filnamn eller en ström som innehåller bilden.
        /// </summary>
        public void /*IFieldMergingCallback.*/imageFieldMerging(ImageFieldMergingArgs e) throws Exception
        {
            // Fältvärdet är en byte-array, bara casta den och skapa en ström på den.
            ByteArrayInputStream imageStream = new ByteArrayInputStream((byte[]) e.getFieldValue());
            // Nu kommer kopplingsmotorn att hämta bilden från strömmen.
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
        /// <sammanfattning>
        /// Anropas för varje sammanslagningsfält som påträffas i dokumentet.
        /// Vi kan antingen returnera vissa data till kopplingsmotorn eller göra något annat med dokumentet.
        /// I det här fallet ändrar vi cellformateringen.
        /// </summary>
        public void /*IFieldMergingCallback.*/fieldMerging(FieldMergingArgs e)
        {
            if (mBuilder == null)
                mBuilder = new DocumentBuilder(e.getDocument());
            if ("CompanyName".equals(e.getFieldName()))
            {
                // Välj färg beroende på om radnumret är jämnt eller udda.
                Color rowColor = isOdd(mRowIdx) 
                    ? new Color((213), (227), (235)) 
                    : new Color((242), (242), (242));
                //Det finns inget sätt att ställa in cellegenskaper för hela raden för tillfället, så vi måste iterera över alla celler i raden.
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
            // Göra ingenting.
        }
        private DocumentBuilder mBuilder;
        private int mRowIdx;
    }
    /// <sammanfattning>
    /// Returnerar sant om värdet är udda; falskt om värdet är jämnt.
    /// </summary>
    private static boolean isOdd(int value)
    {
        return (value / 2 * 2) == value;
    }
    /// <sammanfattning>
    /// Skapa DataTable och fyll den med data.
    /// I verkligheten bör denna datatabell fyllas i från en databas.
    /// </summary>
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

## 6. Sammanfattning

Grattis! Du har lärt dig hur du använder fält i Aspose.Words för Java för att manipulera Word-dokument dynamiskt. Detta kraftfulla API ger dig fullständig kontroll över dina dokument, vilket gör det till en värdefull tillgång för Java-utvecklare.

## 7. Vanliga frågor

### F1: Var kan jag ladda ner Aspose.Words för Java?
 Du kan ladda ner Aspose.Words för Java från[här](https://releases.aspose.com/words/java/).

### F2: Hur kan jag få en tillfällig licens för Aspose.Words för Java?
 Du kan få en tillfällig licens från[här](https://purchase.aspose.com/temporary-license/).

### F3: Var kan jag få support för Aspose.Words för Java?
 För support kan du besöka Aspose.Words-forumet[här](https://forum.aspose.com/).

### F4: Är Aspose.Words för Java lämpligt för att hantera HTML-innehåll i Word-dokument?
Ja, Aspose.Words för Java ger utmärkt stöd för hantering av HTML-innehåll i Word-dokument.

### F5: Kan jag använda Aspose.Words för Java gratis?
 Aspose.Words för Java är en kommersiell produkt, men du kan utforska dess funktioner med en gratis testversion tillgänglig[här](https://releases.aspose.com/).

Kom igång med Aspose.Words för Java idag och ta kontroll över dina Word-dokument som aldrig förr!

