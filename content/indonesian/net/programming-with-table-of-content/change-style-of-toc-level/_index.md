---
title: Ubah Gaya Toc Di Dokumen Word
linktitle: Ubah Gaya Toc Di Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mudah mengubah gaya tingkat daftar isi di dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-table-of-content/change-style-of-toc-level/
---
Aspose.Words untuk .NET adalah perpustakaan yang kuat untuk membuat, mengedit, dan memanipulasi dokumen Word dalam aplikasi C#. Di antara fitur yang ditawarkan Aspose.Words adalah kemampuan untuk mengubah gaya tingkat tertentu dari daftar isi dokumen. Dalam panduan ini, kami akan menunjukkan kepada Anda cara menggunakan kode sumber C# Aspose.Words untuk .NET untuk mengubah gaya tingkat daftar isi dokumen Word.

## Memahami perpustakaan Aspose.Words

Sebelum mendalami kodenya, penting untuk memahami perpustakaan Aspose.Words untuk .NET. Aspose.Words adalah perpustakaan populer yang membuat Pemrosesan Kata dengan dokumen Word menjadi mudah dan efisien. Ia menawarkan berbagai fitur untuk membuat, mengedit, dan memanipulasi dokumen Word, termasuk mengubah gaya daftar isi.

## Membuat dokumen baru

Langkah pertama adalah membuat dokumen Word baru yang ingin Anda ubah gaya daftar isinya. Gunakan kelas Dokumen untuk membuat dokumen baru. Berikut ini contohnya:

```csharp
Document doc = new Document();
```

Dalam contoh ini, kita membuat dokumen kosong baru.

## Mengubah gaya tingkat daftar isi

Setelah dokumen dibuat, Anda dapat mengakses gaya dokumen dan mengubah gaya yang digunakan untuk tingkat tertentu dari daftar isi. Dalam contoh ini, kita akan memodifikasi gaya yang digunakan untuk daftar isi tingkat pertama. Begini caranya:

```csharp
doc.Styles[StyleIdentifier.Toc1].Font.Bold = true;
```

Dalam contoh ini, kita menggunakan properti Styles dari kelas Dokumen untuk mengakses gaya dokumen. Selanjutnya, kita menggunakan pengidentifikasi gaya StyleIdentifier.Toc1 untuk mengakses gaya yang digunakan untuk tingkat pertama daftar isi. Terakhir, kita memodifikasi properti Font.Bold dari gaya untuk menjadikannya tebal.

## Simpan dokumen yang dimodifikasi

Setelah Anda membuat modifikasi yang diperlukan pada gaya daftar isi, Anda dapat menyimpan dokumen yang dimodifikasi menggunakan metode Simpan pada kelas Dokumen. Berikut ini contohnya:

```csharp
doc.Save(dataDir + "WorkingWithChangeStyleOfTocLevel.ModifiedDocument.docx");
```

Dalam contoh ini, kami menyimpan dokumen yang dimodifikasi sebagai "WorkingWithChangeStyleOfTocLevel.ModifiedDocument.docx".

## Contoh kode sumber untuk fitur "Ubah gaya tingkat daftar isi" dengan Aspose.Words untuk .NET

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Buat dokumen baru
Document doc = new Document();

// Modifikasi gaya daftar isi tingkat pertama
doc.Styles[StyleIdentifier.Toc1].Font.Bold = true;

// Simpan dokumen yang diubah
doc.Save(dataDir + "WorkingWithChangeStyleOfTocLevel.ModifiedDocument.docx");
```

## Kesimpulan

Dalam panduan ini, kami menjelaskan cara menggunakan Aspose.Words untuk .NET untuk mengubah gaya tingkat daftar isi dokumen Word menggunakan kode sumber C# yang disediakan. Dengan mengikuti langkah-langkah yang disediakan, Anda dapat dengan mudah menyesuaikan gaya daftar isi dokumen Word di aplikasi C# Anda. Aspose.Words menawarkan fleksibilitas dan kemampuan luar biasa untuk bekerja dengan gaya dan format dokumen Anda, memungkinkan Anda membuat dokumen Word yang menarik dan profesional.

### FAQ untuk mengubah gaya toc di dokumen Word

#### T: Apa tujuan fungsionalitas "Ubah Gaya Toc di Dokumen Word" di Aspose.Words untuk .NET?

J: Fungsionalitas "Ubah Gaya Toc Dalam Dokumen Word" di Aspose.Words untuk .NET memungkinkan Anda mengubah gaya tingkat tertentu dalam daftar isi dokumen Word. Ini memungkinkan Anda untuk menyesuaikan tampilan dan format daftar isi, seperti mengubah gaya font, ukuran, warna, atau aspek visual lainnya pada tingkat tertentu.

#### T: Apa itu Aspose.Words untuk .NET?

J: Aspose.Words for .NET adalah perpustakaan canggih yang dirancang untuk Pemrosesan Kata dengan dokumen Word di aplikasi .NET. Ini menyediakan fitur komprehensif untuk membuat, mengedit, memanipulasi, dan mengonversi dokumen Word secara terprogram menggunakan C# atau bahasa .NET lainnya.

#### T: Bagaimana cara membuat dokumen Word baru menggunakan Aspose.Words untuk .NET?

 J: Untuk membuat dokumen Word baru menggunakan Aspose.Words untuk .NET, Anda dapat menggunakan`Document` kelas dan konstruktornya. Dengan menginisialisasi instance baru dari`Document` kelas, Anda dapat membuat dokumen kosong. Berikut ini contohnya:

```csharp
Document doc = new Document();
```

Cuplikan kode ini membuat dokumen Word baru yang kosong.

#### T: Bagaimana cara mengubah gaya tingkat tertentu dalam daftar isi menggunakan Aspose.Words untuk .NET?

 J: Setelah dokumen dimuat, Anda dapat mengubah gaya tingkat tertentu dalam daftar isi dengan mengakses gaya dokumen dan membuat perubahan yang diperlukan. Di Aspose.Words untuk .NET, Anda dapat menggunakan`Styles` properti dari`Document` kelas untuk mengakses gaya dokumen, dan kemudian memodifikasi gaya yang diinginkan menggunakan propertinya. Misalnya untuk mengubah gaya daftar isi tingkat pertama menjadi tebal, Anda bisa menggunakan kode berikut:

```csharp
doc.Styles[StyleIdentifier.Toc1].Font.Bold = true;
```

 Dalam kode ini,`doc.Styles[StyleIdentifier.Toc1]` mengakses gaya untuk tingkat pertama daftar isi, dan`Font.Bold = true` mengatur gaya font tebal untuk gaya itu.

#### T: Bisakah saya mengubah gaya beberapa level di daftar isi menggunakan Aspose.Words untuk .NET?

 A: Ya, Anda dapat mengubah gaya beberapa level di daftar isi menggunakan Aspose.Words for .NET. Untuk mengubah gaya pada level tertentu, Anda dapat mengakses gaya yang sesuai menggunakan`Styles`properti dan buat perubahan yang diinginkan pada setiap level satu per satu.

#### T: Bagaimana cara menyimpan dokumen yang dimodifikasi setelah mengubah gaya daftar isi menggunakan Aspose.Words untuk .NET?

 J: Setelah Anda melakukan modifikasi yang diperlukan pada gaya daftar isi, Anda dapat menyimpan dokumen yang dimodifikasi menggunakan`Save` metode`Document` kelas. Tentukan jalur file yang diinginkan dan nama untuk dokumen keluaran sebagai parameter ke`Save` metode. Berikut ini contohnya:

```csharp
doc.Save(dataDir + "WorkingWithChangeStyleOfTocLevel.ModifiedDocument.docx");
```

Kode ini menyimpan dokumen yang dimodifikasi sebagai "WorkingWithChangeStyleOfTocLevel.ModifiedDocument.docx".

#### T: Dapatkah saya menerapkan perubahan pemformatan lainnya pada daftar isi menggunakan Aspose.Words untuk .NET?

A: Ya, selain mengubah gaya, Anda dapat menerapkan berbagai perubahan format pada daftar isi menggunakan Aspose.Words for .NET. Misalnya, Anda dapat mengubah ukuran font, warna, perataan, atau menambahkan properti pemformatan tambahan untuk menyempurnakan tampilan daftar isi.

#### T: Bagaimana cara menentukan gaya kustom untuk tingkat tertentu dalam daftar isi menggunakan Aspose.Words untuk .NET?

 A: Untuk menentukan gaya kustom untuk tingkat tertentu dalam daftar isi menggunakan Aspose.Words untuk .NET, Anda dapat membuat yang baru`Style` objek, konfigurasikan propertinya sesuai dengan gaya yang Anda inginkan, dan tetapkan ke tingkat yang sesuai dari daftar isi menggunakan`Styles` properti dari`Document` kelas. Ini memungkinkan Anda menentukan gaya khusus untuk tingkat tertentu berdasarkan kebutuhan Anda.

#### T: Bisakah saya mengubah gaya daftar isi di dokumen Word yang sudah ada menggunakan Aspose.Words untuk .NET?

 J: Ya, Anda dapat mengubah gaya daftar isi di dokumen Word yang sudah ada menggunakan Aspose.Words untuk .NET. Cukup muat dokumen menggunakan`Document` kelas, ubah properti gaya menggunakan`Styles` properti, dan simpan dokumen untuk menerapkan perubahan.

#### T: Apakah Aspose.Words untuk .NET mendukung perubahan gaya dan pemformatan lain di dokumen Word?

J: Ya, Aspose.Words untuk .NET menyediakan dukungan ekstensif untuk mengubah berbagai gaya dan pemformatan dalam dokumen Word. Ini memungkinkan Anda mengubah gaya untuk berbagai elemen seperti paragraf, judul, tabel, daftar, dan banyak lagi. Anda dapat mengubah font, warna, perataan, lekukan, spasi, dan aspek pemformatan lainnya sesuai kebutuhan Anda.