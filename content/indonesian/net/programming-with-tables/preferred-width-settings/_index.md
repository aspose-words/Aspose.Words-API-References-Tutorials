---
title: Pengaturan Lebar Pilihan
linktitle: Pengaturan Lebar Pilihan
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengatur lebar sel tabel pilihan dalam dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-tables/preferred-width-settings/
---

Dalam tutorial ini, kita akan mempelajari cara menyetel pengaturan lebar pilihan untuk sel tabel di dokumen Word menggunakan Aspose.Words untuk .NET. Kami akan mengikuti panduan langkah demi langkah untuk memahami kode dan menerapkan fitur ini. Di akhir tutorial ini, Anda akan dapat menentukan lebar pilihan berbeda untuk sel tabel di dokumen Word Anda.

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

## Langkah 3: Buat tabel dengan lebar yang diinginkan
Selanjutnya, kita akan membuat tabel dengan tiga sel yang memiliki lebar pilihan berbeda. Gunakan kode berikut:

```csharp
// Awal tabel
builder. StartTable();

// Masukkan sel dengan ukuran absolut
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
builder.Writeln("Cell with a width of 40 points");

// Masukkan sel dengan ukuran relatif (dalam persentase)
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
builder.Writeln("Cell with 20% width");

// Sisipkan sel berukuran otomatis
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
builder.Writeln("Auto-size cell. The size of this cell is calculated from the preferred width of the table. In this case, the cell will fill the rest of the available space.");

// Akhir tabel
builder. EndTable();
```

Di sini kita menggunakan pembuat dokumen untuk membuat tabel dengan tiga sel. Sel pertama memiliki lebar pilihan 40 poin, sel kedua memiliki lebar pilihan 20% dari lebar tabel, dan sel ketiga memiliki lebar pilihan otomatis yang menyesuaikan

  tergantung pada ruang yang tersedia.

## Langkah 4: Menyimpan dokumen yang dimodifikasi
Terakhir, kita perlu menyimpan dokumen yang dimodifikasi dengan pengaturan lebar pilihan yang ditentukan untuk sel tabel. Gunakan kode berikut:

```csharp
doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

Pastikan untuk menentukan jalur dan nama file yang benar untuk dokumen keluaran.

### Contoh kode sumber untuk Pengaturan Lebar Pilihan menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Sisipkan baris tabel yang terdiri dari tiga sel yang memiliki lebar pilihan berbeda.
	builder.StartTable();
	// Masukkan sel berukuran absolut.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
	builder.Writeln("Cell at 40 points width");
	// Sisipkan sel berukuran relatif (persen).
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	builder.Writeln("Cell at 20% width");
	// Masukkan sel berukuran otomatis.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
	builder.Writeln(
		"Cell automatically sized. The size of this cell is calculated from the table preferred width.");
	builder.Writeln("In this case the cell will fill up the rest of the available space.");
	doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara mengatur pengaturan lebar pilihan untuk sel tabel di dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah ini dan menerapkan kode C# yang disediakan, Anda dapat menyesuaikan lebar sel tabel dengan kebutuhan spesifik di dokumen Word Anda.