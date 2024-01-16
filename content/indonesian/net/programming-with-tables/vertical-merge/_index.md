---
title: Penggabungan Vertikal
linktitle: Penggabungan Vertikal
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menggabungkan sel secara vertikal dalam tabel di dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-tables/vertical-merge/
---

Dalam tutorial ini, kita akan mempelajari cara menggabungkan sel secara vertikal dalam tabel di dokumen Word menggunakan Aspose.Words untuk .NET. Kami akan mengikuti panduan langkah demi langkah untuk memahami kode dan menerapkan fitur ini. Di akhir tutorial ini, Anda akan dapat menggabungkan sel secara vertikal di tabel Anda di dokumen Word.

## Langkah 1: Pengaturan Proyek
1. Luncurkan Visual Studio dan buat proyek C# baru.
2. Tambahkan referensi ke perpustakaan Aspose.Words untuk .NET.

## Langkah 2: Memuat dokumen
Untuk memulai Pemrosesan Kata dengan dokumen, ikuti langkah-langkah berikut:

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Buat dokumen baru
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Pastikan untuk mengganti "DIREKTORI DOKUMEN ANDA" dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 3: Menggabungkan Sel Vertikal
Selanjutnya kita akan menggabungkan sel vertikal pada tabel. Gunakan kode berikut:

```csharp
// Masukkan sel
builder. InsertCell();

// Terapkan penggabungan vertikal ke sel pertama
builder.CellFormat.VerticalMerge = CellMerge.First;
builder.Write("Text in merged cells.");

// Masukkan sel lain
builder. InsertCell();

// Tidak menerapkan penggabungan vertikal ke sel
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in a cell");
builder. EndRow();

// Masukkan sel
builder. InsertCell();

// Terapkan penggabungan vertikal dengan sel sebelumnya
builder.CellFormat.VerticalMerge = CellMerge.Previous;

// Masukkan sel lain
builder. InsertCell();

// Tidak menerapkan penggabungan vertikal ke sel
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in another cell");
builder. EndRow();

//Akhiri pembuatan tabel
builder. EndTable();
```

Dalam kode ini, kita menggunakan konstruktor DocumentBuilder untuk menyisipkan sel ke dalam tabel. Kami menerapkan penggabungan vertikal ke sel menggunakan properti CellFormat.VerticalMerge. Kami menggunakan CellMerge.First untuk penggabungan sel pertama, CellMerge.Previous untuk menggabungkan dengan sel sebelumnya, dan CellMerge.None untuk penggabungan vertikal.

## Langkah 4: Menyimpan dokumen yang dimodifikasi
Terakhir, kita perlu menyimpan dokumen yang dimodifikasi dengan sel yang digabungkan. Gunakan kode berikut:

```csharp
doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

Pastikan untuk menentukan jalur dan nama file yang benar untuk dokumen keluaran.

### Contoh kode sumber untuk Penggabungan Vertikal menggunakan Aspose.Words untuk .NET 
```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in one cell");
	builder.EndRow();
	builder.InsertCell();
	// Sel ini digabungkan secara vertikal dengan sel di atasnya dan harus kosong.
	builder.CellFormat.VerticalMerge = CellMerge.Previous;
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in another cell");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara menggabungkan sel secara vertikal dalam tabel di dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah ini dan menerapkan kode C# yang disediakan, Anda dapat dengan mudah menggabungkan sel Vertikal di tabel Anda.