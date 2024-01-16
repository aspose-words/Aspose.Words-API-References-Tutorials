---
title: Muat Rentang Halaman Pdf
linktitle: Muat Rentang Halaman Pdf
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk memuat rentang halaman PDF tertentu dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-pdfloadoptions/load-page-range-of-pdf/
---

Dalam tutorial ini, kami akan memandu Anda tentang cara memuat rentang halaman tertentu dari dokumen PDF menggunakan Aspose.Words untuk .NET. Ikuti langkah-langkah di bawah ini:

## Langkah 1: Memuat Berbagai Halaman PDF

Gunakan kode berikut untuk memuat rentang halaman tertentu dari dokumen PDF:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);
```

 Dalam contoh ini, kami memuat halaman pertama dokumen PDF. Anda dapat mengubah nilai`PageIndex` Dan`PageCount` ke rentang halaman yang diinginkan.

## Langkah 2: Menyimpan dokumen

 Terakhir, Anda dapat menyimpan dokumen yang berisi rentang halaman tertentu menggunakan`Save` metode:

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
```

Pastikan untuk menentukan jalur yang benar untuk menyimpan dokumen yang diedit.

Itu saja ! Anda sekarang telah memuat rentang halaman tertentu dari dokumen PDF menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber untuk Memuat Rentang Halaman Pdf menggunakan Aspose.Words untuk .NET

```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

	
	Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
   
```
Ingatlah untuk menentukan jalur yang benar ke direktori dokumen PDF Anda.



