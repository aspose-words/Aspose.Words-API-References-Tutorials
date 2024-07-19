---
title: Tampilkan Sembunyikan Konten yang Ditandai di Dokumen Word
linktitle: Tampilkan Sembunyikan Konten yang Ditandai di Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menampilkan dan menyembunyikan konten yang ditandai di dokumen Word menggunakan Aspose.Words untuk .NET dengan panduan langkah demi langkah yang mendetail ini.
type: docs
weight: 10
url: /id/net/programming-with-bookmarks/show-hide-bookmarked-content/
---
## Perkenalan

Siap terjun ke dunia manipulasi dokumen dengan Aspose.Words untuk .NET? Baik Anda seorang pengembang yang ingin mengotomatiskan tugas dokumen atau sekadar ingin menangani file Word secara terprogram, Anda berada di tempat yang tepat. Hari ini, kita akan mempelajari cara menampilkan dan menyembunyikan konten yang ditandai di dokumen Word menggunakan Aspose.Words untuk .NET. Panduan langkah demi langkah ini akan menjadikan Anda ahli dalam mengontrol visibilitas konten berdasarkan bookmark. Mari kita mulai!

## Prasyarat

Sebelum kita masuk ke seluk beluknya, ada beberapa hal yang Anda perlukan:

1. Visual Studio: Versi apa pun yang kompatibel dengan .NET.
2.  Aspose.Words untuk .NET: Unduh[Di Sini](https://releases.aspose.com/words/net/).
3. Pemahaman Dasar C#: Jika Anda dapat menulis program sederhana "Hello World", Anda siap melakukannya.
4. Dokumen Word dengan Bookmark: Kami akan menggunakan contoh dokumen dengan bookmark untuk tutorial ini.

## Impor Namespace

Hal pertama yang pertama, mari impor namespace yang diperlukan. Ini memastikan kami memiliki semua alat yang kami perlukan untuk tugas kami.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Bookmark;
```

Dengan namespace ini, kita siap untuk memulai perjalanan kita.

## Langkah 1: Menyiapkan Proyek Anda

Baiklah, mari kita mulai dengan menyiapkan proyek kita di Visual Studio.

### Buat Proyek Baru

Buka Visual Studio dan buat proyek Aplikasi Konsol (.NET Core) baru. Beri nama sesuatu yang menarik, seperti "BookmarkVisibilityManager".

### Tambahkan Aspose.Words untuk .NET

Anda harus menambahkan Aspose.Words untuk .NET ke proyek Anda. Anda dapat melakukan ini melalui Manajer Paket NuGet.

1. Buka Alat > Manajer Paket NuGet > Kelola Paket NuGet untuk Solusi.
2. Telusuri "Aspose.Words".
3. Instal paketnya.

Besar! Sekarang proyek kita sudah siap, mari beralih ke memuat dokumen kita.

## Langkah 2: Memuat Dokumen

Kita perlu memuat dokumen Word yang berisi bookmark. Untuk tutorial ini, kita akan menggunakan contoh dokumen bernama "Bookmarks.docx".

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

 Cuplikan kode ini menetapkan jalur ke direktori dokumen Anda dan memuat dokumen ke dalam`doc` obyek.

## Langkah 3: Tampilkan/Sembunyikan Konten yang Ditandai

Sekarang sampai pada bagian yang menyenangkan – menampilkan atau menyembunyikan konten berdasarkan bookmark. Kami akan membuat metode yang disebut`ShowHideBookmarkedContent` untuk menangani ini.

Berikut metode yang akan mengubah visibilitas konten yang di-bookmark:

```csharp
public void ShowHideBookmarkedContent(Document doc, string bookmarkName, bool isHidden)
{
    Bookmark bm = doc.Range.Bookmarks[bookmarkName];

    Node currentNode = bm.BookmarkStart;
    while (currentNode != null && currentNode.NodeType != NodeType.BookmarkEnd)
    {
        if (currentNode.NodeType == NodeType.Run)
        {
            Run run = currentNode as Run;
            run.Font.Hidden = isHidden;
        }
        currentNode = currentNode.NextSibling;
    }
}
```

### Rincian Metode

-  Pengambilan Bookmark:`Bookmark bm = doc.Range.Bookmarks[bookmarkName];` mengambil bookmark.
- Node Traversal: Kami melintasi node di dalam bookmark.
-  Pengalih Visibilitas: Jika simpulnya adalah a`Run` (rangkaian teks yang berdekatan), kami mengaturnya`Hidden` Properti.

## Langkah 4: Menerapkan Metode

Dengan metode kami, mari terapkan untuk menampilkan atau menyembunyikan konten berdasarkan bookmark.

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", true);
```

Baris kode ini akan menyembunyikan konten di dalam bookmark bernama "MyBookmark1".

## Langkah 5: Menyimpan Dokumen

Terakhir, mari simpan dokumen kita yang telah dimodifikasi.

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

Ini menyimpan dokumen dengan perubahan yang kami buat.

## Kesimpulan

Dan itu dia! Anda baru saja mempelajari cara menampilkan dan menyembunyikan konten yang ditandai di dokumen Word menggunakan Aspose.Words untuk .NET. Alat canggih ini memudahkan manipulasi dokumen, baik Anda mengotomatiskan laporan, membuat templat, atau sekadar mengutak-atik file Word. Selamat membuat kode!

## FAQ

### Bisakah saya mengganti beberapa bookmark sekaligus?
 Ya, Anda dapat menghubungi`ShowHideBookmarkedContent` metode untuk setiap bookmark yang ingin Anda alihkan.

### Apakah menyembunyikan konten memengaruhi struktur dokumen?
Tidak, menyembunyikan konten hanya memengaruhi visibilitasnya. Kontennya tetap ada di dokumen.

### Bisakah saya menggunakan metode ini untuk jenis konten lainnya?
Metode ini secara khusus mengubah proses teks. Untuk tipe konten lainnya, Anda harus mengubah logika traversal simpul.

### Apakah Aspose.Words untuk .NET gratis?
 Aspose.Words menawarkan uji coba gratis[Di Sini](https://releases.aspose.com/) , tetapi lisensi penuh diperlukan untuk penggunaan produksi. Anda dapat membelinya[Di Sini](https://purchase.aspose.com/buy).

### Bagaimana saya bisa mendapatkan dukungan jika saya mengalami masalah?
 Anda bisa mendapatkan dukungan dari komunitas Aspose[Di Sini](https://forum.aspose.com/c/words/8).