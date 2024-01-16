---
title: Dapatkan Posisi Meja
linktitle: Dapatkan Posisi Meja
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mendapatkan posisi tabel di dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-tables/get-table-position/
---

Dalam tutorial ini, kita akan mempelajari cara mendapatkan posisi tabel di dokumen Word menggunakan Aspose.Words untuk .NET. Kami akan mengikuti panduan langkah demi langkah untuk memahami kode dan menerapkan fitur ini. Di akhir tutorial ini, Anda akan bisa mendapatkan properti pemosisian tabel di dokumen Word Anda secara terprogram.

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

Pastikan untuk mengganti "DIREKTORI DOKUMEN ANDA" dengan jalur sebenarnya ke direktori dokumen Anda. Pastikan juga dokumen tersebut berisi tabel yang posisinya ingin Anda dapatkan.

## Langkah 3: Mendapatkan Properti Pemosisian Array
Selanjutnya, kita akan memeriksa tipe pemosisian array dan mendapatkan properti pemosisian yang sesuai. Gunakan kode berikut:

```csharp
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.RelativeHorizontalAlignment);
Console.WriteLine(table.RelativeVerticalAlignment);
}
else
{
Console.WriteLine(table.Alignment);
}
```

 Di sini kita menggunakan kondisi untuk memeriksa apakah array bertipe float. Jika ya, kami mencetaknya`RelativeHorizontalAlignment` Dan`RelativeVerticalAlignment` properti untuk mendapatkan keselarasan relatif horizontal dan vertikal tabel. Jika tidak, kami mencetak`Alignment` properti untuk mendapatkan penyelarasan array.

### Contoh kode sumber untuk Mendapatkan Posisi Tabel menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	if (table.TextWrapping == TextWrapping.Around)
	{
		Console.WriteLine(table.RelativeHorizontalAlignment);
		Console.WriteLine(table.RelativeVerticalAlignment);
	}
	else
	{
		Console.WriteLine(table.Alignment);
	}
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara mendapatkan posisi tabel di dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah ini dan menerapkan kode C# yang disediakan, Anda bisa mendapatkan properti pemosisian tabel di dokumen Word Anda secara terprogram. Fitur ini memungkinkan Anda menganalisis dan memanipulasi array berdasarkan posisi spesifiknya.