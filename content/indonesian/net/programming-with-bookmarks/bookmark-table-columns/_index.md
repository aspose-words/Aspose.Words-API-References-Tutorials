---
title: Tandai Kolom Tabel Di Dokumen Word
linktitle: Tandai Kolom Tabel Di Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menandai kolom tabel di dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-bookmarks/bookmark-table-columns/
---

Pada artikel ini, kita akan menjelajahi kode sumber C# di atas untuk memahami cara menggunakan fungsi Kolom Tabel Bookmark di pustaka Aspose.Words untuk .NET. Fitur ini memungkinkan Anda untuk menandai kolom tertentu dari tabel di dokumen Word dan mengakses konten kolom tersebut.

## Prasyarat

- Pengetahuan dasar bahasa C#.
- Lingkungan pengembangan .NET dengan perpustakaan Aspose.Words diinstal.

## Langkah 1: Membuat tabel

 Sebelum membuat bookmark pada kolom tabel, kita harus membuat tabelnya terlebih dahulu dengan menggunakan a`DocumentBuilder`obyek. Dalam contoh kita, kita membuat tabel dengan dua baris dan dua kolom:

```csharp
builder. StartTable();

builder. InsertCell();

builder. StartBookmark("MyBookmark");

builder.Write("This is cell 1 of row 1");

builder. InsertCell();
builder.Write("This is cell 2 of row 1");

builder. EndRow();

builder. InsertCell();
builder.Writeln("This is cell 1 of row 2");

builder. InsertCell();
builder.Writeln("This is cell 2 of row 2");

builder. EndRow();
builder. EndTable();
```

## Langkah 2: Membuat bookmark kolom

 Kami menggunakan`StartBookmark` metode untuk membuat bookmark pada kolom tabel tertentu. Dalam contoh kami, kami menggunakan nama "MyBookmark" untuk bookmark:

```csharp
builder. StartBookmark("MyBookmark");
```

## Langkah 3: Akses konten kolom

 Kami menelusuri semua bookmark di dokumen dan menampilkan namanya. Jika bookmark adalah kolom, kita mengakses konten kolom tersebut menggunakan indeks kolom dan`GetText` metode:

```csharp
foreach (Bookmark

  bookmark in doc.Range.Bookmarks)
{
Console.WriteLine("Bookmark: {0}{1}", bookmark.Name, bookmark.IsColumn?" (Column)": "");

if (bookmark.IsColumn)
{
if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
Console.WriteLine(row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar));
}
}
```

### Contoh kode sumber untuk Kolom Tabel Bookmark menggunakan Aspose.Words untuk .NET

Berikut ini contoh kode sumber lengkap untuk mendemonstrasikan pembuatan bookmark pada kolom tabel menggunakan Aspose.Words untuk .NET:

```csharp

	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.StartTable();
	
	builder.InsertCell();

	builder.StartBookmark("MyBookmark");

	builder.Write("This is row 1 cell 1");

	builder.InsertCell();
	builder.Write("This is row 1 cell 2");

	builder.EndRow();

	builder.InsertCell();
	builder.Writeln("This is row 2 cell 1");

	builder.InsertCell();
	builder.Writeln("This is row 2 cell 2");

	builder.EndRow();
	builder.EndTable();
	
	builder.EndBookmark("MyBookmark");
	

	
	foreach (Bookmark bookmark in doc.Range.Bookmarks)
	{
		Console.WriteLine("Bookmark: {0}{1}", bookmark.Name, bookmark.IsColumn ? " (Column)" : "");

		if (bookmark.IsColumn)
		{
			if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
				Console.WriteLine(row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar));
		}
	}
	
        
```

## Kesimpulan

Dalam artikel ini, kami menjelajahi kode sumber C# untuk memahami cara menggunakan fungsi Kolom Tabel Bookmark Aspose.Words untuk .NET. Kami mengikuti panduan langkah demi langkah untuk menandai kolom tertentu dari tabel di dokumen Word dan melompat ke konten kolom tersebut.

### FAQ untuk kolom tabel bookmark di dokumen Word

#### T: Apa saja prasyarat untuk menggunakan fitur "Bookmark untuk kolom tabel" di Aspose.Words untuk .NET?

J: Untuk menggunakan fitur "Bookmark untuk kolom tabel" di Aspose.Words untuk .NET, Anda harus memiliki pengetahuan dasar tentang bahasa C#. Anda juga memerlukan lingkungan pengembangan .NET dengan perpustakaan Aspose.Words terinstal.

#### T: Bagaimana cara membuat tabel dengan kolom di dokumen Word menggunakan Aspose.Words untuk .NET?

 J: Untuk membuat tabel dengan kolom di dokumen Word menggunakan Aspose.Words untuk .NET, Anda bisa menggunakan`DocumentBuilder` objek untuk menyisipkan sel dan konten ke dalam tabel. Berikut ini contoh kodenya:

```csharp
builder. StartTable();

builder. InsertCell();
builder.Write("Contents of cell 1 of column 1");

builder. InsertCell();
builder.Write("Contents of cell 2 of column 2");

builder. EndRow();

builder. InsertCell();
builder.Write("Contents of cell 1 of column 2");

builder. InsertCell();
builder.Write("Contents of cell 2 of column 2");

builder. EndRow();

builder. EndTable();
```

#### T: Bagaimana cara mem-bookmark kolom tabel menggunakan Aspose.Words untuk .NET?

 A: Untuk membuat bookmark pada kolom tabel menggunakan Aspose.Words untuk .NET, Anda dapat menggunakan`StartBookmark` metode`DocumentBuilder` objek untuk memulai bookmark pada kolom tabel tertentu. Berikut ini contoh kodenya:

```csharp
builder.StartBookmark("MyBookmark");
```

#### T: Bagaimana cara mengakses konten kolom tabel dari bookmark menggunakan Aspose.Words untuk .NET?

A: Untuk mengakses konten kolom tabel dari bookmark menggunakan Aspose.Words untuk .NET, Anda dapat menelusuri semua bookmark di dokumen, memeriksa apakah bookmark adalah kolom, dan menggunakan indeks kolom untuk mengakses konten kolom itu. Berikut ini contoh kodenya:

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     if (bookmark.IsColumn)
     {
         if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
         {
             string content = row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar);
             // Lakukan sesuatu dengan isi kolom...
         }
     }
}
```

#### T: Apakah ada batasan jumlah kolom yang dapat saya buat dalam tabel dengan penanda kolom?

J: Tidak ada batasan khusus untuk jumlah kolom yang dapat Anda buat dalam tabel dengan penanda kolom menggunakan Aspose.Words untuk .NET. Batasannya terutama bergantung pada sumber daya yang tersedia di sistem Anda dan spesifikasi format file Word yang Anda gunakan. Namun, disarankan untuk tidak membuat kolom dalam jumlah yang terlalu banyak, karena dapat mempengaruhi kinerja dan keterbacaan dokumen akhir.