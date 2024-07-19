---
title: Tabel Bersarang
linktitle: Tabel Bersarang
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara membuat tabel bertumpuk di dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-tables/nested-table/
---

Dalam tutorial ini, kita akan mempelajari cara membuat tabel bersarang di dokumen Word menggunakan Aspose.Words untuk .NET. Kami akan mengikuti panduan langkah demi langkah untuk memahami kode dan menerapkan fitur ini. Di akhir tutorial ini, Anda akan dapat membuat tabel bertumpuk di dokumen Word Anda secara terprogram.

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

## Langkah 3: Membangun Tabel Bersarang
Selanjutnya, kita akan membuat tabel bersarang dengan menyisipkan sel ke dalam tabel luar dan membuat tabel baru di dalam sel pertama. Gunakan kode berikut:

```csharp
// Masukkan sel pertama dari tabel luar
Cell cell = builder. InsertCell();
builder.Writeln("Cell 1 of the outer table");

// Masukkan sel kedua dari tabel luar
builder. InsertCell();
builder.Writeln("Cell 2 of the outer table");

// Penghentian tabel luar
builder. EndTable();

// Pindah ke sel pertama tabel luar
builder.MoveTo(cell.FirstParagraph);

// Bangun tabel bagian dalam
builder. InsertCell();
builder.Writeln("Cell 1 of inner table");
builder. InsertCell();
builder.Writeln("Cell 2 of the inner table");

// Akhir dari tabel bagian dalam
builder. EndTable();
```

Di sini kita menggunakan pembuat dokumen untuk menyisipkan sel dan konten ke dalam tabel luar. Kemudian kita pindahkan kursor pembuat dokumen ke sel pertama tabel luar dan buat tabel baru di dalamnya dengan menyisipkan sel dan konten.

## Langkah 4: Menyimpan dokumen yang dimodifikasi
Terakhir, kita perlu menyimpan dokumen yang dimodifikasi dengan tabel bersarang. Gunakan kode berikut:

```csharp
doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

Pastikan untuk menentukan jalur dan nama file yang benar untuk dokumen keluaran.

### Contoh kode sumber untuk Tabel Bersarang menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Cell cell = builder.InsertCell();
	builder.Writeln("Outer Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Outer Table Cell 2");
	// Panggilan ini penting untuk membuat tabel bersarang di dalam tabel pertama.
	//Tanpa panggilan ini, sel yang disisipkan di bawah akan ditambahkan ke tabel luar.
	builder.EndTable();
	// Pindah ke sel pertama tabel luar.
	builder.MoveTo(cell.FirstParagraph);
	// Bangun tabel bagian dalam.
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 2");
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara membuat tabel bersarang di dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah ini dan menerapkan kode C# yang disediakan, Anda dapat membuat tabel bertumpuk sesuai dengan kebutuhan spesifik Anda dalam dokumen Word secara terprogram.
