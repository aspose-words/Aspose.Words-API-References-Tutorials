---
title: Atur Pemformatan Baris Tabel
linktitle: Atur Pemformatan Baris Tabel
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk mengatur pemformatan baris tabel menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-table-styles-and-formatting/set-table-row-formatting/
---

Dalam tutorial ini, kami akan memandu Anda melalui proses langkah demi langkah untuk mengatur pemformatan baris tabel menggunakan Aspose.Words untuk .NET. Kami akan menjelaskan paket kode sumber C# dan memberi Anda panduan komprehensif untuk membantu Anda memahami dan menerapkan fitur ini dalam proyek Anda sendiri. Di akhir tutorial ini, Anda akan mengetahui cara menyesuaikan tinggi dan bantalan baris tabel di dokumen Word Anda menggunakan Aspose.Words untuk .NET.

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
Table table = builder. StartTable();
builder. InsertCell();
```

## Langkah 4: Tentukan format garis
 Sekarang kita dapat mengatur format baris dengan mengakses`RowFormat` objek dari`DocumentBuilder` obyek. Kita dapat mengatur tinggi garis dan margin (padding) menggunakan properti yang sesuai.

```csharp
RowFormat rowFormat = builder.RowFormat;
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## Langkah 5: Tetapkan margin tabel
 Selanjutnya, kita dapat mengatur padding tabel dengan mengakses properti yang sesuai dari`Table` obyek. Margin ini akan diterapkan ke semua baris tabel.

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## Langkah 6: Tambahkan konten ke baris
 Terakhir, kita dapat menambahkan konten ke baris menggunakan pembuat dokumen`Writeln()` metode.

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## Langkah 7: Selesaikan tabel dan simpan dokumen
Di dalam

 selesai, kita selesaikan pembuatan tabel menggunakan`EndRow()` Dan`EndTable()` metode, lalu kami menyimpan dokumen yang dimodifikasi ke file.

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

### Contoh kode sumber untuk Mengatur Pemformatan Baris Tabel menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	RowFormat rowFormat = builder.RowFormat;
	rowFormat.Height = 100;
	rowFormat.HeightRule = HeightRule.Exactly;
	// Properti pemformatan ini diatur pada tabel dan diterapkan ke semua baris dalam tabel.
	table.LeftPadding = 30;
	table.RightPadding = 30;
	table.TopPadding = 30;
	table.BottomPadding = 30;
	builder.Writeln("I'm a wonderful formatted row.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara mengatur pemformatan baris tabel menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah ini, Anda dapat dengan mudah menyesuaikan tinggi dan margin baris tabel di dokumen Word Anda. Aspose.Words menawarkan API yang kuat dan fleksibel untuk memanipulasi dan memformat tabel di dokumen Anda. Dengan pengetahuan ini, Anda dapat menyesuaikan tata letak visual tabel dengan kebutuhan spesifik Anda.