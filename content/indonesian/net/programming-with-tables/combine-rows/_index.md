---
title: Gabungkan Baris
linktitle: Gabungkan Baris
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menggabungkan baris tabel dalam dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-tables/combine-rows/
---

Dalam tutorial ini, kita akan mempelajari cara menggunakan Aspose.Words for .NET untuk menggabungkan baris tabel dalam dokumen Word. Kami akan mengikuti panduan langkah demi langkah untuk memahami kode dan menerapkan fitur ini. Di akhir tutorial ini, Anda akan mampu memanipulasi dan menggabungkan baris tabel di dokumen Word Anda secara terprogram.

## Langkah 1: Pengaturan Proyek
1. Luncurkan Visual Studio dan buat proyek C# baru.
2. Tambahkan referensi ke perpustakaan Aspose.Words untuk .NET.

## Langkah 2: Memuat dokumen dan mengakses tabel
Untuk memulai Pemrosesan Kata dengan tabel, kita perlu memuat dokumen yang berisi tabel tersebut dan mengaksesnya. Ikuti langkah ini:

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Muat dokumen
Document doc = new Document(dataDir + "Tables.docx");

// Akses ke tabel
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);
Table secondTable = (Table)doc.GetChild(NodeType.Table, 1, true);
```

Pastikan untuk mengganti "DIREKTORI DOKUMEN ANDA" dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 3: Menggabungkan baris tabel
Selanjutnya kita akan menggabungkan baris-baris tabel kedua hingga akhir tabel pertama. Gunakan kode berikut:

```csharp
// Kombinasi baris tabel
while (secondTable.HasChildNodes)
     firstTable.Rows.Add(secondTable.FirstRow);
secondTable.Remove();
```

 Di sini kita menggunakan a`while` loop untuk mengulangi semua baris array kedua dan menambahkannya ke akhir array pertama menggunakan`Add` metode. Selanjutnya, kita menghapus tabel kedua dari dokumen menggunakan`Remove` metode.

## Langkah 4: Menyimpan dokumen yang dimodifikasi
Terakhir, kita perlu menyimpan dokumen yang dimodifikasi dengan baris tabel gabungan. Gunakan kode berikut:

```csharp
// Simpan dokumen yang diubah
doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

Pastikan untuk menentukan jalur dan nama file yang benar untuk dokumen keluaran.

### Contoh kode sumber untuk Menggabungkan Baris menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// Baris dari tabel kedua akan ditambahkan ke akhir tabel pertama.
	Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
	Table secondTable = (Table) doc.GetChild(NodeType.Table, 1, true);
	// Tambahkan semua baris dari tabel saat ini ke tabel berikutnya
	// dengan jumlah dan lebar sel yang berbeda dapat digabungkan menjadi satu tabel.
	while (secondTable.HasChildNodes)
		firstTable.Rows.Add(secondTable.FirstRow);
	secondTable.Remove();
	doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara menggabungkan baris tabel dalam dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah ini dan menerapkan kode C# yang disediakan, Anda dapat memanipulasi baris tabel di dokumen Word Anda secara terprogram. Fitur ini memungkinkan Anda menggabungkan dan mengatur data secara efisien ke dalam sebuah tabel.