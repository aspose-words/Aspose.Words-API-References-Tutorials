---
title: Granularitas Perbandingan Dalam Dokumen Word
linktitle: Granularitas Perbandingan Dalam Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari Bandingkan Granularitas dalam fitur dokumen kata Aspose.Words untuk .NET yang memungkinkan dokumen dibandingkan karakter demi karakter, melaporkan perubahan yang dilakukan.
type: docs
weight: 10
url: /id/net/compare-documents/comparison-granularity/
---
Berikut adalah panduan langkah demi langkah untuk menjelaskan kode sumber C# di bawah ini, yang menggunakan fitur Bandingkan Granularitas dalam dokumen Word dari Aspose.Words untuk .NET.

## Langkah 1: Pendahuluan

Fitur Bandingkan Granularitas Aspose.Words untuk .NET memungkinkan Anda membandingkan dokumen pada tingkat karakter. Artinya setiap karakter akan dibandingkan dan perubahannya akan dilaporkan sesuai dengan itu.

## Langkah 2: Menyiapkan lingkungan

Sebelum memulai, Anda perlu menyiapkan lingkungan pengembangan agar berfungsi dengan Aspose.Words untuk .NET. Pastikan Anda telah menginstal pustaka Aspose.Words dan memiliki proyek C# yang sesuai untuk menyematkan kode.

## Langkah 3: Tambahkan Majelis yang Diperlukan

Untuk menggunakan fitur Bandingkan Granularitas Aspose.Words untuk .NET, Anda perlu menambahkan rakitan yang diperlukan ke proyek Anda. Pastikan Anda memiliki referensi yang tepat ke Aspose.Words di proyek Anda.

```csharp
using Aspose.Words;
using Aspose.Words.DocumentBuilder;
```

## Langkah 4: Membuat Dokumen

Pada langkah ini, kita akan membuat dua dokumen menggunakan kelas DocumentBuilder. Dokumen-dokumen ini akan digunakan untuk perbandingan.

```csharp
// Buat dokumen A.
DocumentBuilder builderA = new DocumentBuilder(new Document());
builderA.Writeln("This is a simple A word.");

// Buat dokumen B.
DocumentBuilder builderB = new DocumentBuilder(new Document());
builderB.Writeln("This is simple B words.");
```

## Langkah 5: Mengonfigurasi Opsi Bandingkan

Pada langkah ini, kami akan mengonfigurasi opsi perbandingan untuk menentukan rincian perbandingan. Di sini kita akan menggunakan granularitas tingkat karakter.

```csharp
CompareOptions compareOptions = new CompareOptions { Granularity = Granularity.CharLevel };
```

## Langkah 6: Perbandingan Dokumen

Sekarang mari kita bandingkan dokumen menggunakan metode Bandingkan dari kelas Dokumen. Perubahan akan disimpan dalam dokumen A.

```csharp
builderA.Document.Compare(builderB.Document, "author", DateTime.Now, compareOptions);
```

 Itu`Compare` metode membandingkan dokumen A dengan dokumen B dan menyimpan perubahan pada dokumen A. Anda dapat menentukan nama penulis dan tanggal perbandingan untuk referensi.

## Kesimpulan

Dalam artikel ini, kami menjelajahi fitur Bandingkan Granularitas Aspose.Words untuk .NET. Fitur ini memungkinkan Anda membandingkan dokumen pada tingkat karakter dan melaporkan perubahan. Anda dapat menggunakan pengetahuan ini untuk melakukan perbandingan dokumen mendetail dalam proyek Anda.

### Contoh kode sumber untuk Perbandingan Granularitas menggunakan Aspose.Words untuk .NET

```csharp
            
DocumentBuilder builderA = new DocumentBuilder(new Document());
DocumentBuilder builderB = new DocumentBuilder(new Document());

builderA.Writeln("This is A simple word");
builderB.Writeln("This is B simple words");

CompareOptions compareOptions = new CompareOptions { Granularity = Granularity.CharLevel };

builderA.Document.Compare(builderB.Document, "author", DateTime.Now, compareOptions);            
        
```

## Kesimpulan

Dalam tutorial ini, kita menjelajahi fitur Perbandingan Granularitas Aspose.Words untuk .NET. Fitur ini memungkinkan Anda menentukan tingkat detail saat membandingkan dokumen. Dengan memilih tingkat perincian yang berbeda, Anda dapat melakukan perbandingan mendetail pada tingkat karakter, kata, atau blok, bergantung pada kebutuhan spesifik Anda. Aspose.Words untuk .NET memberikan kemampuan perbandingan dokumen yang fleksibel dan kuat, sehingga memudahkan untuk mengidentifikasi perbedaan dalam dokumen dengan berbagai tingkat perincian.

### FAQ

#### T: Apa tujuan penggunaan Granularitas Perbandingan di Aspose.Words untuk .NET?

J: Granularitas Perbandingan di Aspose.Words untuk .NET memungkinkan Anda menentukan tingkat detail saat membandingkan dokumen. Dengan fitur ini, Anda dapat membandingkan dokumen pada level yang berbeda, seperti level karakter, level kata, atau bahkan level blok. Setiap tingkat granularitas memberikan tingkat detail yang berbeda-beda pada hasil perbandingan.

#### T: Bagaimana cara menggunakan Granularitas Perbandingan di Aspose.Words untuk .NET?

J: Untuk menggunakan Granularitas Perbandingan di Aspose.Words untuk .NET, ikuti langkah-langkah berikut:
1. Siapkan lingkungan pengembangan Anda dengan perpustakaan Aspose.Words.
2. Tambahkan rakitan yang diperlukan ke proyek Anda dengan merujuk Aspose.Words.
3.  Buat dokumen yang ingin Anda bandingkan menggunakan`DocumentBuilder` kelas.
4.  Konfigurasikan opsi perbandingan dengan membuat a`CompareOptions` objek dan pengaturannya`Granularity` properti ke tingkat yang diinginkan (misalnya,`Granularity.CharLevel` untuk perbandingan tingkat karakter).
5.  Menggunakan`Compare` metode pada satu dokumen, meneruskan dokumen lain dan`CompareOptions` objek sebagai parameter. Cara ini akan membandingkan dokumen berdasarkan granularitas yang ditentukan dan menyimpan perubahan pada dokumen pertama.

#### T: Berapa tingkat Granularitas Perbandingan yang tersedia di Aspose.Words untuk .NET?

J: Aspose.Words untuk .NET menyediakan tiga tingkat Granularitas Perbandingan:
- `Granularity.CharLevel`: Membandingkan dokumen pada tingkat karakter.
- `Granularity.WordLevel`: Membandingkan dokumen pada tingkat kata.
- `Granularity.BlockLevel`: Membandingkan dokumen pada tingkat blok.

#### T: Bagaimana cara menafsirkan hasil perbandingan dengan perincian tingkat karakter?

J: Dengan perincian tingkat karakter, setiap karakter dalam dokumen yang dibandingkan dianalisis perbedaannya. Hasil perbandingan akan menunjukkan perubahan pada level karakter individu, meliputi penambahan, penghapusan, dan modifikasi.