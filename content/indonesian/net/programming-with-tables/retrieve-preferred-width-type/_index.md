---
title: Ambil Jenis Lebar Pilihan
linktitle: Ambil Jenis Lebar Pilihan
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengambil jenis dan nilai lebar sel yang diinginkan dalam tabel Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-tables/retrieve-preferred-width-type/
---

Dalam tutorial ini, kita akan mempelajari cara mengambil tipe lebar pilihan dan nilainya dari sel tabel di dokumen Word menggunakan Aspose.Words untuk .NET. Kami akan mengikuti panduan langkah demi langkah untuk memahami kode dan menerapkan fitur ini. Di akhir tutorial ini, Anda akan dapat mengambil tipe lebar pilihan (mutlak, relatif, atau otomatis) dan nilainya untuk sel tertentu di tabel dokumen Word Anda.

## Langkah 1: Pengaturan Proyek
1. Luncurkan Visual Studio dan buat proyek C# baru.
2. Tambahkan referensi ke perpustakaan Aspose.Words untuk .NET.

## Langkah 2: Memuat dokumen
Untuk memulai Pemrosesan Kata dengan dokumen, ikuti langkah-langkah berikut:

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Muat dokumen
Document doc = new Document(dataDir + "Tables.docx");
```

Pastikan untuk mengganti "DIREKTORI DOKUMEN ANDA" dengan jalur sebenarnya ke direktori dokumen Anda dan berikan nama file yang benar.

## Langkah 3: Mengambil jenis dan nilai lebar yang diinginkan
Selanjutnya, kita akan mengambil tipe lebar pilihan dan nilainya untuk sel tabel tertentu. Gunakan kode berikut:

```csharp
// Ambil mejanya
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// Aktifkan penyesuaian tabel otomatis
table. AllowAutoFit = true;

//Ambil sel pertama dari baris pertama
Cell firstCell = table.FirstRow.FirstCell;

// Ambil jenis lebar yang diinginkan dan nilainya
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

 Di sini kita menggunakan dokumen untuk mengambil tabel pertama, lalu kita mengaktifkan penyesuaian tabel otomatis dengan`AllowAutoFit` Properti. Lalu kita mengambil sel pertama dari baris pertama tabel. Dari sel ini, kita dapat mengambil tipe lebar yang diinginkan dengan`PreferredWidth.Type` properti dan nilainya dengan`PreferredWidth.Value` Properti.

### Contoh kode sumber untuk Mengambil Jenis Lebar Pilihan menggunakan Aspose.Words untuk .NET 

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
table.AllowAutoFit = true;
Cell firstCell = table.FirstRow.FirstCell;
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara mengambil tipe lebar pilihan dan nilainya dari sel tabel di dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah ini dan menerapkan kode C# yang disediakan, Anda bisa mengambil informasi ini untuk sel tertentu di tabel dokumen Word Anda.