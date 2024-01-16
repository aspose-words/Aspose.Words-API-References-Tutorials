---
title: Menggabungkan dan Menambahkan Dokumen di Aspose.Words untuk Java
linktitle: Menggabungkan dan Menambahkan Dokumen
second_title: API Pemrosesan Dokumen Java Aspose.Words
description: Pelajari cara menggabungkan dan menambahkan dokumen dengan mudah menggunakan Aspose.Words untuk Java. Pertahankan pemformatan, kelola header dan footer, dan banyak lagi.
type: docs
weight: 30
url: /id/java/document-manipulation/joining-and-appending-documents/
---

## Pengantar Menggabungkan dan Menambahkan Dokumen di Aspose.Words untuk Java

Dalam tutorial ini, kita akan menjelajahi cara menggabungkan dan menambahkan dokumen menggunakan pustaka Aspose.Words untuk Java. Anda akan mempelajari cara menggabungkan beberapa dokumen dengan mulus sambil mempertahankan format dan struktur.

## Prasyarat

Sebelum kita mulai, pastikan Anda telah menyiapkan Aspose.Words for Java API di proyek Java Anda.

## Opsi Penggabungan Dokumen

### Tambahkan Sederhana

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### Tambahkan dengan Opsi Format Impor

```java
ImportFormatOptions options = new ImportFormatOptions();
options.setKeepSourceNumbering(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES, options);
```

### Tambahkan ke Dokumen Kosong

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document();
dstDoc.removeAllChildren();
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### Tambahkan dengan Konversi Nomor Halaman

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
convertNumPageFieldsToPageRef(dstDoc); // Konversi bidang NUMPAGES
dstDoc.updatePageLayout(); // Perbarui tata letak halaman untuk penomoran yang benar
```

## Menangani Pengaturan Halaman yang Berbeda

Saat menambahkan dokumen dengan pengaturan halaman berbeda:

```java
srcDoc.getFirstSection().getPageSetup().setSectionStart(SectionStart.CONTINUOUS);
srcDoc.getFirstSection().getPageSetup().setRestartPageNumbering(true);
// Pastikan pengaturan pengaturan halaman sesuai dengan dokumen tujuan
```

## Menggabungkan Dokumen dengan Gaya Berbeda

```java
dstDoc.appendDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES);
```

## Perilaku Gaya Cerdas

```java
ImportFormatOptions options = new ImportFormatOptions();
options.setSmartStyleBehavior(true);
builder.insertDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES, options);
```

## Memasukkan Dokumen dengan DocumentBuilder

```java
DocumentBuilder builder = new DocumentBuilder(dstDoc);
builder.insertDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

## Menjaga Penomoran Sumber

```java
ImportFormatOptions importFormatOptions = new ImportFormatOptions();
importFormatOptions.setKeepSourceNumbering(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING, importFormatOptions);
```

## Menangani Kotak Teks

```java
ImportFormatOptions importFormatOptions = new ImportFormatOptions();
importFormatOptions.setIgnoreTextBoxes(false);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING, importFormatOptions);
```

## Mengelola Header dan Footer

### Menghubungkan Header dan Footer

```java
srcDoc.getFirstSection().getHeadersFooters().linkToPrevious(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### Membatalkan Tautan Header dan Footer

```java
srcDoc.getFirstSection().getHeadersFooters().linkToPrevious(false);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

## Kesimpulan

Aspose.Words untuk Java menyediakan alat yang fleksibel dan canggih untuk menggabungkan dan menambahkan dokumen, baik Anda perlu mempertahankan pemformatan, menangani pengaturan halaman yang berbeda, atau mengelola header dan footer. Bereksperimenlah dengan teknik ini untuk memenuhi kebutuhan spesifik pemrosesan dokumen Anda.

## FAQ

### Bagaimana cara menggabungkan dokumen dengan gaya berbeda dengan lancar?

 Untuk menggabungkan dokumen dengan gaya berbeda, gunakan`ImportFormatMode.USE_DESTINATION_STYLES` saat menambahkan.

### Bisakah saya mempertahankan penomoran halaman saat menambahkan dokumen?

 Ya, Anda dapat mempertahankan penomoran halaman dengan menggunakan`convertNumPageFieldsToPageRef` metode dan memperbarui tata letak halaman.

### Apa itu Perilaku Gaya Cerdas?

 Smart Style Behavior membantu mempertahankan gaya yang konsisten saat menambahkan dokumen. Gunakan dengan`ImportFormatOptions` untuk hasil yang lebih baik.

### Bagaimana cara menangani kotak teks saat menambahkan dokumen?

Mengatur`importFormatOptions.setIgnoreTextBoxes(false)` untuk menyertakan kotak teks selama penambahan.

### Bagaimana jika saya ingin menautkan/membatalkan tautan header dan footer antar dokumen?

 Anda dapat menautkan header dan footer dengan`linkToPrevious(true)` atau putuskan tautannya`linkToPrevious(false)` sesuai kebutuhan.