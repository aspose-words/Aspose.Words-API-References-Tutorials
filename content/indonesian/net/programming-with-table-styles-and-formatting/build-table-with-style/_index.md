---
title: Bangun Meja Dengan Gaya
linktitle: Bangun Meja Dengan Gaya
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk membuat tabel dengan gaya kustom menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-table-styles-and-formatting/build-table-with-style/
---

Dalam tutorial ini, kami akan memandu Anda melalui proses langkah demi langkah untuk membuat tabel bergaya menggunakan Aspose.Words untuk .NET. Kami akan menjelaskan paket kode sumber C# dan memberi Anda panduan komprehensif untuk membantu Anda memahami dan menerapkan fitur ini dalam proyek Anda sendiri. Di akhir tutorial ini, Anda akan mengetahui cara membuat tabel dengan gaya kustom di dokumen Word Anda menggunakan Aspose.Words untuk .NET.

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

## Langkah 3: Mulai tabel baru dan masukkan sel
 Untuk mulai membuat tabel, kami menggunakan`StartTable()` metode pembuat dokumen, lalu kita masukkan sel ke dalam tabel menggunakan`InsertCell()` metode.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## Langkah 4: Tentukan gaya tabel
 Sekarang kita dapat mengatur gaya tabel menggunakan`StyleIdentifier` Properti. Dalam contoh ini, kita menggunakan gaya "MediumShading1Accent1".

```csharp
table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
```

## Langkah 5: Terapkan opsi gaya ke tabel
 Kita dapat menentukan karakteristik mana yang harus diformat berdasarkan gaya menggunakan`StyleOptions`properti dari array. Dalam contoh ini, kami menerapkan opsi berikut: "FirstColumn", "RowBands" dan "FirstRow".

```csharp
table.StyleOptions = TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
```

## Langkah 6: Sesuaikan ukuran tabel secara otomatis
 Untuk menyesuaikan ukuran array secara otomatis berdasarkan isinya, kami menggunakan`AutoFit()` metode dengan`AutoFitBehavior.AutoFitToContents` perilaku.

```csharp
table. AutoFit(AutoFitBehavior.AutoFitToContents);
```

## Langkah 7: Tambahkan konten ke sel
 Sekarang kita dapat menambahkan konten ke sel menggunakan`Writeln()`Dan`InsertCell()` metode pembuat dokumen. Dalam contoh ini, kita menambahkan header untuk "Item" dan "Quantity (

kg)" dan data terkait.

```csharp
builder.Writeln("Item");
builder.CellFormat.RightPadding = 40;
builder. InsertCell();
builder. Writen("Quantity (kg)");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Apples");
builder. InsertCell();
builder.Writeln("20");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Bananas");
builder. InsertCell();
builder. Writen("40");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Carrots");
builder. InsertCell();
builder.Writeln("50");
builder. EndRow();
```

## Langkah 8: Simpan dokumen yang dimodifikasi
Terakhir, kami menyimpan dokumen yang dimodifikasi ke sebuah file. Anda dapat memilih nama dan lokasi yang sesuai untuk dokumen keluaran.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

Selamat! Anda sekarang telah membuat tabel bergaya khusus menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber untuk Membangun Tabel Dengan Gaya menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	// Kita harus menyisipkan setidaknya satu baris terlebih dahulu sebelum mengatur format tabel apa pun.
	builder.InsertCell();
	// Atur gaya tabel yang digunakan berdasarkan pengidentifikasi gaya unik.
	table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
	// Terapkan fitur mana yang harus diformat berdasarkan gaya.
	table.StyleOptions =
		TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
	table.AutoFit(AutoFitBehavior.AutoFitToContents);
	builder.Writeln("Item");
	builder.CellFormat.RightPadding = 40;
	builder.InsertCell();
	builder.Writeln("Quantity (kg)");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Apples");
	builder.InsertCell();
	builder.Writeln("20");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Bananas");
	builder.InsertCell();
	builder.Writeln("40");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Carrots");
	builder.InsertCell();
	builder.Writeln("50");
	builder.EndRow();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara membuat tabel bergaya menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah ini, Anda bisa dengan mudah mengkustomisasi gaya tabel di dokumen Word Anda. Aspose.Words menawarkan API yang kuat dan fleksibel untuk memanipulasi dan memformat tabel di dokumen Anda. Dengan pengetahuan ini, Anda dapat meningkatkan presentasi visual dokumen Word Anda dan memenuhi kebutuhan spesifik.