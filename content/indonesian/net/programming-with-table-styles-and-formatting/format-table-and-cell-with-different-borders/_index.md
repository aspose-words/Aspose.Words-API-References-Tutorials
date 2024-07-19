---
title: Format Tabel Dan Sel Dengan Batas Berbeda
linktitle: Format Tabel Dan Sel Dengan Batas Berbeda
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk memformat tabel dan sel dengan batas berbeda menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-table-styles-and-formatting/format-table-and-cell-with-different-borders/
---

Dalam tutorial ini, kami akan memandu Anda melalui proses langkah demi langkah untuk memformat tabel dan sel dengan batas berbeda menggunakan Aspose.Words untuk .NET. Kami akan menjelaskan paket kode sumber C# dan memberi Anda panduan komprehensif untuk membantu Anda memahami dan menerapkan fitur ini dalam proyek Anda sendiri. Di akhir tutorial ini, Anda akan mengetahui cara menerapkan batas khusus ke tabel dan sel tertentu di dokumen Word Anda menggunakan Aspose.Words untuk .NET.

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
Untuk mulai membuat tabel, kami menggunakan`StartTable()` metode pembuat dokumen, lalu kita menambahkan sel ke tabel menggunakan`InsertCell()` metode dan kami menulis konten sel ke menggunakan`Writeln()` metode.

```csharp
Table table = builder. StartTable();
builder.InsertCell();
// Tetapkan batas untuk seluruh tabel.
table.SetBorders(LineStyle.Single, 2.0, Color.Black);
// Tetapkan padding untuk sel ini.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
builder.Writeln("Cell #1");
builder.InsertCell();
// Tentukan padding sel yang berbeda untuk sel kedua.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
builder.Writeln("Cell #2");
builder.EndRow();
// Hapus pemformatan sel dari operasi sebelumnya.
builder.CellFormat.ClearFormatting();
builder.InsertCell();
// Buat batas yang lebih tebal untuk sel pertama di baris ini. Ini akan berbeda
// relatif terhadap batas yang ditentukan untuk tabel.
builder.CellFormat.Borders.Left.LineWidth = 4.0;
builder.CellFormat.Borders.Right.LineWidth = 4.0;
builder.CellFormat.Borders.Top.LineWidth = 4.0;
builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
builder.Writeln("Cell #3");
builder.InsertCell();
builder.CellFormat.ClearFormatting();
builder.Writeln("Cell #4");
```

## Langkah 4: Simpan dokumen

  diubah
Terakhir simpan dokumen yang dimodifikasi ke file. Anda dapat memilih nama dan lokasi yang sesuai untuk dokumen keluaran.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

Selamat! Anda sekarang telah memformat tabel dan sel dengan batas berbeda menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber untuk Format Tabel Dan Sel Dengan Batas Berbeda menggunakan Aspose.Words untuk .NET 

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.StartTable();
builder.InsertCell();
//Tetapkan batas untuk seluruh tabel.
table.SetBorders(LineStyle.Single, 2.0, Color.Black);
// Atur bayangan sel untuk sel ini.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
builder.Writeln("Cell #1");
builder.InsertCell();
// Tentukan bayangan sel yang berbeda untuk sel kedua.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
builder.Writeln("Cell #2");
builder.EndRow();
// Hapus pemformatan sel dari operasi sebelumnya.
builder.CellFormat.ClearFormatting();
builder.InsertCell();
// Buat batas yang lebih besar untuk sel pertama baris ini. Ini akan berbeda
// dibandingkan dengan batas yang ditetapkan untuk tabel.
builder.CellFormat.Borders.Left.LineWidth = 4.0;
builder.CellFormat.Borders.Right.LineWidth = 4.0;
builder.CellFormat.Borders.Top.LineWidth = 4.0;
builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
builder.Writeln("Cell #3");
builder.InsertCell();
builder.CellFormat.ClearFormatting();
builder.Writeln("Cell #4");
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara memformat tabel dan sel dengan batas berbeda menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah ini, Anda dapat dengan mudah menyesuaikan tabel dan batas sel di dokumen Word Anda. Aspose.Words menawarkan API yang kuat dan fleksibel untuk memanipulasi dan memformat tabel di dokumen Anda. Dengan pengetahuan ini, Anda dapat meningkatkan presentasi visual dokumen Word Anda dan memenuhi kebutuhan spesifik.