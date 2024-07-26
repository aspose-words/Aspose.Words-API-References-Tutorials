---
title: Tabel Terformat
linktitle: Tabel Terformat
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara membuat tabel berformat dalam dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-tables/formatted-table/
---

Dalam tutorial ini, kita akan mempelajari cara membuat tabel berformat dalam dokumen Word menggunakan Aspose.Words untuk .NET. Kami akan mengikuti panduan langkah demi langkah untuk memahami kode dan menerapkan fitur ini. Di akhir tutorial ini, Anda akan dapat membuat tabel dengan format khusus di dokumen Word Anda secara terprogram.

## Langkah 1: Pengaturan Proyek
1. Luncurkan Visual Studio dan buat proyek C# baru.
2. Tambahkan referensi ke perpustakaan Aspose.Words untuk .NET.

## Langkah 2: Membuat dokumen dan menginisialisasi pembuat dokumen
Untuk mulai membuat tabel yang diformat, kita perlu membuat dokumen baru dan menginisialisasi pembuat dokumen. Ikuti langkah ini:

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Buat dokumen dan inisialisasi pembuat dokumen
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Pastikan untuk mengganti "DIREKTORI DOKUMEN ANDA" dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 3: Membangun Tabel Terformat
Selanjutnya, kita akan membuat tabel yang diformat menggunakan metode yang disediakan oleh pembuat dokumen. Gunakan kode berikut:

```csharp
// Mulailah konstruksi susunan
Table table = builder. StartTable();

// Konstruksi baris header tabel
builder. InsertCell();
table. LeftIndent = 20.0;
builder.RowFormat.Height = 40.0;
builder.RowFormat.HeightRule = HeightRule.AtLeast;
builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Font.Size = 16;
builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.CellFormat.Width = 100.0;
builder.Write("Header Row,\n Cell 1");

builder. InsertCell();
builder.Write("Header Row,\n Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Header Row,\n Cell 3");

builder. EndRow();

// Konstruksi badan array
builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
builder.CellFormat.Width = 100.0;
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.RowFormat.Height = 30.0;
builder.RowFormat.HeightRule = HeightRule.Auto;

builder. InsertCell();
builder.Font.Size = 12;
builder.Font.Bold = false;
builder.Write("Content Line 1, Cell 1");

builder. InsertCell();
builder.Write("Content Line 1, Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Content Line 1, Cell

3");

builder. EndRow();

builder. InsertCell();
builder.CellFormat.Width = 100.0;
builder.Write("Content Line 2, Cell 1");

builder. InsertCell();
builder.Write("Content Line 2, Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Content Line 2, Cell 3");

builder. EndRow();

// Akhir dari konstruksi susunan
builder. EndTable();
```

 Di sini kita menggunakan pembuat dokumen untuk membuat tabel langkah demi langkah. Kami mulai dengan menelepon`StartTable()` untuk menginisialisasi tabel. Lalu kita gunakan`InsertCell()` untuk menyisipkan sel dan`Write()` untuk menambahkan konten ke setiap sel. Kami juga menggunakan properti pemformatan yang berbeda untuk menentukan pemformatan baris tabel, sel, dan teks.

## Langkah 4: Simpan dokumen
Terakhir, kita perlu menyimpan dokumen yang berisi tabel yang diformat. Gunakan kode berikut:

```csharp
// Simpan dokumennya
doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

Pastikan untuk menentukan jalur dan nama file yang benar untuk dokumen keluaran.

### Contoh kode sumber untuk Tabel Terformat menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	// Pemformatan lebar tabel harus diterapkan setelah setidaknya satu baris ada dalam tabel.
	table.LeftIndent = 20.0;
	// Tetapkan tinggi dan tentukan aturan ketinggian untuk baris header.
	builder.RowFormat.Height = 40.0;
	builder.RowFormat.HeightRule = HeightRule.AtLeast;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
	builder.Font.Size = 16;
	builder.Font.Name = "Arial";
	builder.Font.Bold = true;
	builder.CellFormat.Width = 100.0;
	builder.Write("Header Row,\n Cell 1");
	// Kita tidak perlu menentukan lebar sel ini karena merupakan warisan dari sel sebelumnya.
	builder.InsertCell();
	builder.Write("Header Row,\n Cell 2");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Header Row,\n Cell 3");
	builder.EndRow();
	builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
	builder.CellFormat.Width = 100.0;
	builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
	// Setel ulang ketinggian dan tentukan aturan ketinggian yang berbeda untuk badan tabel.
	builder.RowFormat.Height = 30.0;
	builder.RowFormat.HeightRule = HeightRule.Auto;
	builder.InsertCell();
	// Setel ulang pemformatan font.
	builder.Font.Size = 12;
	builder.Font.Bold = false;
	builder.Write("Row 1, Cell 1 Content");
	builder.InsertCell();
	builder.Write("Row 1, Cell 2 Content");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Row 1, Cell 3 Content");
	builder.EndRow();
	builder.InsertCell();
	builder.CellFormat.Width = 100.0;
	builder.Write("Row 2, Cell 1 Content");
	builder.InsertCell();
	builder.Write("Row 2, Cell 2 Content");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Row 2, Cell 3 Content.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara membuat tabel berformat dalam dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah ini dan menerapkan kode C# yang disediakan, Anda dapat membuat tabel khusus dengan format tertentu di dokumen Word Anda secara terprogram. Fitur ini memungkinkan Anda menyajikan dan menyusun data Anda dengan cara yang menarik dan terorganisir secara visual.