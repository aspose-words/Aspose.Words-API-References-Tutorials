---
title: Sematkan Subset Font dalam Dokumen PDF
linktitle: Sematkan Subset Font dalam Dokumen PDF
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk menyematkan subkumpulan font dalam dokumen PDF menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-pdfsaveoptions/embedded-subset-fonts/
---

Artikel ini memberikan panduan langkah demi langkah tentang cara menggunakan fitur penyematan subset font dengan Aspose.Words untuk .NET. Kami akan menjelaskan setiap bagian kode secara detail. Di akhir tutorial ini, Anda akan dapat memahami cara menyematkan subkumpulan font dalam dokumen dan menghasilkan PDF yang hanya berisi mesin terbang yang digunakan dalam dokumen.

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

## Langkah 3: Konfigurasikan opsi simpan sebagai PDF

 Untuk membuat PDF yang hanya berisi subkumpulan font yang digunakan dalam dokumen, kita perlu mengkonfigurasi`PdfSaveOptions` keberatan dengan`EmbedFullFonts` properti disetel ke`false`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
```

## Langkah 4: Simpan dokumen sebagai PDF dengan subset font

 Terakhir, kita dapat menyimpan dokumen sebagai PDF menggunakan subset font. Tentukan nama file keluaran dan`saveOptions` objek yang kita konfigurasikan pada langkah sebelumnya.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);
```

Itu saja ! Anda telah berhasil menyematkan subkumpulan font dalam dokumen dan menghasilkan PDF yang hanya berisi mesin terbang yang digunakan dalam dokumen dengan Aspose.Words untuk .NET.

### Contoh kode sumber untuk menyematkan subset font dengan Aspose.Words untuk .NET

```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// PDF keluaran akan berisi subkumpulan font dalam dokumen.
	// Hanya mesin terbang yang digunakan dalam dokumen yang disertakan dalam font PDF.
	PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);

```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara menyematkan subset font dalam dokumen PDF menggunakan Aspose.Words untuk .NET. Menyematkan subkumpulan font membantu mengurangi ukuran file PDF sekaligus mempertahankan tampilan dokumen dengan hanya menggunakan karakter yang sebenarnya digunakan. Hal ini memastikan kompatibilitas dan kinerja yang lebih baik saat melihat dan mencetak PDF. Jangan ragu untuk menjelajahi lebih jauh fitur Aspose.Words untuk .NET guna mengoptimalkan pembuatan dokumen PDF Anda dengan subset font yang tertanam.

### Pertanyaan yang Sering Diajukan

#### T: Apa yang dimaksud dengan menyematkan subset font dalam dokumen PDF?
J: Menyematkan subkumpulan font dalam dokumen PDF adalah proses menyertakan hanya mesin terbang yang digunakan dalam dokumen, bukan menyertakan semua font lengkap. Ini mengurangi ukuran file PDF dengan hanya menyertakan data font yang diperlukan untuk menampilkan karakter yang sebenarnya digunakan dalam dokumen.

#### T: Apa perbedaan antara menyematkan font lengkap dan menyematkan subkumpulan font?
J: Penyematan font penuh berarti menyertakan semua font yang digunakan dalam dokumen ke dalam file PDF, yang memastikan bahwa dokumen akan ditampilkan persis seperti desainnya, namun dapat memperbesar ukuran file PDF. Sebaliknya, menyematkan subset font hanya berisi mesin terbang yang digunakan dalam dokumen, sehingga mengurangi ukuran file PDF, namun membatasi kemampuan untuk mereplikasi tampilan dokumen secara tepat jika karakter tambahan ditambahkan nanti.

#### T: Bagaimana cara menyematkan subkumpulan font dalam dokumen PDF menggunakan Aspose.Words untuk .NET?
J: Untuk menyematkan subkumpulan font dalam dokumen PDF menggunakan Aspose.Words untuk .NET, ikuti langkah-langkah berikut:

 Atur jalur direktori dokumen dengan mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya dari direktori dokumen Anda.

 Muat dokumen yang ingin Anda proses menggunakan`Document` kelas dan jalur dokumen.

 Konfigurasikan opsi penyimpanan PDF dengan membuat instance dari`PdfSaveOptions` kelas dan pengaturan`EmbedFullFonts`properti ke`false`Hal ini memastikan bahwa hanya subset font yang digunakan dalam dokumen yang akan disertakan dalam file PDF.

 Simpan dokumen dalam format PDF dengan subset font yang disematkan menggunakan`Save` metode`Document` objek, menentukan nama file keluaran dan opsi penyimpanan yang dikonfigurasi sebelumnya.

#### T: Apa manfaat menyematkan subkumpulan font dalam dokumen PDF?
J: Manfaat menyematkan subset font dalam dokumen PDF adalah:

Mengurangi ukuran file PDF: Dengan hanya menyertakan mesin terbang yang digunakan dalam dokumen, ukuran file PDF berkurang dibandingkan dengan menyematkan font lengkap.

Pelestarian tampilan dokumen: Subkumpulan font yang disertakan dalam file PDF memungkinkan untuk mereproduksi tampilan dokumen hanya dengan menggunakan karakter yang sebenarnya digunakan.

Kompatibilitas dengan batasan Lisensi: Menyematkan subkumpulan font mungkin lebih disukai jika font lengkap tidak dapat disematkan secara sah karena batasan lisensi.