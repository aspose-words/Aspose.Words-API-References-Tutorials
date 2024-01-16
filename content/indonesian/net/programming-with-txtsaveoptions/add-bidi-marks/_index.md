---
title: Tambahkan Tanda Bidi di Dokumen Word
linktitle: Tambahkan Tanda Bidi di Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menambahkan tanda Bidi ke dokumen Word menggunakan Aspose.Words untuk .NET dan membuat dokumen multibahasa profesional.
type: docs
weight: 10
url: /id/net/programming-with-txtsaveoptions/add-bidi-marks/
---

Aspose.Words untuk .NET adalah perpustakaan yang kuat untuk membuat, mengedit, dan memanipulasi dokumen Word dalam aplikasi C#. Di antara fitur yang ditawarkan Aspose.Words adalah kemampuan untuk menambahkan tanda Bidi (Bi-arah) pada dokumen. Dalam panduan ini, kami akan memandu Anda tentang cara menggunakan kode sumber C# Aspose.Words untuk .NET untuk menambahkan tanda Bidi ke dokumen.

## Memahami perpustakaan Aspose.Words

Sebelum mendalami kodenya, penting untuk memahami perpustakaan Aspose.Words untuk .NET. Aspose.Words adalah perpustakaan populer yang membuat Pemrosesan Kata dengan dokumen Word menjadi mudah dan efisien. Ia menawarkan berbagai fitur untuk membuat, mengedit, dan memanipulasi dokumen Word, termasuk menambahkan tanda Bidi.

## Membuat dokumen dan menambahkan konten

Langkah pertama adalah membuat dokumen baru dan menambahkan konten ke dalamnya. Gunakan kelas Dokumen untuk membuat instance dokumen baru. Kemudian gunakan kelas DocumentBuilder untuk menambahkan teks ke dokumen. Berikut ini contohnya:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");
```

Dalam contoh ini, kita membuat dokumen baru dan menggunakan DocumentBuilder untuk menambahkan teks. Kami telah menambahkan tiga baris teks: satu dalam bahasa Inggris, satu dalam bahasa Ibrani, dan satu dalam bahasa Arab untuk menunjukkan penambahan konten dalam berbagai bahasa.

## Menambahkan tanda Bidi

Setelah konten ditambahkan, sekarang kita dapat menambahkan tanda Bidi ke dokumen. Untuk ini, kami menggunakan kelas TxtSaveOptions dan menyetel properti AddBidiMarks ke true. Begini caranya:

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

Dalam contoh ini, kita membuat instance TxtSaveOptions dan menyetel properti AddBidiMarks ke true. Selanjutnya, kita menggunakan metode Simpan dari kelas Dokumen untuk menyimpan dokumen dengan tanda Bidi.

### Contoh kode sumber untuk fungsionalitas "Tambahkan Tanda Bidi" dengan Aspose.Words untuk .NET

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Buat dokumen dan tambahkan konten
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");

// Tambahkan tanda Bidi
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true

  };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

## Kesimpulan

Dalam panduan ini, kami telah menjelaskan cara menggunakan Aspose.Words untuk .NET untuk menambahkan tanda Bidi ke dokumen Word menggunakan kode sumber C# yang disediakan. Dengan mengikuti langkah-langkah yang disediakan, Anda dapat dengan mudah menambahkan tanda Bidi ke dokumen Word Anda di aplikasi C# Anda. Aspose.Words menawarkan fleksibilitas dan kekuatan luar biasa untuk Pemrosesan Kata dengan pemformatan teks dan manajemen bahasa, memungkinkan Anda membuat dokumen multibahasa secara profesional.

### Pertanyaan yang Sering Diajukan

#### T: Apa itu Aspose.Words untuk .NET?
Aspose.Words for .NET adalah perpustakaan yang kuat untuk membuat, mengedit, dan memanipulasi dokumen Word dalam aplikasi C#. Ia menawarkan banyak fitur untuk Pemrosesan Kata dengan dokumen Word, termasuk menambahkan tanda Bidi (dua arah).

#### T: Fitur apa saja yang ditawarkan Aspose.Words untuk .NET?
Aspose.Words untuk .NET menawarkan berbagai fitur untuk membuat, mengedit, dan memanipulasi dokumen Word. Beberapa fitur tersebut antara lain membuat dokumen, menambahkan konten, memformat teks, mengelola tabel, menggabungkan dan memisahkan dokumen, mengonversi dokumen, dan masih banyak lagi.

#### T: Bagaimana cara menambahkan tanda Bidi ke dokumen Word menggunakan Aspose.Words untuk .NET?
Anda dapat menambahkan tanda Bidi ke dokumen Word dengan mengikuti langkah-langkah berikut:

 Buat dokumen baru menggunakan`Document` kelas.

 Menggunakan`DocumentBuilder` kelas untuk menambahkan konten ke dokumen.

 Setelah Anda menambahkan konten, gunakan`TxtSaveOptions` kelas dan atur`AddBidiMarks`properti ke`true`.

 Simpan dokumen yang bertanda Bidi dengan menggunakan`Save` metode`Document` kelas.

#### T: Apakah Aspose.Words mendukung banyak bahasa untuk menambahkan tanda Bidi?
Ya, Aspose.Words mendukung banyak bahasa untuk menambahkan tanda Bidi. Anda dapat menambahkan tanda Bidi ke teks dalam berbagai bahasa, seperti Inggris, Ibrani, dan Arab, menggunakan Aspose.Words untuk .NET.

#### Q: Apakah ada opsi tambahan untuk menyimpan dokumen bertanda Bidi?
 Ya, Anda dapat menentukan opsi lain saat menyimpan dokumen bertanda Bidi menggunakan`TxtSaveOptions` kelas. Misalnya, Anda dapat mengatur format penyimpanan dokumen, opsi pengkodean, dll.