---
title: Menambahkan Konten menggunakan DocumentBuilder di Aspose.Words untuk Java
linktitle: Menambahkan Konten menggunakan DocumentBuilder
second_title: API Pemrosesan Dokumen Java Aspose.Words
description: Pembuatan Dokumen Induk dengan Aspose.Words untuk Java. Panduan Langkah demi Langkah untuk Menambahkan Teks, Tabel, Gambar, dan Lainnya. Buat Dokumen Word yang Menakjubkan dengan Mudah.
type: docs
weight: 26
url: /id/java/document-manipulation/adding-content-using-documentbuilder/
---

## Pengantar Menambahkan Konten menggunakan DocumentBuilder di Aspose.Words untuk Java

Dalam panduan langkah demi langkah ini, kita akan mempelajari cara menggunakan Aspose.Words untuk DocumentBuilder Java untuk menambahkan berbagai tipe konten ke dokumen Word. Kami akan membahas penyisipan teks, tabel, aturan horizontal, bidang formulir, HTML, hyperlink, daftar isi, gambar sebaris dan mengambang, paragraf, dan banyak lagi. Mari kita mulai!

## Prasyarat

 Sebelum memulai, pastikan Anda telah menyiapkan pustaka Aspose.Words untuk Java di proyek Anda. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/words/java/).

## Menambahkan Teks

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Sisipkan paragraf teks sederhana
builder.write("This is a simple text paragraph.");

// Simpan dokumennya
doc.save("path/to/your/document.docx");
```

## Menambahkan Tabel

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Mulai sebuah tabel
Table table = builder.startTable();

// Sisipkan sel dan konten
builder.insertCell();
builder.write("Cell 1");

builder.insertCell();
builder.write("Cell 2");

// Akhiri meja
builder.endTable();

// Simpan dokumennya
doc.save("path/to/your/document.docx");
```

## Menambahkan Aturan Horisontal

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Sisipkan aturan horizontal
builder.insertHorizontalRule();

// Simpan dokumennya
doc.save("path/to/your/document.docx");
```

## Menambahkan Bidang Formulir

### Bidang Formulir Input Teks

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Sisipkan kolom formulir input teks
builder.insertTextInput("TextInput", TextFormFieldType.REGULAR, "", "Default text", 0);

// Simpan dokumennya
doc.save("path/to/your/document.docx");
```

### Bidang Formulir Kotak Centang

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Masukkan bidang formulir kotak centang
builder.insertCheckBox("CheckBox", true, true, 0);

// Simpan dokumennya
doc.save("path/to/your/document.docx");
```

### Bidang Bentuk Kotak Kombo

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Tentukan item untuk kotak kombo
String[] items = { "Option 1", "Option 2", "Option 3" };

// Masukkan bidang formulir kotak kombo
builder.insertComboBox("DropDown", items, 0);

// Simpan dokumennya
doc.save("path/to/your/document.docx");
```

## Menambahkan HTML

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Masukkan konten HTML
builder.insertHtml("<p>This is an HTML paragraph.</p>");

// Simpan dokumennya
doc.save("path/to/your/document.docx");
```

## Menambahkan Hyperlink

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Sisipkan hyperlink
builder.write("Visit ");
builder.getFont().setColor(Color.BLUE);
builder.getFont().setUnderline(Underline.SINGLE);
builder.insertHyperlink("Aspose Website", "http://www.aspose.com", salah);
builder.getFont().clearFormatting();
builder.write(" for more information.");

// Simpan dokumennya
doc.save("path/to/your/document.docx");
```

## Menambahkan Daftar Isi

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Masukkan daftar isi
builder.insertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// Tambahkan konten dokumen
// ...

// Perbarui daftar isi
doc.updateFields();

// Simpan dokumennya
doc.save("path/to/your/document.docx");
```

## Menambahkan Gambar

### Gambar Sebaris

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Sisipkan gambar sebaris
builder.insertImage("path/to/your/image.png");

// Simpan dokumennya
doc.save("path/to/your/document.docx");
```

### Gambar Mengambang

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Sisipkan gambar mengambang
builder.insertImage("path/to/your/image.png", RelativeHorizontalPosition.MARGIN, 100.0, RelativeVerticalPosition.MARGIN, 100.0, 200.0, 100.0, WrapType.SQUARE);

// Simpan dokumennya
doc.save("path/to/your/document.docx");
```

## Menambahkan Paragraf

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Atur pemformatan paragraf
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

// Sisipkan paragraf
builder.writeln("This is a formatted paragraph.");

// Simpan dokumennya
doc.save("path/to/your/document.docx");
```

## Langkah 10: Memindahkan Kursor

 Anda dapat mengontrol posisi kursor dalam dokumen menggunakan berbagai metode seperti`moveToParagraph`, `moveToCell`dan banyak lagi. Berikut ini contohnya:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Pindahkan kursor ke paragraf tertentu
builder.moveToParagraph(2, 0);

// Tambahkan konten pada posisi kursor baru
builder.writeln("This is the 3rd paragraph.");
```

Ini adalah beberapa operasi umum yang dapat Anda lakukan menggunakan Aspose.Words untuk DocumentBuilder Java. Jelajahi dokumentasi perpustakaan untuk fitur lebih lanjut dan opsi penyesuaian. Selamat membuat dokumen!


## Kesimpulan

Dalam panduan komprehensif ini, kami telah menjelajahi kemampuan Aspose.Words untuk DocumentBuilder Java untuk menambahkan berbagai jenis konten ke dokumen Word. Kami telah membahas teks, tabel, aturan horizontal, bidang formulir, HTML, hyperlink, daftar isi, gambar, paragraf, dan pergerakan kursor.

## FAQ

### T: Apa itu Aspose.Words untuk Java?

J: Aspose.Words for Java adalah perpustakaan Java yang memungkinkan pengembang membuat, memodifikasi, dan memanipulasi dokumen Microsoft Word secara terprogram. Ini menyediakan berbagai fitur untuk pembuatan dokumen, pemformatan, dan penyisipan konten.

### T: Bagaimana cara menambahkan daftar isi ke dokumen saya?

A: Untuk menambahkan daftar isi, gunakan`DocumentBuilder` untuk menyisipkan bidang daftar isi ke dalam dokumen Anda. Pastikan untuk memperbarui bidang dalam dokumen setelah menambahkan konten untuk mengisi daftar isi. Berikut ini contohnya:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Sisipkan bidang daftar isi
builder.insertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// Tambahkan konten dokumen
// ...

// Perbarui daftar isi
doc.updateFields();
```

### T: Bagaimana cara menyisipkan gambar ke dalam dokumen menggunakan Aspose.Words untuk Java?

 J: Anda dapat menyisipkan gambar, baik inline maupun floating, menggunakan`DocumentBuilder`. Berikut ini contoh keduanya:

#### Gambar Sebaris:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Sisipkan gambar sebaris
builder.insertImage("path/to/your/image.png");
```

#### Gambar Mengambang:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Sisipkan gambar mengambang
builder.insertImage("path/to/your/image.png", RelativeHorizontalPosition.MARGIN, 100.0, RelativeVerticalPosition.MARGIN, 100.0, 200.0, 100.0, WrapType.SQUARE);
```

### T: Dapatkah saya memformat teks dan paragraf saat menambahkan konten?

 J: Ya, Anda dapat memformat teks dan paragraf menggunakan`DocumentBuilder`. Anda dapat mengatur properti font, perataan paragraf, indentasi, dan lainnya. Berikut ini contohnya:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Atur format font dan paragraf
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

// Sisipkan paragraf yang telah diformat
builder.writeln("This is a formatted paragraph.");
```

### T: Bagaimana cara memindahkan kursor ke lokasi tertentu dalam dokumen?

 J: Anda dapat mengontrol posisi kursor menggunakan metode seperti`moveToParagraph`, `moveToCell`dan banyak lagi. Berikut ini contohnya:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Pindahkan kursor ke paragraf tertentu
builder.moveToParagraph(2, 0);

// Tambahkan konten pada posisi kursor baru
builder.writeln("This is the 3rd paragraph.");
```

Ini adalah beberapa pertanyaan dan jawaban umum untuk membantu Anda memulai Aspose.Words untuk DocumentBuilder Java. Jika Anda memiliki pertanyaan lebih lanjut atau memerlukan bantuan lebih lanjut, lihat[dokumentasi perpustakaan](https://reference.aspose.com/words/java/) atau mencari bantuan dari komunitas Aspose.Words dan sumber daya dukungan.