---
title: Terapkan Pemformatan Baris
linktitle: Terapkan Pemformatan Baris
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk menerapkan pemformatan baris ke tabel menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-table-styles-and-formatting/apply-row-formatting/
---

Dalam tutorial ini, kami akan memandu Anda melalui proses langkah demi langkah untuk menerapkan pemformatan baris ke tabel menggunakan Aspose.Words untuk .NET. Kami akan menjelaskan paket kode sumber C# dan memberi Anda panduan komprehensif untuk membantu Anda memahami dan menerapkan fitur ini dalam proyek Anda sendiri. Di akhir tutorial ini, Anda akan memiliki pemahaman yang jelas tentang cara memformat baris tabel di dokumen Word Anda menggunakan Aspose.Words untuk .NET.

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

## Langkah 3: Mulai papan baru
 Untuk menerapkan pemformatan baris, pertama-tama kita harus memulai tabel baru menggunakan`StartTable()` metode pembuat dokumen.

```csharp
Table table = builder. StartTable();
```

## Langkah 4: Sisipkan sel dan buka format baris
Sekarang kita dapat menyisipkan sel ke dalam tabel dan mengakses format baris untuk sel tersebut menggunakan pembuat dokumen`InsertCell()` Dan`RowFormat` metode.

```csharp
builder. InsertCell();
RowFormat rowFormat = builder.RowFormat;
```

## Langkah 5: Atur Tinggi Baris
 Untuk mengatur tinggi baris, kami menggunakan`Height` Dan`HeightRule` properti format baris. Dalam contoh ini, kita menetapkan tinggi baris 100 poin dan menggunakan`Exactly` aturan.

```csharp
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## Langkah 6: Tentukan format tabel
 Beberapa properti pemformatan dapat diatur pada tabel itu sendiri dan diterapkan ke semua baris tabel. Dalam contoh ini, kami mengatur properti margin tabel menggunakan`LeftPadding`, `RightPadding`, `TopPadding` Dan`BottomPadding` properti.

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## Langkah 7: Tambahkan konten ke baris
Sekarang kita bisa

 Kita akan menambahkan konten ke baris menggunakan metode konstruktor dokumen. Dalam contoh ini, kami menggunakan`Writeln()` metode untuk menambahkan teks ke baris.

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## Langkah 8: Selesaikan garis dan tabelnya
 Setelah kita menambahkan konten ke baris, kita dapat mengakhiri baris tersebut menggunakan`EndRow()` metode dan kemudian akhiri tabel menggunakan`EndTable()` metode.

```csharp
builder. EndRow();
builder. EndTable();
```

## Langkah 9: Simpan dokumen yang dimodifikasi
Terakhir, kami menyimpan dokumen yang dimodifikasi ke sebuah file. Anda dapat memilih nama dan lokasi yang sesuai untuk dokumen keluaran.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

Selamat! Anda sekarang telah menerapkan pemformatan baris ke tabel menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber untuk Menerapkan Pemformatan Baris menggunakan Aspose.Words untuk .NET 

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
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara menerapkan pemformatan baris ke tabel menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah ini, Anda dapat dengan mudah mengintegrasikan fungsi ini ke dalam proyek C# Anda. Memanipulasi pemformatan baris tabel merupakan aspek penting dalam pemrosesan dokumen, dan Aspose.Words menawarkan API yang kuat dan fleksibel untuk mencapai hal ini. Dengan pengetahuan ini, Anda dapat meningkatkan presentasi visual dokumen Word Anda dan memenuhi persyaratan tertentu.