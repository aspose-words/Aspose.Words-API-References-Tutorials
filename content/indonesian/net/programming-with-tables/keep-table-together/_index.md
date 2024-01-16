---
title: Jaga Meja Bersama
linktitle: Jaga Meja Bersama
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyatukan tabel dalam dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-tables/keep-table-together/
---

Dalam tutorial ini, kita akan mempelajari cara menyatukan tabel dalam dokumen Word menggunakan Aspose.Words untuk .NET. Kami akan mengikuti panduan langkah demi langkah untuk memahami kode dan menerapkan fitur ini. Di akhir tutorial ini, Anda akan dapat menjaga tabel tetap utuh tanpa membaginya menjadi beberapa halaman di dokumen Word Anda.

## Langkah 1: Pengaturan Proyek
1. Luncurkan Visual Studio dan buat proyek C# baru.
2. Tambahkan referensi ke perpustakaan Aspose.Words untuk .NET.

## Langkah 2: Memuat dokumen dan mengambil tabel
Untuk memulai Pemrosesan Kata dengan tabel, kita perlu memuat dokumen dan mengambil tabel yang ingin kita simpan bersama. Ikuti langkah ini:

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Muat dokumen
Document doc = new Document(dataDir + "Table spanning two pages.docx");

// Ambil mejanya
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Pastikan untuk mengganti "DIREKTORI DOKUMEN ANDA" dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 3: Aktifkan opsi "KeepWithNext".
Untuk menyatukan tabel dan mencegahnya terpecah menjadi beberapa halaman, kita perlu mengaktifkan opsi "KeepWithNext" untuk setiap paragraf dalam tabel kecuali paragraf terakhir dari baris terakhir tabel. Gunakan kode berikut:

```csharp
foreach(Cell cell in table.GetChildNodes(NodeType.Cell, true))
{
cell.EnsureMinimum();
foreach(Paragraph para in cell.Paragraphs)
if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
para.ParagraphFormat.KeepWithNext = true;
}
```

Di sini kita mengulang setiap sel dalam tabel dan mengaktifkan opsi "KeepWithNext" untuk setiap paragraf dalam sel kecuali paragraf terakhir dari baris terakhir dalam tabel.

## Langkah 4: Menyimpan dokumen yang dimodifikasi
Terakhir, kita perlu menyimpan dokumen yang dimodifikasi dengan tabel yang disatukan. Gunakan kode berikut:

```csharp
doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

Pastikan untuk menentukan jalur dan nama file yang benar untuk dokumen keluaran.

### Contoh kode sumber untuk Keep Table Together menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table spanning two pages.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Kita perlu mengaktifkan KeepWithNext untuk setiap paragraf dalam tabel agar tidak terputus di satu halaman,
	// kecuali paragraf terakhir di baris terakhir tabel.
	foreach (Cell cell in table.GetChildNodes(NodeType.Cell, true))
	{
		cell.EnsureMinimum();
		foreach (Paragraph para in cell.Paragraphs)
			if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
				para.ParagraphFormat.KeepWithNext = true;
	}
	doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara menyatukan tabel dalam dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah ini dan menerapkan kode C# yang disediakan, Anda dapat menjaga tabel tetap utuh dan mencegahnya terpecah menjadi beberapa halaman di dokumen Anda. Fitur ini memberi Anda kontrol lebih besar atas tampilan dan tata letak tabel di dokumen Anda.