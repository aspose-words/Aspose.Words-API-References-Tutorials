---
title: Aspose.Words for Java'da DocumentBuilder kullanarak İçerik Ekleme
linktitle: DocumentBuilder Kullanarak İçerik Ekleme
second_title: Aspose.Words Java Belge İşleme API'si
description: Aspose.Words for Java ile Belge Oluşturmada Ustalaşın. Metin, Tablo, Resim ve Daha Fazlasını Eklemeye Yönelik Adım Adım Kılavuz. Zahmetsizce Çarpıcı Word Belgeleri Oluşturun.
type: docs
weight: 26
url: /tr/java/document-manipulation/adding-content-using-documentbuilder/
---

## Aspose.Words for Java'da DocumentBuilder Kullanarak İçerik Eklemeye Giriş

Bu adım adım kılavuzda, bir Word belgesine çeşitli içerik türlerini eklemek için Aspose.Words for Java'nın DocumentBuilder'ının nasıl kullanılacağını keşfedeceğiz. Metin, tablolar, yatay kurallar, form alanları, HTML, köprüler, içindekiler tablosu, satır içi ve kayan resimler, paragraflar ve daha fazlasını eklemeyi ele alacağız. Başlayalım!

## Önkoşullar

 Başlamadan önce projenizde Aspose.Words for Java kütüphanesinin kurulu olduğundan emin olun. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/words/java/).

## Metin Ekleme

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Basit bir metin paragrafı ekleme
builder.write("This is a simple text paragraph.");

// Belgeyi kaydet
doc.save("path/to/your/document.docx");
```

## Tablo Ekleme

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Bir tablo başlat
Table table = builder.startTable();

// Hücre ve içerik ekleme
builder.insertCell();
builder.write("Cell 1");

builder.insertCell();
builder.write("Cell 2");

// Masayı sonlandır
builder.endTable();

// Belgeyi kaydet
doc.save("path/to/your/document.docx");
```

## Yatay Cetvel Ekleme

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Yatay kural ekleme
builder.insertHorizontalRule();

// Belgeyi kaydet
doc.save("path/to/your/document.docx");
```

## Form Alanları Ekleme

### Metin Giriş Formu Alanı

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Metin girişi formu alanı ekleme
builder.insertTextInput("TextInput", TextFormFieldType.REGULAR, "", "Default text", 0);

// Belgeyi kaydet
doc.save("path/to/your/document.docx");
```

### Onay Kutusu Form Alanı

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Onay kutusu form alanı ekleme
builder.insertCheckBox("CheckBox", true, true, 0);

// Belgeyi kaydet
doc.save("path/to/your/document.docx");
```

### Açılan Kutu Form Alanı

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Birleşik giriş kutusu için öğeleri tanımlama
String[] items = { "Option 1", "Option 2", "Option 3" };

// Birleşik giriş kutusu form alanı ekleme
builder.insertComboBox("DropDown", items, 0);

// Belgeyi kaydet
doc.save("path/to/your/document.docx");
```

## HTML ekleme

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// HTML içeriği ekle
builder.insertHtml("<p>This is an HTML paragraph.</p>");

// Belgeyi kaydet
doc.save("path/to/your/document.docx");
```

## Köprü Ekleme

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Köprü ekleme
builder.write("Visit ");
builder.getFont().setColor(Color.BLUE);
builder.getFont().setUnderline(Underline.SINGLE);
builder.insertHyperlink("Aspose Website", "http://www.aspose.com", false);
builder.getFont().clearFormatting();
builder.write(" for more information.");

// Belgeyi kaydet
doc.save("path/to/your/document.docx");
```

## İçindekiler Tablosu Ekleme

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// İçindekiler tablosu ekleme
builder.insertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// Belge içeriği ekle
// ...

// İçindekiler tablosunu güncelleyin
doc.updateFields();

// Belgeyi kaydet
doc.save("path/to/your/document.docx");
```

## Resim Ekleme

### Satır İçi Resim

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Satır içi resim ekleme
builder.insertImage("path/to/your/image.png");

// Belgeyi kaydet
doc.save("path/to/your/document.docx");
```

### Kayan Resim

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Kayan bir resim ekleyin
builder.insertImage("path/to/your/image.png", RelativeHorizontalPosition.MARGIN, 100.0, RelativeVerticalPosition.MARGIN, 100.0, 200.0, 100.0, WrapType.SQUARE);

// Belgeyi kaydet
doc.save("path/to/your/document.docx");
```

## Paragraf Ekleme

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Paragraf biçimlendirmesini ayarlama
Font font = builder.getFont();
font.setSize(16.0);
font.setBold(true);
font.setColor(Color.BLUE);
font.setName("Arial");
font.setUnderline(Underline.DASH);

ParagraphFormat paragraphFormat = builder.getParagraphFormat();
paragraphFormat.setFirstLineIndent(8.0);
paragraphFormat.setAlignment(ParagraphAlignment.JUSTIFY);
paragraphFormat.setKeepTogether(true);

// Paragraf ekle
builder.writeln("This is a formatted paragraph.");

// Belgeyi kaydet
doc.save("path/to/your/document.docx");
```

## Adım 10: İmleci Hareket Ettirme

 Aşağıdaki gibi çeşitli yöntemleri kullanarak belge içindeki imleç konumunu kontrol edebilirsiniz:`moveToParagraph`, `moveToCell`ve dahası. İşte bir örnek:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// İmleci belirli bir paragrafa taşıma
builder.moveToParagraph(2, 0);

// Yeni imleç konumuna içerik ekleyin
builder.writeln("This is the 3rd paragraph.");
```

Bunlar Aspose.Words for Java'nın DocumentBuilder'ını kullanarak gerçekleştirebileceğiniz bazı genel işlemlerdir. Daha gelişmiş özellikler ve özelleştirme seçenekleri için kitaplığın belgelerini inceleyin. Mutlu belge oluşturma!


## Çözüm

Bu kapsamlı kılavuzda Aspose.Words for Java DocumentBuilder'ın Word belgelerine çeşitli içerik türleri ekleme yeteneklerini araştırdık. Metni, tabloları, yatay kuralları, form alanlarını, HTML'yi, köprüleri, içindekiler tablosunu, resimleri, paragrafları ve imleç hareketini ele aldık.

## SSS'ler

### S: Aspose.Words for Java nedir?

C: Aspose.Words for Java, geliştiricilerin Microsoft Word belgelerini programlı olarak oluşturmasına, değiştirmesine ve işlemesine olanak tanıyan bir Java kitaplığıdır. Belge oluşturma, biçimlendirme ve içerik ekleme için geniş bir özellik yelpazesi sunar.

### S: Belgeme nasıl içindekiler tablosu ekleyebilirim?

C: İçindekiler tablosu eklemek için`DocumentBuilder` Belgenize bir içindekiler tablosu alanı eklemek için. İçindekiler tablosunu doldurmak için içerik ekledikten sonra belgedeki alanları güncellediğinizden emin olun. İşte bir örnek:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// İçindekiler alanı ekleme
builder.insertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// Belge içeriği ekle
// ...

// İçindekiler tablosunu güncelleyin
doc.updateFields();
```

### S: Aspose.Words for Java kullanarak bir belgeye nasıl resim eklerim?

 C: Hem satır içi hem de kayan görüntüleri,`DocumentBuilder`. İşte her ikisinin örnekleri:

#### Satır İçi Resim:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Satır içi resim ekleme
builder.insertImage("path/to/your/image.png");
```

#### Yüzen Resim:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Kayan bir resim ekleyin
builder.insertImage("path/to/your/image.png", RelativeHorizontalPosition.MARGIN, 100.0, RelativeVerticalPosition.MARGIN, 100.0, 200.0, 100.0, WrapType.SQUARE);
```

### S: İçerik eklerken metni ve paragrafları biçimlendirebilir miyim?

 C: Evet, metni ve paragrafları aşağıdaki düğmeyi kullanarak biçimlendirebilirsiniz:`DocumentBuilder`. Yazı tipi özelliklerini, paragraf hizalamasını, girintiyi ve daha fazlasını ayarlayabilirsiniz. İşte bir örnek:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Yazı tipi ve paragraf biçimlendirmesini ayarlama
Font font = builder.getFont();
font.setSize(16.0);
font.setBold(true);
font.setColor(Color.BLUE);
font.setName("Arial");
font.setUnderline(Underline.DASH);

ParagraphFormat paragraphFormat = builder.getParagraphFormat();
paragraphFormat.setFirstLineIndent(8.0);
paragraphFormat.setAlignment(ParagraphAlignment.JUSTIFY);
paragraphFormat.setKeepTogether(true);

// Biçimlendirilmiş bir paragraf ekleme
builder.writeln("This is a formatted paragraph.");
```

### S: İmleci belge içinde belirli bir konuma nasıl taşıyabilirim?

 C: Aşağıdaki yöntemleri kullanarak imleç konumunu kontrol edebilirsiniz:`moveToParagraph`, `moveToCell`ve dahası. İşte bir örnek:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// İmleci belirli bir paragrafa taşıma
builder.moveToParagraph(2, 0);

// Yeni imleç konumuna içerik ekleyin
builder.writeln("This is the 3rd paragraph.");
```

Bunlar Aspose.Words for Java'nın DocumentBuilder'ını kullanmaya başlamanıza yardımcı olacak bazı genel sorular ve yanıtlardır. Başka sorularınız varsa veya daha fazla yardıma ihtiyacınız varsa, bkz.[kütüphane dokümantasyonu](https://reference.aspose.com/words/java/) veya Aspose.Words topluluğundan ve destek kaynaklarından yardım isteyin.