---
title: Atur Bantalan Sel
linktitle: Atur Bantalan Sel
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk mengatur margin sel tabel menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-table-styles-and-formatting/set-cell-padding/
---

Dalam tutorial ini, kami akan memandu Anda melalui proses langkah demi langkah untuk mengatur margin sel tabel menggunakan Aspose.Words untuk .NET. Kami akan menjelaskan paket kode sumber C# dan memberi Anda panduan komprehensif untuk membantu Anda memahami dan menerapkan fitur ini dalam proyek Anda sendiri. Di akhir tutorial ini, Anda akan mengetahui cara menyesuaikan margin (spasi) kiri, atas, kanan, dan bawah konten sel dalam tabel di dokumen Word Anda menggunakan Aspose.Words untuk .NET.

## Langkah 1: Tentukan direktori dokumen
Pertama, Anda perlu menyetel jalur ke direktori dokumen Anda. Ini adalah lokasi di mana Anda ingin menyimpan dokumen Word yang telah Anda edit. Ganti "DIREKTORI DOKUMEN ANDA" dengan jalur yang sesuai.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Buat dokumen baru dan pembuat dokumen
 Selanjutnya, Anda perlu membuat instance baru dari`Document` kelas dan konstruktor dokumen untuk dokumen itu.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 3: Mulai tabel baru dan tambahkan sel
Untuk mulai membuat tabel, kami menggunakan`StartTable()` metode konstruktor dokumen, lalu kita menambahkan sel ke tabel menggunakan`InsertCell()` metode.

```csharp
builder. StartTable();
builder. InsertCell();
```

## Langkah 4: Tetapkan margin sel
 Sekarang kita dapat mengatur margin sel menggunakan`SetPaddings()` metode`CellFormat` obyek. Margin ditentukan dalam poin dan ditentukan dalam urutan kiri, atas, kanan, dan bawah.

```csharp
builder.CellFormat.SetPaddings(30, 50, 30, 50);
```

## Langkah 5: Tambahkan konten ke sel
 Lalu kita bisa menambahkan konten ke sel menggunakan pembuat dokumen`Writeln()` metode.

```csharp
builder.Writeln("I'm a beautifully formatted cell.");
```

## Langkah 6: Selesaikan tabel dan simpan dokumen
 Akhirnya, kita selesai membuat tabel menggunakan`EndRow()` metode dan`EndTable()`, lalu kita simpan dokumen yang dimodifikasi ke sebuah file.

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.SetCellPadding.docx");
```
 
### Contoh kode sumber untuk Mengatur Padding Sel menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.StartTable();
	builder.InsertCell();
	// Mengatur jumlah spasi (dalam poin) untuk ditambahkan ke kiri/atas/kanan/bawah konten sel.
	builder.CellFormat.SetPaddings(30, 50, 30, 50);
	builder.Writeln("I'm a wonderful formatted cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.SetCellPadding.docx");
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara mengatur margin sel tabel menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah ini, Anda dapat dengan mudah menyesuaikan margin sel untuk membuat spasi di kiri, atas, kanan, dan bawah konten tabel di dokumen Word Anda. Aspose.Words menawarkan API yang kuat dan fleksibel untuk memanipulasi dan memformat tabel di dokumen Anda. Dengan pengetahuan ini, Anda dapat menyesuaikan format tabel dengan kebutuhan spesifik Anda.