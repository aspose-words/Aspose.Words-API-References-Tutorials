---
title: Ekspor Font Sebagai Basis 64
linktitle: Ekspor Font Sebagai Basis 64
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengekspor font sebagai Base64 menggunakan Aspose.Words untuk .NET dalam tutorial mendetail ini. Pastikan font tertanam dan ditampilkan dengan benar dalam file HTML.
type: docs
weight: 10
url: /id/net/programming-with-htmlsaveoptions/export-fonts-as-base-64/
---
## Perkenalan

Dalam hal memanipulasi dokumen Word secara terprogram, Aspose.Words untuk .NET adalah solusinya. Salah satu fitur bagusnya adalah mengekspor font sebagai Base64 dalam file HTML, memastikan font tertanam dan ditampilkan dengan benar di berbagai browser dan sistem. Dalam tutorial ini, kami akan mendalami bagaimana Anda dapat mencapai hal ini. Siap membuat font dokumen Word Anda ramah web? Mari kita mulai!

## Prasyarat

Sebelum kita beralih ke pengkodean, pastikan Anda memiliki semua yang Anda butuhkan:

-  Aspose.Words untuk .NET Library: Anda dapat mengunduhnya dari[Asumsikan Rilis](https://releases.aspose.com/words/net/) halaman.
- Lingkungan Pengembangan .NET: IDE apa pun seperti Visual Studio akan bekerja dengan sempurna.
- Pengetahuan Dasar C#: Anda tidak perlu menjadi seorang profesional, tetapi pemahaman dasar akan membantu.

## Impor Namespace

Untuk menggunakan Aspose.Words untuk .NET, Anda harus mengimpor namespace yang diperlukan dalam kode C# Anda. Ini membuat semua kelas dan metode tersedia untuk digunakan.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Langkah 1: Siapkan Proyek Anda

Hal pertama yang pertama, mari siapkan proyek Anda dan instal perpustakaan Aspose.Words.

### 1.1 Buat Proyek Baru

Buka Visual Studio dan buat proyek Aplikasi Konsol baru. Beri nama dengan sesuatu yang bermakna seperti "ExportFontsBase64".

### 1.2 Instal Aspose.Words

Anda dapat menginstal Aspose.Words untuk .NET melalui NuGet Package Manager:

1. Klik kanan pada proyek Anda di Solution Explorer.
2. Pilih "Kelola Paket NuGet".
3. Cari "Aspose.Words" dan instal.

Alternatifnya, Anda dapat menjalankan perintah berikut di Konsol Manajer Paket:

```sh
Install-Package Aspose.Words
```

## Langkah 2: Muat Dokumen Word Anda

Sekarang proyek Anda sudah siap, mari muat dokumen Word yang ingin Anda ekspor fontnya.

### 2.1 Tentukan Direktori Dokumen

Pertama, tentukan direktori tempat dokumen Word Anda berada:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

### 2.2 Memuat Dokumen

 Selanjutnya, muat dokumen Anda menggunakan`Document` kelas:

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

Pastikan "Rendering.docx" ada di direktori yang Anda tentukan.

## Langkah 3: Konfigurasikan Opsi Penyimpanan HTML

 Untuk mengekspor font sebagai Base64, kita perlu mengkonfigurasi`HtmlSaveOptions`.


 Buat sebuah contoh dari`HtmlSaveOptions` dan atur`ExportFontsAsBase64`properti ke`true`:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };
```

## Langkah 4: Simpan Dokumen sebagai HTML

Terakhir, mari simpan dokumen dengan opsi yang dikonfigurasi.


 Gunakan`Save` metode`Document` kelas untuk menyimpan dokumen Anda:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
```

Baris ini akan menyimpan dokumen Anda sebagai file HTML dengan font yang diekspor sebagai Base64, memastikan font tersebut tertanam di dalam HTML.

## Kesimpulan

Selamat! Anda telah berhasil mengekspor font sebagai Base64 dari dokumen Word menggunakan Aspose.Words untuk .NET. Ini memastikan font Anda dipertahankan dan ditampilkan dengan benar di berbagai platform. Baik Anda menyiapkan dokumen untuk tampilan web atau sekadar memastikan kompatibilitas, fitur ini sangat berguna.

## FAQ

### Apa itu pengkodean Base64?
Base64 adalah metode pengkodean data biner (seperti font) ke dalam format teks. Hal ini memastikan kompatibilitas dengan format berbasis teks seperti HTML.

### Mengapa saya harus menggunakan Base64 untuk font dalam HTML?
Penggunaan Base64 memastikan font tertanam langsung di HTML, menghindari masalah hilangnya file font, dan memastikan tampilan konsisten.

### Bisakah saya menggunakan metode ini untuk sumber lain seperti gambar?
Sangat! Aspose.Words untuk .NET memungkinkan Anda menyematkan berbagai sumber daya, termasuk gambar, sebagai Base64 dalam file HTML Anda.

### Bagaimana jika dokumen saya memiliki banyak font?
Tidak masalah! Aspose.Words untuk .NET akan menyematkan semua font yang digunakan dalam dokumen Anda sebagai Base64 dalam file HTML yang dihasilkan.

### Apakah Aspose.Words untuk .NET gratis untuk digunakan?
 Aspose.Words untuk .NET adalah perpustakaan komersial. Namun, Anda dapat mengunduh uji coba gratis dari[Asumsikan Rilis](https://releases.aspose.com/) halaman.
