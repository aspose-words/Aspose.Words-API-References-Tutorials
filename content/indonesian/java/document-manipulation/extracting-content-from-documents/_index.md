---
title: Mengekstrak Konten dari Dokumen di Aspose.Words untuk Java
linktitle: Mengekstrak Konten dari Dokumen
second_title: API Pemrosesan Dokumen Java Aspose.Words
description: Pelajari cara mengekstrak konten dari dokumen dengan mudah menggunakan Aspose.Words untuk Java. Panduan langkah demi langkah dan contoh kode kami menyederhanakan prosesnya.
type: docs
weight: 13
url: /id/java/document-manipulation/extracting-content-from-documents/
---

## Pengantar Mengekstrak Konten dari Dokumen di Aspose.Words untuk Java

Dalam dunia pemrosesan dokumen, mengekstraksi konten dari dokumen merupakan persyaratan umum. Baik Anda perlu mengekstrak teks, tabel, gambar, atau elemen dokumen tertentu, Aspose.Words untuk Java menyediakan alat canggih untuk mempermudah tugas ini. Dalam panduan komprehensif ini, kami akan memandu Anda melalui proses mengekstraksi konten dari dokumen menggunakan Aspose.Words untuk Java. 

## Prasyarat

Sebelum kita mendalami proses ekstraksi, pastikan Anda memiliki prasyarat berikut:

1.  Aspose.Words for Java: Anda harus menginstal dan mengatur Aspose.Words for Java di lingkungan pengembangan Java Anda. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/words/java/).

2. Dokumen untuk Mengekstrak Konten: Untuk panduan ini, kami akan menggunakan contoh dokumen bernama "Ekstrak konten.docx." Pastikan Anda memiliki dokumen serupa yang siap untuk diekstraksi.

## Mengekstraksi Konten Antar Node Tingkat Blok

```java
// Contoh kode Java untuk mengekstraksi konten antar node tingkat blok
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

## Mengekstrak Konten Antar Bookmark

```java
//Contoh kode Java untuk mengekstrak konten antar bookmark
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

## Mengekstraksi Konten Antar Rentang Komentar

```java
// Contoh kode Java untuk mengekstraksi konten di antara rentang komentar
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

## Mengekstraksi Konten Antar Paragraf

```java
// Contoh kode Java untuk mengekstrak konten antar paragraf
Document doc = new Document("Your Directory Path" + "Extract content.docx");
Paragraph startPara = (Paragraph) doc.getFirstSection().getBody().getChild(NodeType.PARAGRAPH, 6, true);
Paragraph endPara = (Paragraph) doc.getFirstSection().getBody().getChild(NodeType.PARAGRAPH, 10, true);
ArrayList<Node> extractedNodes = ExtractContentHelper.extractContent(startPara, endPara, true);
Document dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodes);
dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenParagraphs.docx");
```

## Mengekstraksi Konten Antar Gaya Paragraf

```java
// Contoh kode Java untuk mengekstrak konten antar gaya paragraf
Document doc = new Document("Your Directory Path" + "Extract content.docx");
ArrayList<Paragraph> parasStyleHeading1 = ExtractContentHelper.paragraphsByStyleName(doc, "Heading 1");
ArrayList<Paragraph> parasStyleHeading3 = ExtractContentHelper.paragraphsByStyleName(doc, "Heading 3");
Node startPara1 = parasStyleHeading1.get(0);
Node endPara1 = parasStyleHeading3.get(0);
ArrayList<Node> extractedNodes = ExtractContentHelper.extractContent(startPara1, endPara1, false);
Document dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodes);
dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenParagraphStyles.docx");
```

## Mengekstrak Konten Di Antara Proses

```java
// Contoh kode Java untuk mengekstraksi konten di antara proses
Document doc = new Document("Your Directory Path" + "Extract content.docx");
Paragraph para = (Paragraph) doc.getChild(NodeType.PARAGRAPH, 7, true);
Run startRun = para.getRuns().get(1);
Run endRun = para.getRuns().get(4);
ArrayList<Node> extractedNodes = ExtractContentHelper.extractContent(startRun, endRun, true);
Node node = (Node) extractedNodes.get(0);
System.out.println(node.toString(SaveFormat.TEXT));
```

## Mengekstrak Konten Menggunakan DocumentVisitor

```java
// Contoh kode Java untuk mengekstraksi konten menggunakan DocumentVisitor
Document doc = new Document("Your Directory Path" + "Absolute position tab.docx");
MyDocToTxtWriter myConverter = new MyDocToTxtWriter();
doc.accept(myConverter);
System.out.println(myConverter.getText());
```

## Mengekstrak Konten Menggunakan Bidang

```java
// Contoh kode Java untuk mengekstraksi konten menggunakan Field
Document doc = new Document("Your Directory Path" + "Extract content.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
builder.moveToMergeField("Fullname", false, false);
FieldStart startField = (FieldStart) builder.getCurrentNode();
Paragraph endPara = (Paragraph) doc.getFirstSection().getChild(NodeType.PARAGRAPH, 5, true);
ArrayList<Node> extractedNodes = ExtractContentHelper.extractContent(startField, endPara, false);
Document dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodes);
dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentUsingField.docx");
```

## Mengekstrak Daftar Isi

```java
// Contoh kode Java untuk mengekstrak daftar isi
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

## Mengekstrak Teks Saja

```java
// Contoh kode Java untuk mengekstraksi teks saja
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.insertField("MERGEFIELD Field");
System.out.println("GetText() Result: " + doc.getText());
System.out.println("ToString() Result: " + doc.toString(SaveFormat.TEXT));
```

## Mengekstrak Konten Berdasarkan Gaya

```java
// Contoh kode Java untuk mengekstraksi konten berdasarkan gaya
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

## Mengekstrak dan Mencetak Teks

```java
// Contoh kode Java untuk mengekstrak dan mencetak teks
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
System.out.println("Contents of the table: ");
System.out.println(table.getRange().getText());
System.out.println("\nContents of the row: ");
System.out.println(table.getRows().get(1).getRange().getText());
System.out.println("\nContents of the cell: ");
System.out.println(table.getLastRow().getLastCell().getRange().getText());
```

## Mengekstrak Gambar ke File

```java
// Contoh kode Java untuk mengekstrak gambar ke file
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

## Kesimpulan

Selamat! Anda telah mempelajari cara mengekstrak konten dari dokumen menggunakan Aspose.Words untuk Java. Panduan ini mencakup berbagai teknik ekstraksi, termasuk konten antar node tingkat blok, bookmark, rentang komentar, paragraf, dan banyak lagi. Anda kini diperlengkapi untuk menangani ekstraksi konten dokumen secara efisien di aplikasi Java Anda.

## FAQ

### Bagaimana cara mengekstrak konten dari bagian dokumen tertentu?

Untuk mengekstrak konten dari bagian dokumen tertentu, Anda dapat mengidentifikasi titik awal dan akhir bagian tersebut dan menggunakan metode Aspose.Words for Java yang sesuai untuk mengekstrak konten di antara bagian tersebut.

### Bisakah saya mengekstrak konten dari dokumen yang dilindungi kata sandi?

Ya, Aspose.Words untuk Java menyediakan fungsionalitas untuk mengekstrak konten dari dokumen yang dilindungi kata sandi. Anda dapat memberikan kata sandi saat membuka dokumen menggunakan`Document` konstruktor kelas.

### Bagaimana cara mengekstrak konten dan menyimpannya dalam format lain, seperti teks biasa atau HTML?

 Anda dapat mengekstrak konten dari dokumen dan menyimpannya dalam format berbeda menggunakan Aspose.Words untuk Java. Setelah mengekstrak konten, Anda dapat menggunakan`Document` metode kelas untuk menyimpannya dalam format seperti teks biasa, HTML, atau lainnya.

### Apakah ada cara untuk mengekstrak konten dari elemen dokumen tertentu, seperti tabel atau gambar?

Ya, Anda dapat mengekstrak konten dari elemen dokumen tertentu, seperti tabel atau gambar, menggunakan Aspose.Words untuk Java. Identifikasi elemen yang ingin Anda ekstrak, lalu gunakan metode yang sesuai untuk mengekstrak kontennya.

### Bagaimana cara mengotomatiskan proses ekstraksi konten di aplikasi Java saya?

Untuk mengotomatiskan proses ekstraksi konten di aplikasi Java, Anda dapat membuat kode khusus berdasarkan teknik yang dijelaskan dalam panduan ini. Anda juga dapat menerapkan logika untuk melakukan iterasi melalui beberapa dokumen dan mengekstrak konten sesuai kebutuhan.