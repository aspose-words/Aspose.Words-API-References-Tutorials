---
title: Kompresi Gambar dalam Dokumen PDF
linktitle: Kompresi Gambar dalam Dokumen PDF
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk mengompresi gambar dalam Dokumen PDF dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-pdfsaveoptions/image-compression/
---

Artikel ini memberikan panduan langkah demi langkah tentang cara menggunakan fitur Kompresi Gambar dalam Dokumen PDF dengan Aspose.Words untuk .NET. Kami akan menjelaskan setiap bagian kode secara detail. Di akhir tutorial ini, Anda akan dapat memahami cara mengompresi gambar dalam dokumen dan menghasilkan PDF dengan kompresi gambar yang tepat.

Sebelum memulai, pastikan Anda telah menginstal dan mengonfigurasi pustaka Aspose.Words untuk .NET di proyek Anda. Anda dapat menemukan perpustakaan dan petunjuk instalasi di situs web Aspose.

## Langkah 1: Tentukan direktori dokumen

 Untuk memulai, Anda perlu menentukan jalur ke direktori tempat dokumen Anda berada. Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Unggah dokumen

Selanjutnya, kita perlu memuat dokumen yang ingin kita proses. Dalam contoh ini, kami berasumsi bahwa dokumen tersebut bernama "Rendering.docx" dan terletak di direktori dokumen yang ditentukan.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Langkah 3: Konfigurasikan opsi simpan sebagai PDF dengan kompresi gambar

 Untuk mengompresi gambar saat mengonversi ke PDF, kita perlu mengkonfigurasi`PdfSaveOptions` obyek. Kami dapat mengatur jenis kompresi gambar, kualitas JPEG, dan opsi kepatuhan PDF lainnya jika diperlukan.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
ImageCompression = PdfImageCompression.Jpeg,
PreserveFormFields = true
};
```

## Langkah 4: Simpan dokumen sebagai PDF dengan kompresi gambar

Terakhir, kita dapat menyimpan dokumen dalam format PDF menggunakan opsi penyimpanan yang dikonfigurasi sebelumnya.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);
```

## Langkah 5: Konfigurasikan opsi untuk menyimpan ke PDF/A-2u dengan kompresi gambar

Jika Anda ingin menghasilkan PDF yang sesuai dengan PDF/A-2u dengan kompresi gambar, Anda dapat mengonfigurasi opsi penyimpanan tambahan.

```csharp
PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
{
Compliance = PdfCompliance.PdfA2u,
ImageCompression = PdfImageCompression.Jpeg,
JpegQuality=100, // Gunakan kompresi JPEG dengan kualitas 50% untuk memperkecil ukuran file.
};
```

## Langkah 6: Simpan dokumen sebagai PDF/A-2u dengan kompresi gambar

Simpan dokumen dalam format PDF/A-2u menggunakan opsi penyimpanan tambahan yang dikonfigurasi sebelumnya.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
```



Itu saja ! Anda telah berhasil mengompresi gambar dalam dokumen dan menghasilkan PDF dengan kompresi gambar yang tepat menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber untuk mengompresi gambar dengan Aspose.Words untuk .NET

```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		ImageCompression = PdfImageCompression.Jpeg, PreserveFormFields = true
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);

	PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
	{
		Compliance = PdfCompliance.PdfA2u,
		ImageCompression = PdfImageCompression.Jpeg,
		JpegQuality = 100, // Gunakan kompresi JPEG dengan kualitas 50% untuk mengurangi ukuran file.
	};

	

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
	
```

## Kesimpulan

Dalam tutorial ini, kami menjelaskan cara mengompresi gambar dalam dokumen PDF menggunakan Aspose.Words untuk .NET. Dengan mengikuti langkah-langkah yang dijelaskan, Anda dapat dengan mudah mengurangi ukuran gambar dalam dokumen PDF Anda dan menghasilkan PDF dengan kompresi gambar yang tepat. Gunakan fitur kompresi gambar Aspose.Words untuk .NET untuk mengoptimalkan ukuran dokumen PDF Anda sekaligus menjaga kualitas gambar.

### Pertanyaan yang Sering Diajukan

#### T: Apa yang dimaksud dengan kompresi gambar dalam dokumen PDF?
A: Mengompresi gambar dalam dokumen PDF adalah untuk memperkecil ukuran gambar yang disertakan dalam dokumen PDF untuk memperkecil ukuran file PDF secara keseluruhan. Hal ini mengurangi ruang penyimpanan yang dibutuhkan dan meningkatkan kinerja saat memuat dan melihat PDF.

#### T: Bagaimana cara mengompres gambar dalam dokumen PDF dengan Aspose.Words untuk .NET?
J: Untuk mengompresi gambar dalam dokumen PDF dengan Aspose.Words for .NET, ikuti langkah-langkah berikut:

 Buat sebuah instance dari`Document` kelas yang menentukan jalur ke dokumen Word.

 Buat sebuah instance dari`PdfSaveOptions` kelas dan atur`ImageCompression`properti ke`PdfImageCompression.Jpeg` untuk menggunakan kompresi JPEG.

Anda juga dapat mengatur opsi kompresi gambar lainnya, seperti kualitas JPEG, sesuai kebutuhan Anda.

 Menggunakan`Save` metode`Document`kelas untuk menyimpan dokumen dalam format PDF dengan menentukan opsi penyimpanan.

#### T: Apa perbedaan antara kompresi gambar standar dan kompresi gambar PDF/A-2u?
J: Kompresi gambar standar mengurangi ukuran gambar dalam dokumen PDF sambil mempertahankan kolom formulir. Ini mengurangi ukuran keseluruhan file PDF tanpa mengorbankan fungsionalitas bidang formulir.

Kompresi Gambar dengan PDF/A-2u adalah opsi tambahan yang memungkinkan Anda menghasilkan file PDF yang sesuai dengan standar PDF/A-2u sambil menerapkan kompresi gambar. PDF/A-2u adalah standar ISO untuk pengarsipan dokumen PDF dan menjamin pelestarian dokumen dalam jangka panjang.
