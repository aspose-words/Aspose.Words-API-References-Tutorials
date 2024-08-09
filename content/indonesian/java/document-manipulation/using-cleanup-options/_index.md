---
title: Menggunakan Opsi Pembersihan di Aspose.Words untuk Java
linktitle: Menggunakan Opsi Pembersihan
second_title: API Pemrosesan Dokumen Java Aspose.Words
description: Tingkatkan Kejelasan Dokumen dengan Aspose.Words untuk Opsi Pembersihan Java. Pelajari cara menghapus paragraf kosong, wilayah yang tidak digunakan, dan banyak lagi.
type: docs
weight: 10
url: /id/java/document-manipulation/using-cleanup-options/
---

## Pengantar Menggunakan Opsi Pembersihan di Aspose.Words untuk Java

Dalam tutorial ini, kita akan mempelajari cara menggunakan opsi pembersihan di Aspose.Words untuk Java untuk memanipulasi dan membersihkan dokumen selama proses penggabungan surat. Opsi pembersihan memungkinkan Anda mengontrol berbagai aspek pembersihan dokumen, seperti menghapus paragraf kosong, area yang tidak digunakan, dan banyak lagi.

## Prasyarat

 Sebelum kita mulai, pastikan Anda memiliki perpustakaan Aspose.Words untuk Java yang terintegrasi ke dalam proyek Anda. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/words/java/).

## Langkah 1: Menghapus Paragraf Kosong

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Sisipkan bidang gabungan
FieldMergeField mergeFieldOption1 = (FieldMergeField) builder.insertField("MERGEFIELD", "Option_1");
mergeFieldOption1.setFieldName("Option_1");
builder.write(" ? ");
FieldMergeField mergeFieldOption2 = (FieldMergeField) builder.insertField("MERGEFIELD", "Option_2");
mergeFieldOption2.setFieldName("Option_2");

// Tetapkan opsi pembersihan
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_PARAGRAPHS);

// Aktifkan paragraf pembersihan dengan tanda baca
doc.getMailMerge().setCleanupParagraphsWithPunctuationMarks(true);

// Jalankan gabungan surat
doc.getMailMerge().execute(new String[] { "Option_1", "Option_2" }, new Object[] { null, null });

// Simpan dokumennya
doc.save("WorkingWithCleanupOptions.CleanupParagraphsWithPunctuationMarks.docx");
```

Dalam contoh ini, kita membuat dokumen baru, menyisipkan bidang gabungan, dan mengatur opsi pembersihan untuk menghapus paragraf kosong. Selain itu, kami mengaktifkan penghapusan paragraf dengan tanda baca. Setelah menjalankan gabungan surat, dokumen disimpan dengan pembersihan yang ditentukan diterapkan.

## Langkah 2: Menghapus Wilayah yang Tidak Digabung

```java
Document doc = new Document("Your Directory Path" + "Mail merge destination - Northwind suppliers.docx");
DataSet data = new DataSet();

// Atur opsi pembersihan untuk menghapus wilayah yang tidak digunakan
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_UNUSED_REGIONS);

// Jalankan gabungan surat dengan wilayah
doc.getMailMerge().executeWithRegions(data);

// Simpan dokumennya
doc.save("WorkingWithCleanupOptions.RemoveUnmergedRegions.docx");
```

Dalam contoh ini, kita membuka dokumen yang sudah ada dengan wilayah gabungan, mengatur opsi pembersihan untuk menghapus wilayah yang tidak digunakan, lalu menjalankan gabungan surat dengan data kosong. Proses ini secara otomatis menghapus wilayah yang tidak digunakan dari dokumen.

## Langkah 3: Menghapus Bidang Kosong

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// Atur opsi pembersihan untuk menghapus bidang kosong
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_FIELDS);

// Jalankan gabungan surat
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// Simpan dokumennya
doc.save("WorkingWithCleanupOptions.RemoveEmptyFields.docx");
```

Dalam contoh ini, kita membuka dokumen dengan bidang gabungan, mengatur opsi pembersihan untuk menghapus bidang kosong, dan menjalankan gabungan surat dengan data. Setelah penggabungan, kolom kosong apa pun akan dihapus dari dokumen.

## Langkah 4: Menghapus Bidang yang Tidak Digunakan

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// Atur opsi pembersihan untuk menghapus bidang yang tidak digunakan
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_UNUSED_FIELDS);

// Jalankan gabungan surat
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// Simpan dokumennya
doc.save("WorkingWithCleanupOptions.RemoveUnusedFields.docx");
```

Dalam contoh ini, kita membuka dokumen dengan bidang gabungan, mengatur opsi pembersihan untuk menghapus bidang yang tidak digunakan, dan menjalankan gabungan surat dengan data. Setelah penggabungan, semua bidang yang tidak digunakan akan dihapus dari dokumen.

## Langkah 5: Menghapus Bidang yang Berisi

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// Atur opsi pembersihan untuk menghapus bidang yang berisi
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_CONTAINING_FIELDS);

// Jalankan gabungan surat
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// Simpan dokumennya
doc.save("WorkingWithCleanupOptions.RemoveContainingFields.docx");
```

Dalam contoh ini, kita membuka dokumen dengan bidang gabungan, mengatur opsi pembersihan untuk menghapus bidang yang berisi, dan menjalankan gabungan surat dengan data. Setelah penggabungan, bidang itu sendiri akan dihapus dari dokumen.

## Langkah 6: Menghapus Baris Tabel Kosong

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// Atur opsi pembersihan untuk menghapus baris tabel kosong
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_TABLE_ROWS);

// Jalankan gabungan surat
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// Simpan dokumennya
doc.save("WorkingWithCleanupOptions.RemoveEmptyTableRows.docx");
```

Dalam contoh ini, kita membuka dokumen dengan tabel dan bidang gabungan, mengatur opsi pembersihan untuk menghapus baris tabel kosong, dan menjalankan gabungan surat dengan data. Setelah penggabungan, setiap baris tabel kosong akan dihapus dari dokumen.

## Kesimpulan

Dalam tutorial ini, Anda telah mempelajari cara menggunakan opsi pembersihan di Aspose.Words untuk Java untuk memanipulasi dan membersihkan dokumen selama proses penggabungan surat. Opsi ini memberikan kontrol menyeluruh atas pembersihan dokumen, memungkinkan Anda membuat dokumen yang disempurnakan dan disesuaikan dengan mudah.

## FAQ

### Apa saja opsi pembersihan di Aspose.Words untuk Java?

Opsi pembersihan di Aspose.Words untuk Java adalah pengaturan yang memungkinkan Anda mengontrol berbagai aspek pembersihan dokumen selama proses penggabungan surat. Mereka memungkinkan Anda untuk menghapus elemen yang tidak perlu seperti paragraf kosong, wilayah yang tidak terpakai, dan banyak lagi, memastikan dokumen akhir Anda terstruktur dan dipoles dengan baik.

### Bagaimana cara menghapus paragraf kosong dari dokumen saya?

 Untuk menghapus paragraf kosong dari dokumen Anda menggunakan Aspose.Words untuk Java, Anda dapat mengatur`MailMergeCleanupOptions.REMOVE_EMPTY_PARAGRAPHS` pilihan menjadi benar. Ini secara otomatis akan menghilangkan paragraf yang tidak memiliki konten, sehingga menghasilkan dokumen yang lebih bersih.

###  Apa tujuan dari`REMOVE_UNUSED_REGIONS` cleanup option?

 Itu`MailMergeCleanupOptions.REMOVE_UNUSED_REGIONS` Opsi ini digunakan untuk menghapus wilayah dalam dokumen yang tidak memiliki data terkait selama proses penggabungan surat. Ini membantu menjaga dokumen Anda tetap rapi dengan membuang placeholder yang tidak digunakan.

### Bisakah saya menghapus baris tabel kosong dari dokumen menggunakan Aspose.Words untuk Java?

 Ya, Anda dapat menghapus baris tabel kosong dari dokumen dengan mengatur`MailMergeCleanupOptions.REMOVE_EMPTY_TABLE_ROWS`opsi pembersihan ke true. Ini secara otomatis akan menghapus baris tabel apa pun yang tidak berisi data, memastikan tabel terstruktur dengan baik di dokumen Anda.

###  Apa yang terjadi ketika saya menyetel`REMOVE_CONTAINING_FIELDS` option?

 Mengatur`MailMergeCleanupOptions.REMOVE_CONTAINING_FIELDS` opsi ini akan menghapus seluruh bidang gabungan, termasuk paragraf yang memuatnya, dari dokumen selama proses gabungan surat. Ini berguna ketika Anda ingin menghilangkan bidang gabungan dan teks terkait.

### Bagaimana cara menghapus bidang gabungan yang tidak digunakan dari dokumen saya?

 Untuk menghapus bidang gabungan yang tidak digunakan dari dokumen, Anda dapat mengatur`MailMergeCleanupOptions.REMOVE_UNUSED_FIELDS` pilihan menjadi benar. Ini secara otomatis akan menghilangkan bidang gabungan yang tidak diisi selama penggabungan surat, sehingga menghasilkan dokumen yang lebih bersih.

###  Apa perbedaan antara`REMOVE_EMPTY_FIELDS` and `REMOVE_UNUSED_FIELDS` cleanup options?

 Itu`REMOVE_EMPTY_FIELDS` opsi menghapus bidang gabungan yang tidak memiliki data atau kosong selama proses penggabungan surat. Di sisi lain,`REMOVE_UNUSED_FIELDS`opsi menghapus bidang gabungan yang tidak diisi dengan data selama penggabungan. Pilihan di antara keduanya bergantung pada apakah Anda ingin menghapus bidang yang tidak berisi konten atau bidang yang tidak digunakan dalam operasi penggabungan tertentu.

### Bagaimana cara mengaktifkan penghapusan paragraf dengan tanda baca?

 Untuk mengaktifkan penghapusan paragraf dengan tanda baca, Anda dapat mengatur`cleanupParagraphsWithPunctuationMarks` opsi ke true dan tentukan tanda baca yang akan dipertimbangkan untuk pembersihan. Hal ini memungkinkan Anda membuat dokumen yang lebih halus dengan menghapus paragraf yang hanya berisi tanda baca yang tidak perlu.

### Bisakah saya menyesuaikan opsi pembersihan di Aspose.Words untuk Java?

Ya, Anda dapat menyesuaikan opsi pembersihan sesuai dengan kebutuhan spesifik Anda. Anda dapat memilih opsi pembersihan mana yang akan diterapkan dan mengonfigurasinya sesuai kebutuhan pembersihan dokumen Anda, memastikan bahwa dokumen akhir Anda memenuhi standar yang Anda inginkan.