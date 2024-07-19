---
title: Dapatkan Jarak Antar Teks di Sekitar Tabel
linktitle: Dapatkan Jarak Antar Teks di Sekitar Tabel
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk mendapatkan jarak antara teks dan tabel di dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-table-styles-and-formatting/get-distance-between-table-surrounding-text/
---

Dalam tutorial ini, kami akan memandu Anda melalui proses langkah demi langkah untuk mendapatkan jarak antara teks di sekitarnya dalam tabel menggunakan Aspose.Words untuk .NET. Kami akan menjelaskan paket kode sumber C# dan memberi Anda panduan komprehensif untuk membantu Anda memahami dan menerapkan fitur ini dalam proyek Anda sendiri. Di akhir tutorial ini, Anda akan mengetahui cara mengakses berbagai jarak antara tabel dan teks di sekitarnya dalam dokumen Word Anda menggunakan Aspose.Words untuk .NET.

## Langkah 1: Tentukan direktori dokumen
Pertama, Anda perlu menyetel jalur ke direktori dokumen Anda. Di sinilah dokumen Word Anda berada. Ganti "DIREKTORI DOKUMEN ANDA" dengan jalur yang sesuai.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Muat dokumen yang ada
 Selanjutnya, Anda perlu memuat dokumen Word yang ada ke dalam instance`Document` kelas.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Langkah 3: Dapatkan jarak antara tabel dan teks di sekitarnya
 Untuk mendapatkan jarak antara tabel dan teks di sekitarnya, kita perlu mengakses tabel di dokumen menggunakan`GetChild()` metode dan`NodeType.Table` Properti. Kami kemudian dapat menampilkan jarak yang berbeda menggunakan properti array`DistanceTop`, `DistanceBottom`, `DistanceRight`Dan`DistanceLeft`.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Console.WriteLine("Distance between table and top text: " + table.DistanceTop);
Console.WriteLine("Distance between table and bottom text: " + table.DistanceBottom);
Console.WriteLine("Distance between the table and the text on the right: " + table.DistanceRight);
Console.WriteLine("Distance between the table and the text on the left: " + table.DistanceLeft);
```

### Contoh kode sumber untuk Mendapatkan Jarak Antar Teks di Sekitar Tabel menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Console.WriteLine("\nGet distance between table left, right, bottom, top and the surrounding text.");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Console.WriteLine(table.DistanceTop);
	Console.WriteLine(table.DistanceBottom);
	Console.WriteLine(table.DistanceRight);
	Console.WriteLine(table.DistanceLeft);
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara mendapatkan jarak antara teks di sekitarnya dalam tabel menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah ini, Anda dapat dengan mudah mengakses berbagai jarak antara tabel dan teks di sekitarnya dalam dokumen Word Anda. Aspose.Words menawarkan API yang kuat dan fleksibel untuk memanipulasi dan memformat tabel di dokumen Anda. Dengan pengetahuan ini, Anda dapat menganalisis tata letak tabel Anda sehubungan dengan teks dan memenuhi kebutuhan spesifik.