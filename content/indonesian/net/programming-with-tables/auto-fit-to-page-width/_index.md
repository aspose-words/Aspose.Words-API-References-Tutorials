---
title: Pas Otomatis Dengan Lebar Halaman
linktitle: Pas Otomatis Dengan Lebar Halaman
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyesuaikan tabel secara otomatis dengan lebar halaman di dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-tables/auto-fit-to-page-width/
---

Dalam tutorial ini, kita akan mempelajari cara menggunakan Aspose.Words untuk .NET untuk menyesuaikan tabel secara otomatis dengan lebar halaman di dokumen Word. Kami akan mengikuti panduan langkah demi langkah untuk memahami kode dan menerapkan fitur ini. Di akhir tutorial ini, Anda akan mampu memanipulasi tabel di dokumen Word secara terprogram.

## Langkah 1: Pengaturan Proyek
1. Luncurkan Visual Studio dan buat proyek C# baru.
2. Tambahkan referensi ke perpustakaan Aspose.Words untuk .NET.

## Langkah 2: Membuat dan Mengonfigurasi Dokumen
Untuk memulai Pemrosesan Kata dengan tabel, kita perlu membuat dokumen dan mengkonfigurasi pembuat dokumen. Ikuti langkah ini:

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Buat dokumen dan pembuat dokumen
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Pastikan untuk mengganti "DIREKTORI DOKUMEN ANDA" dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 3: Memasukkan dan Mengonfigurasi Tabel
Selanjutnya, kita akan menyisipkan tabel ke dalam dokumen dengan lebar yang memakan setengah lebar halaman. Gunakan kode berikut:

```csharp
// Masukkan tabel dan konfigurasikan lebarnya
Table table = builder. StartTable();
builder. InsertCell();
table. PreferredWidth = PreferredWidth. FromPercent(50);
builder.Writeln("Cell #1");
builder. InsertCell();
builder.Writeln("Cell #2");
builder. InsertCell();
builder.Writeln("Cell #3");
```

Di sini kita menggunakan pembuat dokumen untuk mulai membuat tabel, menyisipkan sel, dan mengatur lebar tabel yang diinginkan menjadi 50% dari lebar halaman. Kemudian kami menambahkan teks di setiap sel.

## Langkah 4: Menyimpan dokumen yang dimodifikasi
Terakhir, kita perlu menyimpan dokumen yang telah dimodifikasi dengan tabel yang disesuaikan dengan lebar halaman. Gunakan kode berikut:

```csharp
// Simpan dokumen yang diubah
doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

Pastikan untuk menentukan jalur dan nama file yang benar untuk dokumen keluaran.
  
### Contoh kode sumber untuk Pas Otomatis Ke Lebar Halaman menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Sisipkan tabel dengan lebar setengah lebar halaman.
	Table table = builder.StartTable();
	builder.InsertCell();
	table.PreferredWidth = PreferredWidth.FromPercent(50);
	builder.Writeln("Cell #1");
	builder.InsertCell();
	builder.Writeln("Cell #2");
	builder.InsertCell();
	builder.Writeln("Cell #3");
	doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara menyesuaikan tabel secara otomatis dengan lebar halaman di dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah ini dan menerapkan kode C# yang disediakan, Anda dapat memanipulasi tabel di dokumen Word Anda secara terprogram. Fitur ini memungkinkan Anda menyesuaikan lebar tabel secara dinamis sesuai halaman, sehingga menawarkan dokumen yang profesional dan menarik secara visual.