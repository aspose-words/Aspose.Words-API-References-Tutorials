---
title: Konversikan Menjadi Sel yang Digabung Secara Horizontal
linktitle: Konversikan Menjadi Sel yang Digabung Secara Horizontal
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengonversi sel tabel menjadi sel yang digabungkan secara horizontal di dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-tables/convert-to-horizontally-merged-cells/
---

Dalam tutorial ini, kita akan mempelajari cara menggunakan Aspose.Words untuk .NET untuk mengonversi sel tabel menjadi sel yang digabungkan secara horizontal dalam dokumen Word. Kami akan mengikuti panduan langkah demi langkah untuk memahami kode dan menerapkan fitur ini. Di akhir tutorial ini, Anda akan mampu memanipulasi sel tabel di dokumen Word Anda secara terprogram.

## Langkah 1: Pengaturan Proyek
1. Luncurkan Visual Studio dan buat proyek C# baru.
2. Tambahkan referensi ke perpustakaan Aspose.Words untuk .NET.

## Langkah 2: Memuat dokumen dan mengakses tabel
Untuk memulai Pemrosesan Kata dengan tabel, kita perlu memuat dokumen yang memuatnya dan mengaksesnya. Ikuti langkah ini:

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Muat dokumen
Document doc = new Document(dataDir + "Table with merged cells.docx");

// Akses ke array
Table table = doc.FirstSection.Body.Tables[0];
```

Pastikan untuk mengganti "DIREKTORI DOKUMEN ANDA" dengan jalur sebenarnya ke direktori dokumen Anda. Selain itu, pastikan dokumen tersebut berisi tabel dengan sel yang digabungkan secara horizontal.

## Langkah 3: Konversikan ke sel yang digabungkan secara horizontal
 Selanjutnya, kita akan mengonversi sel tabel menjadi sel yang digabungkan secara horizontal menggunakan`ConvertToHorizontallyMergedCells()` metode. Gunakan kode berikut:

```csharp
// Konversikan ke sel yang digabungkan secara horizontal
table. ConvertToHorizontallyMergedCells();
```

 Di sini kita hanya memanggil`ConvertToHorizontallyMergedCells()` metode pada array untuk melakukan konversi.

### Contoh kode sumber untuk Konversi Ke Sel yang Digabung Secara Horizontal menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table with merged cells.docx");
	Table table = doc.FirstSection.Body.Tables[0];
	// Sekarang sel yang digabungkan memiliki tanda gabungan yang sesuai.
	table.ConvertToHorizontallyMergedCells();
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara mengonversi sel tabel menjadi sel yang digabungkan secara horizontal dalam dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah ini dan menerapkan kode C# yang disediakan, Anda dapat memanipulasi sel tabel di dokumen Word Anda secara terprogram. Fitur ini memungkinkan Anda mengelola dan mengatur data Anda secara fleksibel dan personal dalam sebuah tabel.