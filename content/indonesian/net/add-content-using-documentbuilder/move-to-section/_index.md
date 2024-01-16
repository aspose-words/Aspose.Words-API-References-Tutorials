---
title: Pindah Ke Bagian Dalam Dokumen Word
linktitle: Pindah Ke Bagian Dalam Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk menggunakan fitur Pindah Ke Bagian di dokumen Word dari Aspose.Words untuk .NET memanipulasi bagian dan paragraf dalam dokumen Word.
type: docs
weight: 10
url: /id/net/add-content-using-documentbuilder/move-to-section/
---
Dalam contoh ini, kami akan memandu Anda tentang cara menggunakan fitur Pindah Ke Bagian di dokumen Word Aspose.Words untuk .NET langkah demi langkah menggunakan kode sumber C# yang disediakan. Fitur ini memungkinkan Anda menavigasi dan memanipulasi berbagai bagian di dalam dokumen Word. Ikuti langkah-langkah di bawah ini untuk mengintegrasikan fungsi ini ke dalam aplikasi Anda.

## Langkah 1: Buat dokumen baru dan tambahkan bagian

Pertama, kita perlu membuat dokumen baru dan menambahkan bagian ke dalamnya. Gunakan kode berikut untuk menyelesaikan langkah ini:

```csharp
Document doc = new Document();
doc.AppendChild(new Section(doc));
```

Kode ini membuat dokumen kosong baru dan menambahkan bagian ke dokumen ini.

## Langkah 2: Pindahkan DocumentBuilder ke bagian kedua dan tambahkan teks

Selanjutnya, kita perlu memindahkan DocumentBuilder ke bagian kedua dokumen dan menambahkan beberapa teks di sana. Gunakan kode berikut untuk melakukan langkah ini:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToSection(1);
builder.Writeln("Text added to the 2nd section.");
```

Kode ini membuat DocumentBuilder dari dokumen yang sudah ada, lalu memindahkan kursor dari DocumentBuilder ke bagian kedua dokumen. Terakhir, ia menambahkan teks tertentu ke bagian ini.

## Langkah 3: Muat dokumen dengan paragraf yang ada

Jika Anda ingin bekerja dengan dokumen yang sudah ada yang berisi paragraf, Anda bisa memuat dokumen ini menggunakan kode berikut:

```csharp
doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
Assert.AreEqual(22, paragraphs.Count);
```

Kode ini memuat dokumen yang ditentukan (ganti "MyDir + "Paragraphs.docx"" dengan jalur sebenarnya ke dokumen Anda) dan mengakses kumpulan paragraf dari bagian pertama dokumen. Garis`Assert.AreEqual(22, paragraphs.Count);` memeriksa apakah dokumen tersebut berisi 22 paragraf.

## Langkah 4: buat DocumentBuilder untuk sebuah dokumen

Anda dapat membuat kursor DocumentBuilder ke paragraf tertentu menggunakan indeks posisi.

```csharp
builder = new DocumentBuilder(doc);
Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));
```

## Langkah 5: Pindahkan kursor ke paragraf tertentu


Anda dapat memindahkan kursor DocumentBuilder ke paragraf tertentu menggunakan indeks posisi. Berikut cara melakukannya:

```csharp
builder. MoveToParagraph(2, 10);
Assert.AreEqual(2, paragraphs.IndexOf(builder.CurrentParagraph));
builder.Writeln("This is a new third paragraph.");
Assert.AreEqual(3, paragraphs.IndexOf(builder.CurrentParagraph));
```

Kode ini memindahkan kursor DocumentBuilder ke paragraf ketiga dari bagian kedua (paragraf di indeks 2) dan ke posisi 10. Kemudian menambahkan paragraf baru dengan beberapa teks dan memeriksa apakah kursor berada pada posisi yang tepat di paragraf baru ini.

### Contoh kode sumber Pindah Ke Pindah Ke Bagian menggunakan Aspose.Words untuk .NET

```csharp
Document doc = new Document();
doc.AppendChild(new Section(doc));

// Pindahkan DocumentBuilder ke bagian kedua dan tambahkan teks.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.MoveToSection(1);
builder.Writeln("Text added to the 2nd section.");

// Buat dokumen dengan paragraf.
doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
Assert.AreEqual(22, paragraphs.Count);

// Saat kita membuat DocumentBuilder untuk sebuah dokumen, kursornya berada di awal dokumen secara default,
// dan konten apa pun yang ditambahkan oleh DocumentBuilder hanya akan ditambahkan ke dokumen.
builder = new DocumentBuilder(doc);
Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));

//Anda dapat memindahkan kursor ke posisi mana pun dalam paragraf.
builder.MoveToParagraph(2, 10);
Assert.AreEqual(2, paragraphs.IndexOf(builder.CurrentParagraph));
builder.Writeln("This is a new third paragraph. ");
Assert.AreEqual(3, paragraphs.IndexOf(builder.CurrentParagraph));
```

Itu saja ! Anda sekarang telah memahami cara menggunakan fungsionalitas pindah ke bagian Aspose.Words untuk .NET menggunakan kode sumber yang disediakan. Anda sekarang dapat mengintegrasikan fungsi ini ke dalam aplikasi Anda sendiri dan memanipulasi bagian dan paragraf dokumen Word Anda secara dinamis.

## Kesimpulan

Dalam contoh ini, kami menjelajahi fitur Pindah Ke Bagian Aspose.Words untuk .NET. Kita mempelajari cara membuat dokumen baru, menambahkan bagian ke dalamnya, dan menggunakan kelas DocumentBuilder untuk menavigasi ke bagian dan paragraf tertentu dalam dokumen Word. Fitur ini memberi pengembang alat canggih untuk memanipulasi konten dan struktur dokumen Word secara terprogram menggunakan Aspose.Words untuk .NET.

### FAQ untuk berpindah ke bagian dalam dokumen Word

#### T: Apa tujuan fitur Pindah Ke Bagian di Aspose.Words untuk .NET?

J: Fitur Pindah Ke Bagian di Aspose.Words untuk .NET memungkinkan pengembang menavigasi dan memanipulasi bagian berbeda dalam dokumen Word secara terprogram. Ini memberikan kemampuan untuk menyisipkan, mengubah, atau menghapus konten di bagian tertentu dari dokumen.

#### T: Bagaimana cara memindahkan DocumentBuilder ke bagian tertentu di dokumen Word?

J: Untuk memindahkan DocumentBuilder ke bagian tertentu di dokumen Word, Anda bisa menggunakan metode MoveToSection dari kelas DocumentBuilder. Metode ini mengambil indeks bagian target sebagai parameter dan menempatkan kursor di awal bagian tersebut.

#### T: Dapatkah saya menambah atau mengubah konten setelah berpindah ke bagian tertentu menggunakan fitur Pindah Ke Bagian?

J: Ya, setelah DocumentBuilder diposisikan pada bagian yang diinginkan menggunakan MoveToSection, Anda dapat menggunakan berbagai metode kelas DocumentBuilder, seperti Writeln, Write, atau InsertHtml, untuk menambah atau mengubah konten bagian tersebut.

#### T: Bagaimana cara mengerjakan paragraf yang sudah ada dalam dokumen menggunakan fitur Pindah Ke Bagian?

J: Anda dapat memuat dokumen yang sudah ada yang berisi paragraf menggunakan konstruktor Dokumen dan kemudian mengakses kumpulan paragraf dari bagian yang diinginkan menggunakan properti FirstSection.Body.Paragraphs.

#### T: Dapatkah saya memindahkan kursor DocumentBuilder ke paragraf tertentu dalam suatu bagian menggunakan fitur Pindah Ke Bagian?

J: Ya, Anda dapat memindahkan kursor DocumentBuilder ke paragraf tertentu dalam suatu bagian menggunakan metode MoveToParagraph. Metode ini mengambil indeks paragraf target dan posisi karakter (offset) dalam paragraf sebagai parameter.