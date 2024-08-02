---
title: Tambahkan Awalan Nama Kelas Css
linktitle: Tambahkan Awalan Nama Kelas Css
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menambahkan awalan nama kelas CSS saat menyimpan dokumen Word sebagai HTML menggunakan Aspose.Words untuk .NET. Panduan langkah demi langkah, cuplikan kode, dan FAQ disertakan.
type: docs
weight: 10
url: /id/net/programming-with-htmlsaveoptions/add-css-class-name-prefix/
---
## Perkenalan

Selamat datang! Jika Anda mendalami dunia Aspose.Words untuk .NET, Anda akan mendapat hadiahnya. Hari ini, kita akan mempelajari cara menambahkan awalan nama kelas CSS saat menyimpan dokumen Word sebagai HTML menggunakan Aspose.Words untuk .NET. Fitur ini sangat berguna ketika Anda ingin menghindari konflik nama kelas dalam file HTML Anda.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal berikut:

-  Aspose.Words untuk .NET: Jika Anda belum menginstalnya,[Unduh di sini](https://releases.aspose.com/words/net/).
- Lingkungan Pengembangan: Visual Studio atau C# IDE lainnya.
-  Dokumen Word: Kami akan menggunakan dokumen bernama`Rendering.docx`. Tempatkan di direktori proyek Anda.

## Impor Namespace

Pertama, pastikan Anda telah mengimpor namespace yang diperlukan ke proyek C# Anda. Tambahkan ini di bagian atas file kode Anda:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

Sekarang, mari selami panduan langkah demi langkah!

## Langkah 1: Siapkan Proyek Anda

Sebelum kita dapat mulai menambahkan awalan nama kelas CSS, mari siapkan proyek kita.

### Langkah 1.1: Buat Proyek Baru

 Jalankan Visual Studio Anda dan buat proyek Aplikasi Konsol baru. Beri nama sesuatu yang menarik`AsposeCssPrefixExample`.

### Langkah 1.2: Tambahkan Aspose.Words untuk .NET

Jika Anda belum melakukannya, tambahkan Aspose.Words for .NET ke proyek Anda melalui NuGet. Cukup buka Konsol Manajer Paket NuGet dan jalankan:

```bash
Install-Package Aspose.Words
```

Besar! Sekarang, kami siap untuk memulai coding.

## Langkah 2: Muat Dokumen Anda

Hal pertama yang perlu kita lakukan adalah memuat dokumen Word yang ingin kita konversi ke HTML.

### Langkah 2.1: Tentukan Jalur Dokumen

 Siapkan jalur ke direktori dokumen Anda. Demi tutorial ini, anggaplah dokumen Anda ada di folder bernama`Documents` dalam direktori proyek Anda.

```csharp
string dataDir = @"C:\YourProject\Documents\";
```

### Langkah 2.2: Muat Dokumen

Sekarang, mari muat dokumen menggunakan Aspose.Words:

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Langkah 3: Konfigurasikan Opsi Penyimpanan HTML

Selanjutnya, kita perlu mengkonfigurasi opsi penyimpanan HTML untuk menyertakan awalan nama kelas CSS.

### Langkah 3.1: Buat Opsi Penyimpanan HTML

 Buat instance`HtmlSaveOptions` objek dan atur jenis lembar gaya CSS menjadi`External`.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
    CssStyleSheetType = CssStyleSheetType.External
};
```

### Langkah 3.2: Tetapkan Awalan Nama Kelas CSS

 Sekarang, mari kita atur`CssClassNamePrefix` properti ke awalan yang Anda inginkan. Untuk contoh ini, kami akan menggunakan`"pfx_"`.

```csharp
saveOptions.CssClassNamePrefix = "pfx_";
```

## Langkah 4: Simpan Dokumen sebagai HTML

Terakhir, mari simpan dokumen sebagai file HTML dengan opsi yang dikonfigurasi.


Tentukan jalur file HTML keluaran dan simpan dokumen.

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
```

## Langkah 5: Verifikasi Outputnya

 Setelah menjalankan proyek Anda, navigasikan ke`Documents` map. Anda harus menemukan file HTML bernama`WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html` . Buka file ini di editor teks atau browser untuk memverifikasi bahwa kelas CSS memiliki awalan`pfx_`.

## Kesimpulan

Dan itu dia! Dengan mengikuti langkah-langkah ini, Anda telah berhasil menambahkan awalan nama kelas CSS ke output HTML Anda menggunakan Aspose.Words untuk .NET. Fitur sederhana namun kuat ini dapat membantu Anda mempertahankan gaya yang bersih dan bebas konflik dalam dokumen HTML Anda.

## FAQ

### Bisakah saya menggunakan awalan berbeda untuk setiap operasi penyimpanan?
 Ya, Anda dapat menyesuaikan awalan setiap kali Anda menyimpan dokumen dengan mengubah`CssClassNamePrefix` Properti.

### Apakah metode ini mendukung CSS sebaris?
 Itu`CssClassNamePrefix`properti berfungsi dengan CSS eksternal. Untuk CSS sebaris, Anda memerlukan pendekatan berbeda.

### Bagaimana cara menyertakan opsi penyimpanan HTML lainnya?
 Anda dapat mengonfigurasi berbagai properti`HtmlSaveOptions` untuk menyesuaikan keluaran HTML Anda. Periksalah[dokumentasi](https://reference.aspose.com/words/net/) untuk lebih jelasnya.

### Apakah mungkin menyimpan HTML ke aliran?
 Sangat! Anda dapat menyimpan dokumen ke aliran dengan meneruskan objek aliran ke`Save` metode.

### Bagaimana cara mendapatkan dukungan jika saya mengalami masalah?
 Anda bisa mendapatkan dukungan dari[Asumsikan forum](https://forum.aspose.com/c/words/8).