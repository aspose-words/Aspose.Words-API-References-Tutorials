---
title: Periksa Efek Teks DrawingML
linktitle: Periksa Efek Teks DrawingML
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara memeriksa efek teks DrawingML di dokumen Word menggunakan Aspose.Words untuk .NET dengan panduan langkah demi langkah kami yang terperinci. Sempurnakan dokumen Anda dengan mudah.
type: docs
weight: 10
url: /id/net/working-with-fonts/check-drawingml-text-effect/
---
## Perkenalan

Selamat datang di tutorial mendetail lainnya tentang bekerja dengan Aspose.Words untuk .NET! Hari ini, kita menyelami dunia efek teks DrawingML yang menakjubkan. Baik Anda ingin menyempurnakan dokumen Word Anda dengan bayangan, pantulan, atau efek 3D, panduan ini akan menunjukkan cara memeriksa efek teks ini di dokumen Anda menggunakan Aspose.Words untuk .NET. Mari kita mulai!

## Prasyarat

Sebelum kita masuk ke tutorial, ada beberapa prasyarat yang harus Anda miliki:

-  Aspose.Words for .NET Library: Pastikan Anda telah menginstal perpustakaan Aspose.Words for .NET. Anda dapat mengunduhnya dari[Halaman rilis Aspose](https://releases.aspose.com/words/net/).
- Lingkungan Pengembangan: Anda harus menyiapkan lingkungan pengembangan, seperti Visual Studio.
- Pengetahuan Dasar C#: Keakraban dengan pemrograman C# akan sangat membantu.

## Impor Namespace

Pertama, Anda perlu mengimpor namespace yang diperlukan. Namespace ini akan memberi Anda akses ke kelas dan metode yang diperlukan untuk memanipulasi dokumen Word dan memeriksa efek teks DrawingML.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Panduan Langkah demi Langkah untuk Memeriksa Efek Teks DrawingML

Sekarang, mari kita bagi prosesnya menjadi beberapa langkah, agar lebih mudah untuk diikuti.

## Langkah 1: Muat Dokumen

Langkah pertama adalah memuat dokumen Word yang ingin Anda periksa efek teks DrawingMLnya. 

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "DrawingML text effects.docx");
```

Cuplikan kode ini memuat dokumen bernama "DrawingML text effect.docx" dari direktori yang Anda tentukan.

## Langkah 2: Akses Koleksi Runs

Selanjutnya, kita perlu mengakses kumpulan proses di paragraf pertama dokumen. Berjalan adalah bagian teks dengan format yang sama.

```csharp
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
```

Baris kode ini mengambil proses dari paragraf pertama di bagian pertama dokumen.

## Langkah 3: Dapatkan Font yang Dijalankan Pertama

Sekarang, kita akan mendapatkan properti font yang dijalankan pertama kali di koleksi run. Hal ini memungkinkan kita memeriksa berbagai efek teks DrawingML yang diterapkan pada teks.

```csharp
Font runFont = runs[0].Font;
```

## Langkah 4: Periksa Efek Teks DrawingML

Terakhir, kita dapat memeriksa berbagai efek teks DrawingML seperti Bayangan, Efek 3D, Refleksi, Garis Besar, dan Isi.

```csharp
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));
```

 Baris kode ini akan dicetak`true` atau`false` bergantung pada apakah setiap efek teks DrawingML tertentu diterapkan ke font proses.

## Kesimpulan

Selamat! Anda baru saja mempelajari cara memeriksa efek teks DrawingML di dokumen Word menggunakan Aspose.Words untuk .NET. Fitur canggih ini memungkinkan Anda mendeteksi dan memanipulasi pemformatan teks canggih secara terprogram, memberi Anda kontrol lebih besar atas tugas pemrosesan dokumen Anda.


## FAQ

### Apa itu efek teks DrawingML?
Efek teks DrawingML adalah opsi pemformatan teks tingkat lanjut di dokumen Word, termasuk bayangan, efek 3D, pantulan, kerangka, dan isian.

### Bisakah saya menerapkan efek teks DrawingML menggunakan Aspose.Words untuk .NET?
Ya, Aspose.Words untuk .NET memungkinkan Anda memeriksa dan menerapkan efek teks DrawingML secara terprogram.

### Apakah saya memerlukan lisensi untuk menggunakan Aspose.Words untuk .NET?
 Ya, Aspose.Words untuk .NET memerlukan lisensi untuk fungsionalitas penuh. Anda dapat memperoleh a[izin sementara](https://purchase.aspose.com/temporary-license/) untuk evaluasi.

### Apakah ada uji coba gratis yang tersedia untuk Aspose.Words untuk .NET?
 Ya, Anda dapat mengunduh a[uji coba gratis](https://releases.aspose.com/) untuk mencoba Aspose.Words untuk .NET sebelum membeli.

### Di mana saya dapat menemukan dokumentasi lebih lanjut tentang Aspose.Words untuk .NET?
 Anda dapat menemukan dokumentasi terperinci di[Aspose.Words untuk halaman Dokumentasi .NET](https://reference.aspose.com/words/net/).