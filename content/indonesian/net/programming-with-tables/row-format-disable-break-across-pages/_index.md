---
title: Format Baris Nonaktifkan Pemisahan Lintas Halaman
linktitle: Format Baris Nonaktifkan Pemisahan Lintas Halaman
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menonaktifkan pemisah baris di seluruh halaman dalam dokumen Word menggunakan Aspose.Words untuk .NET untuk menjaga keterbacaan dan pemformatan tabel.
type: docs
weight: 10
url: /id/net/programming-with-tables/row-format-disable-break-across-pages/
---
## Perkenalan

Saat bekerja dengan tabel di dokumen Word, Anda mungkin ingin memastikan bahwa baris tidak terpecah di seluruh halaman, yang penting untuk menjaga keterbacaan dan pemformatan dokumen Anda. Aspose.Words untuk .NET menyediakan cara mudah untuk menonaktifkan hentian baris di seluruh halaman.

Dalam tutorial ini, kami akan memandu Anda melalui proses menonaktifkan jeda baris di seluruh halaman dalam dokumen Word menggunakan Aspose.Words untuk .NET.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
- Aspose.Words untuk perpustakaan .NET diinstal.
- Dokumen Word dengan tabel yang mencakup beberapa halaman.

## Impor Namespace

Pertama, impor namespace yang diperlukan dalam proyek Anda:

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

## Langkah 1: Muat Dokumen

Muat dokumen yang berisi tabel yang mencakup beberapa halaman.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

## Langkah 2: Akses Tabel

Akses tabel pertama dalam dokumen. Ini mengasumsikan bahwa tabel yang ingin Anda ubah adalah tabel pertama dalam dokumen.

```csharp
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
```

## Langkah 3: Nonaktifkan Pemecahan Halaman untuk Semua Baris

 Ulangi setiap baris dalam tabel dan atur`AllowBreakAcrossPages`properti ke`false`. Hal ini memastikan bahwa baris tidak akan terpecah di seluruh halaman.

```csharp
// Nonaktifkan pembagian halaman untuk semua baris dalam tabel.
foreach (Row row in table.Rows)
    row.RowFormat.AllowBreakAcrossPages = false;
```

## Langkah 4: Simpan Dokumen

Simpan dokumen yang dimodifikasi ke direktori yang Anda tentukan.

```csharp
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

## Kesimpulan

Dalam tutorial ini, kami mendemonstrasikan cara menonaktifkan pemisah baris di seluruh halaman dalam dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti langkah-langkah yang diuraikan di atas, Anda dapat memastikan bahwa baris tabel Anda tetap utuh dan tidak terbagi menjadi beberapa halaman, sehingga menjaga keterbacaan dan pemformatan dokumen.

## FAQ

### Bisakah saya menonaktifkan jeda baris di seluruh halaman untuk baris tertentu, bukan semua baris?  
 Ya, Anda dapat menonaktifkan hentian baris untuk baris tertentu dengan mengakses baris yang diinginkan dan mengaturnya`AllowBreakAcrossPages`properti ke`false`.

### Apakah metode ini berfungsi untuk tabel dengan sel yang digabungkan?  
 Ya, metode ini berfungsi untuk tabel dengan sel yang digabungkan. Properti`AllowBreakAcrossPages` berlaku untuk seluruh baris, terlepas dari penggabungan sel.

### Apakah metode ini akan berhasil jika tabel tersebut disarangkan di dalam tabel lain?  
Ya, Anda dapat mengakses dan mengubah tabel bertumpuk dengan cara yang sama. Pastikan Anda mereferensikan tabel bertumpuk dengan benar berdasarkan indeksnya atau properti lainnya.

### Bagaimana saya bisa memeriksa apakah suatu baris memungkinkan pemisahan halaman?  
 Anda dapat memeriksa apakah suatu baris memungkinkan pemisahan halaman dengan mengakses`AllowBreakAcrossPages` properti dari`RowFormat` dan memeriksa nilainya.

### Apakah ada cara untuk menerapkan pengaturan ini ke semua tabel dalam dokumen?  
Ya, Anda dapat mengulang semua tabel dalam dokumen dan menerapkan pengaturan ini ke masing-masing tabel.