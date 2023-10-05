---
title: Aspose.Words for Java'da Belgelerden İçerik Çıkarma
linktitle: Belgelerden İçerik Çıkarma
second_title: Aspose.Words Java Belge İşleme API'si
description: Aspose.Words for Java'yı kullanarak belgelerden içeriği nasıl kolaylıkla çıkaracağınızı öğrenin. Adım adım kılavuzumuz ve kod örneklerimiz süreci basitleştirir.
type: docs
weight: 13
url: /tr/java/document-manipulation/extracting-content-from-documents/
---

## Aspose.Words for Java'da Belgelerden İçerik Çıkarmaya Giriş

Belge işleme dünyasında belgelerden içerik çıkarmak ortak bir gerekliliktir. Metin, tablo, resim veya belirli belge öğelerini ayıklamanız gerekiyorsa, Aspose.Words for Java bu görevi kolaylaştırmak için güçlü araçlar sağlar. Bu kapsamlı kılavuzda Aspose.Words for Java kullanarak belgelerden içerik çıkarma sürecinde size yol göstereceğiz. 

## Önkoşullar

Çıkarma işlemine geçmeden önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:

1.  Aspose.Words for Java: Java geliştirme ortamınızda Aspose.Words for Java'nın kurulu ve ayarlanmış olması gerekir. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/words/java/).

2. İçerik Çıkarılacak Bir Belge: Bu kılavuz için "İçerik Çıkart.docx" adlı örnek bir belge kullanacağız. Benzer bir belgenin çıkarılmaya hazır olduğundan emin olun.

## Blok Düzeyindeki Düğümler Arasında İçerik Çıkarma

```java
// Blok düzeyindeki düğümler arasında içerik çıkarmak için Java kod örneği
Document doc = new Document("Your Directory Path" + "Extract content.docx");
Paragraph startPara = (Paragraph) doc.getLastSection().getChild(NodeType.PARAGRAPH, 2, true);
Table endTable = (Table) doc.getLastSection().getChild(NodeType.TABLE, 0, true);
ArrayList<Node> extractedNodes = ExtractContentHelper.extractContent(startPara, endTable, true);
Collections.reverse(extractedNodes);
while (extractedNodes.size() > 0) {
    endTable.getParentNode().insertAfter((Node) extractedNodes.get(0), endTable);
    extractedNodes.remove(0);
}
doc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenBlockLevelNodes.docx");
```

## Yer İşaretleri Arasındaki İçeriği Çıkarma

```java
//Yer imleri arasında içerik çıkarmak için Java kod örneği
Document doc = new Document("Your Directory Path" + "Extract content.docx");
Bookmark bookmark = doc.getRange().getBookmarks().get("Bookmark1");
BookmarkStart bookmarkStart = bookmark.getBookmarkStart();
BookmarkEnd bookmarkEnd = bookmark.getBookmarkEnd();
ArrayList<Node> extractedNodesInclusive = ExtractContentHelper.extractContent(bookmarkStart, bookmarkEnd, true);
Document dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodesInclusive);
dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenBookmark.IncludingBookmark.docx");
ArrayList<Node> extractedNodesExclusive = ExtractContentHelper.extractContent(bookmarkStart, bookmarkEnd, false);
dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodesExclusive);
dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenBookmark.WithoutBookmark.docx");
```

## Yorum Aralıkları Arasında İçerik Çıkarma

```java
// Yorum aralıkları arasında içerik çıkarmak için Java kod örneği
Document doc = new Document("Your Directory Path" + "Extract content.docx");
CommentRangeStart commentStart = (CommentRangeStart) doc.getChild(NodeType.COMMENT_RANGE_START, 0, true);
CommentRangeEnd commentEnd = (CommentRangeEnd) doc.getChild(NodeType.COMMENT_RANGE_END, 0, true);
ArrayList<Node> extractedNodesInclusive = ExtractContentHelper.extractContent(commentStart, commentEnd, true);
Document dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodesInclusive);
dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenCommentRange.IncludingComment.docx");
ArrayList<Node> extractedNodesExclusive = ExtractContentHelper.extractContent(commentStart, commentEnd, false);
dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodesExclusive);
dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenCommentRange.WithoutComment.docx");
```

## Paragraf Arasındaki İçeriği Çıkarma

```java
// Paragraflar arasında içerik çıkarmak için Java kod örneği
Document doc = new Document("Your Directory Path" + "Extract content.docx");
Paragraph startPara = (Paragraph) doc.getFirstSection().getBody().getChild(NodeType.PARAGRAPH, 6, true);
Paragraph endPara = (Paragraph) doc.getFirstSection().getBody().getChild(NodeType.PARAGRAPH, 10, true);
ArrayList<Node> extractedNodes = ExtractContentHelper.extractContent(startPara, endPara, true);
Document dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodes);
dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenParagraphs.docx");
```

## Paragraf Stilleri Arasında İçerik Çıkarma

```java
// Paragraf stilleri arasında içerik çıkarmak için Java kod örneği
Document doc = new Document("Your Directory Path" + "Extract content.docx");
ArrayList<Paragraph> parasStyleHeading1 = ExtractContentHelper.paragraphsByStyleName(doc, "Heading 1");
ArrayList<Paragraph> parasStyleHeading3 = ExtractContentHelper.paragraphsByStyleName(doc, "Heading 3");
Node startPara1 = parasStyleHeading1.get(0);
Node endPara1 = parasStyleHeading3.get(0);
ArrayList<Node> extractedNodes = ExtractContentHelper.extractContent(startPara1, endPara1, false);
Document dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodes);
dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenParagraphStyles.docx");
```

## Çalıştırmalar Arasında İçerik Çıkarma

```java
// Çalıştırmalar arasında içerik çıkarmak için Java kod örneği
Document doc = new Document("Your Directory Path" + "Extract content.docx");
Paragraph para = (Paragraph) doc.getChild(NodeType.PARAGRAPH, 7, true);
Run startRun = para.getRuns().get(1);
Run endRun = para.getRuns().get(4);
ArrayList<Node> extractedNodes = ExtractContentHelper.extractContent(startRun, endRun, true);
Node node = (Node) extractedNodes.get(0);
System.out.println(node.toString(SaveFormat.TEXT));
```

## DocumentVisitor'ı Kullanarak İçerik Çıkarma

```java
// DocumentVisitor kullanarak içerik çıkarmak için Java kod örneği
Document doc = new Document("Your Directory Path" + "Absolute position tab.docx");
MyDocToTxtWriter myConverter = new MyDocToTxtWriter();
doc.accept(myConverter);
System.out.println(myConverter.getText());
```

## Alanı Kullanarak İçerik Çıkarma

```java
// Field'ı kullanarak içerik çıkarmak için Java kod örneği
Document doc = new Document("Your Directory Path" + "Extract content.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
builder.moveToMergeField("Fullname", false, false);
FieldStart startField = (FieldStart) builder.getCurrentNode();
Paragraph endPara = (Paragraph) doc.getFirstSection().getChild(NodeType.PARAGRAPH, 5, true);
ArrayList<Node> extractedNodes = ExtractContentHelper.extractContent(startField, endPara, false);
Document dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodes);
dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentUsingField.docx");
```

## İçindekiler Tablosunun Çıkarılması

```java
// İçindekiler tablosunu çıkarmak için Java kod örneği
Document doc = new Document("Your Directory Path" + "Table of contents.docx");
for (Field field : doc.getRange().getFields()) {
    if (field.getType() == FieldType.FIELD_HYPERLINK) {
        FieldHyperlink hyperlink = (FieldHyperlink) field;
        if (hyperlink.getSubAddress() != null && hyperlink.getSubAddress().startsWith("_Toc")) {
            Paragraph tocItem = (Paragraph) field.getStart().getAncestor(NodeType.PARAGRAPH);
            System.out.println(tocItem.toString(SaveFormat.TEXT).trim());
            System.out.println("------------------");
            Bookmark bm = doc.getRange().getBookmarks().get(hyperlink.getSubAddress());
            Paragraph pointer = (Paragraph) bm.getBookmarkStart().getAncestor(NodeType.PARAGRAPH);
            System.out.println(pointer.toString(SaveFormat.TEXT));
        }
    }
}
```

## Yalnızca Metin Çıkarma

```java
// Yalnızca metni çıkarmak için Java kod örneği
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.insertField("MERGEFIELD Field");
System.out.println("GetText() Result: " + doc.getText());
System.out.println("ToString() Result: " + doc.toString(SaveFormat.TEXT));
```

## Stillere Göre İçerik Çıkarma

```java
// Stillere dayalı içerik çıkarmak için Java kod örneği
Document doc = new Document("Your Directory Path" + "Styles.docx");
final String PARA_STYLE = "Heading 1";
final String RUN_STYLE = "Intense Emphasis";
ArrayList<Paragraph> paragraphs = paragraphsByStyleName(doc, PARA_STYLE);
System.out.println("Paragraphs with \"{paraStyle}\" styles ({paragraphs.Count}):");
for (Paragraph paragraph : paragraphs)
    System.out.println(paragraph.toString(SaveFormat.TEXT));
ArrayList<Run> runs = runsByStyleName(doc, RUN_STYLE);
System.out.println("\nRuns with \"{runStyle}\" styles ({runs.Count}):");
for (Run run : runs)
    System.out.println(run.getRange().getText());
}

public ArrayList<Paragraph> paragraphsByStyleName(Document doc, String styleName) {
    ArrayList<Paragraph> paragraphsWithStyle = new ArrayList<Paragraph>();
    NodeCollection paragraphs = doc.getChildNodes(NodeType.PARAGRAPH, true);
    for (Paragraph paragraph : (Iterable<Paragraph>) paragraphs) {
        if (paragraph.getParagraphFormat().getStyle().getName().equals(styleName))
            paragraphsWithStyle.add(paragraph);
    }
    return paragraphsWithStyle;
}

public ArrayList<Run> runsByStyleName(Document doc, String styleName) {
    ArrayList<Run> runsWithStyle = new ArrayList<Run>();
    NodeCollection runs = doc.getChildNodes(NodeType.RUN, true);
    for (Run run : (Iterable<Run>) runs) {
        if (run.getFont().getStyle().getName().equals(styleName))
            runsWithStyle.add(run);
    }
    return runsWithStyle;
}
```

## Metin Çıkarma ve Yazdırma

```java
// Metin çıkarmak ve yazdırmak için Java kod örneği
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
System.out.println("Contents of the table: ");
System.out.println(table.getRange().getText());
System.out.println("\nContents of the row: ");
System.out.println(table.getRows().get(1).getRange().getText());
System.out.println("\nContents of the cell: ");
System.out.println(table.getLastRow().getLastCell().getRange().getText());
```

## Görüntüleri Dosyalara Çıkarma

```java
// Görüntüleri dosyalara çıkarmak için Java kod örneği
Document doc = new Document("Your Directory Path" + "Images.docx");
NodeCollection shapes = doc.getChildNodes(NodeType.SHAPE, true);
int imageIndex = 0;
for (Shape shape : (Iterable<Shape>) shapes) {
    if (shape.hasImage()) {
        String imageFileName = MessageFormat.format("Image.ExportImages.{0}_{1}",
                imageIndex, FileFormatUtil.imageTypeToExtension(shape.getImageData().getImageType()));
        shape.getImageData().save("Your Directory Path" + imageFileName);
        imageIndex++;
    }
}
```

## Çözüm

Tebrikler! Aspose.Words for Java kullanarak belgelerden nasıl içerik çıkaracağınızı öğrendiniz. Bu kılavuz, blok düzeyindeki düğümler arasındaki içerik, yer imleri, yorum aralıkları, paragraflar ve daha fazlası dahil olmak üzere çeşitli çıkarma tekniklerini kapsıyordu. Artık Java uygulamalarınızda belge içeriği çıkarmayı verimli bir şekilde gerçekleştirebilecek donanıma sahipsiniz.

## SSS'ler

### Belirli belge bölümlerinden içeriği nasıl çıkarabilirim?

Belirli belge bölümlerinden içerik çıkarmak için bölümlerin başlangıç ve bitiş noktalarını tanımlayabilir ve bunlar arasında içerik çıkarmak için uygun Aspose.Words for Java yöntemlerini kullanabilirsiniz.

### Parola korumalı belgelerden içerik çıkarabilir miyim?

Evet, Aspose.Words for Java, parola korumalı belgelerden içerik çıkarmaya yönelik işlevsellik sağlar. Belgeyi açarken şifreyi kullanarak girebilirsiniz.`Document` sınıf yapıcısı.

### İçeriği nasıl çıkarabilirim ve onu düz metin veya HTML gibi farklı formatlarda kaydedebilirim?

 Aspose.Words for Java'yı kullanarak bir belgeden içerik çıkarabilir ve onu farklı formatlarda kaydedebilirsiniz. İçeriği çıkardıktan sonra kullanabilirsiniz.`Document` düz metin, HTML veya diğerleri gibi formatlarda kaydetmek için sınıf yöntemleri.

### Tablolar veya resimler gibi belirli belge öğelerinden içerik çıkarmanın bir yolu var mı?

Evet, Aspose.Words for Java'yı kullanarak tablolar veya resimler gibi belirli belge öğelerinden içerik çıkarabilirsiniz. Çıkarmak istediğiniz öğeleri tanımlayın ve ardından içeriklerini çıkarmak için uygun yöntemleri kullanın.

### Java uygulamamda içerik çıkarma işlemini nasıl otomatikleştirebilirim?

Java uygulamanızdaki içerik çıkarma sürecini otomatikleştirmek için bu kılavuzda açıklanan tekniklere dayalı olarak özel kod oluşturabilirsiniz. Ayrıca, birden çok belgeyi yinelemek ve gerektiğinde içeriği çıkarmak için mantığı da uygulayabilirsiniz.