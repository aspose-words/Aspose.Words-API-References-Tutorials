---
title: Menemukan dan Mengganti Teks di Aspose.Words untuk Java
linktitle: Menemukan dan Mengganti Teks
second_title: API Pemrosesan Dokumen Java Aspose.Words
description: Pelajari cara menemukan dan mengganti teks dalam dokumen Word dengan Aspose.Words untuk Java. Panduan langkah demi langkah dengan contoh kode. Tingkatkan keterampilan manipulasi dokumen Java Anda.
type: docs
weight: 15
url: /id/java/document-manipulation/finding-and-replacing-text/
---

## Pengantar Menemukan dan Mengganti Teks di Aspose.Words untuk Java

Aspose.Words for Java adalah Java API canggih yang memungkinkan Anda bekerja dengan dokumen Word secara terprogram. Salah satu tugas umum saat menangani dokumen Word adalah mencari dan mengganti teks. Baik Anda perlu memperbarui placeholder di templat atau melakukan manipulasi teks yang lebih kompleks, Aspose.Words untuk Java dapat membantu Anda mencapai tujuan secara efisien.

## Prasyarat

Sebelum kita mendalami detail pencarian dan penggantian teks, pastikan Anda memiliki prasyarat berikut:

- Lingkungan Pengembangan Jawa
- Aspose.Words untuk perpustakaan Java
- Contoh dokumen Word untuk digunakan

 Anda dapat mengunduh perpustakaan Aspose.Words untuk Java dari[Di Sini](https://releases.aspose.com/words/java/).

## Menemukan dan Mengganti Teks Sederhana

```java
// Muat dokumen
Document doc = new Document("your-document.docx");

// Buat Pembuat Dokumen
DocumentBuilder builder = new DocumentBuilder(doc);

// Temukan dan ganti teks
builder.getRange().replace("old-text", "new-text", new FindReplaceOptions());

// Simpan dokumen yang diubah
doc.save("modified-document.docx");
```

 Dalam contoh ini, kita memuat dokumen Word, membuat a`DocumentBuilder` , dan gunakan`replace` metode untuk menemukan dan mengganti "teks lama" dengan "teks baru" di dalam dokumen.

## Menggunakan Ekspresi Reguler

Ekspresi reguler memberikan kemampuan pencocokan pola yang kuat untuk pencarian dan penggantian teks. Aspose.Words untuk Java mendukung ekspresi reguler untuk operasi pencarian dan penggantian lebih lanjut.

```java
// Muat dokumen
Document doc = new Document("your-document.docx");

// Buat Pembuat Dokumen
DocumentBuilder builder = new DocumentBuilder(doc);

// Gunakan ekspresi reguler untuk menemukan dan mengganti teks
Pattern regex = Pattern.compile("your-pattern");
builder.getRange().replace(regex, "replacement-text", new FindReplaceOptions());

// Simpan dokumen yang diubah
doc.save("modified-document.docx");
```

Dalam contoh ini, kami menggunakan pola ekspresi reguler untuk mencari dan mengganti teks dalam dokumen.

## Mengabaikan Teks di Dalam Bidang

Anda dapat mengonfigurasi Aspose.Words untuk mengabaikan teks di dalam bidang saat melakukan operasi pencarian dan penggantian.

```java
// Muat dokumen
Document doc = new Document("your-document.docx");

// Buat instance FindReplaceOptions dan atur IgnoreFields ke true
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreFields(true);

// Gunakan opsi saat mengganti teks
doc.getRange().replace("text-to-replace", "new-text", options);

// Simpan dokumen yang diubah
doc.save("modified-document.docx");
```

Ini berguna ketika Anda ingin mengecualikan teks di dalam bidang, seperti bidang gabungan, agar tidak diganti.

## Mengabaikan Teks Di Dalam Hapus Revisi

Anda dapat mengonfigurasi Aspose.Words untuk mengabaikan teks di dalam revisi penghapusan selama operasi pencarian dan penggantian.

```java
// Muat dokumen
Document doc = new Document("your-document.docx");

// Buat instance FindReplaceOptions dan setel IgnoreDeleted ke true
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreDeleted(true);

// Gunakan opsi saat mengganti teks
doc.getRange().replace("text-to-replace", "new-text", options);

// Simpan dokumen yang diubah
doc.save("modified-document.docx");
```

Ini memungkinkan Anda mengecualikan teks yang telah ditandai untuk dihapus dalam perubahan terlacak agar tidak diganti.

## Mengabaikan Revisi Sisipkan Teks di Dalam

Anda dapat mengonfigurasi Aspose.Words untuk mengabaikan teks di dalam revisi penyisipan selama operasi pencarian dan penggantian.

```java
// Muat dokumen
Document doc = new Document("your-document.docx");

// Buat instance FindReplaceOptions dan atur IgnoreInserted ke true
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreInserted(true);

// Gunakan opsi saat mengganti teks
doc.getRange().replace("text-to-replace", "new-text", options);

// Simpan dokumen yang diubah
doc.save("modified-document.docx");
```

Hal ini memungkinkan Anda mengecualikan teks yang telah ditandai sebagai disisipkan dalam perubahan terlacak agar tidak diganti.

## Mengganti Teks dengan HTML

Anda dapat menggunakan Aspose.Words for Java untuk mengganti teks dengan konten HTML.

```java
// Muat dokumen
Document doc = new Document("your-document.docx");

// Buat instance FindReplaceOptions dengan callback pengganti khusus
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceWithHtmlEvaluator(options));

// Gunakan opsi saat mengganti teks
doc.getRange().replace("text-to-replace", "new-html-content", options);

// Simpan dokumen yang diubah
doc.save("modified-document.docx");
```

 Dalam contoh ini, kami menggunakan custom`ReplaceWithHtmlEvaluator` untuk mengganti teks dengan konten HTML.

## Mengganti Teks di Header dan Footer

Anda dapat menemukan dan mengganti teks di dalam header dan footer dokumen Word Anda.

```java
// Muat dokumen
Document doc = new Document("your-document.docx");

// Dapatkan koleksi header dan footer
HeaderFooterCollection headersFooters = doc.getFirstSection().getHeadersFooters();

// Pilih jenis header atau footer yang ingin Anda ganti teksnya (misalnya, HeaderFooterType.FOOTER_PRIMARY)
HeaderFooter footer = headersFooters.getByHeaderFooterType(HeaderFooterType.FOOTER_PRIMARY);

// Buat instance FindReplaceOptions dan terapkan ke rentang footer
FindReplaceOptions options = new FindReplaceOptions();
footer.getRange().replace("text-to-replace", "new-text", options);

// Simpan dokumen yang diubah
doc.save("modified-document.docx");
```

Ini memungkinkan Anda melakukan penggantian teks khusus di header dan footer.

## Menampilkan Perubahan Urutan Header dan Footer

Anda dapat menggunakan Aspose.Words untuk memperlihatkan perubahan urutan header dan footer di dokumen Anda.

```java
// Muat dokumen
Document doc = new Document("your-document.docx");

// Dapatkan bagian pertama
Section firstPageSection = doc.getFirstSection();

// Buat instance FindReplaceOptions dan terapkan ke rentang dokumen
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceLog());

//Ganti teks yang memengaruhi urutan header dan footer
doc.getRange().replace(Pattern.compile("(header|footer)"), "", options);

// Simpan dokumen yang diubah
doc.save("modified-document.docx");
```

Ini memungkinkan Anda memvisualisasikan perubahan terkait urutan header dan footer di dokumen Anda.

## Mengganti Teks dengan Bidang

Anda dapat mengganti teks dengan kolom menggunakan Aspose.Words untuk Java.

```java
// Muat dokumen
Document doc = new Document("your-document.docx");

// Buat instance FindReplaceOptions dan atur panggilan balik pengganti khusus untuk bidang
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceTextWithFieldHandler(FieldType.FIELD_MERGE_FIELD));

// Gunakan opsi saat mengganti teks
doc.getRange().replace(Pattern.compile("PlaceHolder(\\d+)"), "", options);

// Simpan dokumen yang diubah
doc.save("modified-document.docx");
```

 Dalam contoh ini, kami mengganti teks dengan kolom dan menentukan jenis kolom (misalnya,`FieldType.FIELD_MERGE_FIELD`).

## Mengganti dengan Evaluator

Anda dapat menggunakan evaluator khusus untuk menentukan teks pengganti secara dinamis.

```java
// Muat dokumen
Document doc = new Document("your-document.docx");

// Buat instance FindReplaceOptions dan atur panggilan balik pengganti khusus
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new MyReplaceEvaluator());

// Gunakan opsi saat mengganti teks
doc.getRange().replace(Pattern.compile("[s|m]ad"), "", options);

// Simpan dokumen yang diubah
doc.save("modified-document.docx");
```

Dalam contoh ini, kami menggunakan evaluator khusus (`MyReplaceEvaluator`) untuk mengganti teks.

## Mengganti dengan Regex

Aspose.Words untuk Java memungkinkan Anda mengganti teks menggunakan ekspresi reguler.

```java
// Muat dokumen
Document doc = new Document("your-document.docx");

// Gunakan ekspresi reguler untuk menemukan dan mengganti teks
doc.getRange().replace(Pattern.compile("[s|m]ad"), "bad", new FindReplaceOptions());

// Simpan dokumen yang diubah
doc.save("modified-document.docx");
```

Dalam contoh ini, kami menggunakan pola ekspresi reguler untuk mencari dan mengganti teks dalam dokumen.

## Mengenali dan Mengganti Dalam Pola Penggantian

Anda dapat mengenali dan melakukan substitusi dalam pola penggantian menggunakan Aspose.Words untuk Java.

```java
// Muat dokumen
Document doc = new Document("your-document.docx");

//Buat instance FindReplaceOptions dengan UseSubstitutions disetel ke true
FindReplaceOptions options = new FindReplaceOptions();
options.setUseSubstitutions(true);

// Gunakan opsi saat mengganti teks dengan pola
doc.getRange().replace(Pattern.compile("([A-z]+) give money to ([A-z]+)"), "$2 take money from $1", options);

// Simpan dokumen yang diubah
doc.save("modified-document.docx");
```

Hal ini memungkinkan Anda melakukan substitusi dalam pola penggantian untuk penggantian lebih lanjut.

## Mengganti dengan String

Anda dapat mengganti teks dengan string sederhana menggunakan Aspose.Words untuk Java.

```java
// Muat dokumen
Document doc = new Document("your-document.docx");

// Ganti teks dengan string
doc.getRange().replace("text-to-replace", "new-string", new FindReplaceOptions());

// Simpan dokumen yang diubah
doc.save("modified-document.docx");
```

Dalam contoh ini, kami mengganti "text-to-replace" dengan "new-string" di dalam dokumen.

## Menggunakan Pesanan Lama

Anda dapat menggunakan pesanan lama saat melakukan operasi pencarian dan penggantian.

```java
// Muat dokumen
Document doc = new Document("your-document.docx");

// Buat instance FindReplaceOptions dan atur UseLegacyOrder ke true
FindReplaceOptions options = new FindReplaceOptions();
options.setUseLegacyOrder(true);

// Gunakan opsi saat mengganti teks
doc.getRange().replace(Pattern.compile("\\[(.*?)\\]"), "", options);

// Simpan dokumen yang diubah
doc.save("modified-document.docx");
```

Hal ini memungkinkan Anda menggunakan pesanan lama untuk operasi pencarian dan penggantian.

## Mengganti Teks dalam Tabel

Anda dapat menemukan dan mengganti teks dalam tabel di dokumen Word Anda.

```java
// Muat dokumen
Document doc = new Document("your-document.docx");

// Dapatkan tabel tertentu (misalnya, tabel pertama)
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);

// Gunakan FindReplaceOptions untuk mengganti teks dalam tabel
table.getRange().replace("old-text", "new-text", new FindReplaceOptions());

// Simpan dokumen yang diubah
doc.save("modified-document.docx");
```

Ini memungkinkan Anda melakukan penggantian teks secara khusus di dalam tabel.

## Kesimpulan

Aspose.Words untuk Java menyediakan kemampuan komprehensif untuk menemukan dan mengganti teks dalam dokumen Word. Apakah Anda perlu melakukan penggantian teks sederhana atau operasi lebih lanjut menggunakan ekspresi reguler, manipulasi bidang, atau evaluator khusus, Aspose.Words untuk Java siap membantu Anda. Pastikan untuk menjelajahi dokumentasi ekstensif dan contoh yang disediakan oleh Aspose untuk memanfaatkan potensi penuh dari perpustakaan Java yang kuat ini.

## FAQ

### Bagaimana cara mengunduh Aspose.Words untuk Java?

 Anda dapat mengunduh Aspose.Words untuk Java dari situs web dengan mengunjungi[Link ini](https://releases.aspose.com/words/java/).

### Bisakah saya menggunakan ekspresi reguler untuk penggantian teks?

Ya, Anda dapat menggunakan ekspresi reguler untuk penggantian teks di Aspose.Words untuk Java. Hal ini memungkinkan Anda melakukan operasi pencarian dan penggantian yang lebih canggih dan fleksibel.

### Bagaimana saya bisa mengabaikan teks di dalam kolom selama penggantian?

 Untuk mengabaikan teks di dalam kolom selama penggantian, Anda dapat mengatur`IgnoreFields` properti dari`FindReplaceOptions` ke`true`Hal ini memastikan bahwa teks di dalam bidang, seperti bidang gabungan, dikecualikan dari penggantian.

### Bisakah saya mengganti teks di dalam header dan footer?

 Ya, Anda dapat mengganti teks di dalam header dan footer dokumen Word Anda. Cukup akses header atau footer yang sesuai dan gunakan`replace` metode dengan yang diinginkan`FindReplaceOptions`.

### Untuk apa opsi UseLegacyOrder?

 Itu`UseLegacyOrder` pilihan di`FindReplaceOptions` memungkinkan Anda menggunakan pesanan lama saat melakukan operasi pencarian dan penggantian. Hal ini dapat berguna dalam skenario tertentu yang menginginkan perilaku tatanan warisan.