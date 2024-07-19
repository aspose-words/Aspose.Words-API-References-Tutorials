---
title: Perbarui Properti Cetakan Terakhir dalam Dokumen PDF
linktitle: Perbarui Properti Cetakan Terakhir dalam Dokumen PDF
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk memperbarui properti "Terakhir Dicetak" saat mengonversi ke PDF dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-pdfsaveoptions/update-last-printed-property/
---

Artikel ini memberikan panduan langkah demi langkah tentang cara menggunakan properti "Pencetakan Terakhir" di fitur pembaruan Dokumen PDF dengan Aspose.Words untuk .NET. Kami akan menjelaskan setiap bagian kode secara detail. Di akhir tutorial ini, Anda akan dapat memahami cara mengonfigurasi opsi untuk memperbarui properti "Terakhir dicetak" saat mengonversi ke PDF.

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

## Langkah 3: Konfigurasikan Opsi Simpan sebagai PDF dengan Properti "Terakhir Dicetak" yang Diperbarui

 Untuk mengaktifkan pembaruan properti "Terakhir Dicetak" saat mengonversi ke PDF, kita perlu mengkonfigurasi`PdfSaveOptions` objek dan atur`UpdateLastPrintedProperty`properti ke`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };
```

## Langkah 4: Simpan dokumen sebagai PDF dengan pembaruan properti "Terakhir dicetak".

Terakhir, kita dapat menyimpan dokumen dalam format PDF menggunakan opsi penyimpanan yang dikonfigurasi sebelumnya.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);
```

Itu saja ! Anda telah berhasil mengaktifkan pembaruan properti "Terakhir Dicetak" saat mengonversi dokumen ke PDF menggunakan Aspose.Words untuk .NET.

### Contoh Kode Sumber untuk Memperbarui Properti "Terakhir Dicetak" dengan Aspose.Words untuk .NET


```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);

```
## Kesimpulan

Dalam tutorial ini, kami menjelaskan cara memperbarui properti "Terakhir Dicetak" dalam dokumen PDF menggunakan Aspose.Words untuk .NET. Dengan mengikuti langkah-langkah yang diberikan, Anda dapat dengan mudah mengonfigurasi opsi untuk memperbarui properti "Terakhir Dicetak" saat mengonversi dokumen ke PDF. Gunakan fitur ini untuk melacak penggunaan dokumen dan informasi terkait.

### Pertanyaan yang Sering Diajukan

#### T: Apa yang dimaksud dengan properti "Terakhir Dicetak" dalam dokumen PDF?
J: Properti "Terakhir Dicetak" dalam dokumen PDF mengacu pada tanggal dan waktu dokumen terakhir dicetak. Properti ini dapat berguna untuk melacak informasi tentang penggunaan dan pengelolaan dokumen.

#### T: Bagaimana cara memperbarui properti "Terakhir Dicetak" di dokumen PDF dengan Aspose.Words untuk .NET?
J: Untuk memperbarui properti "Terakhir Dicetak" dalam dokumen PDF dengan Aspose.Words untuk .NET, ikuti langkah-langkah berikut:

 Buat sebuah instance dari`Document` kelas yang menentukan jalur ke dokumen Word.

 Buat sebuah instance dari`PdfSaveOptions` kelas dan atur`UpdateLastPrintedProperty`properti ke`true` untuk mengaktifkan pembaruan properti "Terakhir Dicetak".

 Menggunakan`Save` metode`Document`kelas untuk menyimpan dokumen dalam format PDF dengan menentukan opsi penyimpanan.

#### T: Bagaimana cara memeriksa apakah properti "Terakhir Dicetak" telah diperbarui dalam dokumen PDF yang dihasilkan?
J: Anda dapat memeriksa apakah properti "Terakhir Dicetak" telah diperbarui dalam dokumen PDF yang dihasilkan dengan membuka file PDF dengan penampil PDF yang kompatibel, seperti Adobe Acrobat Reader, dan melihat informasi dokumen. Tanggal dan waktu pencetakan terakhir harus sesuai dengan tanggal dan waktu pembuatan dokumen PDF.
