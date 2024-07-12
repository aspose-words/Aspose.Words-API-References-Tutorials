---
title: Utilizzo dei campi in Aspose.Words per Java
linktitle: Utilizzo dei campi
second_title: API di elaborazione dei documenti Java Aspose.Words
description: Impara a utilizzare i campi Aspose.Words per Java in modo efficace in questo tutorial passo passo. Crea facilmente documenti Word dinamici.
type: docs
weight: 11
url: /it/java/using-document-elements/using-fields/
---

In questo tutorial passo passo, ti guideremo su come utilizzare i campi in Aspose.Words per Java per manipolare facilmente i documenti. Aspose.Words per Java è una potente API che ti consente di lavorare con documenti Word a livello di codice, dandoti il pieno controllo sul loro contenuto e formattazione.

## 1. Introduzione

Aspose.Words per Java è uno strumento essenziale per chiunque abbia a che fare con documenti Word in applicazioni Java. I campi sono segnaposto che possono memorizzare dati dinamici nel documento. Questo tutorial ti mostrerà come lavorare con i campi in modo efficace.

## 2. Configurazione dell'ambiente

 Prima di iniziare, assicurati di avere Aspose.Words per Java installato. Puoi scaricarlo da[Qui](https://releases.aspose.com/words/java/). Inoltre, assicurati di avere Java e un ambiente di sviluppo integrato (IDE) come Eclipse o IntelliJ IDEA installati sul tuo sistema.

## 3. Caricamento di un documento Word

Nella tua applicazione Java, devi caricare il documento Word con cui vuoi lavorare. Ecco uno snippet di codice per iniziare:

```java
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
Document doc = new Document(dataDir + "Mail merge destinations - Fax.docx");
```

 Sostituire`"Your Document Directory"`E`"Your Output Directory"` con gli appositi percorsi.

## 4. Personalizzazione della stampa unione

Aspose.Words per Java fornisce un eccellente supporto per le operazioni di stampa unione. È possibile personalizzare il processo di stampa unione impostando un gestore eventi di stampa unione. Ecco come farlo:

```java
// Configura il gestore eventi di stampa unione per eseguire il lavoro personalizzato.
doc.getMailMerge().setFieldMergingCallback(new HandleMergeField());

// Taglia i valori della stampa unione degli spazi bianchi finali e iniziali.
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

## 5. Salvataggio del documento

Dopo aver personalizzato il tuo documento, puoi salvarlo utilizzando il seguente codice:

```java
doc.save(outPath + "WorkingWithFields.MailMergeFormFields.docx");
```

 Sostituire`"Your Output Directory"` con il percorso di output desiderato.

## Codice sorgente completo
```java
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
Document doc = new Document(dataDir + "Mail merge destinations - Fax.docx");
// Configura il gestore eventi di stampa unione per eseguire il lavoro personalizzato.
doc.getMailMerge().setFieldMergingCallback(new HandleMergeField());
// Taglia i valori della stampa unione degli spazi bianchi finali e iniziali.
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
Codice sorgente della classe HandleMergeField

```java
    private static class HandleMergeField implements IFieldMergingCallback
    {
        /// <riepilogo>
        /// Questo gestore viene richiamato per ogni campo di stampa unione trovato nel documento,
        /// per ogni record trovato nell'origine dati.
        ///</summary>
        public void /*IFieldMergingCallback.*/fieldMerging(FieldMergingArgs e) throws Exception
        {
            if (mBuilder == null)
                mBuilder = new DocumentBuilder(e.getDocument());
            // Abbiamo deciso di volere che tutti i valori booleani vengano emessi come campi del modulo con casella di controllo.
            if (e.getFieldValue() instanceof /*boolean*/Boolean)
            {
                // Sposta il "cursore" sul campo di unione corrente.
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
            // L'implementazione non è richiesta.
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
        // Inserisci un MERGEFIELD nidificato all'interno di un campo IF.
        // Poiché l'istruzione del campo IF è falsa, il risultato del MERGEFIELD interno non verrà visualizzato,
        // il MERGEFIELD non riceverà alcun dato durante una stampa unione.
        FieldIf fieldIf = (FieldIf)builder.insertField(" IF 1 = 2 ");
        builder.moveTo(fieldIf.getSeparator());
        builder.insertField(" MERGEFIELD  FullName ");
        // Possiamo ancora contare MERGEFIELD all'interno dei campi IF con istruzioni false se impostiamo questo flag su true.
        doc.getMailMerge().setUnconditionalMergeFieldsAndRegions(true);
        DataTable dataTable = new DataTable();
        dataTable.getColumns().add("FullName");
        dataTable.getRows().add("James Bond");
        doc.getMailMerge().execute(dataTable);
        // Il risultato non sarà visibile nel documento perché il campo IF è falso,
        // ma il MERGEFIELD interno ha effettivamente ricevuto dati.
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
            // Fare niente.
        }
        /// <riepilogo>
        /// Viene chiamato quando il motore di stampa unione rileva il campo unione Immagine:XXX nel documento.
        /// Hai la possibilità di restituire un oggetto Immagine, un nome file o uno stream che contiene l'immagine.
        ///</summary>
        public void /*IFieldMergingCallback.*/imageFieldMerging(ImageFieldMergingArgs e) throws Exception
        {
            // Il valore del campo è un array di byte, basta lanciarlo e creare un flusso su di esso.
            ByteArrayInputStream imageStream = new ByteArrayInputStream((byte[]) e.getFieldValue());
            // Ora il motore di stampa unione recupererà l'immagine dal flusso.
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
        /// <riepilogo>
        /// Chiamato per ogni campo di unione riscontrato nel documento.
        /// Possiamo restituire alcuni dati al motore di stampa unione o fare qualcos'altro con il documento.
        /// In questo caso modifichiamo la formattazione della cella.
        ///</summary>
        public void /*IFieldMergingCallback.*/fieldMerging(FieldMergingArgs e)
        {
            if (mBuilder == null)
                mBuilder = new DocumentBuilder(e.getDocument());
            if ("CompanyName".equals(e.getFieldName()))
            {
                // Seleziona il colore a seconda che il numero della riga sia pari o dispari.
                Color rowColor = isOdd(mRowIdx) 
                    ? new Color((213), (227), (235)) 
                    : new Color((242), (242), (242));
                //Al momento non è possibile impostare le proprietà della cella per l'intera riga, quindi dobbiamo ripetere l'iterazione su tutte le celle della riga.
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
            // Fare niente.
        }
        private DocumentBuilder mBuilder;
        private int mRowIdx;
    }
    /// <riepilogo>
    /// Restituisce vero se il valore è dispari; false se il valore è pari.
    ///</summary>
    private static boolean isOdd(int value)
    {
        return (value / 2 * 2) == value;
    }
    /// <riepilogo>
    /// Crea DataTable e riempilo con i dati.
    /// Nella vita reale questo DataTable dovrebbe essere compilato da un database.
    ///</summary>
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

## 6. Conclusione

Congratulazioni! Hai imparato come utilizzare i campi in Aspose.Words per Java per manipolare dinamicamente i documenti di Word. Questa potente API ti offre il controllo completo sui tuoi documenti, rendendola una risorsa preziosa per gli sviluppatori Java.

## 7. Domande frequenti

### Q1: Dove posso scaricare Aspose.Words per Java?
 È possibile scaricare Aspose.Words per Java da[Qui](https://releases.aspose.com/words/java/).

### Q2: Come posso ottenere una licenza temporanea per Aspose.Words per Java?
 È possibile ottenere una licenza temporanea da[Qui](https://purchase.aspose.com/temporary-license/).

### Q3: Dove posso ottenere supporto per Aspose.Words per Java?
 Per supporto, puoi visitare il forum Aspose.Words[Qui](https://forum.aspose.com/).

### Q4: Aspose.Words per Java è adatto alla gestione del contenuto HTML nei documenti Word?
Sì, Aspose.Words per Java fornisce un eccellente supporto per la gestione del contenuto HTML nei documenti Word.

### Q5: Posso utilizzare Aspose.Words per Java gratuitamente?
 Aspose.Words per Java è un prodotto commerciale, ma puoi esplorare le sue funzionalità con una prova gratuita disponibile[Qui](https://releases.aspose.com/).

Inizia oggi con Aspose.Words per Java e prendi il controllo dei tuoi documenti Word come mai prima d'ora!

