---
title: Buat Bookmark Di Dokumen Word
linktitle: Buat Bookmark Di Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara membuat bookmark di dokumen Word dan menentukan tingkat pratinjau bookmark di PDF menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-bookmarks/create-bookmark/
---

Pada artikel ini, kita akan menjelajahi kode sumber C# di atas untuk memahami cara menggunakan fungsi Buat Bookmark di pustaka Aspose.Words untuk .NET. Fitur ini memungkinkan Anda membuat bookmark dalam dokumen dan menentukan tingkat pratinjau bookmark dalam file PDF keluaran.

## Prasyarat

- Pengetahuan dasar bahasa C#.
- Lingkungan pengembangan .NET dengan perpustakaan Aspose.Words diinstal.

## Langkah 1: Membuat Dokumen dan Generator

 Sebelum membuat bookmark, kita perlu membuat dokumen dan pembuat dokumen menggunakan`Document` Dan`DocumentBuilder` objek:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 2: Membuat bookmark utama

 Kami menggunakan`StartBookmark` metode untuk memulai bookmark utama dan`EndBookmark` metode untuk mengakhirinya. Di antaranya, kita dapat menambahkan teks dan bookmark lainnya:

```csharp
builder. StartBookmark("My Bookmark");
builder.Writeln("Text inside a bookmark.");

// Tambahkan lebih banyak bookmark atau teks di sini.

builder. EndBookmark("My Bookmark");
```

## Langkah 3: Membuat Bookmark Bersarang

 Kita juga dapat membuat bookmark bersarang di dalam bookmark utama. Kami menggunakan hal yang sama`StartBookmark` Dan`EndBookmark` metode untuk membuat dan mengakhiri bookmark bersarang:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

## Langkah 4: Menentukan tingkat pratinjau bookmark di file PDF keluaran

 Kami menggunakan`PdfSaveOptions` objek untuk menentukan tingkat pratinjau bookmark dalam file PDF keluaran. Kami menggunakan`BookmarksOutlineLevels` Properti

  untuk menambahkan bookmark utama dan bookmark bersarang dengan levelnya masing-masing:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
```

### Contoh kode sumber untuk Membuat Bookmark menggunakan Aspose.Words untuk .NET

Berikut adalah contoh lengkap kode sumber untuk mendemonstrasikan pembuatan bookmark menggunakan Aspose.Words untuk .NET:

```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.StartBookmark("My Bookmark");
	builder.Writeln("Text inside a bookmark.");

	builder.StartBookmark("Nested Bookmark");
	builder.Writeln("Text inside a NestedBookmark.");
	builder.EndBookmark("Nested Bookmark");

	builder.Writeln("Text after Nested Bookmark.");
	builder.EndBookmark("My Bookmark");

	PdfSaveOptions options = new PdfSaveOptions();
	options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
	options.OutlineOptions.BookmarksOutlineLevels.Add("Nested Bookmark", 2);

	doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
  
```

## Kesimpulan

Dalam artikel ini, kami menjelajahi kode sumber C# untuk memahami cara menggunakan fungsi Buat Bookmark Aspose.Words untuk .NET. Kami telah mengikuti panduan langkah demi langkah untuk membuat bookmark di dokumen dan menentukan tingkat pratinjau bookmark di file PDF keluaran.

### FAQ

#### T: Apa saja prasyarat untuk menggunakan fungsi "Buat bookmark" di Aspose.Words untuk .NET?

J: Untuk menggunakan fungsi "Buat bookmark" di Aspose.Words untuk .NET, Anda harus memiliki pengetahuan dasar tentang bahasa C#. Anda juga memerlukan lingkungan pengembangan .NET dengan perpustakaan Aspose.Words terinstal.

#### T: Bagaimana cara membuat dokumen di Aspose.Words untuk .NET?

 J: Untuk membuat dokumen di Aspose.Words untuk .NET, Anda dapat menggunakan`Document` kelas. Berikut ini contoh kodenya:

```csharp
Document doc = new Document();
```

#### T: Bagaimana cara membuat bookmark utama dalam dokumen menggunakan Aspose.Words untuk .NET?

 A: Untuk membuat bookmark utama dalam dokumen menggunakan Aspose.Words untuk .NET, Anda dapat menggunakan`StartBookmark` metode untuk memulai bookmark, menambahkan teks atau bookmark lain di dalamnya, lalu gunakan` EndBookmark` untuk mengakhirinya. Berikut ini contoh kodenya:

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### T: Bagaimana cara membuat bookmark bersarang di dalam bookmark utama menggunakan Aspose.Words untuk .NET?

 J: Untuk membuat bookmark bersarang di dalam bookmark utama menggunakan Aspose.Words untuk .NET, Anda dapat menggunakan yang sama`StartBookmark` Dan`EndBookmark` metode untuk memulai dan mengakhiri bookmark bersarang. Berikut ini contoh kodenya:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

#### T: Bagaimana cara menentukan tingkat pratinjau bookmark dalam PDF keluaran menggunakan Aspose.Words untuk .NET?

 J: Untuk menentukan tingkat pratinjau bookmark dalam PDF keluaran menggunakan Aspose.Words untuk .NET, Anda dapat menggunakan`PdfSaveOptions` kelas dan`BookmarksOutlineLevels` Properti. Anda dapat menambahkan bookmark utama dan bookmark bersarang dengan levelnya masing-masing. Berikut ini contoh kodenya:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
```

#### T: Bagaimana cara menyimpan dokumen setelah membuat bookmark menggunakan Aspose.Words untuk .NET?

 A: Untuk menyimpan dokumen setelah membuat bookmark menggunakan Aspose.Words untuk .NET, Anda dapat menggunakan`Save` metode`Document` objek yang menentukan jalur file tujuan. Berikut ini contoh kodenya:

```csharp
doc.Save("path/to/your/output-document.docx");
```

#### T: Bagaimana cara menentukan tingkat pratinjau bookmark dalam PDF keluaran menggunakan Aspose.Words untuk .NET?

 J: Untuk menentukan tingkat pratinjau bookmark dalam PDF keluaran menggunakan Aspose.Words untuk .NET, Anda dapat menggunakan`PdfSaveOptions` kelas dan`BookmarksOutlineLevels` Properti. Anda dapat menambahkan bookmark utama dan bookmark bersarang dengan levelnya masing-masing. Berikut ini contoh kodenya:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save("path/to/your/output-pdf-file.pdf", options);
```

#### T: Bagaimana cara membuat bookmark bersarang di dalam bookmark utama menggunakan Aspose.Words untuk .NET?

 J: Untuk membuat bookmark bersarang di dalam bookmark utama menggunakan Aspose.Words untuk .NET, Anda dapat menggunakan yang sama`StartBookmark` Dan`EndBookmark` metode untuk memulai dan mengakhiri bookmark bersarang. Pastikan untuk menentukan bookmark induk sebagai parameter saat memanggil`StartBookmark` metode. Berikut ini contoh kodenya:

```csharp
builder.StartBookmark("Main bookmark");
builder.Writeln("Text inside main bookmark.");

builder.StartBookmark("Nested bookmark 1");
builder.Writeln("Text inside first nested bookmark.");
builder.EndBookmark("Nested bookmark 1");

builder.StartBookmark("Nested bookmark 2");
builder.Writeln("Text inside second nested bookmark.");
builder.EndBookmark("Nested bookmark 2");

builder.EndBookmark("Main bookmark");
```

#### T: Bagaimana cara menambahkan teks di dalam bookmark menggunakan Aspose.Words untuk .NET?

 A: Untuk menambahkan teks di dalam bookmark menggunakan Aspose.Words untuk .NET, Anda dapat menggunakan`Write` metode`DocumentBuilder`objek yang menentukan teks yang akan ditambahkan. Berikut ini contoh kodenya:

```csharp
builder.StartBookmark("My Bookmark");
builder.Write("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### T: Bagaimana cara membuat bookmark utama dalam dokumen menggunakan Aspose.Words untuk .NET?

 A: Untuk membuat bookmark utama dalam dokumen menggunakan Aspose.Words untuk .NET, Anda dapat menggunakan`StartBookmark` metode untuk memulai bookmark dan`EndBookmark` metode untuk mengakhirinya. Berikut ini contoh kodenya:

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```