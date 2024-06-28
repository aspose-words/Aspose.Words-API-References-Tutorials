---
title: Kurangi Ukuran Dokumen PDF dengan Downsampling Gambar
linktitle: Kurangi Ukuran Dokumen PDF dengan Downsampling Gambar
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara memperkecil ukuran dokumen pdf dengan downsampling gambar saat mengonversi ke PDF dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-pdfsaveoptions/downsampling-images/
---

Dalam tutorial ini, kami akan memandu Anda melalui langkah-langkah untuk mengurangi ukuran dokumen pdf dengan downsampling gambar saat mengonversi ke PDF dengan Aspose.Words untuk .NET. Ini mengurangi ukuran file PDF yang dihasilkan. Ikuti langkah-langkah di bawah ini:

## Langkah 1: Memuat dokumen

Mulailah dengan mengunggah dokumen yang ingin Anda konversi ke PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Pastikan untuk menentukan jalur yang benar ke dokumen Anda.

## Langkah 2: Konfigurasikan opsi penyimpanan PDF

Buat instance kelas PdfSaveOptions dan atur opsi penurunan skala gambar:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
};
```

 Itu`Resolution` properti menentukan resolusi target gambar dan`ResolutionThreshold`Properti ini menentukan resolusi minimum yang di bawahnya gambar tidak akan diperkecil.

## Langkah 3: Konversi Dokumen ke PDF

 Menggunakan`Save` metode untuk mengonversi dokumen ke PDF dengan menentukan opsi penyimpanan:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);
```

Pastikan untuk menentukan jalur yang benar untuk menyimpan PDF yang dikonversi.

### Contoh kode sumber untuk Downsampling Gambar menggunakan Aspose.Words untuk .NET

```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Kita dapat menetapkan ambang batas minimum untuk downsampling.
	// Nilai ini akan mencegah gambar kedua dalam dokumen masukan didownsampling.
	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);

```

Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah mengurangi resolusi gambar saat mengonversi ke PDF dengan Aspose.Words untuk .NET.

## Kesimpulan

Dalam tutorial ini, kami telah menjelaskan cara memperkecil ukuran dokumen PDF dengan pengambilan sampel gambar saat mengonversi ke PDF menggunakan Aspose.Words untuk .NET. Dengan mengikuti langkah-langkah yang dijelaskan, Anda dapat dengan mudah mengurangi resolusi gambar dan ukuran file PDF yang dihasilkan. Pastikan untuk menentukan jalur yang benar ke dokumen Anda dan konfigurasikan opsi pengambilan sampel gambar sesuai kebutuhan. Mengurangi ukuran file PDF memudahkan berbagi, menyimpan, dan memuat file dengan cepat di berbagai platform. Nikmati manfaat mengurangi ukuran dokumen PDF dengan pengambilan sampel gambar menggunakan Aspose.Words untuk .NET.

### Pertanyaan yang Sering Diajukan

#### T: Apa yang dimaksud dengan pengurangan ukuran dokumen PDF dengan pengambilan sampel gambar?
A: Mengurangi ukuran dokumen PDF dengan Image Sampling adalah memperkecil ukuran file PDF yang dihasilkan dengan mengurangi resolusi gambar saat mengkonversi ke PDF. Ini mengoptimalkan penggunaan ruang penyimpanan dan mempermudah berbagi dan mentransfer file PDF.

#### T: Bagaimana cara mengurangi ukuran dokumen PDF dengan pengambilan sampel gambar menggunakan Aspose.Words untuk .NET?
J: Untuk memperkecil ukuran dokumen PDF dengan pengambilan sampel gambar menggunakan Aspose.Words untuk .NET, ikuti langkah-langkah berikut:

 Atur jalur direktori tempat dokumen Anda berada dengan mengganti`"YOUR DOCUMENTS DIRECTORY"` dengan jalur sebenarnya dari direktori dokumen Anda.

 Muat dokumen yang ingin Anda konversi ke PDF menggunakan`Document` kelas dan tentukan jalur ke dokumen di direktori dokumen yang ditentukan.

 Konfigurasikan opsi simpan sebagai PDF dengan membuat instance dari`PdfSaveOptions` kelas dan mengatur opsi pengambilan sampel gambar menggunakan`DownsampleOptions` Properti. Anda dapat menentukan resolusi target gambar menggunakan`Resolution` properti dan tetapkan ambang resolusi minimum yang di atasnya gambar tidak akan diperkecil menggunakan`ResolutionThreshold` Properti.

 Simpan dokumen dalam format PDF menggunakan`Save` metode`Document` kelas yang menentukan jalur dan opsi penyimpanan.

#### T: Apa manfaat memperkecil ukuran dokumen PDF dengan pengambilan sampel gambar?
A: Keuntungan memperkecil ukuran dokumen PDF dengan pengambilan sampel gambar adalah:

Mengurangi ukuran file PDF: Pengambilan sampel gambar mengurangi resolusi gambar dalam dokumen PDF, sehingga mengurangi ukuran file PDF secara signifikan. Hal ini memudahkan untuk berbagi dan mentransfer file, terutama melalui email atau online.

Optimalisasi ruang penyimpanan: Mengurangi ukuran file PDF membantu mengoptimalkan penggunaan ruang penyimpanan, terutama bila Anda memiliki banyak file PDF yang berisi gambar beresolusi tinggi.

Peningkatan kinerja: File PDF yang lebih kecil dimuat lebih cepat dan dapat dibuka serta dilihat lebih cepat di perangkat berbeda.