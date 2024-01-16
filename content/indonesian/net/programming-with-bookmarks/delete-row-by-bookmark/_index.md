---
title: Hapus Baris Berdasarkan Bookmark Di Dokumen Word
linktitle: Hapus Baris Berdasarkan Bookmark Di Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menghapus baris tabel berdasarkan bookmark tertentu di dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-bookmarks/delete-row-by-bookmark/
---

Pada artikel ini, kita akan menjelajahi kode sumber C# di atas untuk memahami cara menggunakan fungsi Hapus Baris Berdasarkan Bookmark di perpustakaan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda untuk menghapus baris tabel berdasarkan penanda tertentu di dokumen Word.

## Prasyarat

- Pengetahuan dasar bahasa C#.
- Lingkungan pengembangan .NET dengan perpustakaan Aspose.Words diinstal.

## Langkah 1: Mendapatkan bookmark

 Kami menggunakan`Bookmarks` properti rentang dokumen untuk mendapatkan bookmark spesifik yang ingin kita gunakan untuk menghapus baris tabel:

```csharp
Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];
```

## Langkah 2: Menghapus baris tabel

 Kami menggunakan`GetAncestor` metode untuk mendapatkan`Row` ketik elemen induk dari bookmark. Selanjutnya kita menggunakan`Remove` metode untuk menghapus baris tabel:

```csharp
Row row = (Row)bookmark?.BookmarkStart.GetAncestor(typeof(Row));
row?.Remove();
```

### Contoh kode sumber untuk Hapus Baris Berdasarkan Bookmark menggunakan Aspose.Words untuk .NET

Berikut ini contoh kode sumber lengkap untuk menunjukkan penghapusan baris tabel berdasarkan bookmark tertentu menggunakan Aspose.Words untuk .NET:

```csharp

	Bookmark bookmark = doc.Range.Bookmarks[bookmarkName];

	Row row = (Row) bookmark?.BookmarkStart.GetAncestor(typeof(Row));
	row?.Remove();
        
```

## Kesimpulan

Dalam artikel ini, kami telah menjelajahi kode sumber C# untuk memahami cara menggunakan fungsi Hapus Baris Berdasarkan Bookmark Aspose.Words untuk .NET. Kami mengikuti panduan langkah demi langkah untuk menghapus baris tabel berdasarkan penanda tertentu dalam dokumen.

### FAQ untuk menghapus baris demi bookmark di dokumen Word

#### T: Dapatkah saya menghapus beberapa baris menggunakan bookmark yang sama?

J: Ya, Anda dapat menghapus beberapa baris menggunakan bookmark yang sama. Namun, Anda perlu menangani logika dalam kode Anda untuk menentukan jumlah baris yang akan dihapus dan melakukan penyesuaian yang diperlukan pada cuplikan kode yang disediakan.

#### T: Apa yang terjadi jika bookmark tidak ada di dokumen?

J: Jika bookmark yang ditentukan tidak ada dalam dokumen, cuplikan kode akan mengembalikan nilai null untuk objek bookmark. Oleh karena itu, Anda perlu menangani skenario ini dalam kode Anda dengan menambahkan pemeriksaan yang sesuai sebelum mencoba menghapus baris tabel.

#### T: Apakah perpustakaan Aspose.Words gratis untuk digunakan?

 J: Perpustakaan Aspose.Words adalah perpustakaan komersial, dan Anda mungkin memerlukan lisensi yang valid untuk menggunakannya dalam proyek Anda. Anda dapat mengunjungi[Aspose.Words untuk referensi .NET API](https://reference.aspose.com/words/net/) untuk mempelajari lebih lanjut tentang opsi lisensi dan harga mereka.

#### T: Bisakah saya menghapus baris dari tabel di bagian tertentu pada dokumen Word?

J: Ya, Anda bisa menghapus baris dari tabel di bagian tertentu dokumen Word. Anda dapat mengubah cuplikan kode yang disediakan untuk menargetkan bagian tertentu dengan menggunakan rentang atau bookmark yang sesuai dalam bagian tersebut.