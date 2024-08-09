---
title: Kode Berpagar
linktitle: Kode Berpagar
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menambahkan kode berpagar dan string info ke dokumen Word menggunakan Aspose.Words untuk .NET. Panduan langkah demi langkah disertakan. Tingkatkan keterampilan pemformatan dokumen Anda.
type: docs
weight: 10
url: /id/net/working-with-markdown/fenced-code/
---
## Perkenalan

Hai, rekan pembuat kode! Hari ini, kita menyelami dunia Aspose.Words untuk .NET untuk menguasai seni menambahkan kode berpagar dan kode berpagar dengan string info ke dokumen Word Anda. Bayangkan dokumen Word Anda sebagai kanvas, dan Anda, sang seniman, akan melukis dengan ketelitian seperti seorang pengembang berpengalaman. Dengan Aspose.Words, Anda mendapatkan kemampuan untuk menyempurnakan dokumen Anda secara terprogram dengan blok kode yang terstruktur dan terformat, membuat dokumen teknis Anda bersinar dengan profesionalisme dan kejelasan.

## Prasyarat

Sebelum kita masuk ke tutorial, pastikan Anda memiliki semua yang Anda butuhkan:

- Pengetahuan dasar C#: Pemahaman umum tentang C# akan membantu Anda memahami konsep dengan cepat.
-  Aspose.Words untuk .NET: Anda harus menginstal Aspose.Words untuk .NET. Jika Anda belum mendapatkannya, ambillah[Di Sini](https://releases.aspose.com/words/net/).
- Lingkungan Pengembangan: Visual Studio atau IDE C# lainnya yang Anda sukai.

## Impor Namespace

Hal pertama yang pertama, Anda perlu mengimpor namespace yang diperlukan. Ini seperti mengumpulkan semua alat Anda sebelum memulai sebuah proyek.

```csharp
using Aspose.Words;
using Aspose.Words.Style;
```

Sekarang, mari kita uraikan prosesnya langkah demi langkah.

## Langkah 1: Menyiapkan Proyek Anda

Sebelum kita dapat membuat blok kode yang indah dan terformat di dokumen Word kita, kita perlu menyiapkan proyek baru di Visual Studio.

1. Buat Proyek Baru: Buka Visual Studio dan buat Aplikasi Konsol C# baru.
2. Tambahkan Referensi Aspose.Words: Instal Aspose.Words melalui NuGet Package Manager. Anda dapat melakukan ini dengan mengklik kanan proyek Anda di Solution Explorer, memilih "Kelola Paket NuGet," dan mencari Aspose.Words.

## Langkah 2: Inisialisasi DocumentBuilder

Sekarang proyek Anda sudah siap, mari kita inisialisasi DocumentBuilder, yang akan menjadi alat utama kita untuk menambahkan konten ke dokumen Word.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Langkah 3: Buat Gaya untuk Kode Berpagar

Untuk menambahkan kode berpagar, pertama-tama kita perlu membuat gaya. Anggap saja ini sebagai pengaturan tema untuk blok kode kita.

```csharp
Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
fencedCode.Font.Name = "Courier New";
fencedCode.Font.Size = 10;
fencedCode.ParagraphFormat.LeftIndent = 20;
fencedCode.ParagraphFormat.RightIndent = 20;
fencedCode.ParagraphFormat.Shading.BackgroundPatternColor = Color.LightGray;
```

## Langkah 4: Tambahkan Kode Berpagar ke Dokumen

Dengan gaya kita yang siap, sekarang kita dapat menambahkan blok kode berpagar ke dokumen.

```csharp
builder.ParagraphFormat.Style = fencedCode;
builder.Writeln("This is a fenced code block");
```

## Langkah 5: Buat Style untuk Kode Berpagar dengan Info String

Terkadang, Anda mungkin ingin menentukan bahasa pemrograman atau menambahkan informasi tambahan ke blok kode Anda. Mari ciptakan gaya untuk itu.

```csharp
Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
fencedCodeWithInfo.Font.Name = "Courier New";
fencedCodeWithInfo.Font.Size = 10;
fencedCodeWithInfo.ParagraphFormat.LeftIndent = 20;
fencedCodeWithInfo.ParagraphFormat.RightIndent = 20;
fencedCodeWithInfo.ParagraphFormat.Shading.BackgroundPatternColor = Color.LightGray;
```

## Langkah 6: Tambahkan Kode Berpagar dengan Info String ke Dokumen

Sekarang, mari tambahkan blok kode berpagar dengan string info untuk menunjukkan bahwa itu adalah kode C#.

```csharp
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code block with info string - C#");
```

## Kesimpulan

Selamat! Anda baru saja menambahkan blok kode berpagar dan kode berpagar dengan string info ke dokumen Word Anda menggunakan Aspose.Words untuk .NET. Ini hanyalah puncak gunung es. Dengan Aspose.Words, Anda dapat mengotomatiskan dan meningkatkan pemrosesan dokumen Anda ke tingkat yang lebih tinggi. Teruslah menjelajah dan selamat coding!

## FAQ

### Apa itu Aspose.Words untuk .NET?
Aspose.Words untuk .NET adalah perpustakaan canggih yang memungkinkan pengembang membuat, memanipulasi, dan mengonversi dokumen Word secara terprogram.

### Bisakah saya menggunakan Aspose.Words dengan bahasa pemrograman lain?
Aspose.Words terutama mendukung bahasa .NET, tetapi ada versi yang tersedia untuk Java, Python, dan bahasa lainnya.

### Apakah Aspose.Words gratis untuk digunakan?
 Aspose.Words adalah produk komersial, tetapi Anda dapat mengunduh uji coba gratis[Di Sini](https://releases.aspose.com/)untuk menjelajahi fitur-fiturnya.

### Bagaimana saya bisa mendapatkan dukungan untuk Aspose.Words?
 Anda bisa mendapatkan dukungan dari komunitas dan pengembang Aspose[Di Sini](https://forum.aspose.com/c/words/8).

### Fitur lain apa yang ditawarkan Aspose.Words?
Aspose.Words menawarkan berbagai fitur termasuk konversi dokumen, pembuatan dokumen berbasis template, pelaporan, dan banyak lagi.