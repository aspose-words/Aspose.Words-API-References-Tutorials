---
title: Menguraikan Kekusutan Dalam Dokumen Word
linktitle: Menguraikan Kekusutan Dalam Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menguraikan penanda bertumpuk dokumen Word di baris tabel yang berdekatan menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-bookmarks/untangle/
---

Pada artikel ini, kita akan menjelajahi kode sumber C# di atas untuk memahami cara menggunakan fungsi Untangle di pustaka Aspose.Words untuk .NET. Fungsi ini menguraikan bookmark bersarang yang berada di baris tabel yang berdekatan.

## Prasyarat

- Pengetahuan dasar bahasa C#.
- Lingkungan pengembangan .NET dengan perpustakaan Aspose.Words diinstal.

## Langkah 1: Telusuri Penanda Dokumen

Kami menggunakan perulangan foreach untuk menelusuri semua bookmark yang ada di dokumen:

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     // Kode untuk menangani bookmark di sini
}
```

## Langkah 2: Dapatkan baris induk dari bookmark

 Kami menggunakan`GetAncestor` metode untuk mengambil baris induk dari node awal dan akhir bookmark:

```csharp
Row row1 = (Row)bookmark.BookmarkStart.GetAncestor(typeof(Row));
Row row2 = (Row)bookmark.BookmarkEnd.GetAncestor(typeof(Row));
```

## Langkah 3: Menguraikan Bookmark Bersarang

Jika kedua baris induk ditemukan dan penanda dimulai dan diakhiri pada baris yang berdekatan, kita pindahkan simpul akhir penanda ke akhir paragraf terakhir sel terakhir di baris atas:

```csharp
if (row1 != null && row2 != null && row1.NextSibling == row2)
     row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
```

### Contoh kode sumber untuk Untangle menggunakan Aspose.Words untuk .NET

Berikut adalah contoh kode sumber lengkap untuk menguraikan bookmark bersarang menggunakan Aspose.Words untuk .NET:

```csharp

	foreach (Bookmark bookmark in doc.Range.Bookmarks)
	{
		// Dapatkan baris induk dari node akhir bookmark dan bookmark.
		Row row1 = (Row) bookmark.BookmarkStart.GetAncestor(typeof(Row));
		Row row2 = (Row) bookmark.BookmarkEnd.GetAncestor(typeof(Row));

		// Jika kedua baris ditemukan baik-baik saja, dan awal dan akhir penanda berada di baris yang berdekatan,
		// pindahkan simpul akhir penanda ke akhir paragraf terakhir di sel terakhir baris atas.
		if (row1 != null && row2 != null && row1.NextSibling == row2)
			row1.LastCell.LastParagraph.AppendChild(bookmark.BookmarkEnd);
	}

```

## Kesimpulan

Dalam artikel ini, kami menjelajahi kode sumber C# untuk memahami cara menggunakan fungsi Untangle Aspose.Words untuk .NET. Kami telah mengikuti panduan langkah demi langkah untuk menguraikan bookmark yang bersarang di baris tabel yang berdekatan.

### FAQ

#### T: Apakah fungsi Untangle hanya berfungsi dengan penanda bertumpuk di baris tabel yang berdekatan?

A: Ya, fitur Untangle dirancang khusus untuk menguraikan bookmark bersarang yang ada di baris tabel yang berdekatan. Jika penanda tidak berada pada baris yang berdekatan, fungsi ini tidak akan berlaku.

#### T: Bagaimana cara mengidentifikasi penanda bertumpuk di dokumen Word saya?

J: Anda dapat mengidentifikasi penanda bertumpuk dengan menelusuri penanda di dokumen dan memeriksa apakah penanda awal dan penanda akhir berada di baris tabel yang berdekatan. Anda dapat menggunakan kode sumber yang disediakan dalam artikel ini sebagai titik awal untuk mengimplementasikan fungsi ini.

#### T: Apakah fungsi Unscramble mengubah konten dokumen asli?

A: Ya, fungsi Untangle memodifikasi dokumen asli dengan memindahkan simpul akhir penanda ke akhir paragraf terakhir sel terakhir di baris atas. Pastikan untuk menyimpan salinan cadangan dokumen sebelum menerapkan fitur ini.

#### T: Bagaimana cara memisahkan penanda bertumpuk di jenis elemen dokumen lain, seperti bagian atau paragraf?

J: Fungsi Untangle yang disajikan dalam artikel ini dirancang khusus untuk menguraikan bookmark yang bersarang di baris tabel yang berdekatan. Jika Anda ingin menguraikan bookmark yang bersarang di elemen dokumen lain, Anda perlu menyesuaikan kodenya dan menggunakan metode yang sesuai untuk mengakses elemen yang diinginkan.

#### T: Apakah ada metode lain untuk menguraikan penanda bertumpuk di dokumen Word menggunakan Aspose.Words untuk .NET?

 J: Metode yang disajikan dalam artikel ini adalah metode umum untuk mengurai kekusutan bookmark yang bersarang di baris tabel yang berdekatan. Namun, mungkin ada pendekatan atau teknik lain tergantung pada kebutuhan spesifik proyek Anda. Anda dapat memeriksanya[Aspose.Words untuk referensi .NET API](https://reference.aspose.com/words/net/) untuk mengeksplorasi lebih jauh fitur-fitur yang tersedia.