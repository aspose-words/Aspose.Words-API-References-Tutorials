---
title: Tampilkan Judul Dokumen di Bilah Judul Jendela
linktitle: Tampilkan Judul Dokumen di Bilah Judul Jendela
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menampilkan judul dokumen di bilah judul jendela saat mengonversi ke PDF dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-pdfsaveoptions/display-doc-title-in-window-titlebar/
---

Dalam tutorial ini, kami akan memandu Anda melalui langkah-langkah untuk menampilkan judul dokumen di bilah judul jendela dengan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda untuk menampilkan judul dokumen di bilah judul jendela saat Anda membuka dokumen PDF yang dihasilkan. Ikuti langkah-langkah di bawah ini:

## Langkah 1: Memuat dokumen

Mulailah dengan mengunggah dokumen yang ingin Anda konversi ke PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Pastikan untuk menentukan jalur yang benar ke dokumen Anda.

## Langkah 2: Konfigurasikan Opsi Penyimpanan PDF

Buat instance kelas PdfSaveOptions dan aktifkan tampilan judul dokumen di bilah judul jendela:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { DisplayDocTitle = true };
```

Opsi ini memungkinkan tampilan judul dokumen di bilah judul jendela saat mengonversi ke PDF.

## Langkah 3: Konversi Dokumen ke PDF

 Menggunakan`Save` metode untuk mengonversi dokumen ke PDF dengan menentukan opsi konversi:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisplayDocTitleInWindowTitlebar.pdf", saveOptions);
```

Pastikan untuk menentukan jalur yang benar untuk menyimpan PDF yang dikonversi.

### Contoh kode sumber untuk Menampilkan Judul Dokumen di Bilah Judul Jendela menggunakan Aspose.Words untuk .NET

Berikut adalah kode sumber lengkap untuk menampilkan judul dokumen di bilah judul jendela dalam dokumen PDF dengan Aspose.Words untuk .NET:

```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { DisplayDocTitle = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisplayDocTitleInWindowTitlebar.pdf", saveOptions);
        
```
Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah menampilkan judul dokumen di bilah judul jendela saat mengonversi ke PDF dengan Aspose.Words untuk .NET.

### Pertanyaan yang Sering Diajukan

#### T: Apa yang dimaksud dengan fitur "Tampilkan judul dokumen di bilah judul jendela" dengan Aspose.Words untuk .NET?
Fitur "Tampilkan judul dokumen di bilah judul jendela" dengan Aspose.Words untuk .NET memungkinkan Anda menampilkan judul dokumen di bilah judul jendela saat Anda membuka dokumen PDF yang dihasilkan. Hal ini memudahkan untuk mengidentifikasi dan membedakan dokumen PDF di lingkungan membaca Anda.

#### T: Bagaimana cara menggunakan fitur ini dengan Aspose.Words untuk .NET?
Untuk menggunakan fitur ini dengan Aspose.Words untuk .NET, ikuti langkah-langkah berikut:

 Muat dokumen menggunakan`Document` metode dan menentukan jalur file yang akan dikonversi ke PDF.

 Konfigurasikan opsi penyimpanan PDF dengan membuat instance dari`PdfSaveOptions` kelas dan pengaturan`DisplayDocTitle`properti ke`true`. Ini memungkinkan tampilan judul dokumen di bilah judul jendela saat mengonversi ke PDF.

 Menggunakan`Save` metode untuk mengonversi dokumen ke PDF dengan menentukan opsi konversi.

#### T: Apakah fitur ini mengubah konten dokumen itu sendiri?
Tidak, fitur ini tidak mengubah konten dokumen itu sendiri. Ini hanya mempengaruhi tampilan judul dokumen di bilah judul jendela ketika dibuka sebagai dokumen PDF. Isi dokumen tersebut tetap tidak berubah.

#### T: Apakah mungkin untuk menyesuaikan judul dokumen yang ditampilkan di bilah judul jendela?
 Ya, Anda dapat menyesuaikan judul dokumen yang ditampilkan di bilah judul jendela dengan mengubah`Document.Title` properti dokumen sebelum mengonversinya ke PDF. Anda dapat mengatur judul yang diinginkan menggunakan string. Pastikan untuk mengatur judul sebelum memanggil`Save` metode untuk mengkonversi ke PDF.

#### T: Format keluaran lain apa yang didukung Aspose.Words untuk konversi dokumen?
Aspose.Words for .NET mendukung banyak format output untuk konversi dokumen, seperti PDF, XPS, HTML, EPUB, MOBI, gambar (JPEG, PNG, BMP, TIFF, GIF), dan masih banyak lagi. masih yang lain. Anda dapat memilih format keluaran yang sesuai dengan kebutuhan spesifik Anda.