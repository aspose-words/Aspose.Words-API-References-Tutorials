---
title: Pisahkan Dokumen Word Berdasarkan Judul Html
linktitle: Dengan Judul Html
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk menjelaskan kode sumber C# dari dokumen kata terpisah Dengan fitur Heading HTML dari Aspose.Words untuk .NET
type: docs
weight: 10
url: /id/net/split-document/by-headings-html/
---
Dalam tutorial ini, kami akan memandu Anda tentang cara membagi dokumen Word menjadi bagian-bagian yang lebih kecil menggunakan fitur By HTML Heading dari Aspose.Words untuk .NET. Ikuti langkah-langkah di bawah ini untuk memahami kode sumber dan menghasilkan dokumen HTML terpisah berdasarkan Judul.

## Langkah 1: Memuat dokumen

Untuk memulai, tentukan direktori untuk dokumen Anda dan muat dokumen ke dalam objek Dokumen. Begini caranya:

```csharp
//Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## Langkah 2: Membagi dokumen dengan Heading dalam format HTML

Sekarang kita akan mengatur opsi penyimpanan untuk membagi dokumen menjadi bagian-bagian yang lebih kecil berdasarkan Heading dalam format HTML. Begini caranya:

```csharp
HtmlSaveOptions options = new HtmlSaveOptions
{
// Pisahkan dokumen menjadi bagian-bagian yang lebih kecil, dalam hal ini pisahkan berdasarkan judul.
DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};

doc.Save(dataDir + "SplitDocument.ParTitresHtml.html", options);
```

### Contoh kode sumber By Headings HTML menggunakan Aspose.Words untuk .NET

Berikut ini source code lengkap fitur By HTML Heading Aspose.Words for .NET:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");

HtmlSaveOptions options = new HtmlSaveOptions
{
	// Pisahkan dokumen menjadi beberapa bagian yang lebih kecil, dalam hal ini pisahkan berdasarkan judul.
	DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};


doc.Save(dataDir + "SplitDocument.ByHeadingsHtml.html", options);
```

Dengan kode ini, Anda akan dapat membagi dokumen Word menjadi bagian-bagian yang lebih kecil menggunakan Aspose.Words untuk .NET, berdasarkan judulnya. Anda kemudian dapat membuat dokumen HTML terpisah untuk setiap bagian.

## Kesimpulan

 Dalam tutorial ini, kita mempelajari cara membagi dokumen Word menjadi bagian-bagian yang lebih kecil menggunakan fitur By HTML Heading dari Aspose.Words untuk .NET. Dengan menentukan`DocumentSplitCriteria` sebagai`HeadingParagraph` dalam`HtmlSaveOptions`, kami dapat membuat dokumen HTML terpisah berdasarkan judul yang ada di dokumen asli.

Memisahkan dokumen berdasarkan judul dapat berguna untuk mengatur dan mengelola konten, terutama dalam dokumen besar dengan banyak bagian. Aspose.Words untuk .NET memberikan solusi yang andal dan efisien untuk menangani pemisahan dokumen dan menghasilkan keluaran dalam berbagai format.

Jangan ragu untuk menjelajahi fitur dan opsi tambahan yang disediakan oleh Aspose.Words untuk .NET untuk lebih meningkatkan kemampuan pemrosesan dokumen dan menyederhanakan alur kerja Anda.

### FAQ

#### Bagaimana cara membagi dokumen Word menjadi bagian-bagian yang lebih kecil berdasarkan judul menggunakan Aspose.Words untuk .NET?

 Untuk membagi dokumen Word berdasarkan judul, Anda dapat menggunakan fitur Berdasarkan Judul HTML dari Aspose.Words untuk .NET. Ikuti kode sumber yang disediakan dan atur`DocumentSplitCriteria` ke`HeadingParagraph` dalam`HtmlSaveOptions` obyek. Ini akan membagi dokumen menjadi bagian-bagian yang lebih kecil di setiap judul.

#### Dalam format apa saya dapat membagi dokumen Word?

 Kode sumber yang disediakan menunjukkan pemisahan dokumen Word menjadi bagian-bagian kecil dalam format HTML. Namun, Aspose.Words untuk .NET mendukung berbagai format keluaran, termasuk DOCX, PDF, EPUB, dan banyak lagi. Anda dapat memodifikasi kode dan menentukan format keluaran yang diinginkan di`HtmlSaveOptions` objek sesuai.

#### Bisakah saya memilih kriteria lain untuk memisahkan dokumen?

Ya, Anda dapat memilih kriteria berbeda untuk memisahkan dokumen berdasarkan kebutuhan Anda. Aspose.Words for .NET menyediakan beberapa pilihan kriteria, seperti`HeadingParagraph`, `Page`, `Section` , dan banyak lagi. Ubah`DocumentSplitCriteria` properti di`HtmlSaveOptions` objek untuk memilih kriteria pemisahan yang sesuai.

#### Bagaimana cara menyesuaikan HTML keluaran untuk bagian yang terpisah?

 Aspose.Words untuk .NET memungkinkan Anda menyesuaikan HTML keluaran untuk bagian yang terpisah dengan menentukan opsi tambahan di`HtmlSaveOptions` obyek. Anda dapat mengontrol berbagai aspek seperti gaya CSS, gambar, font, dan lainnya. Lihat dokumentasi Aspose.Words untuk detail selengkapnya tentang menyesuaikan output HTML.

#### Bisakah saya membagi dokumen berdasarkan beberapa kriteria?

 Ya, Anda dapat membagi dokumen berdasarkan beberapa kriteria dengan menggabungkan pilihan kriteria yang sesuai. Misalnya, Anda dapat membagi dokumen berdasarkan judul dan halaman dengan mengatur`DocumentSplitCriteria`properti ke`HeadingParagraph | Page`. Ini akan membagi dokumen pada setiap judul dan setiap halaman, membuat bagian-bagian yang lebih kecil berdasarkan kedua kriteria tersebut.