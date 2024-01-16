---
title: Tabel Terpisah
linktitle: Tabel Terpisah
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara membagi tabel dalam dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-tables/split-table/
---

Dalam tutorial ini, kita akan mempelajari cara membagi tabel di dokumen Word menggunakan Aspose.Words untuk .NET. Kami akan mengikuti panduan langkah demi langkah untuk memahami kode dan menerapkan fitur ini. Di akhir tutorial ini, Anda akan dapat memisahkan tabel dari baris tertentu di dokumen Word Anda.

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

## Langkah 3: Membagi meja
Selanjutnya kita akan memisahkan tabel dari baris tertentu. Gunakan kode berikut:

```csharp
// Ambil tabel pertama
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);

// Penentuan garis untuk membagi tabel
Row row = firstTable.Rows[2];

// Buat wadah baru untuk tabel terpisah
Table table = (Table)firstTable.Clone(false);

// Masukkan wadah setelah tabel aslinya
firstTable.ParentNode.InsertAfter(table, firstTable);

// Tambahkan paragraf buffer untuk menjaga jarak antar tabel
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);

// Pindahkan baris dari tabel asli ke tabel terpisah
Row currentRow;
do
{
currentRow = firstTable.LastRow;
table. PrependChild(currentRow);
} while (currentRow != row);
```

Di sini kita menggunakan dokumen untuk mengambil tabel pertama dari node dokumen. Kemudian kita tentukan baris yang ingin kita bagi tabelnya, dalam contoh ini adalah baris ketiga (indeks 2). Kami kemudian membuat wadah baru dengan mengkloning tabel asli dan kemudian menyisipkannya setelah tabel asli. Kami juga menambahkan paragraf penyangga untuk menjaga jarak antara kedua tabel. Kemudian kita memindahkan baris dari tabel asli ke tabel terpisah menggunakan perulangan do- while hingga kita mencapai baris yang ditentukan.

## Langkah 4: Menyimpan dokumen yang dimodifikasi
Akhirnya, kita perlu menyelamatkannya

  dokumen dimodifikasi dengan tabel terpisah. Gunakan kode berikut:

```csharp
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

Pastikan untuk menentukan jalur dan nama file yang benar untuk dokumen keluaran.

### Contoh kode sumber untuk Split Table menggunakan Aspose.Words untuk .NET 

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
// Kami akan membagi tabel di baris ketiga (inklusif).
Row row = firstTable.Rows[2];
// Buat wadah baru untuk tabel terpisah.
Table table = (Table) firstTable.Clone(false);
// Masukkan wadah setelah aslinya.
firstTable.ParentNode.InsertAfter(table, firstTable);
// Tambahkan paragraf penyangga untuk memastikan tabel tetap terpisah.
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);
Row currentRow;
do
{
	currentRow = firstTable.LastRow;
	table.PrependChild(currentRow);
} while (currentRow != row);
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara membagi tabel dalam dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah ini dan menerapkan kode C# yang disediakan, Anda dapat dengan mudah memisahkan tabel dari baris tertentu di dokumen Word Anda.