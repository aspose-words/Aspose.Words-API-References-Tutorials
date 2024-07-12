---
title: Tabel Lengkap Klon
linktitle: Tabel Lengkap Klon
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengkloning seluruh tabel ke dalam dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-tables/clone-complete-table/
---

Dalam tutorial ini, kita akan mempelajari cara menggunakan Aspose.Words untuk .NET untuk mengkloning seluruh tabel ke dalam dokumen Word. Kami akan mengikuti panduan langkah demi langkah untuk memahami kode dan menerapkan fitur ini. Di akhir tutorial ini, Anda akan dapat mengkloning tabel ke dalam dokumen Word Anda secara terprogram.

## Langkah 1: Pengaturan Proyek
1. Luncurkan Visual Studio dan buat proyek C# baru.
2. Tambahkan referensi ke perpustakaan Aspose.Words untuk .NET.

## Langkah 2: Memuat dokumen dan mengakses tabel
Untuk memulai Pemrosesan Kata dengan tabel, kita perlu memuat dokumen yang memuatnya dan mengaksesnya. Ikuti langkah ini:

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Muat dokumen
Document doc = new Document(dataDir + "Tables.docx");

// Akses ke array
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Pastikan untuk mengganti "DIREKTORI DOKUMEN ANDA" dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 3: Klon Array Penuh
Selanjutnya, kita akan mengkloning seluruh tabel dan memasukkannya ke dalam dokumen setelah aslinya. Gunakan kode berikut:

```csharp
// Kloning arraynya
Table tableClone = (Table)table.Clone(true);

//Masukkan tabel yang dikloning ke dalam dokumen setelah aslinya
table.ParentNode.InsertAfter(tableClone, table);

// Sisipkan paragraf kosong di antara kedua tabel
// Kalau tidak, mereka akan digabungkan menjadi satu saat disimpan (ini karena validasi dokumen)
table.ParentNode.InsertAfter(new Paragraph(doc), table);
```

 Di sini kami menggunakan`Clone` metode untuk membuat salinan lengkap array. Lalu kita gunakan`InsertAfter` untuk menyisipkan tabel kloning ke dalam dokumen, setelah tabel asli. Kami juga menambahkan paragraf kosong di antara kedua tabel untuk mencegah penggabungannya saat menyimpan.

## Langkah 4: Menyimpan dokumen yang dimodifikasi
Terakhir, kita perlu menyimpan dokumen yang dimodifikasi dengan tabel yang dikloning. Gunakan kode berikut:

```csharp
// Simpan dokumen yang diubah
doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

Pastikan untuk menentukan jalur dan nama file yang benar untuk dokumen keluaran.
  
### Contoh kode sumber untuk Clone Complete Table menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Kloning tabel dan masukkan ke dalam dokumen setelah aslinya.
	Table tableClone = (Table) table.Clone(true);
	table.ParentNode.InsertAfter(tableClone, table);
	// Sisipkan paragraf kosong di antara dua tabel,
	// atau mereka akan digabungkan menjadi satu setelah disimpan, ini ada hubungannya dengan validasi dokumen.
	table.ParentNode.InsertAfter(new Paragraph(doc), table);
	doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara mengkloning seluruh tabel ke dalam dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah ini dan menerapkan kode C# yang disediakan, Anda dapat mengkloning tabel di dokumen Word Anda secara terprogram. Fitur ini memungkinkan Anda melakukan manipulasi tingkat lanjut pada array untuk memenuhi kebutuhan spesifik Anda.