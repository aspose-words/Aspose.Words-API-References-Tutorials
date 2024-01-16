---
title: Dapatkan Posisi Meja Mengambang
linktitle: Dapatkan Posisi Meja Mengambang
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mendapatkan posisi tabel mengambang di dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-tables/get-floating-table-position/
---

Dalam tutorial ini, kita akan mempelajari cara mendapatkan posisi tabel mengambang di dokumen Word menggunakan Aspose.Words untuk .NET. Kami akan mengikuti panduan langkah demi langkah untuk memahami kode dan menerapkan fitur ini. Di akhir tutorial ini, Anda akan bisa mendapatkan properti posisi tabel mengambang di dokumen Word Anda secara terprogram.

## Langkah 1: Pengaturan Proyek
1. Luncurkan Visual Studio dan buat proyek C# baru.
2. Tambahkan referensi ke perpustakaan Aspose.Words untuk .NET.

## Langkah 2: Memuat dokumen dan mengakses tabel
Untuk memulai Pemrosesan Kata dengan tabel, kita perlu memuat dokumen yang berisi tabel tersebut dan mengaksesnya. Ikuti langkah ini:

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Muat dokumen
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

Pastikan untuk mengganti "DIREKTORI DOKUMEN ANDA" dengan jalur sebenarnya ke direktori dokumen Anda. Selain itu, pastikan dokumen tersebut berisi tabel mengambang.

## Langkah 3: Mendapatkan Properti Pemosisian Tabel Mengambang
Selanjutnya, kita akan mengulang semua tabel dalam dokumen dan mendapatkan properti pemosisian tabel mengambang. Gunakan kode berikut:

```csharp
foreach(Table table in doc.FirstSection.Body.Tables)
{
// Jika array adalah tipe mengambang, cetak properti pemosisiannya.
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.HorizontalAnchor);
Console.WriteLine(table.VerticalAnchor);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.AbsoluteVerticalDistance);
Console.WriteLine(table.AllowOverlap);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.RelativeVerticalAlignment);
Console.WriteLine("...............................");
}
}
```

 Di sini kita menggunakan a`foreach` loop untuk mengulang semua array dalam dokumen. Kami memeriksa apakah array bertipe float dengan memeriksa`TextWrapping` Properti. Jika demikian, kami mencetak properti pemosisian tabel, seperti jangkar horizontal, jangkar vertikal, jarak horizontal dan vertikal absolut, izin tumpang tindih, jarak horizontal absolut, dan relatif perataan vertikal.
 
### Contoh kode sumber untuk Mendapatkan Posisi Tabel Mengambang menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	foreach (Table table in doc.FirstSection.Body.Tables)
	{
		// Jika tabel bertipe mengambang, cetak properti posisinya.
		if (table.TextWrapping == TextWrapping.Around)
		{
			Console.WriteLine(table.HorizontalAnchor);
			Console.WriteLine(table.VerticalAnchor);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.AbsoluteVerticalDistance);
			Console.WriteLine(table.AllowOverlap);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.RelativeVerticalAlignment);
			Console.WriteLine("..............................");
		}
	}
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara mendapatkan posisi tabel mengambang di dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah ini dan menerapkan kode C# yang disediakan, Anda bisa mendapatkan properti pemosisian tabel mengambang di dokumen Word Anda secara terprogram. Fitur ini memungkinkan Anda menganalisis dan memanipulasi tabel mengambang sesuai dengan kebutuhan spesifik Anda.