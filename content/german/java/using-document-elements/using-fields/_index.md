---
title: Verwenden von Feldern in Aspose.Words für Java
linktitle: Verwenden von Feldern
second_title: Aspose.Words Java-Dokumentverarbeitungs-API
description: Erfahren Sie in diesem Schritt-für-Schritt-Tutorial, wie Sie Aspose.Words für Java-Felder effektiv nutzen. Erstellen Sie ganz einfach dynamische Word-Dokumente.
type: docs
weight: 11
url: /de/java/using-document-elements/using-fields/
---

In diesem Schritt-für-Schritt-Tutorial zeigen wir Ihnen, wie Sie Felder in Aspose.Words für Java verwenden, um Dokumente einfach zu bearbeiten. Aspose.Words für Java ist eine leistungsstarke API, die Ihnen die programmgesteuerte Arbeit mit Word-Dokumenten ermöglicht und Ihnen die volle Kontrolle über deren Inhalt und Formatierung gibt.

## 1. Einleitung

Aspose.Words für Java ist ein unverzichtbares Werkzeug für jeden, der mit Word-Dokumenten in Java-Anwendungen arbeitet. Felder sind Platzhalter, die dynamische Daten in Ihrem Dokument speichern können. Dieses Tutorial zeigt Ihnen, wie Sie effektiv mit Feldern arbeiten.

## 2. Einrichten Ihrer Umgebung

 Bevor Sie beginnen, stellen Sie sicher, dass Aspose.Words für Java installiert ist. Sie können es herunterladen unter[Hier](https://releases.aspose.com/words/java/). Stellen Sie außerdem sicher, dass auf Ihrem System Java und eine integrierte Entwicklungsumgebung (IDE) wie Eclipse oder IntelliJ IDEA installiert sind.

## 3. Laden eines Word-Dokuments

In Ihrer Java-Anwendung müssen Sie das Word-Dokument laden, mit dem Sie arbeiten möchten. Hier ist ein Codeausschnitt, um Ihnen den Einstieg zu erleichtern:

```java
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
Document doc = new Document(dataDir + "Mail merge destinations - Fax.docx");
```

 Ersetzen`"Your Document Directory"` Und`"Your Output Directory"` mit den entsprechenden Pfaden.

## 4. Anpassen des Seriendrucks

Aspose.Words für Java bietet hervorragende Unterstützung für Serienbriefvorgänge. Sie können den Serienbriefprozess anpassen, indem Sie einen Serienbrief-Ereignishandler einrichten. So geht's:

```java
// Richten Sie den Mail-Merge-Ereignishandler ein, um die benutzerdefinierten Arbeiten auszuführen.
doc.getMailMerge().setFieldMergingCallback(new HandleMergeField());

// Schneiden Sie nachgestellte und führende Leerzeichen bei Serienbriefwerten ab.
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

## 5. Speichern des Dokuments

Nachdem Sie Ihr Dokument angepasst haben, können Sie es mit dem folgenden Code speichern:

```java
doc.save(outPath + "WorkingWithFields.MailMergeFormFields.docx");
```

 Ersetzen`"Your Output Directory"` mit dem gewünschten Ausgabepfad.

## Vollständiger Quellcode
```java
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
Document doc = new Document(dataDir + "Mail merge destinations - Fax.docx");
// Richten Sie den Mail-Merge-Ereignishandler ein, um die benutzerdefinierten Arbeiten auszuführen.
doc.getMailMerge().setFieldMergingCallback(new HandleMergeField());
// Schneiden Sie nachgestellte und führende Leerzeichen bei Serienbriefwerten ab.
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
Quellcode der Klasse HandleMergeField

```java
    private static class HandleMergeField implements IFieldMergingCallback
    {
        /// <Zusammenfassung>
        /// Dieser Handler wird für jedes im Dokument gefundene Serienbrieffeld aufgerufen.
        /// für jeden in der Datenquelle gefundenen Datensatz.
        /// </summary>
        public void /*IFieldMergingCallback.*/fieldMerging(FieldMergingArgs e) throws Exception
        {
            if (mBuilder == null)
                mBuilder = new DocumentBuilder(e.getDocument());
            // Wir haben beschlossen, dass alle booleschen Werte als Kontrollkästchen-Formularfelder ausgegeben werden sollen.
            if (e.getFieldValue() instanceof /*boolean*/Boolean)
            {
                // Bewegen Sie den „Cursor“ zum aktuellen Zusammenführungsfeld.
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
            // Eine Umsetzung ist nicht erforderlich.
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
        // Fügen Sie ein MERGEFIELD ein, das in einem IF-Feld verschachtelt ist.
        // Da die IF-Feldanweisung falsch ist, wird das Ergebnis des inneren MERGEFIELD nicht angezeigt.
        //und das MERGEFIELD empfängt während eines Seriendrucks keine Daten.
        FieldIf fieldIf = (FieldIf)builder.insertField(" IF 1 = 2 ");
        builder.moveTo(fieldIf.getSeparator());
        builder.insertField(" MERGEFIELD  FullName ");
        // Wir können MERGEFIELDs immer noch in IF-Feldern mit falscher Aussage zählen, wenn wir dieses Flag auf true setzen.
        doc.getMailMerge().setUnconditionalMergeFieldsAndRegions(true);
        DataTable dataTable = new DataTable();
        dataTable.getColumns().add("FullName");
        dataTable.getRows().add("James Bond");
        doc.getMailMerge().execute(dataTable);
        // Das Ergebnis wird im Dokument nicht sichtbar sein, da das IF-Feld falsch ist.
        // aber das innere MERGEFIELD hat tatsächlich Daten empfangen.
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
            // Nichts tun.
        }
        /// <Zusammenfassung>
        /// Dies wird aufgerufen, wenn die Mail-Merge-Engine auf das Serienbrieffeld „Image:XXX“ im Dokument stößt.
        /// Sie haben die Möglichkeit, ein Bildobjekt, einen Dateinamen oder einen Stream zurückzugeben, der das Bild enthält.
        /// </summary>
        public void /*IFieldMergingCallback.*/imageFieldMerging(ImageFieldMergingArgs e) throws Exception
        {
            // Der Feldwert ist ein Byte-Array. Wandeln Sie ihn einfach um und erstellen Sie einen Stream darauf.
            ByteArrayInputStream imageStream = new ByteArrayInputStream((byte[]) e.getFieldValue());
            // Jetzt ruft die Mail-Merge-Engine das Bild aus dem Stream ab.
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
        /// <Zusammenfassung>
        /// Wird für jedes im Dokument gefundene Zusammenführungsfeld aufgerufen.
        /// Wir können entweder einige Daten an die Serienbrief-Engine zurückgeben oder etwas anderes mit dem Dokument tun.
        /// In diesem Fall ändern wir die Zellformatierung.
        /// </summary>
        public void /*IFieldMergingCallback.*/fieldMerging(FieldMergingArgs e)
        {
            if (mBuilder == null)
                mBuilder = new DocumentBuilder(e.getDocument());
            if ("CompanyName".equals(e.getFieldName()))
            {
                // Wählen Sie die Farbe abhängig davon, ob die Zeilennummer gerade oder ungerade ist.
                Color rowColor = isOdd(mRowIdx) 
                    ? new Color((213), (227), (235)) 
                    : new Color((242), (242), (242));
                //Im Moment gibt es keine Möglichkeit, Zelleigenschaften für die gesamte Zeile festzulegen, daher müssen wir über alle Zellen in der Zeile iterieren.
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
            // Nichts tun.
        }
        private DocumentBuilder mBuilder;
        private int mRowIdx;
    }
    /// <Zusammenfassung>
    /// Gibt true zurück, wenn der Wert ungerade ist; false, wenn der Wert gerade ist.
    /// </summary>
    private static boolean isOdd(int value)
    {
        return (value / 2 * 2) == value;
    }
    /// <Zusammenfassung>
    /// DataTable erstellen und mit Daten füllen.
    /// Im wirklichen Leben sollte diese Datentabelle aus einer Datenbank gefüllt werden.
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

## 6. Fazit

Glückwunsch! Sie haben gelernt, wie Sie Felder in Aspose.Words für Java verwenden, um Word-Dokumente dynamisch zu bearbeiten. Diese leistungsstarke API gibt Ihnen die vollständige Kontrolle über Ihre Dokumente und macht sie zu einem wertvollen Vorteil für Java-Entwickler.

## 7. FAQs

### F1: Wo kann ich Aspose.Words für Java herunterladen?
 Sie können Aspose.Words für Java herunterladen von[Hier](https://releases.aspose.com/words/java/).

### F2: Wie kann ich eine temporäre Lizenz für Aspose.Words für Java erhalten?
 Eine temporäre Lizenz erhalten Sie bei[Hier](https://purchase.aspose.com/temporary-license/).

### F3: Wo erhalte ich Unterstützung für Aspose.Words für Java?
 Für Unterstützung können Sie das Aspose.Words-Forum besuchen[Hier](https://forum.aspose.com/).

### F4: Ist Aspose.Words für Java für die Verarbeitung von HTML-Inhalten in Word-Dokumenten geeignet?
Ja, Aspose.Words für Java bietet hervorragende Unterstützung für die Verarbeitung von HTML-Inhalten in Word-Dokumenten.

### F5: Kann ich Aspose.Words für Java kostenlos nutzen?
 Aspose.Words für Java ist ein kommerzielles Produkt, aber Sie können seine Funktionen mit einer kostenlosen Testversion erkunden[Hier](https://releases.aspose.com/).

Beginnen Sie noch heute mit Aspose.Words für Java und übernehmen Sie die Kontrolle über Ihre Word-Dokumente wie nie zuvor!

