---
title: Korzystanie z pól w Aspose.Words dla Java
linktitle: Korzystanie z pól
second_title: Aspose.Words API przetwarzania dokumentów Java
description: Naucz się efektywnie korzystać z pól Aspose.Words for Java w tym samouczku krok po kroku. Z łatwością twórz dynamiczne dokumenty Word.
type: docs
weight: 11
url: /pl/java/using-document-elements/using-fields/
---

tym samouczku krok po kroku poprowadzimy Cię, jak używać pól w Aspose.Words dla Java do łatwego manipulowania dokumentami. Aspose.Words for Java to potężny interfejs API, który umożliwia programową pracę z dokumentami programu Word, zapewniając pełną kontrolę nad ich zawartością i formatowaniem.

## 1. Wstęp

Aspose.Words for Java jest niezbędnym narzędziem dla każdego, kto ma do czynienia z dokumentami Worda w aplikacjach Java. Pola to elementy zastępcze, w których można przechowywać dane dynamiczne w dokumencie. W tym samouczku dowiesz się, jak efektywnie pracować z polami.

## 2. Konfigurowanie środowiska

 Zanim zaczniesz, upewnij się, że masz zainstalowany Aspose.Words for Java. Można go pobrać z[Tutaj](https://releases.aspose.com/words/java/). Upewnij się także, że masz zainstalowaną w systemie Javę i zintegrowane środowisko programistyczne (IDE), takie jak Eclipse lub IntelliJ IDEA.

## 3. Ładowanie dokumentu Word

W aplikacji Java musisz załadować dokument Word, z którym chcesz pracować. Oto fragment kodu na początek:

```java
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
Document doc = new Document(dataDir + "Mail merge destinations - Fax.docx");
```

 Zastępować`"Your Document Directory"` I`"Your Output Directory"` z odpowiednimi ścieżkami.

## 4. Dostosowywanie korespondencji seryjnej

Aspose.Words dla Java zapewnia doskonałe wsparcie dla operacji korespondencji seryjnej. Proces korespondencji seryjnej można dostosować, konfigurując procedurę obsługi zdarzeń korespondencji seryjnej. Oto jak to zrobić:

```java
// Skonfiguruj procedurę obsługi zdarzeń korespondencji seryjnej, aby wykonać niestandardową pracę.
doc.getMailMerge().setFieldMergingCallback(new HandleMergeField());

// Przytnij końcowe i początkowe białe spacje wartości korespondencji seryjnej.
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

## 5. Zapisywanie dokumentu

Po dostosowaniu dokumentu możesz go zapisać, używając następującego kodu:

```java
doc.save(outPath + "WorkingWithFields.MailMergeFormFields.docx");
```

 Zastępować`"Your Output Directory"` z żądaną ścieżką wyjściową.

## Kompletny kod źródłowy
```java
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
Document doc = new Document(dataDir + "Mail merge destinations - Fax.docx");
// Skonfiguruj procedurę obsługi zdarzeń korespondencji seryjnej, aby wykonać niestandardową pracę.
doc.getMailMerge().setFieldMergingCallback(new HandleMergeField());
// Przytnij końcowe i początkowe białe spacje wartości korespondencji seryjnej.
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
Kod źródłowy klasy HandleMergeField

```java
    private static class HandleMergeField implements IFieldMergingCallback
    {
        /// <podsumowanie>
        /// Ta procedura obsługi jest wywoływana dla każdego pola korespondencji seryjnej znalezionego w dokumencie,
        /// dla każdego rekordu znalezionego w źródle danych.
        /// </podsumowanie>
        public void /*IFieldMergingCallback.*/fieldMerging(FieldMergingArgs e) throws Exception
        {
            if (mBuilder == null)
                mBuilder = new DocumentBuilder(e.getDocument());
            // Zdecydowaliśmy, że chcemy, aby wszystkie wartości logiczne były wyświetlane jako pola formularza wyboru.
            if (e.getFieldValue() instanceof /*boolean*/Boolean)
            {
                // Przesuń „kursor” do bieżącego pola scalania.
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
            // Wdrożenie nie jest wymagane.
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
        // Wstaw pole MERGEFIELD zagnieżdżone w polu JEŻELI.
        // Ponieważ instrukcja pola IF jest fałszywa, wynik wewnętrznego MERGEFIELD nie zostanie wyświetlony,
        // MERGEFIELD nie będzie otrzymywać żadnych danych podczas korespondencji seryjnej.
        FieldIf fieldIf = (FieldIf)builder.insertField(" IF 1 = 2 ");
        builder.moveTo(fieldIf.getSeparator());
        builder.insertField(" MERGEFIELD  FullName ");
        // Nadal możemy zliczać pola MERGEFIELD w polach IF zawierających fałszywe instrukcje, jeśli ustawimy tę flagę na wartość true.
        doc.getMailMerge().setUnconditionalMergeFieldsAndRegions(true);
        DataTable dataTable = new DataTable();
        dataTable.getColumns().add("FullName");
        dataTable.getRows().add("James Bond");
        doc.getMailMerge().execute(dataTable);
        // Wynik nie będzie widoczny w dokumencie, ponieważ pole JEŻELI jest fałszywe,
        // ale wewnętrzne MERGEFIELD rzeczywiście otrzymało dane.
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
            // Nic nie robić.
        }
        /// <podsumowanie>
        /// Nazywa się to, gdy silnik korespondencji seryjnej napotyka w dokumencie pole scalania Image:XXX.
        /// Masz szansę zwrócić obiekt Image, nazwę pliku lub strumień zawierający obraz.
        /// </podsumowanie>
        public void /*IFieldMergingCallback.*/imageFieldMerging(ImageFieldMergingArgs e) throws Exception
        {
            // Wartość pola jest tablicą bajtów, po prostu rzuć ją i utwórz na niej strumień.
            ByteArrayInputStream imageStream = new ByteArrayInputStream((byte[]) e.getFieldValue());
            // Teraz mechanizm korespondencji seryjnej pobierze obraz ze strumienia.
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
        /// <podsumowanie>
        /// Wywoływane dla każdego pola scalania napotkanego w dokumencie.
        /// Możemy zwrócić część danych do mechanizmu korespondencji seryjnej lub zrobić z dokumentem coś innego.
        /// W tym przypadku modyfikujemy formatowanie komórek.
        /// </podsumowanie>
        public void /*IFieldMergingCallback.*/fieldMerging(FieldMergingArgs e)
        {
            if (mBuilder == null)
                mBuilder = new DocumentBuilder(e.getDocument());
            if ("CompanyName".equals(e.getFieldName()))
            {
                // Wybierz kolor w zależności od tego, czy numer wiersza jest parzysty czy nieparzysty.
                Color rowColor = isOdd(mRowIdx) 
                    ? new Color((213), (227), (235)) 
                    : new Color((242), (242), (242));
                // tej chwili nie ma możliwości ustawienia właściwości komórki dla całego wiersza, więc musimy iterować po wszystkich komórkach w wierszu.
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
            // Nic nie robić.
        }
        private DocumentBuilder mBuilder;
        private int mRowIdx;
    }
    /// <podsumowanie>
    /// Zwraca wartość true, jeśli wartość jest nieparzysta; false, jeśli wartość jest parzysta.
    /// </podsumowanie>
    private static boolean isOdd(int value)
    {
        return (value / 2 * 2) == value;
    }
    /// <podsumowanie>
    /// Utwórz tabelę danych i wypełnij ją danymi.
    /// W prawdziwym życiu tę tabelę danych należy wypełnić z bazy danych.
    /// </podsumowanie>
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

## 6. Wniosek

Gratulacje! Nauczyłeś się, jak używać pól w Aspose.Words dla języka Java do dynamicznego manipulowania dokumentami programu Word. Ten potężny interfejs API zapewnia pełną kontrolę nad dokumentami, co czyni go cennym nabytkiem dla programistów Java.

## 7. Często zadawane pytania

### P1: Gdzie mogę pobrać Aspose.Words dla Java?
 Możesz pobrać Aspose.Words dla Java z[Tutaj](https://releases.aspose.com/words/java/).

### P2: Jak mogę uzyskać tymczasową licencję na Aspose.Words dla Java?
 Licencję tymczasową można uzyskać od[Tutaj](https://purchase.aspose.com/temporary-license/).

### P3: Gdzie mogę uzyskać pomoc dotyczącą Aspose.Words dla Java?
 Aby uzyskać pomoc, możesz odwiedzić forum Aspose.Words[Tutaj](https://forum.aspose.com/).

### P4: Czy Aspose.Words for Java nadaje się do obsługi zawartości HTML w dokumentach Word?
Tak, Aspose.Words for Java zapewnia doskonałe wsparcie w obsłudze zawartości HTML w dokumentach Word.

### P5: Czy mogę używać Aspose.Words dla Java za darmo?
 Aspose.Words for Java jest produktem komercyjnym, ale możesz poznać jego funkcje, korzystając z bezpłatnej wersji próbnej[Tutaj](https://releases.aspose.com/).

Zacznij korzystać z Aspose.Words dla Java już dziś i przejmij kontrolę nad swoimi dokumentami Word jak nigdy dotąd!

