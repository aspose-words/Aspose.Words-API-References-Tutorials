---
title: Atur Pengaturan Halaman dan Pemformatan Bagian
linktitle: Atur Pengaturan Halaman dan Pemformatan Bagian
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk menyiapkan tata letak dokumen dan pemformatan bagian dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-document-options-and-settings/set-page-setup-and-section-formatting/
---

Dalam tutorial ini, kami akan memandu Anda melalui kode sumber C# untuk menyiapkan tata letak dan pemformatan bagian dengan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda mengatur orientasi halaman, margin, dan ukuran kertas.

## Langkah 1: Pengaturan Proyek

Untuk memulai, buat proyek C# baru di IDE favorit Anda. Pastikan perpustakaan Aspose.Words untuk .NET direferensikan dalam proyek Anda.

## Langkah 2: Membuat dokumen

Pada langkah ini, kita akan membuat dokumen baru. Gunakan kode berikut untuk membuat dokumen dan menginisialisasi konstruktor:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Mengganti`"YOUR DOCUMENTS DIRECTORY"` dengan jalur sebenarnya dari direktori tempat Anda ingin menyimpan dokumen.

## Langkah 3: Menyiapkan tata letak dan menyimpan dokumen

Sekarang mari kita konfigurasikan tata letak dokumen. Gunakan kode berikut untuk mengatur orientasi, margin, dan ukuran kertas:

```csharp
builder.PageSetup.Orientation = Orientation.Landscape;
builder.PageSetup.LeftMargin = 50;
builder.PageSetup.PaperSize = PaperSize.Paper10x14;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
```

Kode ini akan mengatur orientasi halaman menjadi lanskap, margin kiri menjadi 50, dan ukuran kertas menjadi 10x14.

### Contoh kode sumber untuk Mengatur Pengaturan Halaman dan Pemformatan Bagian menggunakan Aspose.Words untuk .NET

```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.PageSetup.Orientation = Orientation.Landscape;
	builder.PageSetup.LeftMargin = 50;
	builder.PageSetup.PaperSize = PaperSize.Paper10x14;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
  
```

 Pastikan untuk menentukan jalur yang benar ke direktori tempat Anda ingin menyimpan dokumen di`dataDir` variabel.

Anda sekarang telah mempelajari cara mengonfigurasi tata letak dan pemformatan bagian dokumen menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah yang disediakan dalam tutorial ini, Anda dapat dengan mudah menyesuaikan tata letak dan format dokumen Anda sendiri.