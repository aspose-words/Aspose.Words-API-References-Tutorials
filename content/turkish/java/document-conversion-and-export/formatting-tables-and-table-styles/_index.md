---
title: Aspose.Words for Java'da Tabloları ve Tablo Stillerini Formatlama
linktitle: Tabloları ve Tablo Stillerini Biçimlendirme
second_title: Aspose.Words Java Belge İşleme API'si
description: Aspose.Words for Java'da tabloları nasıl formatlayacağınızı ve tablo stillerini nasıl uygulayacağınızı öğrenin. Etkili tablo biçimlendirmesi için kaynak kodlu adım adım kılavuzları keşfedin. Aspose.Words ile belge düzeninizi geliştirin.
type: docs
weight: 17
url: /tr/java/document-conversion-and-export/formatting-tables-and-table-styles/
---

## Aspose.Words for Java'da Tabloları Formatlamaya Giriş ve Tablo Stilleri

Tablolar, belgelerdeki bilgilerin yapılandırılmasında ve düzenlenmesinde çok önemli bir rol oynar. Aspose.Words for Java, belgelerinizin görsel çekiciliğini artırmak amacıyla tabloları biçimlendirmek ve tablo stillerini uygulamak için güçlü özellikler sağlar. Bu adım adım kılavuzda Aspose.Words for Java'yı kullanarak tabloları biçimlendirmenin ve tablo stillerini uygulamanın çeşitli yönlerini inceleyeceğiz.

## Önkoşullar

Ayrıntılara dalmadan önce Aspose.Words for Java kütüphanesinin projenize entegre olduğundan emin olun. Aspose web sitesinden indirebilirsiniz:[Aspose.Words for Java'yı indirin](https://releases.aspose.com/words/java/).

## Tablo ve Çevreleyen Metin Arasındaki Mesafeyi Alın

Başlamak için, bir tablo ile onu çevreleyen belgedeki metin arasındaki mesafenin nasıl alınacağını inceleyelim.

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
System.out.println("Distance Top: " + table.getDistanceTop());
System.out.println("Distance Bottom: " + table.getDistanceBottom());
System.out.println("Distance Right: " + table.getDistanceRight());
System.out.println("Distance Left: " + table.getDistanceLeft());
```

## Tabloya Anahat Kenarlığı Uygulama

Bu kodla bir tabloyu sayfanın ortasına hizalayabilir, mevcut sınırları temizleyebilir ve özel bir anahat kenarlığı ayarlayabilirsiniz:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setAlignment(TableAlignment.CENTER);
table.clearBorders();
table.setBorder(BorderType.LEFT, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setBorder(BorderType.RIGHT, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setBorder(BorderType.TOP, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setBorder(BorderType.BOTTOM, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setShading(TextureIndex.TEXTURE_SOLID, Color.lightGray, new Color(0, true));
```

## Kenarlıklı Bir Tablo Oluşturun

Bu kod parçacığı, bir tablonun nasıl oluşturulacağını ve hem tablo hem de hücreler için sınırların nasıl ayarlanacağını gösterir:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.clearBorders();
table.setBorders(LineStyle.SINGLE, 1.5, Color.GREEN);
```

## Satır Biçimlendirmesini Değiştir

Bir tablodaki belirli bir satırın formatını nasıl değiştireceğinizi öğrenin:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Row firstRow = table.getFirstRow();
firstRow.getRowFormat().getBorders().setLineStyle(LineStyle.NONE);
firstRow.getRowFormat().setHeightRule(HeightRule.AUTO);
firstRow.getRowFormat().setAllowBreakAcrossPages(true);
```

## Satır Biçimlendirmesini Uygula

Bu örnek, biçimlendirmenin bir tablodaki satırın tamamına nasıl uygulanacağını gösterir:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
builder.insertCell();
RowFormat rowFormat = builder.getRowFormat();
rowFormat.setHeight(100.0);
rowFormat.setHeightRule(HeightRule.EXACTLY);
table.setLeftPadding(30.0);
table.setRightPadding(30.0);
table.setTopPadding(30.0);
table.setBottomPadding(30.0);
builder.writeln("I'm a wonderfully formatted row.");
```

## Hücre Dolgusunu Ayarla

Bir tablodaki tek tek hücreler için dolgunun nasıl ayarlanacağını keşfedin:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.startTable();
builder.insertCell();
builder.getCellFormat().setPaddings(30.0, 50.0, 30.0, 50.0);
builder.writeln("I'm a wonderfully formatted cell.");
```

## Hücre Biçimlendirmesini Değiştir

Bir tablodaki belirli bir hücrenin formatını nasıl değiştireceğinizi keşfedin:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
firstCell.getCellFormat().setWidth(30.0);
firstCell.getCellFormat().setOrientation(TextOrientation.DOWNWARD);
firstCell.getCellFormat().getShading().setForegroundPatternColor(Color.GREEN);
```

## Tabloyu ve Hücreyi Farklı Kenarlıklarla Biçimlendirme

Bir tablodaki tek tek hücreler için farklı kenarlıkları nasıl ayarlayacağınızı öğrenin:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
// Tablo kenarlıklarını ayarlama
table.setBorders(LineStyle.SINGLE, 2.0, Color.BLACK);
// Tek tek hücreler için hücre gölgelendirmesini ayarlama
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.RED);
// Hücrelere içerik ekleme
builder.writeln("Cell #1");
builder.insertCell();
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.GREEN);
builder.writeln("Cell #2");
// Sonraki satır için hücre biçimlendirmesini temizle
builder.getCellFormat().clearFormatting();
// Bu satırın ilk hücresi için daha büyük kenarlıklar oluşturun
builder.getCellFormat().getBorders().getLeft().setLineWidth(4.0);
builder.getCellFormat().getBorders().getRight().setLineWidth(4.0);
builder.getCellFormat().getBorders().getTop().setLineWidth(4.0);
builder.getCellFormat().getBorders().getBottom().setLineWidth(4.0);
builder.writeln("Cell #3");
builder.insertCell();
builder.getCellFormat().clearFormatting();
builder.writeln("Cell #4");
```

## Tablo Başlığını ve Açıklamasını Ayarla

Tablonuza bir başlık ve açıklama ekleyin:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setTitle("Test title");
table.setDescription("Test description");
```

## Adım 10: Hücre Aralığına İzin Verin

Hücre aralığına izin verin ve bir tablo için değerini ayarlayın:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setAllowCellSpacing(true);
table.setCellSpacing(2.0);
```

## Adım 11: Stil Sahibi Bir Tablo Oluşturun

Önceden tanımlanmış bir stile sahip bir tablo oluşturun:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
table.setStyleIdentifier(StyleIdentifier.MEDIUM_SHADING_1_ACCENT_1);
table.setStyleOptions(TableStyleOptions.FIRST_COLUMN | TableStyleOptions.ROW_BANDS | TableStyleOptions.FIRST_ROW);
builder.writeln("Item");
builder.getCellFormat().setRightPadding(40.0);
builder.insertCell();
builder.writeln("Quantity (kg)");
```

## Adım 12: Stilden Hücre ve Satırlarda Biçimlendirmeyi Genişletin

Hücrelere ve satırlara biçimlendirme uygulamak için tablo stillerini nasıl genişleteceğinizi öğrenin:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
Color cellShadingBefore = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
doc.expandTableStylesToDirectFormatting();
Color cellShadingAfter = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
```

## Adım 13: Tablo Stili Oluşturun

Belirli biçimlendirmeyle özel bir tablo stili oluşturun:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
table.setStyleIdentifier(StyleIdentifier.MEDIUM_SHADING_1_ACCENT_1);
table.setStyleOptions(TableStyleOptions.FIRST_COLUMN | TableStyleOptions.ROW_BANDS | TableStyleOptions.FIRST_ROW);
builder.writeln("Item");
builder.getCellFormat().setRightPadding(40.0);
builder.insertCell();
builder.writeln("Quantity (kg)");
```

## Adım 14: Koşullu Biçimlendirmeyi Tanımlayın

Tablodaki satırlara koşullu biçimlendirme uygulayın:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
TableStyle tableStyle = (TableStyle) doc.getStyles().add(StyleType.TABLE, "MyTableStyle1");
tableStyle.getConditionalStyles().getFirstRow().getShading().setBackgroundPatternColor(Color.yellow);
table.setStyle(tableStyle);
```

## Adım 15: TableCell Formatını Ayarlayın

Tek tek hücreler için özel biçimlendirme ayarlayın:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.startTable();
builder.insertCell();
CellFormat cellFormat = builder.getCellFormat();
cellFormat.setWidth(250.0);
cellFormat.setLeftPadding(30.0);
cellFormat.setRightPadding(30.0);
cellFormat.setTopPadding(30.0);
cellFormat.setBottomPadding(30.0);
builder.writeln("I'm a wonderfully formatted cell.");
```

## Adım 16: TableRow Formatını Ayarlayın

Biçimlendirmeyi bir tablodaki satırların tamamına uygulayın:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
RowFormat rowFormat = builder.getRowFormat();
rowFormat.setHeight(100.0);
rowFormat.setHeightRule(HeightRule.EXACTLY);
table.setLeftPadding(30.0);
table.setRightPadding(30.0);
table.setTopPadding(30.0);
table.setBottomPadding(30.0);
builder.writeln("I'm a wonderfully formatted row.");
```

## Çözüm

Aspose.Words for Java, tabloları formatlamanıza ve tablo stillerini hassas bir şekilde uygulamanıza olanak tanır. Bireysel hücre formatını değiştirmekten özel tablo stilleri oluşturmaya kadar belgelerinizi görsel olarak çekici ve düzenli hale getirecek araçlara sahipsiniz.

## SSS'ler

### Aspose.Words for Java'yı nasıl indirebilirim?

 Aspose.Words for Java'yı Aspose web sitesinden indirebilirsiniz:[Aspose.Words for Java'yı indirin](https://releases.aspose.com/words/java/).

### Bir tablodaki tek tek hücrelere farklı kenarlıklar uygulayabilir miyim?

Evet, bu kılavuzda gösterildiği gibi Aspose.Words for Java'yı kullanarak bir tablodaki tek tek hücreler için farklı kenarlıklar ayarlayabilirsiniz.

### Tablo başlığı ve açıklamasını ayarlamanın amacı nedir?

Tablo başlığı ve açıklamasının ayarlanması belgenizin erişilebilirliğini ve düzenini geliştirerek okuyucuların ve yardımcı teknolojilerin içeriği anlamasını kolaylaştırır.

### Bir tablodaki belirli satırlara koşullu biçimlendirmeyi nasıl uygulayabilirim?

Bu kılavuzda gösterildiği gibi, özel tablo stillerini koşullu biçimlendirme kurallarıyla tanımlayarak bir tablodaki belirli satırlara koşullu biçimlendirme uygulayabilirsiniz.

### Aspose.Words for Java için daha fazla belge ve kaynağı nerede bulabilirim?

 Kapsamlı belgeler ve ek kaynaklar için lütfen Aspose.Words for Java belgelerini ziyaret edin:[Aspose.Words for Java Belgelendirmesi](https://reference.aspose.com/words/java/).