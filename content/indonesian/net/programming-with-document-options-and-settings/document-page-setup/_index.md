---
title: Pengaturan Halaman Dokumen
linktitle: Pengaturan Halaman Dokumen
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk menyiapkan tata letak dokumen dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-document-options-and-settings/document-page-setup/
---

Dalam tutorial ini, kami akan memandu Anda melalui kode sumber C# untuk mengonfigurasi tata letak dokumen dengan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda mengatur mode tata letak, jumlah karakter per baris, dan jumlah baris per halaman.

## Langkah 1: Pengaturan Proyek

Untuk memulai, buat proyek C# baru di IDE favorit Anda. Pastikan perpustakaan Aspose.Words untuk .NET direferensikan dalam proyek Anda.

## Langkah 2: Memuat dokumen

Pada langkah ini, kita akan memuat dokumen Word yang ingin kita konfigurasi. Gunakan kode berikut untuk memuat dokumen:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Mengganti`"YOUR DOCUMENTS DIRECTORY"` dengan jalur sebenarnya dari direktori tempat dokumen Anda berada.

## Langkah 3: Menyiapkan tata letak

Sekarang mari kita konfigurasikan tata letak dokumen. Gunakan kode berikut untuk mengatur mode tata letak, jumlah karakter per baris, dan jumlah baris per halaman:

```csharp
doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
doc.FirstSection.PageSetup.CharactersPerLine = 30;
doc.FirstSection.PageSetup.LinesPerPage = 10;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
```

Kode ini menyetel mode tata letak ke "Kisi" dan kemudian menentukan jumlah karakter per baris dan jumlah baris per halaman.

### Contoh kode sumber untuk Pengaturan Halaman Dokumen menggunakan Aspose.Words untuk .NET


```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	// Atur mode tata letak untuk bagian yang memungkinkan untuk menentukan perilaku kisi dokumen.
	// Perhatikan bahwa tab Document Grid menjadi terlihat dalam dialog Page Setup MS Word.
	// jika ada bahasa Asia yang didefinisikan sebagai bahasa penyuntingan.
	doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
	doc.FirstSection.PageSetup.CharactersPerLine = 30;
	doc.FirstSection.PageSetup.LinesPerPage = 10;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
   
```

 Pastikan untuk menentukan jalur dokumen yang benar di`dataDir` variabel.

Anda sekarang telah mempelajari cara mengonfigurasi tata letak dokumen menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah yang disediakan dalam tutorial ini, Anda dapat dengan mudah menyesuaikan tata letak dokumen Anda sendiri.