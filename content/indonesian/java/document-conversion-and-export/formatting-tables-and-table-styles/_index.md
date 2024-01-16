---
title: Memformat Tabel dan Gaya Tabel di Aspose.Words untuk Java
linktitle: Memformat Tabel dan Gaya Tabel
second_title: API Pemrosesan Dokumen Java Aspose.Words
description: Pelajari cara memformat tabel dan menerapkan gaya tabel di Aspose.Words untuk Java. Jelajahi panduan langkah demi langkah dengan kode sumber untuk pemformatan tabel yang efektif. Sempurnakan tata letak dokumen Anda dengan Aspose.Words.
type: docs
weight: 17
url: /id/java/document-conversion-and-export/formatting-tables-and-table-styles/
---

## Pengantar Pemformatan Tabel dan Gaya Tabel di Aspose.Words untuk Java

Tabel memainkan peran penting dalam penataan dan pengorganisasian informasi dalam dokumen. Aspose.Words untuk Java menyediakan fitur canggih untuk memformat tabel dan menerapkan gaya tabel untuk meningkatkan daya tarik visual dokumen Anda. Dalam panduan langkah demi langkah ini, kita akan menjelajahi berbagai aspek pemformatan tabel dan penerapan gaya tabel menggunakan Aspose.Words untuk Java.

## Prasyarat

Sebelum kita mendalami detailnya, pastikan Anda memiliki perpustakaan Aspose.Words untuk Java yang terintegrasi ke dalam proyek Anda. Anda dapat mengunduhnya dari situs web Aspose:[Unduh Aspose.Words untuk Java](https://releases.aspose.com/words/java/).

## Dapatkan Jarak Antara Tabel dan Teks Sekitarnya

Untuk memulai, mari kita jelajahi cara mengambil jarak antara tabel dan teks di sekitarnya dalam dokumen.

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
System.out.println("Distance Top: " + table.getDistanceTop());
System.out.println("Distance Bottom: " + table.getDistanceBottom());
System.out.println("Distance Right: " + table.getDistanceRight());
System.out.println("Distance Left: " + table.getDistanceLeft());
```

## Terapkan Garis Batas pada Tabel

Anda dapat menyelaraskan tabel ke tengah halaman, menghapus batas yang ada, dan menetapkan batas kerangka khusus dengan kode ini:

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

## Bangun Tabel dengan Batas

Cuplikan kode ini menunjukkan cara membuat tabel dan menetapkan batas untuk tabel dan selnya:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.clearBorders();
table.setBorders(LineStyle.SINGLE, 1.5, Color.GREEN);
```

## Ubah Pemformatan Baris

Pelajari cara mengubah format baris tertentu dalam tabel:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Row firstRow = table.getFirstRow();
firstRow.getRowFormat().getBorders().setLineStyle(LineStyle.NONE);
firstRow.getRowFormat().setHeightRule(HeightRule.AUTO);
firstRow.getRowFormat().setAllowBreakAcrossPages(true);
```

## Terapkan Pemformatan Baris

Contoh ini menunjukkan cara menerapkan pemformatan ke seluruh baris dalam tabel:

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

## Atur Bantalan Sel

Jelajahi cara mengatur padding untuk masing-masing sel dalam tabel:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.startTable();
builder.insertCell();
builder.getCellFormat().setPaddings(30.0, 50.0, 30.0, 50.0);
builder.writeln("I'm a wonderfully formatted cell.");
```

## Ubah Pemformatan Sel

Temukan cara mengubah format sel tertentu dalam tabel:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
firstCell.getCellFormat().setWidth(30.0);
firstCell.getCellFormat().setOrientation(TextOrientation.DOWNWARD);
firstCell.getCellFormat().getShading().setForegroundPatternColor(Color.GREEN);
```

## Format Tabel dan Sel dengan Batas Berbeda

Pelajari cara mengatur batas berbeda untuk masing-masing sel dalam tabel:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
// Tetapkan batas tabel
table.setBorders(LineStyle.SINGLE, 2.0, Color.BLACK);
// Atur bayangan sel untuk masing-masing sel
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.RED);
// Tambahkan konten ke sel
builder.writeln("Cell #1");
builder.insertCell();
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.GREEN);
builder.writeln("Cell #2");
// Hapus pemformatan sel untuk baris berikutnya
builder.getCellFormat().clearFormatting();
// Buat batas yang lebih besar untuk sel pertama baris ini
builder.getCellFormat().getBorders().getLeft().setLineWidth(4.0);
builder.getCellFormat().getBorders().getRight().setLineWidth(4.0);
builder.getCellFormat().getBorders().getTop().setLineWidth(4.0);
builder.getCellFormat().getBorders().getBottom().setLineWidth(4.0);
builder.writeln("Cell #3");
builder.insertCell();
builder.getCellFormat().clearFormatting();
builder.writeln("Cell #4");
```

## Tetapkan Judul dan Deskripsi Tabel

Tambahkan judul dan deskripsi ke tabel Anda:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setTitle("Test title");
table.setDescription("Test description");
```

## Langkah 10: Izinkan Spasi Sel

Izinkan spasi sel dan tetapkan nilainya untuk tabel:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setAllowCellSpacing(true);
table.setCellSpacing(2.0);
```

## Langkah 11: Bangun Tabel dengan Gaya

Buat tabel dengan gaya yang telah ditentukan sebelumnya:

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

## Langkah 12: Perluas Pemformatan pada Sel dan Baris dari Gaya

Pelajari cara memperluas gaya tabel untuk menerapkan pemformatan ke sel dan baris:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
Color cellShadingBefore = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
doc.expandTableStylesToDirectFormatting();
Color cellShadingAfter = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
```

## Langkah 13: Buat Gaya Tabel

Buat gaya tabel khusus dengan format tertentu:

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

## Langkah 14: Tentukan Pemformatan Bersyarat

Menerapkan pemformatan bersyarat ke baris dalam tabel:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
TableStyle tableStyle = (TableStyle) doc.getStyles().add(StyleType.TABLE, "MyTableStyle1");
tableStyle.getConditionalStyles().getFirstRow().getShading().setBackgroundPatternColor(Color.yellow);
table.setStyle(tableStyle);
```

## Langkah 15: Atur Pemformatan TableCell

Tetapkan pemformatan spesifik untuk sel individual:

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

## Langkah 16: Atur Pemformatan TableRow

Menerapkan pemformatan ke seluruh baris dalam tabel:

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

## Kesimpulan

Aspose.Words untuk Java memberdayakan Anda untuk memformat tabel dan menerapkan gaya tabel dengan presisi. Dari memodifikasi pemformatan sel individual hingga membuat gaya tabel khusus, Anda memiliki alat untuk membuat dokumen Anda menarik dan terorganisir secara visual.

## FAQ

### Bagaimana cara mengunduh Aspose.Words untuk Java?

 Anda dapat mengunduh Aspose.Words untuk Java dari situs web Aspose:[Unduh Aspose.Words untuk Java](https://releases.aspose.com/words/java/).

### Bisakah saya menerapkan batas berbeda ke masing-masing sel dalam tabel?

Ya, Anda dapat mengatur batas berbeda untuk masing-masing sel dalam tabel menggunakan Aspose.Words untuk Java, seperti yang ditunjukkan dalam panduan ini.

### Apa tujuan menetapkan judul dan deskripsi tabel?

Menetapkan judul dan deskripsi tabel akan meningkatkan aksesibilitas dan pengorganisasian dokumen Anda, sehingga memudahkan pembaca dan teknologi pendukung untuk memahami konten.

### Bagaimana cara menerapkan pemformatan bersyarat ke baris tertentu dalam tabel?

Anda bisa menerapkan pemformatan bersyarat ke baris tertentu dalam tabel dengan menentukan gaya tabel khusus dengan aturan pemformatan bersyarat, seperti yang diperlihatkan dalam panduan ini.

### Di mana saya dapat menemukan lebih banyak dokumentasi dan sumber daya untuk Aspose.Words untuk Java?

 Untuk dokumentasi komprehensif dan sumber daya tambahan, silakan kunjungi dokumentasi Aspose.Words untuk Java:[Aspose.Words untuk Dokumentasi Java](https://reference.aspose.com/words/java/).