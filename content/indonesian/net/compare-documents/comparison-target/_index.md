---
title: Target Perbandingan Dalam Dokumen Word
linktitle: Target Perbandingan Dalam Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari membandingkan target dalam fitur dokumen Word Aspose.Words untuk .NET yang memungkinkan Anda membandingkan dokumen dan menghasilkan dokumen baru yang berisi perubahan yang dibuat.
type: docs
weight: 10
url: /id/net/compare-documents/comparison-target/
---
Berikut adalah panduan langkah demi langkah untuk menjelaskan kode sumber C# di bawah ini, yang menggunakan target perbandingan dalam fungsionalitas dokumen Word Aspose.Words untuk .NET.

## Langkah 1: Pendahuluan

Fitur bandingkan target Aspose.Words untuk .NET memungkinkan Anda membandingkan dua dokumen dan menghasilkan dokumen baru yang berisi perubahan yang dibuat pada dokumen target. Ini berguna untuk melacak perubahan yang dilakukan antara berbagai versi dokumen.

## Langkah 2: Menyiapkan lingkungan

Sebelum memulai, Anda perlu menyiapkan lingkungan pengembangan agar berfungsi dengan Aspose.Words untuk .NET. Pastikan Anda telah menginstal pustaka Aspose.Words dan memiliki proyek C# yang sesuai untuk menyematkan kode.

## Langkah 3: Tambahkan Majelis yang Diperlukan

Untuk menggunakan fitur target perbandingan Aspose.Words untuk .NET, Anda harus menambahkan rakitan yang diperlukan ke proyek Anda. Pastikan Anda memiliki referensi yang tepat ke Aspose.Words di proyek Anda.

```csharp
using Aspose.Words;
```

## Langkah 4: Inisialisasi Dokumen

Pada langkah ini, kita akan menginisialisasi dua dokumen untuk perbandingan. Anda harus menentukan jalur direktori tempat dokumen Anda berada, serta nama dokumen sumber.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Inisialisasi dokumen A untuk dibandingkan.
Document docA = new Document(dataDir + "DocumentA.docx");

// Kloning dokumen A untuk membuat salinan dokumen B yang identik.
Document docB = docA.Clone();
```

## Langkah 5: Mengonfigurasi Opsi Bandingkan

Pada langkah ini, kita akan mengonfigurasi opsi perbandingan untuk menentukan perilaku perbandingan. Pilihannya mencakup kemampuan untuk mengabaikan pemformatan, serta target perbandingan, yang merupakan opsi "Tampilkan perubahan" di kotak dialog "Bandingkan Dokumen" Microsoft Word.

```csharp
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };
```

## Langkah 6: Perbandingan Dokumen

Sekarang kita akan membandingkan dokumen dan menghasilkan hasilnya dalam dokumen baru.

```csharp
docA.Compare(docB, "user", DateTime.Now, options);
```

 Itu`Compare`metode membandingkan dokumen A dengan dokumen B dan menyimpan perubahan pada dokumen A. Anda dapat menentukan nama pengguna dan tanggal perbandingan untuk referensi.

### Contoh kode sumber untuk Bandingkan Target menggunakan Aspose.Words untuk .NET


```csharp
            
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();

// Berkaitan dengan opsi Microsoft Word "Tampilkan perubahan" di kotak dialog "Bandingkan Dokumen".
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };

docA.Compare(docB, "user", DateTime.Now, options);
            
        
```

## Kesimpulan

Dalam artikel ini, kami menjelajahi fitur target berbeda dari Aspose.Words untuk .NET. Fitur ini memungkinkan Anda membandingkan dua dokumen dan menghasilkan dokumen baru yang berisi perubahan yang dilakukan. Anda dapat menggunakan pengetahuan ini untuk melacak perubahan antara berbagai versi dokumen Anda.

### FAQ

#### T: Apa tujuan menggunakan Target Perbandingan di Aspose.Words untuk .NET?

J: Target Perbandingan di Aspose.Words untuk .NET memungkinkan Anda membandingkan dua dokumen dan menghasilkan dokumen baru yang berisi perubahan yang dibuat pada dokumen target. Fitur ini berguna untuk melacak perubahan yang dilakukan antara versi dokumen yang berbeda dan memvisualisasikan perbedaan dalam dokumen terpisah.

#### T: Bagaimana cara menggunakan Target Perbandingan di Aspose.Words untuk .NET?

J: Untuk menggunakan Target Perbandingan di Aspose.Words untuk .NET, ikuti langkah-langkah berikut:
1. Siapkan lingkungan pengembangan Anda dengan perpustakaan Aspose.Words.
2. Tambahkan rakitan yang diperlukan ke proyek Anda dengan merujuk Aspose.Words.
3.  Inisialisasi dokumen yang ingin Anda bandingkan menggunakan`Document` kelas atau itu`DocumentBuilder` kelas.
4.  Konfigurasikan opsi perbandingan dengan membuat a`CompareOptions` objek dan pengaturan properti seperti`IgnoreFormatting` Dan`Target` (misalnya.,`ComparisonTargetType.New` untuk target perbandingan).
5.  Menggunakan`Compare` metode pada satu dokumen, meneruskan dokumen lain dan`CompareOptions` objek sebagai parameter. Cara ini akan membandingkan dokumen dan menyimpan perubahan pada dokumen pertama.

####  T: Apa tujuan dari`Target` property in the `CompareOptions` class?

 J: Itu`Target` properti di`CompareOptions` kelas memungkinkan Anda menentukan target perbandingan, yang mirip dengan opsi "Tampilkan perubahan" di kotak dialog "Bandingkan Dokumen" Microsoft Word. Targetnya dapat diatur`ComparisonTargetType.New` untuk menampilkan perubahan pada dokumen baru,`ComparisonTargetType.Current` untuk menampilkan perubahan pada dokumen saat ini, atau`ComparisonTargetType.Formatting` untuk hanya menampilkan perubahan format.