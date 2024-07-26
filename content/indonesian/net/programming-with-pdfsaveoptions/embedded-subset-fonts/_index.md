---
title: Sematkan Subset Font dalam Dokumen PDF
linktitle: Sematkan Subset Font dalam Dokumen PDF
second_title: API Pemrosesan Dokumen Aspose.Words
description: Kurangi ukuran file PDF dengan hanya menyematkan subset font yang diperlukan menggunakan Aspose.Words untuk .NET. Ikuti panduan langkah demi langkah kami untuk mengoptimalkan PDF Anda secara efisien.
type: docs
weight: 10
url: /id/net/programming-with-pdfsaveoptions/embedded-subset-fonts/
---
## Perkenalan

Pernahkah Anda memperhatikan bagaimana beberapa file PDF jauh lebih besar daripada yang lain, meskipun berisi konten serupa? Pelakunya sering kali terletak pada font. Menyematkan font dalam PDF memastikan tampilannya sama di perangkat apa pun, tetapi juga dapat memperbesar ukuran file. Untungnya, Aspose.Words untuk .NET menawarkan fitur praktis untuk menyematkan subset font yang diperlukan saja, menjaga PDF Anda tetap ramping dan efisien. Tutorial ini akan memandu Anda melalui prosesnya, langkah demi langkah.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal berikut:

-  Aspose.Words untuk .NET: Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/words/net/).
- Lingkungan .NET: Pastikan Anda memiliki lingkungan pengembangan .NET yang berfungsi.
- Pengetahuan Dasar C#: Keakraban dengan pemrograman C# akan membantu Anda mengikutinya.

## Impor Namespace

Untuk menggunakan Aspose.Words untuk .NET, Anda perlu mengimpor namespace yang diperlukan dalam proyek Anda. Tambahkan ini di bagian atas file C# Anda:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

## Langkah 1: Muat Dokumen

 Pertama, kita perlu memuat dokumen Word yang ingin kita konversi ke PDF. Ini dilakukan dengan menggunakan`Document` kelas yang disediakan oleh Aspose.Words.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Cuplikan kode ini memuat dokumen yang terletak di`dataDir` . Pastikan untuk mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke dokumen Anda.

## Langkah 2: Konfigurasikan Opsi Penyimpanan PDF

 Selanjutnya kita konfigurasikan`PdfSaveOptions` untuk memastikan bahwa hanya subset font yang diperlukan yang tertanam. Dengan mengatur`EmbedFullFonts` ke`false`, kami memberi tahu Aspose.Words untuk hanya menyematkan mesin terbang yang digunakan dalam dokumen.

```csharp
// PDF keluaran akan berisi subkumpulan font dalam dokumen.
// Hanya mesin terbang yang digunakan dalam dokumen yang disertakan dalam font PDF.
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
```

Langkah kecil namun penting ini membantu mengurangi ukuran file PDF secara signifikan.

## Langkah 3: Simpan Dokumen sebagai PDF

 Terakhir, kami menyimpan dokumen sebagai PDF menggunakan`Save` metode, menerapkan yang dikonfigurasi`PdfSaveOptions`.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbedSubsetFonts.pdf", saveOptions);
```

 Kode ini akan menghasilkan file PDF dengan nama`WorkingWithPdfSaveOptions.EmbedSubsetFonts.pdf` di direktori yang ditentukan, dengan hanya subset font yang diperlukan yang tertanam.

## Kesimpulan

Dan itu dia! Dengan mengikuti langkah-langkah sederhana ini, Anda dapat mengurangi ukuran file PDF secara efisien dengan hanya menyematkan subkumpulan font yang diperlukan menggunakan Aspose.Words untuk .NET. Hal ini tidak hanya menghemat ruang penyimpanan tetapi juga memastikan waktu muat lebih cepat dan kinerja lebih baik, terutama untuk dokumen dengan font besar.

## FAQ

### Mengapa saya harus menyematkan subkumpulan font saja dalam PDF?
Menyematkan hanya subset font yang diperlukan dapat mengurangi ukuran file PDF secara signifikan tanpa mengurangi tampilan dan keterbacaan dokumen.

### Bisakah saya kembali menyematkan font lengkap jika diperlukan?
 Ya kamu bisa. Cukup atur`EmbedFullFonts`properti ke`true` dalam`PdfSaveOptions`.

### Apakah Aspose.Words untuk .NET mendukung fitur pengoptimalan PDF lainnya?
Sangat! Aspose.Words untuk .NET menawarkan berbagai opsi untuk mengoptimalkan PDF, termasuk kompresi gambar dan menghapus objek yang tidak digunakan.

### Jenis font apa yang dapat disisipkan subset menggunakan Aspose.Words untuk .NET?
Aspose.Words untuk .NET mendukung penyematan subset untuk semua font TrueType yang digunakan dalam dokumen.

### Bagaimana cara memverifikasi font mana yang tertanam dalam PDF saya?
Anda dapat membuka PDF di Adobe Acrobat Reader dan memeriksa properti di bawah tab Font untuk melihat font yang disematkan.
