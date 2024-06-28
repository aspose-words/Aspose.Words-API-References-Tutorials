---
title: Velden gebruiken in Aspose.Words voor Java
linktitle: Velden gebruiken
second_title: Aspose.Words Java-documentverwerkings-API
description: Leer hoe u Aspose.Words effectief kunt gebruiken voor Java-velden in deze stapsgewijze zelfstudie. Creëer eenvoudig dynamische Word-documenten.
type: docs
weight: 11
url: /nl/java/using-document-elements/using-fields/
---

In deze stapsgewijze zelfstudie laten we u zien hoe u velden in Aspose.Words voor Java kunt gebruiken om documenten gemakkelijk te manipuleren. Aspose.Words voor Java is een krachtige API waarmee u programmatisch met Word-documenten kunt werken, waardoor u volledige controle krijgt over de inhoud en opmaak ervan.

## 1. Inleiding

Aspose.Words voor Java is een essentieel hulpmiddel voor iedereen die met Word-documenten in Java-toepassingen werkt. Velden zijn tijdelijke aanduidingen die dynamische gegevens in uw document kunnen opslaan. In deze tutorial leert u hoe u effectief met velden kunt werken.

## 2. Uw omgeving instellen

 Zorg ervoor dat Aspose.Words voor Java is geïnstalleerd voordat u begint. Je kunt het downloaden van[hier](https://releases.aspose.com/words/java/). Zorg er ook voor dat Java en een geïntegreerde ontwikkelomgeving (IDE) zoals Eclipse of IntelliJ IDEA op uw systeem zijn geïnstalleerd.

## 3. Een Word-document laden

In uw Java-toepassing moet u het Word-document laden waarmee u wilt werken. Hier is een codefragment om u op weg te helpen:

```java
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
Document doc = new Document(dataDir + "Mail merge destinations - Fax.docx");
```

 Vervangen`"Your Document Directory"` En`"Your Output Directory"` met de juiste paden.

## 4. Afdruk samenvoegen aanpassen

Aspose.Words voor Java biedt uitstekende ondersteuning voor samenvoegbewerkingen. U kunt het samenvoegproces aanpassen door een gebeurtenishandler voor het samenvoegen in te stellen. Hier leest u hoe u het moet doen:

```java
// Stel de gebeurtenishandler voor mail merge in om het aangepaste werk uit te voeren.
doc.getMailMerge().setFieldMergingCallback(new HandleMergeField());

// Trim de waarden voor de navolgende en voorlopende witruimten bij het samenvoegen.
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

## 5. Het document opslaan

Nadat u uw document heeft aangepast, kunt u het opslaan met de volgende code:

```java
doc.save(outPath + "WorkingWithFields.MailMergeFormFields.docx");
```

 Vervangen`"Your Output Directory"` met het gewenste uitvoerpad.

## Volledige broncode
```java
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
Document doc = new Document(dataDir + "Mail merge destinations - Fax.docx");
// Stel de gebeurtenishandler voor mail merge in om het aangepaste werk uit te voeren.
doc.getMailMerge().setFieldMergingCallback(new HandleMergeField());
// Trim de waarden voor de navolgende en voorlopende witruimten bij het samenvoegen.
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
Broncode van klasse HandleMergeField

```java
    private static class HandleMergeField implements IFieldMergingCallback
    {
        /// <samenvatting>
        /// Deze handler wordt aangeroepen voor elk samenvoegveld in het document,
        /// voor elk record gevonden in de gegevensbron.
        ///</samenvatting>
        public void /*IFieldMergingCallback.*/fieldMerging(FieldMergingArgs e) throws Exception
        {
            if (mBuilder == null)
                mBuilder = new DocumentBuilder(e.getDocument());
            // We hebben besloten dat we willen dat alle Booleaanse waarden worden uitgevoerd als selectievakje-formuliervelden.
            if (e.getFieldValue() instanceof /*boolean*/Boolean)
            {
                // Verplaats de "cursor" naar het huidige samenvoegveld.
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
            // Implementatie is niet vereist.
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
        // Voeg een MERGEFIELD in, genest in een IF-veld.
        // Omdat de IF-veldinstructie onwaar is, wordt het resultaat van het binnenste MERGEFIELD niet weergegeven.
        //en het MERGEFIELD ontvangt geen gegevens tijdens een samenvoegbewerking.
        FieldIf fieldIf = (FieldIf)builder.insertField(" IF 1 = 2 ");
        builder.moveTo(fieldIf.getSeparator());
        builder.insertField(" MERGEFIELD  FullName ");
        // We kunnen nog steeds MERGEFIELD's tellen in IF-velden met valse verklaringen als we deze vlag op true instellen.
        doc.getMailMerge().setUnconditionalMergeFieldsAndRegions(true);
        DataTable dataTable = new DataTable();
        dataTable.getColumns().add("FullName");
        dataTable.getRows().add("James Bond");
        doc.getMailMerge().execute(dataTable);
        // Het resultaat zal niet zichtbaar zijn in het document omdat het IF-veld onwaar is.
        // maar het binnenste MERGEFIELD ontving inderdaad gegevens.
        doc.save("Your Directory Path" + "WorkingWithFields.MailMergeAndConditionalField.docx");
    }
    @Test
    public void mailMergeImageFromBlob() throws Exception
    {
        Document doc = new Document("Your Directory Path" + "Mail merge destination - Northwind employees.docx");
        doc.getMailMerge().setFieldMergingCallback(new HandleMergeImageFieldFromBlob());
        Class.forName("net.ucanaccess.jdbc.UcanaccessDriver");
        String connString = "jdbc:ucanaccess://" + getDatabaseDir() + "Noordenwind.mdb";
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
            // Niets doen.
        }
        /// <samenvatting>
        /// Dit wordt aangeroepen wanneer de mail merge-engine het samenvoegveld Image:XXX in het document tegenkomt.
        /// U heeft de kans om een afbeeldingsobject, bestandsnaam of een stream terug te sturen die de afbeelding bevat.
        ///</samenvatting>
        public void /*IFieldMergingCallback.*/imageFieldMerging(ImageFieldMergingArgs e) throws Exception
        {
            // De veldwaarde is een byte-array, cast deze gewoon en maak er een stream op.
            ByteArrayInputStream imageStream = new ByteArrayInputStream((byte[]) e.getFieldValue());
            // Nu haalt de mail merge-engine de afbeelding uit de stream.
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
        /// <samenvatting>
        /// Opgeroepen voor elk samenvoegveld dat in het document voorkomt.
        /// We kunnen bepaalde gegevens terugsturen naar de mail merge-engine of iets anders met het document doen.
        /// In dit geval wijzigen we de celopmaak.
        ///</samenvatting>
        public void /*IFieldMergingCallback.*/fieldMerging(FieldMergingArgs e)
        {
            if (mBuilder == null)
                mBuilder = new DocumentBuilder(e.getDocument());
            if ("CompanyName".equals(e.getFieldName()))
            {
                // Selecteer de kleur afhankelijk van of het rijnummer even of oneven is.
                Color rowColor = isOdd(mRowIdx) 
                    ? new Color((213), (227), (235)) 
                    : new Color((242), (242), (242));
                //Er is momenteel geen manier om celeigenschappen voor de hele rij in te stellen, dus moeten we alle cellen in de rij herhalen.
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
            // Niets doen.
        }
        private DocumentBuilder mBuilder;
        private int mRowIdx;
    }
    /// <samenvatting>
    /// Geeft waar terug als de waarde oneven is; false als de waarde even is.
    ///</samenvatting>
    private static boolean isOdd(int value)
    {
        return (value / 2 * 2) == value;
    }
    /// <samenvatting>
    /// Maak een DataTable en vul deze met gegevens.
    /// In het echte leven zou deze DataTable gevuld moeten worden vanuit een database.
    ///</samenvatting>
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

## 6. Conclusie

Gefeliciteerd! U hebt geleerd hoe u velden in Aspose.Words voor Java kunt gebruiken om Word-documenten dynamisch te manipuleren. Deze krachtige API geeft u volledige controle over uw documenten, waardoor het een waardevol bezit is voor Java-ontwikkelaars.

## 7.Veelgestelde vragen

### V1: Waar kan ik Aspose.Words voor Java downloaden?
 U kunt Aspose.Words voor Java downloaden van[hier](https://releases.aspose.com/words/java/).

### V2: Hoe kan ik een tijdelijke licentie krijgen voor Aspose.Words voor Java?
 Een tijdelijke licentie kunt u verkrijgen bij[hier](https://purchase.aspose.com/temporary-license/).

### V3: Waar kan ik ondersteuning krijgen voor Aspose.Words voor Java?
 Voor ondersteuning kunt u het Aspose.Words-forum bezoeken[hier](https://forum.aspose.com/).

### V4: Is Aspose.Words voor Java geschikt voor het verwerken van HTML-inhoud in Word-documenten?
Ja, Aspose.Words voor Java biedt uitstekende ondersteuning voor het verwerken van HTML-inhoud in Word-documenten.

### V5: Kan ik Aspose.Words voor Java gratis gebruiken?
 Aspose.Words voor Java is een commercieel product, maar u kunt de functies ervan verkennen met een gratis proefversie[hier](https://releases.aspose.com/).

Ga vandaag nog aan de slag met Aspose.Words voor Java en beheer uw Word-documenten als nooit tevoren!

