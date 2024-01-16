---
title: Menyimpan Dokumen sebagai File Teks di Aspose.Words untuk Java
linktitle: Menyimpan Dokumen sebagai File Teks
second_title: API Pemrosesan Dokumen Java Aspose.Words
description: Pelajari cara menyimpan dokumen sebagai file teks di Aspose.Words untuk Java. Ikuti panduan langkah demi langkah kami dengan contoh kode Java.
type: docs
weight: 24
url: /id/java/document-loading-and-saving/saving-documents-as-text-files/
---

## Pengantar Menyimpan Dokumen sebagai File Teks di Aspose.Words untuk Java

Dalam tutorial ini, kita akan mempelajari cara menyimpan dokumen sebagai file teks menggunakan perpustakaan Aspose.Words untuk Java. Aspose.Words adalah Java API yang kuat untuk bekerja dengan dokumen Word, dan menyediakan berbagai opsi untuk menyimpan dokumen dalam berbagai format, termasuk teks biasa. Kami akan membahas langkah-langkah untuk mencapai hal ini dan memberikan contoh kode Java sepanjang prosesnya.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:

- Java Development Kit (JDK) diinstal pada sistem Anda.
-  Aspose.Words untuk perpustakaan Java terintegrasi ke dalam proyek Anda. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/words/java/).
- Pengetahuan dasar tentang pemrograman Java.

## Langkah 1: Buat Dokumen

Untuk menyimpan dokumen sebagai file teks, pertama-tama kita perlu membuat dokumen menggunakan Aspose.Words. Berikut cuplikan kode Java sederhana untuk membuat dokumen dengan beberapa konten:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.writeln("Hello world!");
builder.getParagraphFormat().setBidi(true);
builder.writeln("שלום עולם!");
builder.writeln("مرحبا بالعالم!");
```

Dalam kode ini, kita membuat dokumen baru dan menambahkan beberapa teks ke dalamnya, termasuk teks dalam berbagai bahasa.

## Langkah 2: Tentukan Opsi Penyimpanan Teks

Selanjutnya, kita perlu menentukan opsi penyimpanan teks yang menentukan bagaimana dokumen harus disimpan sebagai file teks. Kita dapat mengkonfigurasi berbagai pengaturan seperti menambahkan tanda bidi, indentasi daftar, dan lainnya. Mari kita lihat dua contoh:

### Contoh 1: Menambahkan Tanda Bidi

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.setAddBidiMarks(true);
doc.save("output.txt", saveOptions);
```

 Dalam contoh ini, kita membuat a`TxtSaveOptions` objek dan atur`AddBidiMarks`properti ke`true` untuk memasukkan tanda bidi dalam keluaran teks.

### Contoh 2: Menggunakan Karakter Tab untuk Indentasi Daftar

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.getListIndentation().setCount(1);
saveOptions.getListIndentation().setCharacter('\t');
doc.save("output.txt", saveOptions);
```

Di sini, kami mengonfigurasi opsi penyimpanan untuk menggunakan karakter tab untuk indentasi daftar dengan hitungan 1.

## Langkah 3: Simpan Dokumen sebagai Teks

Sekarang kita telah menentukan opsi penyimpanan teks, kita dapat menyimpan dokumen sebagai file teks. Kode berikut menunjukkan cara melakukan ini:

```java
doc.save("output.txt", saveOptions);
```

 Mengganti`"output.txt"` dengan jalur file yang diinginkan tempat Anda ingin menyimpan file teks.

## Kode Sumber Lengkap Untuk Menyimpan Dokumen sebagai File Teks di Aspose.Words untuk Java

```java
    public void addBidiMarks() throws Exception
    {        
		Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.writeln("Hello world!");
        builder.getParagraphFormat().setBidi(true);
        builder.writeln("שלום עולם!");
        builder.writeln("مرحبا بالعالم!");
        TxtSaveOptions saveOptions = new TxtSaveOptions(); { saveOptions.setAddBidiMarks(true); }
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
    }
    @Test
    public void useTabCharacterPerLevelForListIndentation() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // Buat daftar dengan tiga tingkat lekukan.
        builder.getListFormat().applyNumberDefault();
        builder.writeln("Item 1");
        builder.getListFormat().listIndent();
        builder.writeln("Item 2");
        builder.getListFormat().listIndent(); 
        builder.write("Item 3");
        TxtSaveOptions saveOptions = new TxtSaveOptions();
        saveOptions.getListIndentation().setCount(1);
        saveOptions.getListIndentation().setCharacter('\t');
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt", saveOptions);
    }
    @Test
    public void useSpaceCharacterPerLevelForListIndentation() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // Buat daftar dengan tiga tingkat lekukan.
        builder.getListFormat().applyNumberDefault();
        builder.writeln("Item 1");
        builder.getListFormat().listIndent();
        builder.writeln("Item 2");
        builder.getListFormat().listIndent(); 
        builder.write("Item 3");
        TxtSaveOptions saveOptions = new TxtSaveOptions();
        saveOptions.getListIndentation().setCount(3);
        saveOptions.getListIndentation().setCharacter(' ');
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
	}
```

## Kesimpulan

Dalam tutorial ini, kita telah mempelajari cara menyimpan dokumen sebagai file teks di Aspose.Words untuk Java. Kami membahas langkah-langkah untuk membuat dokumen, menentukan opsi penyimpanan teks, dan menyimpan dokumen dalam format teks. Aspose.Words memberikan fleksibilitas luas dalam hal menyimpan dokumen, memungkinkan Anda menyesuaikan keluaran dengan kebutuhan spesifik Anda.

## FAQ

### Bagaimana cara menambahkan tanda bidi ke keluaran teks?

 Untuk menambahkan tanda bidi pada keluaran teks, atur`AddBidiMarks` milik`TxtSaveOptions` ke`true`. Misalnya:

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.setAddBidiMarks(true);
```

### Bisakah saya mengkustomisasi karakter lekukan daftar?

 Ya, Anda dapat menyesuaikan karakter indentasi daftar dengan mengonfigurasi`ListIndentation` milik`TxtSaveOptions`. Misalnya, untuk menggunakan karakter tab untuk indentasi daftar, Anda dapat melakukan hal berikut:

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.getListIndentation().setCount(1);
saveOptions.getListIndentation().setCharacter('\t');
```

### Apakah Aspose.Words untuk Java cocok untuk menangani teks multibahasa?

Ya, Aspose.Words for Java cocok untuk menangani teks multibahasa. Ini mendukung berbagai bahasa dan pengkodean karakter, menjadikannya pilihan serbaguna untuk bekerja dengan dokumen dalam berbagai bahasa.

### Bagaimana saya bisa mengakses lebih banyak dokumentasi dan sumber daya untuk Aspose.Words untuk Java?

 Anda dapat menemukan dokumentasi dan sumber daya komprehensif untuk Aspose.Words untuk Java di situs web dokumentasi Aspose:[Aspose.Words untuk Dokumentasi Java](https://reference.aspose.com/words/java/).

### Di mana saya dapat mengunduh Aspose.Words untuk Java?

 Anda dapat mengunduh perpustakaan Aspose.Words untuk Java dari situs web Aspose:[Unduh Aspose.Words untuk Java](https://releases.aspose.com/words/java/).