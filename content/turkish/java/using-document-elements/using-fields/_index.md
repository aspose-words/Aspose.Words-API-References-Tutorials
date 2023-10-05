---
title: Aspose.Words for Java'da Alanları Kullanma
linktitle: Alanları Kullanma
second_title: Aspose.Words Java Belge İşleme API'si
description: Bu adım adım eğitimde Aspose.Words for Java alanlarını etkili bir şekilde kullanmayı öğrenin. Kolaylıkla dinamik Word belgeleri oluşturun.
type: docs
weight: 11
url: /tr/java/using-document-elements/using-fields/
---

Bu adım adım eğitimde, belgeleri kolaylıkla işlemek için Aspose.Words for Java'daki alanların nasıl kullanılacağı konusunda size rehberlik edeceğiz. Aspose.Words for Java, Word belgeleriyle programlı olarak çalışmanıza olanak tanıyan, içerikleri ve formatları üzerinde tam kontrol sahibi olmanızı sağlayan güçlü bir API'dir.

## 1. Giriş

Aspose.Words for Java, Java uygulamalarında Word belgeleriyle ilgilenen herkes için önemli bir araçtır. Alanlar, dinamik verileri belgenizde saklayabilen yer tutuculardır. Bu eğitim size alanlarla etkili bir şekilde nasıl çalışacağınızı gösterecektir.

## 2. Ortamınızı Kurmak

 Başlamadan önce Aspose.Words for Java'nın kurulu olduğundan emin olun. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/words/java/). Ayrıca sisteminizde Java'nın ve Eclipse veya IntelliJ IDEA gibi bir entegre geliştirme ortamının (IDE) kurulu olduğundan emin olun.

## 3. Word Belgesi Yükleme

Java uygulamanızda çalışmak istediğiniz Word belgesini yüklemeniz gerekmektedir. İşte başlamanıza yardımcı olacak bir kod pasajı:

```java
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
Document doc = new Document(dataDir + "Mail merge destinations - Fax.docx");
```

 Yer değiştirmek`"Your Document Directory"` Ve`"Your Output Directory"` uygun yollar ile.

## 4. Adres Mektup Birleştirmeyi Özelleştirme

Aspose.Words for Java, adres-mektup birleştirme işlemleri için mükemmel destek sağlar. Bir adres-mektup birleştirme olay işleyicisi ayarlayarak adres-mektup birleştirme işlemini özelleştirebilirsiniz. Bunu nasıl yapacağınız aşağıda açıklanmıştır:

```java
// Özel işi yapmak için adres-mektup birleştirme olay işleyicisini kurun.
doc.getMailMerge().setFieldMergingCallback(new HandleMergeField());

// Sondaki ve baştaki boşlukların adres-mektup birleştirme değerlerini kırpın.
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

## 5. Belgeyi Kaydetmek

Belgenizi özelleştirdikten sonra aşağıdaki kodu kullanarak kaydedebilirsiniz:

```java
doc.save(outPath + "WorkingWithFields.MailMergeFormFields.docx");
```

 Yer değiştirmek`"Your Output Directory"` İstenilen çıkış yolu ile.

## Kaynak Kodunu Tamamlayın
```java
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
Document doc = new Document(dataDir + "Mail merge destinations - Fax.docx");
// Özel işi yapmak için adres-mektup birleştirme olay işleyicisini kurun.
doc.getMailMerge().setFieldMergingCallback(new HandleMergeField());
// Sondaki ve baştaki boşlukların adres-mektup birleştirme değerlerini kırpın.
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
HandleMergeField Sınıfının kaynak kodu

```java
    private static class HandleMergeField implements IFieldMergingCallback
    {
        /// <özet>
        /// Bu işleyici, belgede bulunan her adres-mektup birleştirme alanı için çağrılır,
        /// veri kaynağında bulunan her kayıt için.
        /// </özet>
        public void /*IFieldMergingCallback.*/fieldMerging(FieldMergingArgs e) throws Exception
        {
            if (mBuilder == null)
                mBuilder = new DocumentBuilder(e.getDocument());
            // Tüm boole değerlerinin onay kutusu form alanları olarak çıktılanmasını istediğimize karar verdik.
            if (e.getFieldValue() instanceof /*boolean*/Boolean)
            {
                // "İmleci" mevcut birleştirme alanına taşıyın.
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
            // Uygulama gerekli değildir.
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
        // IF alanının içine yerleştirilmiş bir MERGEFIELD ekleyin.
        // IF alanı ifadesi yanlış olduğundan iç MERGEFIELD'ın sonucu görüntülenmez,
        //ve MERGEFIELD, adres-mektup birleştirme sırasında herhangi bir veri almayacaktır.
        FieldIf fieldIf = (FieldIf)builder.insertField(" IF 1 = 2 ");
        builder.moveTo(fieldIf.getSeparator());
        builder.insertField(" MERGEFIELD  FullName ");
        // Bu bayrağı true olarak ayarlarsak, false-statement IF alanlarının içindeki MERGEFIELD'leri hâlâ sayabiliriz.
        doc.getMailMerge().setUnconditionalMergeFieldsAndRegions(true);
        DataTable dataTable = new DataTable();
        dataTable.getColumns().add("FullName");
        dataTable.getRows().add("James Bond");
        doc.getMailMerge().execute(dataTable);
        // IF alanı yanlış olduğundan sonuç belgede görünmeyecektir,
        // ancak iç MERGEFIELD gerçekten de veri aldı.
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
            // Hiçbir şey yapma.
        }
        /// <özet>
        /// Bu, adres-mektup birleştirme motoru belgede Resim:XXX birleştirme alanıyla karşılaştığında çağrılır.
        /// Bir Görüntü nesnesini, dosya adını veya görüntüyü içeren bir akışı döndürme şansınız vardır.
        /// </özet>
        public void /*IFieldMergingCallback.*/imageFieldMerging(ImageFieldMergingArgs e) throws Exception
        {
            // Alan değeri bir bayt dizisidir, onu yayınlayın ve üzerinde bir akış oluşturun.
            ByteArrayInputStream imageStream = new ByteArrayInputStream((byte[]) e.getFieldValue());
            // Artık adres-mektup birleştirme motoru görüntüyü akıştan alacaktır.
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
        /// <özet>
        /// Belgede karşılaşılan her birleştirme alanı için çağrılır.
        /// Bazı verileri adres-mektup birleştirme motoruna geri gönderebiliriz veya belgeyle başka bir şey yapabiliriz.
        /// Bu durumda hücre formatını değiştiriyoruz.
        /// </özet>
        public void /*IFieldMergingCallback.*/fieldMerging(FieldMergingArgs e)
        {
            if (mBuilder == null)
                mBuilder = new DocumentBuilder(e.getDocument());
            if ("CompanyName".equals(e.getFieldName()))
            {
                // Satır numarasının çift veya tek olmasına bağlı olarak rengi seçin.
                Color rowColor = isOdd(mRowIdx) 
                    ? new Color((213), (227), (235)) 
                    : new Color((242), (242), (242));
                //Şu anda satırın tamamı için hücre özelliklerini ayarlamanın bir yolu yok, bu nedenle satırdaki tüm hücreleri yinelememiz gerekiyor.
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
            // Hiçbir şey yapma.
        }
        private DocumentBuilder mBuilder;
        private int mRowIdx;
    }
    /// <özet>
    /// Değer tek ise true değerini döndürür; değer çift ise false.
    /// </özet>
    private static boolean isOdd(int value)
    {
        return (value / 2 * 2) == value;
    }
    /// <özet>
    /// DataTable'ı oluşturun ve verilerle doldurun.
    /// Gerçek hayatta bu DataTable bir veritabanından doldurulmalıdır.
    /// </özet>
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

## 6. Sonuç

Tebrikler! Word belgelerini dinamik olarak değiştirmek için Aspose.Words for Java'daki alanların nasıl kullanılacağını öğrendiniz. Bu güçlü API, belgeleriniz üzerinde tam kontrol sahibi olmanızı sağlar ve bu da onu Java geliştiricileri için değerli bir varlık haline getirir.

## 7. SSS

### S1: Aspose.Words for Java'yı nereden indirebilirim?
 Aspose.Words for Java'yı şu adresten indirebilirsiniz:[Burada](https://releases.aspose.com/words/java/).

### S2: Aspose.Words for Java için nasıl geçici lisans alabilirim?
 adresinden geçici lisans alabilirsiniz.[Burada](https://purchase.aspose.com/temporary-license/).

### S3: Aspose.Words for Java desteğini nereden alabilirim?
 Destek için Aspose.Words forumunu ziyaret edebilirsiniz.[Burada](https://forum.aspose.com/).

### S4: Aspose.Words for Java, Word belgelerindeki HTML içeriğini işlemeye uygun mudur?
Evet, Aspose.Words for Java, Word belgelerindeki HTML içeriğinin işlenmesi için mükemmel destek sağlar.

### S5: Aspose.Words for Java'yı ücretsiz kullanabilir miyim?
 Aspose.Words for Java ticari bir üründür, ancak özelliklerini mevcut ücretsiz deneme sürümüyle keşfedebilirsiniz[Burada](https://releases.aspose.com/).

Aspose.Words for Java'yı bugün kullanmaya başlayın ve Word belgelerinizin kontrolünü daha önce hiç olmadığı şekilde elinize alın!

