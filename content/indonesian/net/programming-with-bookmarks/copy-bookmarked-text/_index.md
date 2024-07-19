---
title: Salin Teks yang Ditandai Dalam Dokumen Word
linktitle: Salin Teks yang Ditandai Dalam Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Salin teks yang diberi bookmark dengan mudah di antara dokumen Word menggunakan Aspose.Words untuk .NET. Pelajari caranya dengan panduan langkah demi langkah ini.
type: docs
weight: 10
url: /id/net/programming-with-bookmarks/copy-bookmarked-text/
---
## Perkenalan

Pernahkah Anda merasa perlu menyalin bagian tertentu dari satu dokumen Word ke dokumen lainnya? Nah, Anda beruntung! Dalam tutorial ini, kami akan memandu Anda tentang cara menyalin teks yang diberi bookmark dari satu dokumen Word ke dokumen lainnya menggunakan Aspose.Words untuk .NET. Baik Anda membuat laporan dinamis atau mengotomatiskan pembuatan dokumen, panduan ini akan menyederhanakan prosesnya untuk Anda.

## Prasyarat

Sebelum kita mendalaminya, pastikan Anda memiliki hal berikut:

-  Aspose.Words untuk .NET Library: Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/words/net/).
- Lingkungan Pengembangan: Visual Studio atau lingkungan pengembangan .NET lainnya.
- Pengetahuan Dasar C#: Keakraban dengan pemrograman C# dan kerangka .NET.

## Impor Namespace

Untuk memulai, pastikan Anda telah mengimpor namespace yang diperlukan dalam proyek Anda:

```csharp
using Aspose.Words;
using Aspose.Words.Import;
using Aspose.Words.Bookmark;
```

## Langkah 1: Muat Dokumen Sumber

Hal pertama yang pertama, Anda perlu memuat dokumen sumber yang berisi teks yang diberi bookmark yang ingin Anda salin.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Bookmarks.docx");
```

 Di Sini,`dataDir` adalah jalur ke direktori dokumen Anda, dan`Bookmarks.docx` adalah dokumen sumber.

## Langkah 2: Identifikasi Bookmark

Selanjutnya, identifikasi bookmark yang ingin Anda salin dari dokumen sumber.

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];
```

 Mengganti`"MyBookmark1"` dengan nama sebenarnya dari bookmark Anda.

## Langkah 3: Buat Dokumen Tujuan

Sekarang, buat dokumen baru tempat teks yang ditandai akan disalin.

```csharp
Document dstDoc = new Document();
CompositeNode dstNode = dstDoc.LastSection.Body;
```

## Langkah 4: Impor Konten yang Ditandai

 Untuk memastikan gaya dan pemformatan dipertahankan, gunakan`NodeImporter` untuk mengimpor konten yang diberi bookmark dari dokumen sumber ke dokumen tujuan.

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);
AppendBookmarkedText(importer, srcBookmark, dstNode);
```

## Langkah 5: Tentukan Metode AppendBookmarkedText

Di sinilah keajaiban terjadi. Tentukan metode untuk menangani penyalinan teks yang diberi bookmark:

```csharp
private void AppendBookmarkedText(NodeImporter importer, Bookmark srcBookmark, CompositeNode dstNode)
{
    Paragraph startPara = (Paragraph)srcBookmark.BookmarkStart.ParentNode;
    Paragraph endPara = (Paragraph)srcBookmark.BookmarkEnd.ParentNode;

    if (startPara == null || endPara == null)
        throw new InvalidOperationException("Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

    if (startPara.ParentNode != endPara.ParentNode)
        throw new InvalidOperationException("Start and end paragraphs have different parents, cannot handle this scenario yet.");

    Node endNode = endPara.NextSibling;

    for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
    {
        Node newNode = importer.ImportNode(curNode, true);
        dstNode.AppendChild(newNode);
    }
}
```

## Langkah 6: Simpan Dokumen Tujuan

Terakhir, simpan dokumen tujuan untuk memverifikasi konten yang disalin.

```csharp
dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");
```

## Kesimpulan

Dan itu saja! Anda telah berhasil menyalin teks yang diberi bookmark dari satu dokumen Word ke dokumen lainnya menggunakan Aspose.Words untuk .NET. Metode ini ampuh untuk mengotomatiskan tugas manipulasi dokumen, membuat alur kerja Anda lebih efisien dan efisien.

## FAQ

### Bisakah saya menyalin beberapa bookmark sekaligus?
Ya, Anda dapat mengulangi beberapa bookmark dan menggunakan metode yang sama untuk menyalin masing-masing bookmark.

### Apa yang terjadi jika bookmark tidak ditemukan?
 Itu`Range.Bookmarks` properti akan kembali`null`, jadi pastikan Anda menangani kasus ini untuk menghindari pengecualian.

### Bisakah saya mempertahankan format bookmark asli?
 Sangat! Menggunakan`ImportFormatMode.KeepSourceFormatting` memastikan bahwa format aslinya dipertahankan.

### Apakah ada batasan ukuran teks yang di-bookmark?
Tidak ada batasan khusus, namun kinerja mungkin berbeda dengan dokumen yang sangat besar.

### Bisakah saya menyalin teks antara berbagai format dokumen Word?
Ya, Aspose.Words mendukung berbagai format Word, dan metode ini berfungsi di seluruh format ini.