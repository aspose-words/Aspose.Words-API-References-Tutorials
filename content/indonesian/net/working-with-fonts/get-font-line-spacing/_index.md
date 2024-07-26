---
title: Dapatkan Spasi Baris Font
linktitle: Dapatkan Spasi Baris Font
second_title: API Pemrosesan Dokumen Aspose.Words
description: Dalam tutorial ini, pelajari cara mendapatkan spasi baris font di dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-fonts/get-font-line-spacing/
---
Dalam tutorial ini, kami akan memberi tahu Anda cara mendapatkan spasi baris font di dokumen Word menggunakan perpustakaan Aspose.Words untuk .NET. Spasi baris font menentukan spasi vertikal antar baris teks. Kami akan memandu Anda langkah demi langkah untuk membantu Anda memahami dan menerapkan kode dalam proyek .NET Anda.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki item berikut:
- Pengetahuan tentang bahasa pemrograman C#
- Pustaka Aspose.Words untuk .NET diinstal di proyek Anda

## Langkah 1: Buat dokumen baru dan pembuat dokumen
 Pertama, kita akan membuat dokumen baru dengan membuat instance`Document` kelas dan pembuat dokumen dengan membuat instance`DocumentBuilder` kelas.

```csharp
// Buat dokumen baru
Document doc = new Document();

//Buat pembuat dokumen
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 2: Konfigurasikan font
 Selanjutnya kita akan mengkonfigurasi font dengan mengatur`Name` milik pembuat dokumen.

```csharp
// Konfigurasikan fontnya
builder.Font.Name = "Calibri";
```

## Langkah 3: Tambahkan teks ke dokumen
Kami sekarang akan menggunakan pembuat dokumen untuk menambahkan teks berformat ke dokumen.

```csharp
// Tambahkan teks ke dokumen
builder. Writen("qText");
```

## Langkah 4: Dapatkan Spasi Baris Font
 Sekarang kita akan mengakses`Font` objek paragraf pertama dokumen dan mengambil nilai`LineSpacing` Properti.

```csharp
// Dapatkan spasi baris font
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

### Contoh kode sumber untuk Mendapatkan Spasi Baris Font menggunakan Aspose.Words untuk .NET 
```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Calibri";
builder.Writeln("qText");
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

## Kesimpulan
Dalam tutorial ini, kita melihat cara mendapatkan spasi baris font di dokumen Word dengan Aspose.Words untuk .NET. Spasi baris font penting untuk mengontrol spasi vertikal antar baris teks. Jangan ragu untuk menggunakan fitur ini untuk menyesuaikan tampilan teks di dokumen Anda.

### FAQ

#### T: Bagaimana cara mengubah spasi baris teks tertentu di dokumen Word?

J: Dengan Aspose.Words, Anda dapat dengan mudah mengubah spasi baris teks tertentu dalam dokumen Word. Gunakan API untuk memilih teks yang diinginkan dan sesuaikan jarak antar baris dengan menentukan nilai yang sesuai.

#### T: Apakah mungkin menerapkan spasi tepat antar baris dalam dokumen Word?

J: Ya, Aspose.Words memungkinkan Anda menerapkan spasi tepat antar baris dalam dokumen Word. Anda dapat menentukan nilai tepat untuk spasi baris menggunakan API.

#### T: Bagaimana cara menyesuaikan spasi baris untuk seluruh dokumen Word?

J: Dengan Aspose.Words, Anda dapat dengan mudah menyesuaikan spasi baris untuk seluruh dokumen Word. Gunakan metode yang disediakan oleh API untuk menentukan spasi baris yang diinginkan untuk keseluruhan dokumen.

#### T: Apakah Aspose.Words mendukung spasi beberapa baris?

J: Ya, Aspose.Words mendukung spasi beberapa baris di dokumen Word. Anda dapat mengatur beberapa spasi, misalnya 1,5 kali atau 2 kali spasi normal, untuk baris teks Anda.

#### T: Bagaimana cara menghindari masalah garis yang tumpang tindih saat menyesuaikan spasi baris?

J: Untuk menghindari masalah garis yang tumpang tindih saat mengatur jarak antar baris, pastikan untuk memilih nilai jarak yang sesuai. Uji juga rendering akhir dokumen Anda untuk memastikan teks tetap dapat dibaca dan diformat dengan baik.