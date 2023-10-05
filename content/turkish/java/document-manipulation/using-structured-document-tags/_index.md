---
title: Aspose.Words for Java'da Yapılandırılmış Belge Etiketlerini (SDT) Kullanmak
linktitle: Yapılandırılmış Belge Etiketlerini (SDT) Kullanma
second_title: Aspose.Words Java Belge İşleme API'si
description: Bu kapsamlı kılavuzla Aspose.Words for Java'da Yapılandırılmış Belge Etiketlerini (SDT) nasıl kullanacağınızı öğrenin. SDT'leri özel XML verilerine oluşturun, değiştirin ve bağlayın.
type: docs
weight: 19
url: /tr/java/document-manipulation/using-structured-document-tags/
---

## Aspose.Words for Java'da Yapılandırılmış Belge Etiketlerini (SDT) Kullanmaya Giriş

Yapılandırılmış Belge Etiketleri (SDT), Aspose.Words for Java'nın belgelerinizde yapılandırılmış içerik oluşturmanıza ve değiştirmenize olanak tanıyan güçlü bir özelliğidir. Bu kapsamlı kılavuzda, Aspose.Words for Java'da SDT'leri kullanmanın çeşitli yönlerini size anlatacağız. İster yeni başlayan ister deneyimli bir geliştirici olun, bu makalede değerli bilgiler ve pratik örnekler bulacaksınız.

## Başlarken

Ayrıntılara dalmadan önce ortamımızı kuralım ve temel bir SDT oluşturalım. Bu bölümde aşağıdaki konuları ele alacağız:

- Yeni bir belge oluşturma
- Yapılandırılmış Belge Etiketi Ekleme
- Belgeyi kaydetme

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// CHECKBOX türünde bir Yapılandırılmış Belge Etiketi oluşturun
StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.CHECKBOX, MarkupLevel.INLINE);
builder.insertNode(sdtCheckBox);

// Belgeyi kaydet
doc.save("WorkingWithSDT.docx");
```

## Onay Kutusu SDT'sinin Mevcut Durumunu Kontrol Etme

Belgenize bir onay kutusu SDT'si ekledikten sonra, mevcut durumunu programlı olarak kontrol etmek isteyebilirsiniz. Bu, kullanıcı girişini doğrulamanız veya onay kutusu durumuna göre belirli eylemleri gerçekleştirmeniz gerektiğinde yararlı olabilir.

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtCheckBox = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

if (sdtCheckBox.getSdtType() == SdtType.CHECKBOX) {
    // Onay kutusu işaretlendi
    sdtCheckBox.setChecked(true);
}

doc.save("UpdatedDocument.docx");
```

## İçerik Kontrollerini Değiştirme

Bu bölümde belgenizdeki içerik kontrollerini nasıl değiştireceğinizi inceleyeceğiz. Üç tür içerik kontrolünü ele alacağız: Düz Metin, Açılır Liste ve Resim.

### Düz Metin İçerik Denetimini Değiştirme

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtPlainText = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

if (sdtPlainText.getSdtType() == SdtType.PLAIN_TEXT) {
    // Mevcut içeriği temizle
    sdtPlainText.removeAllChildren();

    // Yeni metin ekle
    Paragraph para = (Paragraph) sdtPlainText.appendChild(new Paragraph(doc));
    Run run = new Run(doc, "New text goes here");
    para.appendChild(run);
}

doc.save("ModifiedDocument.docx");
```

### Açılır Liste İçerik Denetimini Değiştirme

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtDropDown = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

if (sdtDropDown.getSdtType() == SdtType.DROP_DOWN_LIST) {
    // Listeden ikinci öğeyi seçin
    SdtListItem secondItem = sdtDropDown.getListItems().get(2);
    sdtDropDown.getListItems().setSelectedValue(secondItem);
}

doc.save("ModifiedDocument.docx");
```

### Resim İçeriği Kontrolünü Değiştirme

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtPicture = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);
Shape shape = (Shape) sdtPicture.getChild(NodeType.SHAPE, 0, true);

if (shape.hasImage()) {
    // Resmi yenisiyle değiştirin
    shape.getImageData().setImage("Watermark.png");
}

doc.save("ModifiedDocument.docx");
```

## ComboBox İçerik Denetimi Oluşturma

ComboBox İçerik Kontrolü, kullanıcıların önceden tanımlanmış seçenekler listesinden seçim yapmasına olanak tanır. Belgemizde bir tane oluşturalım.

```java
Document doc = new Document();
StructuredDocumentTag sdtComboBox = new StructuredDocumentTag(doc, SdtType.COMBO_BOX, MarkupLevel.BLOCK);
sdtComboBox.getListItems().add(new SdtListItem("Choose an item", "-1"));
sdtComboBox.getListItems().add(new SdtListItem("Item 1", "1"));
sdtComboBox.getListItems().add(new SdtListItem("Item 2", "2"));
doc.getFirstSection().getBody().appendChild(sdtComboBox);

doc.save("ComboBoxDocument.docx");
```

## Zengin Metin İçeriği Denetimi ile Çalışma

Zengin Metin İçeriği Kontrolleri, belgelerinize biçimlendirilmiş metin eklemek için mükemmeldir. Bir tane oluşturalım ve içeriğini ayarlayalım.

```java
Document doc = new Document();
StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RICH_TEXT, MarkupLevel.BLOCK);
Paragraph para = new Paragraph(doc);
Run run = new Run(doc);
run.setText("Hello World");
run.getFont().setColor(Color.GREEN);
para.getRuns().add(run);
sdtRichText.getChildNodes().add(para);
doc.getFirstSection().getBody().appendChild(sdtRichText);

doc.save("RichTextDocument.docx");
```

## İçerik Kontrol Stillerini Ayarlama

Belgenizin görsel görünümünü geliştirmek için içerik kontrollerine stiller uygulayabilirsiniz. İçerik kontrolünün stilinin nasıl ayarlanacağını görelim.

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

//Özel bir stil uygulama
Style style = doc.getStyles().getByStyleIdentifier(StyleIdentifier.QUOTE);
sdt.setStyle(style);

doc.save("StyledDocument.docx");
```

## Bir SDT'yi Özel XML Verilerine Bağlama

Bazı senaryolarda dinamik içerik oluşturmak için bir SDT'yi özel XML verilerine bağlamanız gerekebilir. Bunu nasıl başaracağımızı keşfedelim.

```java
Document doc = new Document();
CustomXmlPart xmlPart = doc.getCustomXmlParts().add(UUID.randomUUID().toString(), "<root><text>Hello, World!</text></root>");
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PLAIN_TEXT, MarkupLevel.BLOCK);
doc.getFirstSection().getBody().appendChild(sdt);
sdt.getXmlMapping().setMapping(xmlPart, "/root[1]/text[1]", "");

doc.save("CustomXMLBinding.docx");
```

## Özel XML Verilerine Eşlenen Yinelenen Bölümlere Sahip Bir Tablo Oluşturma

Tekrarlanan bölümlere sahip tablolar, yapılandırılmış verileri sunmak için son derece yararlı olabilir. Böyle bir tablo oluşturalım ve onu özel XML verileriyle eşleştirelim.

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
CustomXmlPart xmlPart = doc.getCustomXmlParts().add("Books", "<books>...</books>");
Table table = builder.startTable();
builder.insertCell();
builder.write("Title");
builder.insertCell();
builder.write("Author");
builder.endRow();
builder.endTable();

StructuredDocumentTag repeatingSectionSdt = new StructuredDocumentTag(doc, SdtType.REPEATING_SECTION, MarkupLevel.ROW);
repeatingSectionSdt.getXmlMapping().setMapping(xmlPart, "/books[1]/book", "");
table.appendChild(repeatingSectionSdt);

StructuredDocumentTag repeatingSectionItemSdt = new StructuredDocumentTag(doc, SdtType.REPEATING_SECTION_ITEM, MarkupLevel.ROW);
repeatingSectionSdt.appendChild(repeatingSectionItemSdt);

Row row = new Row(doc);
repeatingSectionItemSdt.appendChild(row);

StructuredDocumentTag titleSdt = new StructuredDocumentTag(doc, SdtType.PLAIN_TEXT, MarkupLevel.CELL);
titleSdt.getXmlMapping().setMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
row.appendChild(titleSdt);

StructuredDocumentTag authorSdt = new StructuredDocumentTag(doc, SdtType.PLAIN_TEXT, MarkupLevel.CELL);
authorSdt.getXmlMapping().setMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
row.appendChild(authorSdt);

doc.save("RepeatingTableDocument.docx");
```

## Çok Bölümlü Yapılandırılmış Belge Etiketleriyle Çalışma

Yapılandırılmış Belge Etiketleri bir belgedeki birden çok bölüme yayılabilir. Bu bölümde çok bölümlü SDT'lerle nasıl çalışılacağını inceleyeceğiz.

```java
Document doc = new Document("MultiSectionDocument.docx");
NodeCollection tags = doc.getChildNodes(NodeType.STRUCTURED_DOCUMENT_TAG_RANGE_START, true);

for (StructuredDocumentTagRangeStart tag : tags) {
    System.out.println(tag.getTitle());
}

doc.save("ModifiedMultiSectionDocument.docx");
```

## Çözüm

Aspose.Words for Java'daki Yapılandırılmış Belge Etiketleri, belgelerinizdeki içeriği yönetmenin ve biçimlendirmenin çok yönlü bir yolunu sunar. Şablonlar, formlar veya dinamik belgeler oluşturmanız gerekiyorsa SDT'ler ihtiyacınız olan esnekliği ve kontrolü sunar. Bu makalede verilen örnekleri ve yönergeleri izleyerek belge işleme görevlerinizi geliştirmek için SDT'lerin gücünden yararlanabilirsiniz.

## SSS'ler

### Yapılandırılmış Belge Etiketlerinin (SDT'ler) amacı nedir?

Yapılandırılmış Belge Etiketleri (SDT'ler), belgeler içindeki içeriği düzenleme ve biçimlendirme amacına hizmet ederek şablonlar, formlar ve yapılandırılmış belgeler oluşturmayı kolaylaştırır.

### Checkbox SDT'nin mevcut durumunu nasıl kontrol edebilirim?

 Checkbox SDT'nin geçerli durumunu aşağıdaki komutu kullanarak kontrol edebilirsiniz:`setChecked` Makalede gösterildiği gibi yöntem.

### İçerik Kontrollerine stiller uygulayabilir miyim?

Evet, belgedeki görünümlerini özelleştirmek için İçerik Kontrollerine stiller uygulayabilirsiniz.

### Bir SDT'yi özel XML verilerine bağlamak mümkün mü?

Evet, bir SDT'yi özel XML verilerine bağlayarak dinamik içerik oluşturmaya ve veri eşlemeye olanak tanıyabilirsiniz.

### SDT'lerde Tekrarlanan Bölümler Nelerdir?

SDT'lerdeki Tekrarlanan Bölümler, satırların eşlenen XML verilerine göre tekrarlanabileceği dinamik verilere sahip tablolar oluşturmanıza olanak tanır.