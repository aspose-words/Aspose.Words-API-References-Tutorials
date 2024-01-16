---
title: Menghasilkan Daftar Isi di Aspose.Words untuk Java
linktitle: Menghasilkan Daftar Isi
second_title: API Pemrosesan Dokumen Java Aspose.Words
description: Pelajari cara membuat dan menyesuaikan Daftar Isi (TOC) menggunakan Aspose.Words untuk Java. Buat dokumen yang terorganisir dan profesional dengan mudah.
type: docs
weight: 21
url: /id/java/document-manipulation/generating-table-of-contents/
---

## Pengantar Membuat Daftar Isi di Aspose.Words untuk Java

Dalam tutorial ini, kami akan memandu Anda melalui proses pembuatan Daftar Isi (TOC) menggunakan Aspose.Words untuk Java. TOC adalah fitur penting untuk membuat dokumen terorganisir. Kami akan membahas cara menyesuaikan tampilan dan tata letak TOC.

## Prasyarat

Sebelum memulai, pastikan Anda telah menginstal dan menyiapkan Aspose.Words for Java di proyek Java Anda.

## Langkah 1: Buat Dokumen Baru

Pertama, mari buat dokumen baru untuk dikerjakan.

```java
Document doc = new Document();
```

## Langkah 2: Sesuaikan Gaya TOC

Untuk menyesuaikan tampilan TOC Anda, Anda dapat memodifikasi gaya yang terkait dengannya. Dalam contoh ini, kita akan membuat entri TOC tingkat pertama menjadi tebal.

```java
doc.getStyles().getByStyleIdentifier(StyleIdentifier.TOC_1).getFont().setBold(true);
```

## Langkah 3: Tambahkan Konten ke Dokumen Anda

Anda dapat menambahkan konten Anda ke dokumen. Konten ini akan digunakan untuk menghasilkan TOC.

## Langkah 4: Hasilkan TOC

Untuk menghasilkan TOC, masukkan kolom TOC di lokasi yang diinginkan dalam dokumen Anda. Bidang ini akan terisi secara otomatis berdasarkan judul dan gaya di dokumen Anda.

```java
// Masukkan bidang TOC di lokasi yang diinginkan dalam dokumen Anda.
FieldToc fieldToc = new FieldToc();
doc.getFirstSection().getBody().getFirstParagraph().appendChild(fieldToc);
```

## Langkah 5: Simpan Dokumen

Terakhir, simpan dokumen dengan TOC.

```java
doc.save("your_output_path_here");
```

## Menyesuaikan Tab Stop di TOC

Anda juga dapat menyesuaikan perhentian tab di TOC Anda untuk mengontrol tata letak nomor halaman. Inilah cara Anda dapat mengubah perhentian tab:

```java
Document doc = new Document("Table of contents.docx");

for (Paragraph para : (Iterable<Paragraph>) doc.getChildNodes(NodeType.PARAGRAPH, true))
{
    if (para.getParagraphFormat().getStyle().getStyleIdentifier() >= StyleIdentifier.TOC_1 &&
        para.getParagraphFormat().getStyle().getStyleIdentifier() <= StyleIdentifier.TOC_9)
    {
        //Gunakan tab pertama dalam paragraf ini, yang menyelaraskan nomor halaman.
        TabStop tab = para.getParagraphFormat().getTabStops().get(0);
        
        // Hapus tab lama.
        para.getParagraphFormat().getTabStops().removeByPosition(tab.getPosition());
        
        // Sisipkan tab baru pada posisi yang diubah (misalnya 50 unit ke kiri).
        para.getParagraphFormat().getTabStops().add(tab.getPosition() - 50.0, tab.getAlignment(), tab.getLeader());
    }
}

doc.save("output.docx");
```

Sekarang Anda memiliki Daftar Isi yang disesuaikan dalam dokumen Anda dengan perhentian tab yang disesuaikan untuk perataan nomor halaman.


## Kesimpulan

Dalam tutorial ini, kita telah menjelajahi cara membuat Daftar Isi (TOC) menggunakan Aspose.Words untuk Java, perpustakaan canggih untuk bekerja dengan dokumen Word. TOC yang terstruktur dengan baik sangat penting untuk mengatur dan menavigasi dokumen yang panjang, dan Aspose.Words menyediakan alat untuk membuat dan menyesuaikan TOC dengan mudah.

## FAQ

### Bagaimana cara mengubah format entri TOC?

 Anda dapat memodifikasi gaya yang terkait dengan level TOC menggunakan`doc.getStyles().getByStyleIdentifier(StyleIdentifier.TOC_X)`, di mana X adalah tingkat TOC.

### Bagaimana cara menambahkan lebih banyak level ke TOC saya?

Untuk memasukkan lebih banyak level dalam TOC Anda, Anda dapat memodifikasi kolom TOC dan menentukan jumlah level yang diinginkan.

### Bisakah saya mengubah posisi tab stop untuk entri TOC tertentu?

Ya, seperti yang ditunjukkan pada contoh kode di atas, Anda dapat mengubah posisi tab stop untuk entri TOC tertentu dengan mengulangi paragraf dan memodifikasi tab stop sesuai dengan itu.