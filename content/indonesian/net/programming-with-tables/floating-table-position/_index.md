---
title: Posisi Meja Mengambang
linktitle: Posisi Meja Mengambang
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara memposisikan tabel dalam posisi mengambang di dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-tables/floating-table-position/
---

Dalam tutorial ini, kita akan mempelajari cara menggunakan Aspose.Words untuk .NET untuk memposisikan tabel dalam posisi mengambang di dokumen Word. Kami akan mengikuti panduan langkah demi langkah untuk memahami kode dan menerapkan fitur ini. Di akhir tutorial ini, Anda akan dapat mengontrol posisi dan perataan tabel mengambang di dokumen Word Anda secara terprogram.

## Langkah 1: Pengaturan Proyek
1. Luncurkan Visual Studio dan buat proyek C# baru.
2. Tambahkan referensi ke perpustakaan Aspose.Words untuk .NET.

## Langkah 2: Memuat dokumen dan mengakses tabel
Untuk memulai Pemrosesan Kata dengan tabel, kita perlu memuat dokumen yang memuatnya dan mengaksesnya. Ikuti langkah ini:

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Muat dokumen
Document doc = new Document(dataDir + "Table wrapped by text.docx");

// Akses ke array
Table table = doc.FirstSection.Body.Tables[0];
```

Pastikan untuk mengganti "DIREKTORI DOKUMEN ANDA" dengan jalur sebenarnya ke direktori dokumen Anda. Pastikan juga dokumen tersebut berisi tabel yang akan diposisikan dalam posisi mengambang.

## Langkah 3: Memposisikan papan apung
Selanjutnya, kita akan memposisikan tabel dalam posisi mengambang menggunakan properti yang disediakan oleh Aspose.Words untuk .NET. Gunakan kode berikut:

```csharp
// Memposisikan meja mengambang
table. AbsoluteHorizontalDistance = 10;
table. RelativeVerticalAlignment = VerticalAlignment. Center;
```

 Di sini kita menggunakan`AbsoluteHorizontalDistance` properti untuk mengatur jarak horizontal absolut tabel dari tepi kiri halaman. Kami juga menggunakan`RelativeVerticalAlignment` properti untuk mengatur perataan vertikal relatif tabel terhadap konten di sekitarnya.

## Langkah 4: Menyimpan dokumen yang dimodifikasi
Terakhir, kita perlu menyimpan dokumen yang dimodifikasi dengan tabel diposisikan dalam posisi mengambang. Gunakan kode berikut:

```csharp
// Simpan dokumen yang diubah
doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

Pastikan untuk menentukan jalur dan nama file yang benar untuk dokumen keluaran.

### Contoh kode sumber untuk Posisi Tabel Mengambang menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	Table table = doc.FirstSection.Body.Tables[0];
	table.AbsoluteHorizontalDistance = 10;
	table.RelativeVerticalAlignment = VerticalAlignment.Center;
	doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara memposisikan tabel dalam posisi mengambang di dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah ini dan menerapkan kode C# yang disediakan, Anda dapat mengontrol posisi dan perataan tabel mengambang di dokumen Word Anda secara terprogram.