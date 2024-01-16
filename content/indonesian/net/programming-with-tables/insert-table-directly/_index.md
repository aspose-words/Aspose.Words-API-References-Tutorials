---
title: Masukkan Tabel Secara Langsung
linktitle: Masukkan Tabel Secara Langsung
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyisipkan tabel langsung ke dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-tables/insert-table-directly/
---

Dalam tutorial ini, kita akan mempelajari cara menyisipkan tabel secara langsung ke dalam dokumen Word menggunakan Aspose.Words untuk .NET. Kami akan mengikuti panduan langkah demi langkah untuk memahami kode dan menerapkan fitur ini. Di akhir tutorial ini, Anda akan dapat menyisipkan tabel langsung ke dokumen Word Anda secara terprogram.

## Langkah 1: Pengaturan Proyek
1. Luncurkan Visual Studio dan buat proyek C# baru.
2. Tambahkan referensi ke perpustakaan Aspose.Words untuk .NET.

## Langkah 2: Membuat Dokumen dan Tabel
Untuk memulai Pemrosesan Kata dengan array, kita perlu membuat dokumen baru dan menginisialisasi array. Ikuti langkah ini:

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Pembuatan dokumen
Document doc = new Document();

//Buat susunannya
Table table = new Table(doc);
doc.FirstSection.Body.AppendChild(table);
```

Pastikan untuk mengganti "DIREKTORI DOKUMEN ANDA" dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 3: Membangun array
Selanjutnya, kita akan membuat tabel dengan menambahkan baris dan sel. Gunakan kode berikut sebagai contoh:

```csharp
// Buat baris pertama
Row row = new Row(doc);
row.RowFormat.AllowBreakAcrossPages = true;
table.AppendChild(row);

// Buat sel pertama
Cell cell = new Cell(doc);
cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
cell.CellFormat.Width = 80;
cell.AppendChild(new Paragraph(doc));
cell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 1"));
row.AppendChild(cell);

// Gandakan sel untuk sel kedua di baris
row.AppendChild(cell.Clone(false));
row.LastCell.AppendChild(new Paragraph(doc));
row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 2"));
```

 Di sini kita membuat baris dengan`AllowBreakAcrossPages` properti disetel ke`true` untuk memungkinkan pemisahan halaman antar baris. Kami kemudian membuat sel dengan latar belakang berwarna, lebar tetap, dan konten teks tertentu. Kami kemudian menduplikasi sel ini untuk membuat sel kedua di baris.

## Langkah 4: Tabel Pas Otomatis
Kita dapat menerapkan penyesuaian otomatis pada tabel untuk memformatnya dengan benar. Gunakan kode berikut:

```csharp
table. AutoFit(AutoFitBehavior.FixedColumnWidths);
```

Baris kode ini menerapkan penyesuaian otomatis berdasarkan lebar kolom tetap.

## Langkah 5: Mendaftarkan

  dokumen yang dimodifikasi
Terakhir, kita perlu menyimpan dokumen yang dimodifikasi dengan tabel yang disisipkan secara langsung. Gunakan kode berikut:

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

Pastikan untuk menentukan jalur dan nama file yang benar untuk dokumen keluaran.

### Contoh kode sumber untuk Sisipkan Tabel Secara Langsung menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	// Kita mulai dengan membuat objek tabel. Perhatikan bahwa kita harus meneruskan objek dokumen
	//ke konstruktor setiap node. Hal ini karena setiap node yang kita buat harus dimiliki
	// ke beberapa dokumen.
	Table table = new Table(doc);
	doc.FirstSection.Body.AppendChild(table);
	// Di sini kita dapat memanggil PastikanMinimum untuk membuat baris dan sel untuk kita. Metode ini digunakan
	// untuk memastikan bahwa node yang ditentukan valid. Dalam hal ini, tabel yang valid harus memiliki setidaknya satu Baris dan satu sel.
	// Sebagai gantinya, kita akan menangani sendiri pembuatan baris dan tabelnya.
	// Ini akan menjadi cara terbaik untuk melakukan ini jika kita membuat tabel di dalam suatu algoritma.
	Row row = new Row(doc);
	row.RowFormat.AllowBreakAcrossPages = true;
	table.AppendChild(row);
	// Kami sekarang dapat menerapkan pengaturan penyesuaian otomatis apa pun.
	table.AutoFit(AutoFitBehavior.FixedColumnWidths);
	Cell cell = new Cell(doc);
	cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	cell.CellFormat.Width = 80;
	cell.AppendChild(new Paragraph(doc));
	cell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 1 Text"));
	row.AppendChild(cell);
	// Kami kemudian akan mengulangi proses untuk sel dan baris lain dalam tabel.
	// Kita juga dapat mempercepatnya dengan mengkloning sel dan baris yang ada.
	row.AppendChild(cell.Clone(false));
	row.LastCell.AppendChild(new Paragraph(doc));
	row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 2 Text"));
	doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara menyisipkan tabel secara langsung ke dalam dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah ini dan menerapkan kode C# yang disediakan, Anda dapat menyisipkan tabel langsung ke dokumen Word Anda secara terprogram. Fitur ini memungkinkan Anda membuat dan menyesuaikan tabel sesuai dengan kebutuhan spesifik Anda.