---
title: Daftar pesanan
linktitle: Daftar pesanan
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara membuat daftar berurutan di dokumen Word menggunakan Aspose.Words untuk .NET dengan panduan langkah demi langkah kami. Sempurna untuk mengotomatiskan pembuatan dokumen.
type: docs
weight: 10
url: /id/net/working-with-markdown/ordered-list/
---
## Perkenalan

Jadi, Anda memutuskan untuk mendalami Aspose.Words untuk .NET guna membuat dokumen Word yang menakjubkan secara terprogram. Pilihan yang fantastis! Hari ini, kami akan menguraikan cara membuat daftar terurut dalam dokumen Word. Kami akan melakukannya langkah demi langkah, jadi apakah Anda seorang pemula coding atau profesional berpengalaman, Anda akan merasakan panduan ini sangat berguna. Mari kita mulai!

## Prasyarat

Sebelum kita mendalami kodenya, ada beberapa hal yang Anda perlukan:

1.  Aspose.Words for .NET: Pastikan Anda telah menginstal Aspose.Words for .NET. Jika tidak, Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/words/net/).
2. Lingkungan Pengembangan: Visual Studio atau IDE lain yang kompatibel dengan .NET.
3. Pengetahuan Dasar C#: Anda harus terbiasa dengan dasar-dasar C# agar mudah diikuti.

## Impor Namespace

Untuk menggunakan Aspose.Words dalam proyek Anda, Anda perlu mengimpor namespace yang diperlukan. Ini seperti menyiapkan kotak peralatan Anda sebelum mulai bekerja.

```csharp
using Aspose.Words;
using Aspose.Words.Lists;
```

Mari kita pecahkan kodenya menjadi beberapa langkah kecil dan jelaskan setiap bagiannya. Siap? Ini dia!

## Langkah 1: Inisialisasi Dokumen

Hal pertama yang pertama, Anda perlu membuat dokumen baru. Anggap saja ini seperti membuka dokumen Word kosong di komputer Anda.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Di sini, kami menginisialisasi dokumen baru dan objek DocumentBuilder. DocumentBuilder seperti pena Anda, memungkinkan Anda menulis konten ke dalam dokumen.

## Langkah 2: Terapkan Format Daftar Bernomor

Sekarang, mari terapkan format daftar bernomor default. Ini seperti mengatur dokumen Word Anda untuk menggunakan poin bernomor.

```csharp
builder.ListFormat.ApplyNumberDefault();
```

Baris kode ini mengatur penomoran daftar Anda. Mudah, bukan?

## Langkah 3: Tambahkan Item Daftar

Selanjutnya, mari tambahkan beberapa item ke daftar kita. Bayangkan Anda sedang mencatat daftar belanjaan.

```csharp
builder.Writeln("Item 1");
builder.Writeln("Item 2");
```

Dengan baris ini, Anda menambahkan dua item pertama ke daftar Anda.

## Langkah 4: Indentasi Daftar

Bagaimana jika Anda ingin menambahkan sub-item di bawah suatu item? Ayo lakukan itu!

```csharp
builder.ListFormat.ListIndent();

builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

 Itu`ListIndent` metode membuat indentasi daftar, membuat sub-daftar. Anda sekarang membuat daftar hierarki, seperti daftar tugas yang disarangkan.

## Kesimpulan

Membuat daftar berurutan dalam dokumen Word secara terprogram mungkin tampak menakutkan pada awalnya, namun dengan Aspose.Words untuk .NET, semuanya menjadi sangat mudah. Dengan mengikuti langkah-langkah sederhana ini, Anda dapat dengan mudah menambahkan dan mengelola daftar di dokumen Anda. Baik Anda membuat laporan, membuat dokumen terstruktur, atau sekadar mengotomatiskan alur kerja Anda, Aspose.Words untuk .NET siap membantu Anda. Jadi, mengapa menunggu? Mulailah membuat kode dan lihat keajaibannya terungkap!

## FAQ

### Bisakah saya menyesuaikan gaya penomoran daftar?  
 Ya, Anda dapat menyesuaikan gaya penomoran menggunakan`ListFormat` properti. Anda dapat mengatur gaya penomoran yang berbeda seperti angka Romawi, huruf, dll.

### Bagaimana cara menambahkan lebih banyak tingkat lekukan?  
 Anda dapat menggunakan`ListIndent` metode beberapa kali untuk membuat tingkat sub-daftar yang lebih dalam. Setiap panggilan ke`ListIndent` menambahkan satu tingkat lekukan.

### Bisakah saya menggabungkan poin-poin dan daftar bernomor?  
 Sangat! Anda dapat menerapkan format daftar berbeda dalam dokumen yang sama menggunakan`ListFormat` Properti.

### Apakah mungkin untuk melanjutkan penomoran dari daftar sebelumnya?  
Ya, Anda dapat melanjutkan penomoran dengan menggunakan format daftar yang sama. Aspose.Words memungkinkan Anda mengontrol penomoran daftar di berbagai paragraf.

### Bagaimana cara menghapus format daftar?  
 Anda dapat menghapus format daftar dengan menelepon`ListFormat.RemoveNumbers()`. Ini akan mengubah item daftar kembali menjadi paragraf biasa.