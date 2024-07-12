---
title: Menggunakan Properti Dokumen di Aspose.Words untuk Java
linktitle: Menggunakan Properti Dokumen
second_title: API Pemrosesan Dokumen Java Aspose.Words
description: Optimalkan manajemen dokumen dengan Aspose.Words untuk Java. Pelajari cara bekerja dengan properti dokumen, menambahkan metadata khusus, dan banyak lagi dalam tutorial komprehensif ini.
type: docs
weight: 32
url: /id/java/document-manipulation/using-document-properties/
---

## Pengantar Properti Dokumen

Properti dokumen adalah bagian penting dari dokumen apa pun. Mereka memberikan informasi tambahan tentang dokumen itu sendiri, seperti judul, penulis, subjek, kata kunci, dan banyak lagi. Di Aspose.Words untuk Java, Anda dapat memanipulasi properti dokumen bawaan dan kustom.

## Menghitung Properti Dokumen

### Properti Bawaan

Untuk mengambil dan bekerja dengan properti dokumen bawaan, Anda dapat menggunakan cuplikan kode berikut:

```java
@Test
public void enumerateProperties() throws Exception
{
    Document doc = new Document("Your Directory Path" + "Properties.docx");
    System.out.println(MessageFormat.format("1. Document name: {0}", doc.getOriginalFileName()));
    System.out.println("2. Built-in Properties");
    for (DocumentProperty prop : doc.getBuiltInDocumentProperties())
        System.out.println(MessageFormat.format("{0} : {1}", prop.getName(), prop.getValue()));
}
```

Kode ini akan menampilkan nama dokumen dan properti bawaannya, termasuk properti seperti "Judul", "Penulis", dan "Kata Kunci".

### Properti Kustom

Untuk bekerja dengan properti dokumen kustom, Anda dapat menggunakan cuplikan kode berikut:

```java
@Test
public void addCustomDocumentProperties() throws Exception
{
    Document doc = new Document("Your Directory Path" + "Properties.docx");
    CustomDocumentProperties customDocumentProperties = doc.getCustomDocumentProperties();

    if (customDocumentProperties.get("Authorized") != null) return;

    customDocumentProperties.add("Authorized", true);
    customDocumentProperties.add("Authorized By", "John Smith");
    customDocumentProperties.add("Authorized Date", new Date());
    customDocumentProperties.add("Authorized Revision", doc.getBuiltInDocumentProperties().getRevisionNumber());
    customDocumentProperties.add("Authorized Amount", 123.45);
}
```

Cuplikan kode ini menunjukkan cara menambahkan properti dokumen kustom, termasuk nilai boolean, string, tanggal, nomor revisi, dan nilai numerik.

## Menghapus Properti Dokumen

Untuk menghapus properti dokumen tertentu, Anda dapat menggunakan kode berikut:

```java
@Test
public void removeCustomDocumentProperties() throws Exception
{
    Document doc = new Document("Your Directory Path" + "Properties.docx");
    doc.getCustomDocumentProperties().remove("Authorized Date");
}
```

Kode ini menghapus properti khusus "Tanggal Resmi" dari dokumen.

## Mengonfigurasi Tautan ke Konten

Dalam beberapa kasus, Anda mungkin ingin membuat link dalam dokumen Anda. Inilah cara Anda melakukannya:

```java
@Test
public void configuringLinkToContent() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.startBookmark("MyBookmark");
    builder.writeln("Text inside a bookmark.");
    builder.endBookmark("MyBookmark");

    CustomDocumentProperties customProperties = doc.getCustomDocumentProperties();

    // Tambahkan properti tertaut ke konten.
    DocumentProperty customProperty = customProperties.addLinkToContent("Bookmark", "MyBookmark");
    customProperty = customProperties.get("Bookmark");
    boolean isLinkedToContent = customProperty.isLinkToContent();
    String linkSource = customProperty.getLinkSource();
    String customPropertyValue = customProperty.getValue().toString();
}
```

Cuplikan kode ini menunjukkan cara membuat bookmark di dokumen Anda dan menambahkan properti dokumen khusus yang tertaut ke bookmark tersebut.

## Konversi Antar Satuan Pengukuran

Di Aspose.Words untuk Java, Anda dapat mengonversi satuan pengukuran dengan mudah. Berikut ini contoh cara melakukannya:

```java
@Test
public void convertBetweenMeasurementUnits() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    PageSetup pageSetup = builder.getPageSetup();

    // Tetapkan margin dalam inci.
    pageSetup.setTopMargin(ConvertUtil.inchToPoint(1.0));
    pageSetup.setBottomMargin(ConvertUtil.inchToPoint(1.0));
    pageSetup.setLeftMargin(ConvertUtil.inchToPoint(1.5));
    pageSetup.setRightMargin(ConvertUtil.inchToPoint(1.5));
    pageSetup.setHeaderDistance(ConvertUtil.inchToPoint(0.2));
    pageSetup.setFooterDistance(ConvertUtil.inchToPoint(0.2));
}
```

Cuplikan kode ini menetapkan berbagai margin dan jarak dalam inci dengan mengonversinya menjadi poin.

## Menggunakan Karakter Kontrol

Karakter kontrol dapat berguna ketika berhadapan dengan teks. Berikut cara mengganti karakter kontrol dalam teks Anda:

```java
@Test
public void useControlCharacters()
{
    final String TEXT = "test\r";

    // Ganti karakter kontrol "\r" dengan "\r\n".
    String replace = TEXT.replace(ControlChar.CR, ControlChar.CR_LF);
}
```

Dalam contoh ini, kami mengganti carriage return (`\r`) dengan pengangkutan kembali diikuti dengan umpan baris (`\r\n`).

## Kesimpulan

Properti dokumen memainkan peran penting dalam mengelola dan mengatur dokumen Anda secara efektif di Aspose.Words untuk Java. Baik itu bekerja dengan properti bawaan, properti kustom, atau menggunakan karakter kontrol, Anda memiliki serangkaian alat yang dapat Anda gunakan untuk meningkatkan kemampuan manajemen dokumen Anda.

## FAQ

### Bagaimana cara mengakses properti dokumen bawaan?

 Untuk mengakses properti dokumen bawaan di Aspose.Words untuk Java, Anda dapat menggunakan`getBuiltInDocumentProperties` metode pada`Document` obyek. Metode ini mengembalikan kumpulan properti bawaan yang dapat Anda ulangi.

### Bisakah saya menambahkan properti dokumen khusus ke dokumen?

 Ya, Anda dapat menambahkan properti dokumen kustom ke dokumen menggunakan`CustomDocumentProperties` koleksi. Anda dapat menentukan properti kustom dengan berbagai tipe data, termasuk string, boolean, tanggal, dan nilai numerik.

### Bagaimana cara menghapus properti dokumen khusus tertentu?

 Untuk menghapus properti dokumen kustom tertentu, Anda dapat menggunakan`remove` metode pada`CustomDocumentProperties`koleksi, meneruskan nama properti yang ingin Anda hapus sebagai parameter.

### Apa tujuan menautkan ke konten dalam dokumen?

Menautkan ke konten dalam dokumen memungkinkan Anda membuat referensi dinamis ke bagian tertentu dari dokumen. Hal ini dapat berguna untuk membuat dokumen interaktif atau referensi silang antar bagian.

### Bagaimana cara mengonversi unit pengukuran yang berbeda di Aspose.Words untuk Java?

 Anda dapat mengonversi antara unit pengukuran yang berbeda di Aspose.Words untuk Java dengan menggunakan`ConvertUtil` kelas. Ini menyediakan metode untuk mengonversi satuan seperti inci ke titik, titik ke sentimeter, dan banyak lagi.