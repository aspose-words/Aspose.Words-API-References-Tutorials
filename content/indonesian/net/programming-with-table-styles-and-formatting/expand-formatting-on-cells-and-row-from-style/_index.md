---
title: Perluas Pemformatan Pada Sel Dan Baris Dari Gaya
linktitle: Perluas Pemformatan Pada Sel Dan Baris Dari Gaya
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk memperluas pemformatan ke sel dan baris dari gaya tabel menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-table-styles-and-formatting/expand-formatting-on-cells-and-row-from-style/
---

Dalam tutorial ini, kami akan memandu Anda melalui proses langkah demi langkah untuk memperluas pemformatan ke sel dan baris dari suatu gaya menggunakan Aspose.Words untuk .NET. Kami akan menjelaskan paket kode sumber C# dan memberi Anda panduan komprehensif untuk membantu Anda memahami dan menerapkan fitur ini dalam proyek Anda sendiri. Di akhir tutorial ini, Anda akan mengetahui cara menerapkan pemformatan gaya tabel ke sel dan baris tertentu di dokumen Word Anda menggunakan Aspose.Words untuk .NET.


## Langkah 1: Tentukan direktori dokumen
Pertama, Anda perlu menyetel jalur ke direktori dokumen Anda. Di sinilah dokumen Word Anda berada. Ganti "DIREKTORI DOKUMEN ANDA" dengan jalur yang sesuai.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Muat dokumen yang ada
 Selanjutnya, Anda perlu memuat dokumen Word yang ada ke dalam instance`Document` kelas.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Langkah 3: Pergi ke sel pertama dari tabel pertama
 Untuk memulai, kita perlu menavigasi ke sel pertama dari tabel pertama dalam dokumen. Kami menggunakan`GetChild()` Dan`FirstRow.FirstCell` metode untuk mendapatkan referensi ke sel pertama.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Cell firstCell = table.FirstRow.FirstCell;
```

## Langkah 4: Tampilkan Pemformatan Sel Awal
Sebelum Memperluas gaya tabel, kami menampilkan warna latar belakang sel saat ini. Ini harus kosong karena format saat ini disimpan dalam gaya tabel.

```csharp
Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("Shading cell before style expansion: " + cellShadingBefore);
```

## Langkah 5: Perluas Gaya Tabel ke Pemformatan Langsung
 Sekarang kita memperluas gaya tabel ke pemformatan langsung menggunakan dokumen`ExpandTableStylesToDirectFormatting()` metode.

```csharp
doc.ExpandTableStylesToDirectFormatting();
```

## Langkah 6: Tampilkan pemformatan sel setelah perluasan gaya
Sekarang kita menampilkan warna latar belakang sel setelah Memperluas gaya tabel. Warna latar belakang biru harus diterapkan dari gaya tabel.

```csharp
Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("

Shading the cell after style expansion: " + cellShadingAfter);
```

### Contoh kode sumber untuk Perluas Pemformatan Pada Sel dan Baris Dari Gaya menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// Dapatkan sel pertama dari tabel pertama dalam dokumen.
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Cell firstCell = table.FirstRow.FirstCell;
	// Pertama cetak warna bayangan sel.
	// Ini harus kosong karena bayangan saat ini disimpan dalam gaya tabel.
	Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading before style expansion: " + cellShadingBefore);
	doc.ExpandTableStylesToDirectFormatting();
	// Sekarang cetak bayangan sel setelah memperluas gaya tabel.
	// Warna pola latar belakang biru seharusnya diterapkan dari gaya tabel.
	Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading after style expansion: " + cellShadingAfter);
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara memperluas pemformatan ke sel dan baris dari gaya tabel menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah ini, Anda bisa dengan mudah menerapkan pemformatan gaya tabel ke sel dan baris tertentu di dokumen Word Anda. Aspose.Words menawarkan API yang kuat dan fleksibel untuk memanipulasi dan memformat tabel di dokumen Anda. Dengan pengetahuan ini, Anda dapat menyesuaikan lebih lanjut tata letak dan presentasi dokumen Word Anda.