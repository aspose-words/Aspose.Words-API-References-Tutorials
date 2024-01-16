---
title: Menggunakan Penurunan Harga di Aspose.Words untuk Java
linktitle: Menggunakan penurunan harga
second_title: API Pemrosesan Dokumen Java Aspose.Words
description: Pelajari cara menggunakan Markdown di Aspose.Words untuk Java dengan tutorial langkah demi langkah ini. Buat, tata gaya, dan simpan dokumen Markdown dengan mudah.
type: docs
weight: 19
url: /id/java/using-document-elements/using-markdown/
---

Dalam dunia pemrosesan dokumen, Aspose.Words for Java adalah alat canggih yang memungkinkan pengembang bekerja dengan dokumen Word dengan mudah. Salah satu fiturnya adalah kemampuan untuk menghasilkan dokumen Markdown, sehingga serbaguna untuk berbagai aplikasi. Dalam tutorial ini, kami akan memandu Anda melalui proses penggunaan Markdown di Aspose.Words untuk Java.

## Prasyarat

Sebelum kita mendalami kodenya, pastikan Anda memiliki prasyarat berikut:

### Aspose.Kata-kata untuk Java 
Anda harus menginstal dan menyiapkan pustaka Aspose.Words untuk Java di lingkungan pengembangan Anda.

### Lingkungan Pengembangan Jawa 
Pastikan Anda memiliki lingkungan pengembangan Java yang siap digunakan.

## Menyiapkan Lingkungan

Mari kita mulai dengan menyiapkan lingkungan pengembangan kita. Pastikan Anda telah mengimpor perpustakaan yang diperlukan dan mengatur direktori yang diperlukan.

```java
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Menata Dokumen Anda

Di bagian ini, kita akan membahas cara menerapkan gaya ke dokumen Markdown Anda. Kami akan membahas judul, penekanan, daftar, dan banyak lagi.

### Judul

Judul penurunan harga sangat penting untuk menyusun dokumen Anda. Kita akan menggunakan gaya "Heading 1" untuk heading utama.

```java
builder.getParagraphFormat().setStyleName("Heading 1");
builder.writeln("Heading 1");
```

### Tekanan

Anda dapat menekankan teks di Markdown menggunakan berbagai gaya seperti miring, tebal, dan dicoret.

```java
builder.getFont().setItalic(true);
builder.writeln("Italic Text");
builder.getFont().setItalic(false);

builder.getFont().setBold(true);
builder.writeln("Bold Text");
builder.getFont().setBold(false);

builder.getFont().setStrikeThrough(true);
builder.writeln("StrikeThrough Text");
builder.getFont().setStrikeThrough(false);
```

### Daftar

Penurunan harga mendukung daftar terurut dan tidak berurutan. Di sini, kami akan menentukan daftar terurut.

```java
builder.getListFormat().applyNumberDefault();
```

### Kutipan

Kutipan adalah cara terbaik untuk menyorot teks dalam penurunan harga.

```java
builder.getParagraphFormat().setStyleName("Quote");
builder.writeln("A Quote block");
```

### Hyperlink

Penurunan harga memungkinkan Anda menyisipkan hyperlink. Di sini, kami akan menyisipkan hyperlink ke situs Aspose.

```java
builder.getFont().setBold(true);
builder.insertHyperlink("Aspose", "https://www.aspose.com", salah);
builder.getFont().setBold(false);
```

## Tabel

Menambahkan tabel ke dokumen Markdown Anda sangatlah mudah dengan Aspose.Words untuk Java.

```java
builder.startTable();
builder.insertCell();
builder.write("Cell1");
builder.insertCell();
builder.write("Cell2");
builder.endTable();
```

## Menyimpan Dokumen Penurunan Harga

Setelah Anda membuat dokumen Penurunan Harga, simpan ke lokasi yang Anda inginkan.

```java
doc.save(outPath + "WorkingWithMarkdown.CreateMarkdownDocument.md");
```

## Kode Sumber Lengkap
```java
string outPath = "Your Output Directory";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
//Tentukan gaya "Judul 1" untuk paragraf tersebut.
builder.getParagraphFormat().setStyleName("Heading 1");
builder.writeln("Heading 1");
// Reset gaya dari paragraf sebelumnya agar tidak menggabungkan gaya antar paragraf.
builder.getParagraphFormat().setStyleName("Normal");
// Sisipkan aturan horizontal.
builder.insertHorizontalRule();
// Tentukan daftar yang dipesan.
builder.insertParagraph();
builder.getListFormat().applyNumberDefault();
// Tentukan penekanan miring untuk teks.
builder.getFont().setItalic(true);
builder.writeln("Italic Text");
builder.getFont().setItalic(false);
// Tentukan penekanan tebal pada teks.
builder.getFont().setBold(true);
builder.writeln("Bold Text");
builder.getFont().setBold(false);
// Tentukan penekanan StrikeThrough untuk teks.
builder.getFont().setStrikeThrough(true);
builder.writeln("StrikeThrough Text");
builder.getFont().setStrikeThrough(false);
// Hentikan penomoran paragraf.
builder.getListFormat().removeNumbers();
// Tentukan gaya "Kutipan" untuk paragraf tersebut.
builder.getParagraphFormat().setStyleName("Quote");
builder.writeln("A Quote block");
// Tentukan Kutipan bersarang.
Style nestedQuote = doc.getStyles().add(StyleType.PARAGRAPH, "Quote1");
nestedQuote.setBaseStyleName("Quote");
builder.getParagraphFormat().setStyleName("Quote1");
builder.writeln("A nested Quote block");
// Setel ulang gaya paragraf ke Normal untuk menghentikan blok Kutipan.
builder.getParagraphFormat().setStyleName("Normal");
// Tentukan Hyperlink untuk teks yang diinginkan.
builder.getFont().setBold(true);
// Catatan, teks hyperlink dapat ditekankan.
builder.insertHyperlink("Aspose", "https://www.aspose.com", salah);
builder.getFont().setBold(false);
// Masukkan tabel sederhana.
builder.startTable();
builder.insertCell();
builder.write("Cell1");
builder.insertCell();
builder.write("Cell2");
builder.endTable();
// Simpan dokumen Anda sebagai file penurunan harga.
doc.save(outPath + "WorkingWithMarkdown.CreateMarkdownDocument.md");
```

## Kesimpulan

Dalam tutorial ini, kami telah membahas dasar-dasar penggunaan Markdown di Aspose.Words untuk Java. Anda telah mempelajari cara menyiapkan lingkungan, menerapkan gaya, menambahkan tabel, dan menyimpan dokumen Penurunan Harga. Dengan pengetahuan ini, Anda dapat mulai menggunakan Aspose.Words untuk Java untuk menghasilkan dokumen Markdown secara efisien.

### FAQ

### Apa itu Aspose.Words untuk Java? 
   Aspose.Words for Java adalah perpustakaan Java yang memungkinkan pengembang membuat, memanipulasi, dan mengonversi dokumen Word dalam aplikasi Java.

### Bisakah saya menggunakan Aspose.Words untuk Java untuk mengonversi Markdown ke dokumen Word? 
   Ya, Anda dapat menggunakan Aspose.Words for Java untuk mengonversi dokumen Markdown ke dokumen Word dan sebaliknya.

### Apakah Aspose.Words untuk Java gratis untuk digunakan? 
    Aspose.Words untuk Java adalah produk komersial, dan lisensi diperlukan untuk penggunaannya. Anda dapat memperoleh lisensi dari[Di Sini](https://purchase.aspose.com/buy).

### Apakah ada tutorial atau dokumentasi yang tersedia untuk Aspose.Words untuk Java? 
    Ya, Anda dapat menemukan tutorial dan dokumentasi komprehensif di[Aspose.Words untuk Dokumentasi Java API](https://reference.aspose.com/words/java/).

### Di mana saya bisa mendapatkan dukungan untuk Aspose.Words untuk Java? 
    Untuk dukungan dan bantuan, Anda dapat mengunjungi[Aspose.Words untuk forum Java](https://forum.aspose.com/).

Sekarang setelah Anda menguasai dasar-dasarnya, mulailah menjelajahi kemungkinan tak terbatas dalam menggunakan Aspose.Words untuk Java dalam proyek pemrosesan dokumen Anda.
   