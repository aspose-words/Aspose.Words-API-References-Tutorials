---
title: Penggabungan Horisontal
linktitle: Penggabungan Horisontal
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menggabungkan sel secara horizontal dalam tabel Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-tables/horizontal-merge/
---

Dalam tutorial ini, kita akan mempelajari cara menggabungkan sel secara horizontal dalam tabel di dokumen Word menggunakan Aspose.Words untuk .NET. Kami akan mengikuti panduan langkah demi langkah untuk memahami kode dan menerapkan fitur ini. Di akhir tutorial ini, Anda akan dapat menggabungkan sel secara horizontal di tabel Word Anda secara terprogram.

## Langkah 1: Pengaturan Proyek
1. Luncurkan Visual Studio dan buat proyek C# baru.
2. Tambahkan referensi ke perpustakaan Aspose.Words untuk .NET.

## Langkah 2: Membuat dokumen dan menginisialisasi pembuat dokumen
Untuk memulai Pemrosesan Kata dengan tabel dan sel, kita perlu membuat dokumen baru dan menginisialisasi pembuat dokumen. Ikuti langkah ini:

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Buat dokumen dan inisialisasi pembuat dokumen
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Pastikan untuk mengganti "DIREKTORI DOKUMEN ANDA" dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 3: Membangun tabel dengan penggabungan sel secara horizontal
Selanjutnya, kita akan membuat tabel dan menerapkan penggabungan sel horizontal menggunakan properti yang disediakan oleh Aspose.Words untuk .NET. Gunakan kode berikut:

```csharp
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.First;
builder.Write("Text in merged cells.");
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.Previous;
// Sel ini digabungkan dengan sel sebelumnya dan harus kosong.
builder. EndRow();

builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.None;
builder.Write("Text in a cell.");
builder. InsertCell();
builder.Write("Text in another cell.");
builder. EndRow();
builder. EndTable();
```

 Di sini kita menggunakan pembuat dokumen untuk membuat tabel dan mengatur properti penggabungan horizontal sel. Kami menggunakan`HorizontalMerge` properti dari`CellFormat` objek untuk menentukan jenis penggabungan horizontal yang akan diterapkan ke setiap sel. Menggunakan`CellMerge.First` kami menggabungkan sel pertama dengan sel berikutnya, sambil menggunakan`CellMerge.Previous` kami menggabungkan sel saat ini dengan sel sebelumnya.`CellMerge.None` menunjukkan bahwa sel tidak boleh digabungkan.

## Langkah 4: Menyimpan dokumen yang dimodifikasi
Terakhir, kita perlu menyimpan dokumen yang dimodifikasi dengan sel yang digabungkan secara horizontal. Gunakan kode berikut:

```csharp
doc.Save(data

Dir + "WorkingWithTables.HorizontalMerge.docx");
```

Pastikan untuk menentukan jalur dan nama file yang benar untuk dokumen keluaran.

### Contoh kode sumber untuk Penggabungan Horizontal menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	// Sel ini digabungkan dengan sel sebelumnya dan harus kosong.
	builder.CellFormat.HorizontalMerge = CellMerge.Previous;
	builder.EndRow();
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.None;
	builder.Write("Text in one cell.");
	builder.InsertCell();
	builder.Write("Text in another cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.HorizontalMerge.docx");
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara menggabungkan sel secara horizontal dalam tabel di dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah ini dan menerapkan kode C# yang disediakan, Anda bisa menerapkan penggabungan sel horizontal di tabel Word Anda secara terprogram. Fitur ini memungkinkan Anda membuat tata letak tabel yang lebih kompleks dan mengatur data Anda dengan lebih baik.