---
title: Putuskan tautan Header Footer
linktitle: Putuskan tautan Header Footer
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara memutuskan tautan header dan footer di dokumen Word menggunakan Aspose.Words untuk .NET. Ikuti panduan langkah demi langkah kami yang terperinci untuk menguasai manipulasi dokumen.
type: docs
weight: 10
url: /id/net/join-and-append-documents/unlink-headers-footers/
---
## Perkenalan

Dalam dunia pemrosesan dokumen, menjaga konsistensi header dan footer terkadang bisa menjadi tantangan. Baik Anda menggabungkan dokumen atau hanya ingin memiliki header dan footer berbeda untuk bagian berbeda, mengetahui cara memutuskan tautannya sangatlah penting. Hari ini, kita akan mendalami bagaimana Anda dapat mencapai hal ini menggunakan Aspose.Words untuk .NET. Kami akan menguraikannya langkah demi langkah sehingga Anda dapat mengikutinya dengan mudah. Siap menguasai manipulasi dokumen? Mari kita mulai!

## Prasyarat

Sebelum kita mendalami seluk beluknya, ada beberapa hal yang Anda perlukan:

-  Aspose.Words untuk .NET Library: Anda dapat mengunduhnya dari[Halaman rilis Aspose](https://releases.aspose.com/words/net/).
- .NET Framework: Pastikan Anda telah menginstal kerangka .NET yang kompatibel.
- IDE: Visual Studio atau Lingkungan Pengembangan Terintegrasi yang kompatibel dengan .NET lainnya.
- Pemahaman Dasar C#: Anda memerlukan pemahaman dasar tentang bahasa pemrograman C#.

## Impor Namespace

Untuk memulai, pastikan untuk mengimpor namespace yang diperlukan dalam proyek Anda. Ini akan memungkinkan Anda mengakses perpustakaan Aspose.Words dan fitur-fiturnya.

```csharp
using Aspose.Words;
```

Mari kita bagi prosesnya menjadi langkah-langkah yang dapat dikelola untuk membantu Anda memutuskan tautan header dan footer di dokumen Word Anda.

## Langkah 1: Siapkan Proyek Anda

Pertama, Anda harus menyiapkan lingkungan proyek Anda. Buka IDE Anda dan buat proyek .NET baru. Tambahkan referensi ke perpustakaan Aspose.Words yang Anda unduh sebelumnya.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Muat Dokumen Sumber

Selanjutnya, Anda perlu memuat dokumen sumber yang ingin Anda modifikasi. Header dan footer dokumen ini akan dibatalkan tautannya.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
```

## Langkah 3: Muat Dokumen Tujuan

Sekarang, muat dokumen tujuan tempat Anda akan menambahkan dokumen sumber setelah memutuskan tautan header dan footernya.

```csharp
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Langkah 4: Putuskan Tautan Header dan Footer

 Langkah ini sangat penting. Untuk membatalkan tautan header dan footer dokumen sumber dari dokumen tujuan, Anda akan menggunakan`LinkToPrevious` metode. Metode ini memastikan bahwa header dan footer tidak terbawa ke dokumen terlampir.

```csharp
// Putuskan tautan header dan footer di dokumen sumber untuk menghentikan hal ini
//dari melanjutkan header dan footer dokumen tujuan.
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Langkah 5: Tambahkan Dokumen Sumber

 Setelah membatalkan tautan header dan footer, Anda dapat menambahkan dokumen sumber ke dokumen tujuan. Menggunakan`AppendDocument` metode dan atur mode format impor ke`KeepSourceFormatting` untuk mempertahankan format asli dokumen sumber.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Langkah 6: Simpan Dokumen Akhir

Terakhir, simpan dokumen yang baru dibuat. Dokumen ini akan memiliki konten dokumen sumber yang ditambahkan ke dokumen tujuan, dengan header dan footer tidak tertaut.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

## Kesimpulan

Dan itu dia! Dengan mengikuti langkah-langkah ini, Anda telah berhasil memutuskan tautan header dan footer di dokumen sumber dan menambahkannya ke dokumen tujuan menggunakan Aspose.Words untuk .NET. Teknik ini bisa sangat berguna ketika Anda bekerja dengan dokumen kompleks yang memerlukan header dan footer berbeda untuk bagian berbeda. Selamat membuat kode!

## FAQ

### Apa itu Aspose.Words untuk .NET?  
Aspose.Words for .NET adalah perpustakaan yang kuat untuk bekerja dengan dokumen Word di aplikasi .NET. Hal ini memungkinkan pengembang untuk membuat, memodifikasi, mengkonversi, dan mencetak dokumen secara terprogram.

### Bisakah saya membatalkan tautan header dan footer hanya untuk bagian tertentu?  
 Ya, Anda dapat memutuskan tautan header dan footer untuk bagian tertentu dengan mengakses`HeadersFooters` properti bagian yang diinginkan dan menggunakan`LinkToPrevious` metode.

### Apakah mungkin mempertahankan format asli dokumen sumber?  
 Ya, saat menambahkan dokumen sumber, gunakan`ImportFormatMode.KeepSourceFormatting` pilihan untuk mempertahankan format asli.

### Bisakah saya menggunakan Aspose.Words untuk .NET dengan bahasa .NET lain selain C#?  
Sangat! Aspose.Words untuk .NET dapat digunakan dengan bahasa .NET apa pun, termasuk VB.NET dan F#.

### Di mana saya dapat menemukan lebih banyak dokumentasi dan dukungan untuk Aspose.Words untuk .NET?  
 Anda dapat menemukan dokumentasi lengkap di[Halaman dokumentasi Aspose.Words untuk .NET](https://reference.aspose.com/words/net/) , dan dukungan tersedia di[Asumsikan forum](https://forum.aspose.com/c/words/8).
