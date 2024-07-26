---
title: Escape URI dalam Dokumen PDF
linktitle: Escape URI dalam Dokumen PDF
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara keluar dari URI dalam PDF menggunakan Aspose.Words untuk .NET. Panduan terperinci ini memandu Anda melalui proses langkah demi langkah.
type: docs
weight: 10
url: /id/net/programming-with-pdfsaveoptions/escape-uri/
---
## Perkenalan

Hai! Pernah bertanya-tanya bagaimana cara menangani URI saat menyimpan dokumen Word sebagai PDF menggunakan Aspose.Words untuk .NET? Anda berada di tempat yang tepat! Hari ini, kita akan mendalami cara keluar dari URI dalam dokumen PDF untuk memastikan URI berfungsi dengan benar saat dokumen Anda dikonversi. Mari kita memulai perjalanan ini bersama-sama, selangkah demi selangkah, memastikan Anda memahami setiap konsep selama prosesnya.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki semua yang Anda butuhkan:

1.  Aspose.Words untuk .NET: Pastikan Anda memiliki versi terbaru. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/words/net/).
2. Lingkungan Pengembangan: Visual Studio atau lingkungan pengembangan .NET lainnya.
3. Pengetahuan Dasar C#: Tutorial ini mengasumsikan Anda memiliki pemahaman dasar tentang pemrograman C#.

## Impor Namespace

Hal pertama yang pertama, Anda perlu mengimpor namespace yang diperlukan. Ini penting untuk mengakses fungsionalitas Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Baiklah, mari kita bagi prosesnya menjadi langkah-langkah yang mudah dicerna. Ikuti terus dan Anda akan menjadi ahli dalam keluar dari URI dalam waktu singkat!

## Langkah 1: Siapkan Direktori Dokumen Anda

Sebelum mendalami kodenya, siapkan jalur ke direktori dokumen Anda. Di sinilah file Anda akan disimpan.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya tempat Anda ingin menyimpan dokumen PDF Anda.

## Langkah 2: Buat Dokumen Baru

Selanjutnya, kita akan membuat dokumen baru menggunakan Aspose.Words. Dokumen ini akan berfungsi sebagai kanvas kita untuk menyisipkan hyperlink.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Di Sini,`Document` adalah dokumen Word baru Anda, dan`DocumentBuilder` adalah kelas pembantu yang menyederhanakan proses pembuatan dokumen.

## Langkah 3: Masukkan Hyperlink

Sekarang, mari masukkan hyperlink ke dalam dokumen. Hyperlink ini akan menjadi fokus proses pelolosan URI kami.

```csharp
builder.InsertHyperlink("Testlink", "https://www.google.com/search?q= aspose", salah);
```

 Di baris ini,`"Testlink"` adalah teks tampilan untuk hyperlink, dan`"https://www.google.com/search?q= aspose"` adalah URL-nya. Itu`false` parameter menunjukkan bahwa tautan tidak boleh diformat sebagai hyperlink (yaitu, tidak akan digarisbawahi dan berwarna biru).

## Langkah 4: Simpan Dokumen sebagai PDF

Terakhir, simpan dokumen sebagai PDF. Di sinilah Aspose.Words menangani pelolosan URI dalam keluaran PDF.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");
```

 Baris ini menyimpan dokumen ke direktori yang ditentukan dengan nama file`WorkingWithPdfSaveOptions.EscapeUri.pdf`.

## Kesimpulan

Dan itu dia! Anda baru saja mempelajari cara keluar dari URI saat menyimpan dokumen Word sebagai PDF menggunakan Aspose.Words untuk .NET. Proses ini memastikan bahwa hyperlink Anda tetap berfungsi dan diformat dengan benar dalam PDF yang dihasilkan. 

Ingat, menguasai teknik-teknik kecil namun signifikan ini dapat meningkatkan kualitas dan fungsionalitas dokumen Anda secara signifikan. Selamat membuat kode!

## FAQ

### Apa itu Aspose.Words untuk .NET?

Aspose.Words untuk .NET adalah perpustakaan canggih yang memungkinkan pengembang membuat, memanipulasi, dan mengonversi dokumen Word dalam aplikasi .NET.

### Mengapa pelolosan URI penting dalam PDF?

Pelarian URI memastikan bahwa karakter khusus dalam URL diinterpretasikan dengan benar, mencegah tautan rusak dan memastikannya berfungsi sebagaimana mestinya.

### Bisakah saya menggunakan jenis tautan lain di Aspose.Words untuk .NET?

Sangat! Aspose.Words mendukung berbagai jenis tautan, termasuk tautan dokumen internal, bookmark, dan URL eksternal.

### Bagaimana saya bisa mendapatkan uji coba gratis Aspose.Words untuk .NET?

 Anda bisa mendapatkan uji coba gratis[Di Sini](https://releases.aspose.com/).

### Di mana saya dapat menemukan dokumentasi lebih rinci tentang Aspose.Words untuk .NET?

 Anda dapat menemukan dokumentasi detailnya[Di Sini](https://reference.aspose.com/words/net/).
