---
title: Pisahkan Dokumen Word Berdasarkan Bagian HTML
linktitle: Berdasarkan Bagian Html
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara membagi dokumen Word menjadi beberapa bagian Html menggunakan Aspose.Words untuk .NET dengan contoh kode lengkap.
type: docs
weight: 10
url: /id/net/split-document/by-sections-html/
---

Dalam contoh ini, kami akan menunjukkan kepada Anda cara membagi dokumen Word menjadi beberapa bagian terpisah dalam format HTML menggunakan fitur Berdasarkan Bagian HTML di Aspose.Words untuk .NET. Ikuti langkah-langkah di bawah ini untuk memahami kode sumber dan menghasilkan dokumen HTML terpisah untuk setiap bagian.

## Langkah 1: Memuat dokumen

Untuk memulai, tentukan direktori untuk dokumen Anda dan muat dokumen ke dalam objek Dokumen. Begini caranya:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## Langkah 2: Membagi dokumen menjadi beberapa bagian dalam format HTML

Sekarang kita akan mengatur opsi penyimpanan untuk membagi dokumen menjadi beberapa bagian dalam format HTML. Berikut cara melakukannya:

```csharp
HtmlSaveOptions options = new HtmlSaveOptions { DocumentSplitCriteria = DocumentSplitCriteria.SectionBreak };

doc.Save(dataDir + "SplitDocument.ParSectionsHtml.html", options);
```

### Contoh kode sumber untuk By Sections HTML menggunakan Aspose.Words untuk .NET

Berikut adalah kode sumber lengkap untuk fitur By HTML Sections Aspose.Words untuk .NET:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");


HtmlSaveOptions options = new HtmlSaveOptions { DocumentSplitCriteria = DocumentSplitCriteria.SectionBreak };


doc.Save(dataDir + "SplitDocument.BySectionsHtml.html", options);
```

Dengan kode ini Anda akan dapat membagi dokumen Word menjadi beberapa bagian terpisah dalam format HTML menggunakan Aspose.Words untuk .NET.

Sekarang Anda dapat membuat dokumen HTML terpisah untuk setiap bagian dokumen awal.

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara membagi dokumen Word menjadi beberapa bagian terpisah dalam format HTML menggunakan fitur Berdasarkan Bagian HTML dari Aspose.Words untuk .NET. Dengan mengikuti kode sumber yang disediakan, Anda dapat menghasilkan dokumen HTML individual untuk setiap bagian dokumen asli.

Membagi dokumen menjadi beberapa bagian dapat berguna untuk berbagai tujuan seperti membuat halaman web, mengekstraksi konten tertentu, atau mengatur informasi. Aspose.Words untuk .NET menyediakan API canggih yang memungkinkan Anda memanipulasi dan menyesuaikan dokumen Word sesuai kebutuhan Anda.

Jangan ragu untuk menjelajahi fitur tambahan yang ditawarkan oleh Aspose.Words untuk .NET untuk lebih meningkatkan kemampuan pemrosesan dokumen dan meningkatkan alur kerja Anda.

### FAQ

#### Bagaimana cara menyesuaikan format keluaran HTML?

Aspose.Words for .NET menyediakan berbagai opsi untuk menyesuaikan format output HTML. Anda dapat mengubah gaya, pengaturan font, resolusi gambar, dan banyak aspek lain dari dokumen HTML dengan menyesuaikan opsi penyimpanan. Lihat dokumentasi Aspose.Words untuk .NET untuk informasi mendetail tentang opsi yang tersedia dan cara menggunakannya.

#### Bisakah saya membagi dokumen berdasarkan kriteria yang berbeda?

Ya, selain menggunakan hentian bagian sebagai kriteria pemisahan, Aspose.Words untuk .NET menawarkan opsi lain seperti hentian paragraf, gaya judul, atau konten tertentu sebagai kriteria untuk membagi dokumen. Anda dapat memilih kriteria yang paling sesuai berdasarkan kebutuhan Anda dan menyesuaikan kodenya.

#### Apakah mungkin untuk membagi dokumen ke dalam format selain HTML?

Ya, Aspose.Words untuk .NET mendukung pemisahan dokumen ke dalam berbagai format termasuk PDF, teks biasa, gambar, dan banyak lagi. Anda dapat mengubah opsi penyimpanan untuk menghasilkan format keluaran yang diinginkan. Lihat dokumentasi Aspose.Words untuk .NET untuk detail selengkapnya tentang format yang tersedia dan cara menentukannya dalam opsi penyimpanan.

#### Bisakah saya membagi beberapa dokumen secara bersamaan?

Ya, Anda dapat menerapkan proses pemisahan ke beberapa dokumen secara bersamaan dengan melakukan iterasi melalui kumpulan dokumen dan mengeksekusi kode pemisahan untuk setiap dokumen satu per satu. Ini memungkinkan Anda memproses banyak dokumen secara efisien dan menghasilkan bagian terpisah untuk masing-masing dokumen.

#### Bagaimana cara menggabungkan kembali bagian-bagian tersebut menjadi satu dokumen?

Aspose.Words untuk .NET juga menyediakan metode untuk menggabungkan beberapa dokumen atau bagian kembali menjadi satu dokumen. Dengan memanfaatkan fitur penggabungan ini, Anda dapat menggabungkan bagian yang dibuat secara terpisah dan membuat dokumen terpadu. Lihat dokumentasi Aspose.Words untuk .NET untuk informasi selengkapnya tentang cara menggabungkan dokumen atau bagian.


