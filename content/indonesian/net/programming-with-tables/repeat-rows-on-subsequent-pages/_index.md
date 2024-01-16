---
title: Ulangi Baris Di Halaman Berikutnya
linktitle: Ulangi Baris Di Halaman Berikutnya
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengulang baris tabel pada halaman berikutnya dalam dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-tables/repeat-rows-on-subsequent-pages/
---

Dalam tutorial ini, kita akan mempelajari cara mengulang baris tabel di halaman berikutnya dokumen Word menggunakan Aspose.Words untuk .NET. Kami akan mengikuti panduan langkah demi langkah untuk memahami kode dan menerapkan fitur ini. Di akhir tutorial ini, Anda akan dapat menentukan baris yang akan diulang pada halaman tabel berikutnya di dokumen Word Anda.

## Langkah 1: Pengaturan Proyek
1. Luncurkan Visual Studio dan buat proyek C# baru.
2. Tambahkan referensi ke perpustakaan Aspose.Words untuk .NET.

## Langkah 2: Membuat dokumen dan menginisialisasi pembuat dokumen
Untuk memulai Pemrosesan Kata dengan dokumen dan pembuat dokumen, ikuti langkah-langkah berikut:

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Pembuatan dokumen
Document doc = new Document();

// Inisialisasi pembuat dokumen
DocumentBuilder builder = new DocumentBuilder(doc);
```

Pastikan untuk mengganti "DIREKTORI DOKUMEN ANDA" dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 3: Membangun tabel dengan baris berulang
Selanjutnya, kita akan membuat tabel dengan baris berulang di halaman berikutnya. Gunakan kode berikut:

```csharp
// Awal tabel
builder. StartTable();

// Konfigurasi parameter baris pertama (garis header)
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;

// Masukkan sel pertama dari baris pertama
builder. InsertCell();
builder.Writeln("Header line 1");
builder. EndRow();

// Masukkan sel kedua dari baris pertama
builder. InsertCell();
builder.Writeln("Header line 2");
builder. EndRow();

// Konfigurasikan parameter baris berikut
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();

// Ulangi untuk menyisipkan sel di baris berikutnya
for (int i = 0; i < 50; i++)
{
builder. InsertCell();
builder.RowFormat.HeadingFormat = false;
builder.Write("Text column 1");
builder. InsertCell();
builder.Write("Text column 2");
builder. EndRow();
}

// Akhir tabel
builder. EndTable();
```

 Di sini kita menggunakan pembuat dokumen untuk membuat tabel dengan dua baris header dan beberapa baris data. Itu`RowFormat.HeadingFormat`parameter digunakan untuk menandai baris header yang harus diulang pada halaman berikutnya.

## Langkah 4: Menyimpan dokumen yang dimodifikasi
Akhirnya AS

  perlu menyimpan dokumen yang dimodifikasi dengan baris header diulangi pada halaman tabel berikutnya. Gunakan kode berikut:

```csharp
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

Pastikan untuk menentukan jalur dan nama file yang benar untuk dokumen keluaran.

### Contoh kode sumber untuk Ulangi Baris Pada Halaman Berikutnya menggunakan Aspose.Words untuk .NET 

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.StartTable();
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;
builder.InsertCell();
builder.Writeln("Heading row 1");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Heading row 2");
builder.EndRow();
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();
for (int i = 0; i < 50; i++)
{
	builder.InsertCell();
	builder.RowFormat.HeadingFormat = false;
	builder.Write("Column 1 Text");
	builder.InsertCell();
	builder.Write("Column 2 Text");
	builder.EndRow();
}
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara mengulang baris tabel pada halaman berikutnya dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah ini dan menerapkan kode C# yang disediakan, Anda dapat menentukan baris mana yang akan diulang sesuai dengan kebutuhan spesifik Anda di dokumen Word Anda.