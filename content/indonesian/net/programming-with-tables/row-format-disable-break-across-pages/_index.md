---
title: Format Baris Nonaktifkan Pemisahan Lintas Halaman
linktitle: Format Baris Nonaktifkan Pemisahan Lintas Halaman
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menonaktifkan jeda baris untuk tabel di beberapa halaman dalam dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-tables/row-format-disable-break-across-pages/
---

Dalam tutorial ini, kita akan mempelajari cara menonaktifkan jeda baris tabel multi-halaman di dokumen Word menggunakan Aspose.Words untuk .NET. Kami akan mengikuti panduan langkah demi langkah untuk memahami kode dan menerapkan fitur ini. Di akhir tutorial ini, Anda akan dapat menonaktifkan pemutusan baris untuk semua baris tabel di dokumen Word Anda.

## Langkah 1: Pengaturan Proyek
1. Luncurkan Visual Studio dan buat proyek C# baru.
2. Tambahkan referensi ke perpustakaan Aspose.Words untuk .NET.

## Langkah 2: Memuat dokumen
Untuk memulai Pemrosesan Kata dengan dokumen, ikuti langkah-langkah berikut:

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Muat dokumen
Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

Pastikan untuk mengganti "DIREKTORI DOKUMEN ANDA" dengan jalur sebenarnya ke direktori dokumen Anda dan berikan nama file yang benar.

## Langkah 3: Nonaktifkan pemutusan baris tabel
Selanjutnya, kita akan menonaktifkan pemutusan baris untuk semua baris dalam tabel. Gunakan kode berikut:

```csharp
// Ambil mejanya
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// Nonaktifkan jeda baris untuk semua baris dalam tabel
foreach(Row row in table.Rows)
row.RowFormat.AllowBreakAcrossPages = false;
```

 Di sini kita menggunakan dokumen untuk mengambil tabel pertama dan kemudian mengulangi semua baris dalam tabel menggunakan loop foreach. Di dalam loop, kami menonaktifkan pemutusan baris untuk setiap baris dengan mengatur`RowFormat.AllowBreakAcrossPages`properti ke`false`.

## Langkah 4: Menyimpan dokumen yang dimodifikasi
Terakhir, kita perlu menyimpan dokumen yang dimodifikasi dengan pemisah baris tabel dinonaktifkan. Gunakan kode berikut:

```csharp
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

Pastikan untuk menentukan jalur dan nama file yang benar untuk dokumen keluaran.

### Contoh kode sumber untuk Format Baris Nonaktifkan Pemisahan Halaman menggunakan Aspose.Words untuk .NET 

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table spanning two pages.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
// Nonaktifkan pembagian halaman untuk semua baris dalam tabel.
foreach (Row row in table.Rows)
	row.RowFormat.AllowBreakAcrossPages = false;
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara menonaktifkan jeda baris tabel multi-halaman di dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah ini dan menerapkan kode C# yang disediakan, Anda dapat menerapkan penonaktifan ini ke tabel di dokumen Word Anda.