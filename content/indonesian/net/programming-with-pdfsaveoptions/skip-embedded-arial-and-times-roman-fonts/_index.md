---
title: Optimalkan Ukuran PDF dengan Lewati Font Arial & Times Roman yang Tersemat
linktitle: Optimalkan Ukuran PDF dengan Lewati Font Arial & Times Roman yang Tersemat
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk menghasilkan PDF yang dioptimalkan tanpa menyematkan font Arial dan Times Roman dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-pdfsaveoptions/skip-embedded-arial-and-times-roman-fonts/
---

Artikel ini memberikan panduan langkah demi langkah tentang cara menggunakan fitur untuk mengoptimalkan ukuran PDF dengan melewatkan font Arial dan Times Roman yang tertanam ke ukuran metafile dengan Aspose.Words untuk .NET. Kami akan menjelaskan setiap bagian kode secara detail. Di akhir tutorial ini, Anda akan dapat memahami cara mengonfigurasi opsi mode penyematan font dalam dokumen dan menghasilkan PDF tanpa menyematkan font Arial dan Times Roman.

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

## Langkah 3: Konfigurasikan opsi simpan sebagai PDF dengan penyematan font

 Untuk melewati penyematan font Arial dan Times Roman di PDF yang dihasilkan, kita perlu mengkonfigurasi`PdfSaveOptions` objek dan atur`FontEmbeddingMode`properti ke`PdfFontEmbeddingMode.EmbedAll`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };
```

## Langkah 4: Simpan dokumen sebagai PDF tanpa font yang disematkan

Terakhir, kita dapat menyimpan dokumen dalam format PDF menggunakan opsi penyimpanan yang dikonfigurasi sebelumnya.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
```

Itu saja ! Anda telah berhasil membuat PDF tanpa menyematkan font Arial dan Times Roman menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber untuk melewati font Arial dan Times Roman yang tertanam pada ukuran metafile dengan Aspose.Words untuk .NET

```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
   
```

## Kesimpulan

Dalam tutorial ini, kami menjelaskan cara menonaktifkan penyematan font Arial dan Times Roman dalam dokumen PDF menggunakan Aspose.Words untuk .NET. Dengan mengikuti langkah-langkah yang diuraikan, Anda dapat membuat file PDF tanpa menyematkan font khusus ini, yang dapat membantu mengurangi ukuran file dan memastikan kompatibilitas dokumen yang lebih baik di berbagai platform. Pastikan untuk mempertimbangkan konsekuensi menonaktifkan penyematan font saat menggunakan fitur ini. Jangan ragu untuk menjelajahi lebih banyak fitur Aspose.Words untuk .NET untuk mengoptimalkan pembuatan file PDF Anda.

### Pertanyaan yang Sering Diajukan

#### T: Apa yang dimaksud dengan menonaktifkan penyematan font Arial dan Times Roman dalam dokumen PDF dan mengapa ini penting?
A: Menonaktifkan penyematan font Arial dan Times Roman dalam dokumen PDF adalah proses tidak menyertakan font tersebut dalam file PDF yang dihasilkan. Hal ini penting untuk mengurangi ukuran file PDF dengan menghindari penyertaan font yang sudah umum tersedia di sistem pembaca PDF. Ini juga dapat membantu memastikan kompatibilitas yang lebih baik dan tampilan dokumen PDF yang konsisten di berbagai perangkat dan platform.

#### T: Bagaimana cara mengonfigurasi Aspose.Words untuk .NET agar tidak menyematkan font Arial dan Times Roman dalam dokumen PDF?
J: Untuk mengonfigurasi Aspose.Words untuk .NET agar tidak menyematkan font Arial dan Times Roman dalam dokumen PDF, ikuti langkah-langkah berikut:

 Atur jalur direktori tempat dokumen Anda berada dengan mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya dari direktori dokumen Anda.

 Muat dokumen yang ingin Anda proses menggunakan`Document` kelas dan jalur dokumen yang ditentukan.

 Buat sebuah instance dari`PdfSaveOptions` kelas dan atur`FontEmbeddingMode`properti ke`PdfFontEmbeddingMode.EmbedAll`. Ini akan menyematkan semua font kecuali Arial dan Times Roman dalam file PDF yang dihasilkan.

 Menggunakan`Save` metode`Document` objek untuk menyimpan dokumen dalam format PDF dengan menentukan opsi penyimpanan yang dikonfigurasi sebelumnya.

#### T: Apa manfaat menonaktifkan penyematan font Arial dan Times Roman di dokumen PDF?
A: Keuntungan menonaktifkan penyematan font Arial dan Times Roman di dokumen PDF adalah:

Pengurangan ukuran file PDF: Dengan menghindari penyematan font yang umum tersedia seperti Arial dan Times Roman, ukuran file PDF dapat diperkecil, sehingga lebih mudah untuk menyimpan, berbagi, dan mentransfer file.

Kompatibilitas yang lebih baik: Dengan menggunakan font yang umumnya tersedia di sistem pembaca PDF, Anda memastikan kompatibilitas dan tampilan dokumen yang lebih baik di berbagai perangkat dan platform.

#### T: Apa konsekuensi dari menonaktifkan penyematan font Arial dan Times Roman di dokumen PDF?
A: Akibat dari menonaktifkan penyematan font Arial dan Times Roman pada dokumen PDF adalah sebagai berikut:

Tampilan berbeda: Jika font Arial dan Times Roman tidak tersedia di sistem tempat PDF dibuka, font pengganti akan digunakan, yang mungkin menghasilkan tampilan berbeda dari yang diharapkan.

Masalah keterbacaan: Font pengganti yang digunakan mungkin tidak dapat dibaca seperti font aslinya, sehingga dapat mempengaruhi keterbacaan dokumen.