---
title: Atur Folder Font
linktitle: Atur Folder Font
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengatur folder font khusus di Aspose.Words untuk .NET untuk memastikan dokumen Word Anda dirender dengan benar tanpa kehilangan font.
type: docs
weight: 10
url: /id/net/working-with-fonts/set-fonts-folder/
---
## Perkenalan

Pernahkah Anda menghadapi masalah dengan font yang hilang saat bekerja dengan dokumen Word di aplikasi .NET Anda? Ya, kamu tidak sendirian. Mengatur folder font yang benar dapat mengatasi masalah ini dengan mulus. Dalam panduan ini, kami akan memandu Anda tentang cara mengatur folder font menggunakan Aspose.Words untuk .NET. Ayo selami!

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal berikut:

- Visual Studio diinstal pada mesin Anda
- Pengaturan .NET Framework
-  Aspose.Words untuk perpustakaan .NET. Jika Anda belum melakukannya, Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/words/net/).

## Impor Namespace

Pertama, Anda perlu mengimpor namespace yang diperlukan untuk bekerja dengan Aspose.Words. Tambahkan baris berikut di bagian atas file kode Anda:

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
```

Menyiapkan folder font sangatlah mudah jika Anda mengikuti langkah-langkah ini dengan cermat.

## Langkah 1: Tentukan Direktori Dokumen

Sebelum melakukan hal lain, tentukan jalur ke direktori dokumen Anda. Direktori ini akan berisi dokumen Word Anda dan font yang ingin Anda gunakan.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Pastikan untuk mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori Anda.

## Langkah 2: Inisialisasi Pengaturan Font

 Sekarang, Anda perlu menginisialisasi`FontSettings` obyek. Objek ini memungkinkan Anda menentukan folder font khusus.

```csharp
FontSettings fontSettings = new FontSettings();
```

## Langkah 3: Atur Folder Font

 Menggunakan`SetFontsFolder` metode`FontSettings` objek, tentukan folder tempat font khusus Anda disimpan.

```csharp
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
```

 Di Sini,`dataDir + "Fonts"` menunjuk ke folder bernama "Font" di dalam direktori dokumen Anda. Parameter kedua,`false`, menunjukkan bahwa folder tersebut tidak rekursif.

## Langkah 4: Buat LoadOptions

 Selanjutnya, buat sebuah instance dari`LoadOptions` kelas. Kelas ini akan membantu Anda memuat dokumen dengan pengaturan font yang ditentukan.

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
```

## Langkah 5: Muat Dokumen

 Terakhir, muat dokumen Word menggunakan`Document` kelas dan`LoadOptions` obyek.

```csharp
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);
```

 Pastikan itu`"Rendering.docx"` adalah nama dokumen Word Anda. Anda dapat menggantinya dengan nama file Anda.

## Kesimpulan

Dan itu dia! Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah mengatur folder font kustom di Aspose.Words untuk .NET, memastikan bahwa semua font Anda dirender dengan benar. Penyiapan sederhana ini dapat menghemat banyak kerumitan dan membuat dokumen Anda terlihat persis seperti yang Anda inginkan.

## FAQ

### Mengapa saya perlu mengatur folder font khusus?
Menyetel folder font khusus memastikan bahwa semua font yang digunakan dalam dokumen Word Anda dirender dengan benar, menghindari masalah font yang hilang.

### Bisakah saya mengatur beberapa folder font?
 Ya, Anda dapat menggunakan`SetFontsFolders` metode untuk menentukan beberapa folder.

### Apa yang terjadi jika font tidak ditemukan?
Aspose.Words akan mencoba mengganti font yang hilang dengan font serupa dari font sistem.

### Apakah Aspose.Words kompatibel dengan .NET Core?
Ya, Aspose.Words mendukung .NET Core bersama dengan .NET Framework.

### Di mana saya bisa mendapatkan dukungan jika saya menghadapi masalah?
 Anda bisa mendapatkan dukungan dari[Forum dukungan Aspose.Words](https://forum.aspose.com/c/words/8).