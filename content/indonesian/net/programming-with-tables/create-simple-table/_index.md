---
title: Buat Tabel Sederhana
linktitle: Buat Tabel Sederhana
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara membuat tabel sederhana di dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-tables/create-simple-table/
---

Dalam tutorial ini, kita akan mempelajari cara membuat tabel sederhana di dokumen Word menggunakan Aspose.Words untuk .NET. Kami akan mengikuti panduan langkah demi langkah untuk memahami kode dan menerapkan fitur ini. Di akhir tutorial ini, Anda akan dapat membuat tabel kustom di dokumen Word Anda secara terprogram.

## Langkah 1: Pengaturan Proyek
1. Luncurkan Visual Studio dan buat proyek C# baru.
2. Tambahkan referensi ke perpustakaan Aspose.Words untuk .NET.

## Langkah 2: Membuat dokumen dan menginisialisasi pembuat dokumen
Untuk mulai membuat tabel, kita perlu membuat dokumen baru dan menginisialisasi pembuat dokumen. Ikuti langkah ini:

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Buat dokumen dan inisialisasi pembuat dokumen
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Pastikan untuk mengganti "DIREKTORI DOKUMEN ANDA" dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 3: Membangun array
Selanjutnya, kita akan membuat tabel menggunakan metode yang disediakan oleh pembuat dokumen. Gunakan kode berikut:

```csharp
// Mulailah konstruksi susunan
builder. StartTable();

// Konstruksi sel pertama dari baris pertama
builder. InsertCell();
builder.Write("Contents of cell 1 of row 1.");

// Konstruksi sel kedua dari baris pertama
builder. InsertCell();
builder.Write("Contents of cell 2 of row 1.");

// Panggil metode berikut untuk mengakhiri baris pertama dan memulai baris baru
builder. EndRow();

// Konstruksi sel pertama dari baris kedua
builder. InsertCell();
builder.Write("Contents of cell 1 of row 2.");

// Konstruksi sel kedua dari baris kedua
builder. InsertCell();
builder.Write("Contents of cell 2 of row 2.");

// Panggil metode selanjutnya untuk mengakhiri baris kedua
builder. EndRow();

// Indikasi bahwa pembangunan meja telah selesai
builder. EndTable();
```

 Di sini kita menggunakan pembuat dokumen untuk membuat tabel langkah demi langkah. Kami mulai dengan menelepon`StartTable()` untuk menginisialisasi tabel, lalu gunakan`InsertCell()` untuk menyisipkan sel dan`Write()` untuk menambahkan konten ke setiap sel. Kami juga menggunakan`EndRow()` untuk mengakhiri baris dan memulai baris baru. Akhirnya, kami menelepon`EndTable()` untuk menunjukkan bahwa konstruksi tabel telah selesai.

## Langkah 4: Simpan dokumen
Terakhir, kita perlu menabung

  dokumen dengan tabel yang dibuat. Gunakan kode berikut:

```csharp
// Simpan dokumennya
doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

Pastikan untuk menentukan jalur dan nama file yang benar untuk dokumen keluaran.

### Contoh kode sumber untuk Membuat Tabel Sederhana menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Mulailah membangun meja.
	builder.StartTable();
	builder.InsertCell();
	builder.Write("Row 1, Cell 1 Content.");
	// Bangun sel kedua.
	builder.InsertCell();
	builder.Write("Row 1, Cell 2 Content.");
	// Panggil metode berikut untuk mengakhiri baris dan memulai baris baru.
	builder.EndRow();
	// Bangun sel pertama dari baris kedua.
	builder.InsertCell();
	builder.Write("Row 2, Cell 1 Content");
	// Bangun sel kedua.
	builder.InsertCell();
	builder.Write("Row 2, Cell 2 Content.");
	builder.EndRow();
	// Tanda bahwa kita telah selesai membuat tabel.
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara membuat tabel sederhana di dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah ini dan menerapkan kode C# yang disediakan, Anda dapat membuat tabel khusus di dokumen Word Anda secara terprogram. Fitur ini memungkinkan Anda memformat dan mengatur data Anda secara terstruktur dan jelas.