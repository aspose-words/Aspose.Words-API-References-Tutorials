---
title: Terapkan Batas Garis Besar
linktitle: Terapkan Batas Garis Besar
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk menerapkan batas kerangka ke tabel menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-table-styles-and-formatting/apply-outline-border/
---

Dalam tutorial ini, kami akan memandu Anda melalui proses langkah demi langkah untuk menerapkan batas kerangka ke tabel menggunakan Aspose.Words untuk .NET. Kami akan menjelaskan paket kode sumber C# dan memberi Anda panduan komprehensif untuk membantu Anda memahami dan menerapkan fitur ini dalam proyek Anda sendiri. Di akhir tutorial ini, Anda akan memiliki pemahaman yang jelas tentang cara memanipulasi batas tabel di dokumen Word Anda menggunakan Aspose.Words untuk .NET.

## Langkah 1: Tentukan direktori dokumen
Pertama, Anda perlu menyetel jalur ke direktori dokumen Anda. Di sinilah dokumen Word Anda disimpan. Ganti "DIREKTORI DOKUMEN ANDA" dengan jalur yang sesuai.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Unggah dokumen
 Selanjutnya, Anda perlu memuat dokumen Word ke dalam instance`Document` kelas.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Langkah 3: Akses tabel
 Untuk menerapkan batas garis, kita perlu mengakses tabel di dokumen. Itu`Table` kelas mewakili tabel di Aspose.Words.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## Langkah 4: Sejajarkan tabel ke tengah halaman
 Sekarang kita bisa menyelaraskan tabel ke tengah halaman menggunakan`Alignment` properti tabel.

```csharp
table. Alignment = Table Alignment. Center;
```

## Langkah 5: Hapus batas tabel yang ada
Untuk memulai dengan batas garis baru, pertama-tama kita perlu menghapus semua batas yang ada dari tabel. Ini dapat dilakukan dengan menggunakan`ClearBorders()` metode.

```csharp
table. ClearBorders();
```

## Langkah 6: Tentukan batas hijau di sekeliling tabel
 Kita sekarang dapat mengatur batas hijau di sekeliling tabel menggunakan`SetBorder()` metode untuk setiap sisi meja. Dalam contoh ini, kita menggunakan border tipe "Single" dengan ketebalan 1,5 poin dan warna hijau.

```csharp
table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
```

## Langkah 7: Isi sel dengan warna latar belakang
Untuk meningkatkan presentasi visual tabel, kita bisa mengisi sel dengan warna latar belakang dasar

ide. Dalam contoh ini, kita menggunakan warna hijau muda.

```csharp
table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
```

## Langkah 8: Simpan dokumen yang dimodifikasi
Terakhir, kami menyimpan dokumen yang dimodifikasi ke sebuah file. Anda dapat memilih nama dan lokasi yang sesuai untuk dokumen keluaran.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

Selamat! Anda sekarang telah menerapkan batas kerangka ke tabel menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber untuk Menerapkan Batas Garis Besar menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Sejajarkan tabel ke tengah halaman.
	table.Alignment = TableAlignment.Center;
	//Hapus semua batas yang ada dari tabel.
	table.ClearBorders();
	// Tetapkan batas hijau di sekeliling meja tetapi tidak di dalam.
	table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
	// Isi sel dengan warna solid hijau muda.
	table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara menerapkan batas kerangka ke tabel menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah ini, Anda dapat dengan mudah mengintegrasikan fungsi ini ke dalam proyek C# Anda. Memanipulasi pemformatan tabel merupakan aspek penting dalam pemrosesan dokumen, dan Aspose.Words menawarkan API yang kuat dan fleksibel untuk mencapai hal ini. Dengan pengetahuan ini, Anda dapat meningkatkan presentasi visual dokumen Word Anda dan memenuhi persyaratan tertentu.