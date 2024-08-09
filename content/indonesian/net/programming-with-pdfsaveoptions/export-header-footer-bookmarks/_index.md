---
title: Ekspor Bookmark Header Footer Dokumen Word ke Dokumen PDF
linktitle: Ekspor Bookmark Header Footer Dokumen Word ke Dokumen PDF
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengekspor bookmark header dan footer dari dokumen Word ke PDF menggunakan Aspose.Words untuk .NET dengan panduan langkah demi langkah kami.
type: docs
weight: 10
url: /id/net/programming-with-pdfsaveoptions/export-header-footer-bookmarks/
---
## Perkenalan

Mengonversi dokumen Word ke PDF adalah tugas umum, terutama saat Anda ingin berbagi atau mengarsipkan dokumen sambil mempertahankan formatnya. Terkadang, dokumen-dokumen ini berisi penanda penting di dalam header dan footer. Dalam tutorial ini, kita akan memandu proses mengekspor bookmark ini dari dokumen Word ke PDF menggunakan Aspose.Words untuk .NET.

## Prasyarat

Sebelum kita mendalaminya, pastikan Anda memiliki hal berikut:

- Aspose.Words untuk .NET: Anda harus menginstal Aspose.Words untuk .NET. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/words/net/).
- Lingkungan Pengembangan: Siapkan lingkungan pengembangan Anda. Anda dapat menggunakan Visual Studio atau IDE lain yang kompatibel dengan .NET.
- Pengetahuan Dasar C#: Keakraban dengan pemrograman C# diperlukan untuk mengikuti contoh kode.

## Impor Namespace

Hal pertama yang pertama, Anda perlu mengimpor namespace yang diperlukan dalam proyek C# Anda. Tambahkan baris ini di bagian atas file kode Anda:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Mari kita bagi prosesnya menjadi langkah-langkah yang mudah diikuti.

## Langkah 1: Inisialisasi Dokumen

Langkah pertama adalah memuat dokumen Word Anda. Inilah cara Anda melakukannya:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");
```

Pada langkah ini, Anda cukup menentukan jalur ke direktori dokumen Anda dan memuat dokumen Word.

## Langkah 2: Konfigurasikan Opsi Penyimpanan PDF

Selanjutnya, Anda perlu mengonfigurasi opsi penyimpanan PDF untuk memastikan bahwa bookmark di header dan footer diekspor dengan benar.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;
```

 Di sini, kami sedang menyiapkan`PdfSaveOptions` . Itu`DefaultBookmarksOutlineLevel` properti menetapkan tingkat garis besar untuk bookmark, dan`HeaderFooterBookmarksExportMode` properti memastikan bahwa hanya kemunculan pertama bookmark di header dan footer yang diekspor.

## Langkah 3: Simpan Dokumen sebagai PDF

Terakhir, simpan dokumen Anda sebagai PDF dengan opsi yang dikonfigurasi.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);
```

Pada langkah ini, Anda menyimpan dokumen ke jalur yang ditentukan dengan opsi yang telah Anda konfigurasi.

## Kesimpulan

Dan itu dia! Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah mengekspor bookmark dari header dan footer dokumen Word ke PDF menggunakan Aspose.Words untuk .NET. Metode ini memastikan bahwa alat bantu navigasi penting dalam dokumen Anda disimpan dalam format PDF, sehingga memudahkan pembaca untuk menavigasi dokumen Anda.

## FAQ

### Bisakah saya mengekspor semua bookmark dari dokumen Word ke PDF?

 Ya, kamu bisa. Di`PdfSaveOptions`, Anda dapat menyesuaikan pengaturan untuk menyertakan semua bookmark jika diperlukan.

### Bagaimana jika saya ingin mengekspor bookmark dari badan dokumen juga?

 Anda dapat mengonfigurasi`OutlineOptions` di dalam`PdfSaveOptions` untuk menyertakan penanda dari badan dokumen.

### Apakah mungkin untuk menyesuaikan level bookmark di PDF?

 Sangat! Anda dapat menyesuaikannya`DefaultBookmarksOutlineLevel` properti untuk mengatur tingkat garis besar yang berbeda untuk bookmark Anda.

### Bagaimana cara menangani dokumen tanpa bookmark?

Jika dokumen Anda tidak memiliki penanda, PDF akan dihasilkan tanpa kerangka penanda apa pun. Pastikan dokumen Anda berisi penanda jika Anda memerlukannya dalam PDF.

### Bisakah saya menggunakan metode ini untuk jenis dokumen lain seperti DOCX atau RTF?

Ya, Aspose.Words for .NET mendukung berbagai jenis dokumen, termasuk DOCX, RTF, dan lainnya.