---
title: Periksa Efek Teks DrawingML
linktitle: Periksa Efek Teks DrawingML
second_title: API Pemrosesan Dokumen Aspose.Words
description: Dalam tutorial ini, pelajari cara memeriksa efek teks DrawingML di dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-fonts/check-drawingml-text-effect/
---

Dalam tutorial ini, kami akan memandu Anda tentang cara memeriksa efek teks DrawingML di dokumen Word menggunakan Aspose.Words Library untuk .NET. Memeriksa efek teks DrawingML memungkinkan Anda menentukan apakah efek tertentu diterapkan ke bagian teks. Kami akan memandu Anda langkah demi langkah untuk membantu Anda memahami dan menerapkan kode dalam proyek .NET Anda.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki item berikut:
- Pengetahuan tentang bahasa pemrograman C#
- Pustaka Aspose.Words untuk .NET diinstal di proyek Anda
- Dokumen Word yang berisi efek teks DrawingML

## Langkah 1: Tentukan direktori dokumen
 Pertama, Anda perlu mengatur jalur direktori ke lokasi dokumen Word Anda. Mengganti`"YOUR DOCUMENT DIRECTORY"` dalam kode dengan jalur yang sesuai.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Muat dokumen dan periksa efek teksnya
Selanjutnya, kita akan memuat dokumen Word dan mengakses kumpulan proses (urutan karakter) di paragraf pertama badan dokumen. Selanjutnya, kita akan memeriksa apakah ada efek teks DrawingML tertentu yang diterapkan pada font saat pertama kali dijalankan.

```csharp
// Muat dokumen
Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

// Periksa efek teks DrawingML
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));
```

### Contoh kode sumber untuk Periksa Efek Teks DML menggunakan Aspose.Words untuk .NET 

```csharp

// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

// Satu kali proses mungkin menerapkan beberapa efek teks Dml.
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));

```

## Kesimpulan
Dalam tutorial ini, kita melihat cara memeriksa efek teks DrawingML di dokumen Word menggunakan Aspose.Words untuk .NET. Memeriksa efek teks DrawingML memungkinkan Anda mengidentifikasi bagian teks yang menerapkan efek tertentu. Jangan ragu untuk menggunakan fitur ini untuk memanipulasi dan menganalisis efek teks di dokumen Word Anda.

### FAQ

#### T: Bagaimana cara mengakses efek teks DrawingML di dokumen Word menggunakan Aspose.Words?

J: Dengan Aspose.Words, Anda dapat mengakses efek teks DrawingML di dokumen Word menggunakan API yang disediakan. Anda dapat menelusuri elemen teks dan memeriksa properti tertentu dari efek teks, seperti warna, ukuran, dll.

#### T: Jenis efek teks DrawingML apa yang biasa digunakan di dokumen Word?

J: Jenis efek teks DrawingML yang umum digunakan di dokumen Word mencakup bayangan, pantulan, cahaya, gradien, dll. Efek ini dapat diterapkan untuk meningkatkan tampilan dan pemformatan teks.

#### T: Bagaimana cara memeriksa warna efek teks DrawingML di dokumen Word?

A: Untuk memeriksa warna efek teks DrawingML di dokumen Word, Anda dapat menggunakan metode yang disediakan oleh Aspose.Words untuk mengakses properti warna efek teks. Dengan cara ini Anda bisa mendapatkan warna yang digunakan untuk efek teks tertentu.

#### T: Apakah mungkin untuk memeriksa efek teks di dokumen Word yang berisi banyak bagian?

J: Ya, Aspose.Words memungkinkan pemeriksaan efek teks di dokumen Word yang berisi banyak bagian. Anda dapat menavigasi setiap bagian dokumen dan mengakses efek teks untuk setiap bagian satu per satu.

#### T: Bagaimana cara memeriksa opasitas efek teks DrawingML di dokumen Word?

J: Untuk memeriksa opacity efek teks DrawingML di dokumen Word, Anda dapat menggunakan metode yang disediakan oleh Aspose.Words untuk mengakses properti opacity dari efek teks. Ini akan memungkinkan Anda untuk menerapkan nilai opacity ke efek teks tertentu.