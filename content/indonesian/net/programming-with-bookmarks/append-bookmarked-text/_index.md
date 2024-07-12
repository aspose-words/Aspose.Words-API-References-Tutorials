---
title: Tambahkan Teks yang Ditandai Dalam Dokumen Word
linktitle: Tambahkan Teks yang Ditandai Dalam Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menambahkan teks yang ditandai di dokumen Word menggunakan Aspose.Words untuk .NET dengan panduan langkah demi langkah ini. Sempurna untuk pengembang.
type: docs
weight: 10
url: /id/net/programming-with-bookmarks/append-bookmarked-text/
---
## Perkenalan

Hai! Pernah mencoba menambahkan teks dari bagian yang diberi bookmark di dokumen Word dan ternyata rumit? Anda beruntung! Tutorial ini akan memandu Anda melalui proses menggunakan Aspose.Words untuk .NET. Kami akan membaginya menjadi beberapa langkah sederhana sehingga Anda dapat mengikutinya dengan mudah. Mari selami dan tambahkan teks yang diberi bookmark seperti seorang profesional!

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki semua yang Anda butuhkan:

-  Aspose.Words untuk .NET: Pastikan Anda telah menginstalnya. Jika tidak, Anda bisa[Unduh di sini](https://releases.aspose.com/words/net/).
- Lingkungan Pengembangan: Lingkungan pengembangan .NET apa pun seperti Visual Studio.
- Pengetahuan Dasar C#: Memahami konsep dasar pemrograman C# akan membantu.
- Dokumen Word dengan Bookmark: Dokumen Word dengan bookmark yang diatur, yang akan kita gunakan untuk menambahkan teks.

## Impor Namespace

Hal pertama yang pertama, mari impor namespace yang diperlukan. Ini akan memastikan kita memiliki semua alat yang kita butuhkan di ujung jari kita.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Importing;
```

Mari kita pecahkan contoh ini menjadi langkah-langkah mendetail.

## Langkah 1: Muat Dokumen dan Inisialisasi Variabel

Baiklah, mari kita mulai dengan memuat dokumen Word kita dan menginisialisasi variabel yang kita perlukan.

```csharp
// Muat dokumen sumber dan tujuan.
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");

// Inisialisasi pengimpor dokumen.
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

// Temukan bookmark di dokumen sumber.
Bookmark srcBookmark = srcDoc.Range.Bookmarks["YourBookmarkName"];
```

## Langkah 2: Identifikasi Paragraf Awal dan Akhir

Sekarang, mari cari paragraf di mana penanda dimulai dan diakhiri. Hal ini penting karena kita perlu menangani teks dalam batas-batas ini.

```csharp
// Ini adalah paragraf yang berisi awal penanda.
Paragraph startPara = (Paragraph)srcBookmark.BookmarkStart.ParentNode;

// Ini adalah paragraf yang berisi akhir dari bookmark.
Paragraph endPara = (Paragraph)srcBookmark.BookmarkEnd.ParentNode;

if (startPara == null || endPara == null)
    throw new InvalidOperationException("Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");
```

## Langkah 3: Validasi Paragraf Orang Tua

Kita perlu memastikan paragraf awal dan akhir memiliki induk yang sama. Ini adalah skenario sederhana untuk menjaga segala sesuatunya tetap sederhana.

```csharp
// Batasi diri kita pada skenario yang cukup sederhana.
if (startPara.ParentNode != endPara.ParentNode)
    throw new InvalidOperationException("Start and end paragraphs have different parents, cannot handle this scenario yet.");
```

## Langkah 4: Identifikasi Node yang Akan Dihentikan

Selanjutnya, kita perlu menentukan node dimana kita akan berhenti menyalin teks. Ini akan menjadi simpul tepat setelah paragraf akhir.

```csharp
// Kami ingin menyalin semua paragraf dari paragraf awal hingga (dan termasuk) paragraf akhir,
// oleh karena itu simpul tempat kita berhenti adalah satu setelah paragraf akhir.
Node endNode = endPara.NextSibling;
```

## Langkah 5: Tambahkan Teks yang Ditandai ke Dokumen Tujuan

Terakhir, mari kita ulangi node dari paragraf awal ke node setelah paragraf akhir, dan menambahkannya ke dokumen tujuan.

```csharp
for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
{
    // Ini membuat salinan node saat ini dan mengimpornya (membuatnya valid) dalam konteksnya
    // dari dokumen tujuan. Mengimpor berarti menyesuaikan gaya dan pengidentifikasi daftar dengan benar.
    Node newNode = importer.ImportNode(curNode, true);

    // Tambahkan node yang diimpor ke dokumen tujuan.
    dstDoc.FirstSection.Body.AppendChild(newNode);
}

// Simpan dokumen tujuan dengan teks yang ditambahkan.
dstDoc.Save("appended_document.docx");
```

## Kesimpulan

Dan itu dia! Anda telah berhasil menambahkan teks dari bagian yang ditandai di dokumen Word menggunakan Aspose.Words untuk .NET. Alat canggih ini membuat manipulasi dokumen menjadi mudah, dan sekarang Anda memiliki satu trik lagi. Selamat membuat kode!

## FAQ

### Bisakah saya menambahkan teks dari beberapa bookmark sekaligus?
Ya, Anda dapat mengulangi proses untuk setiap bookmark dan menambahkan teks yang sesuai.

### Bagaimana jika paragraf awal dan akhir memiliki orang tua yang berbeda?
Contoh saat ini mengasumsikan mereka memiliki orang tua yang sama. Bagi orang tua yang berbeda-beda, diperlukan penanganan yang lebih kompleks.

### Bisakah saya mempertahankan format asli teks yang ditambahkan?
 Sangat! Itu`ImportFormatMode.KeepSourceFormatting` memastikan format asli dipertahankan.

### Apakah mungkin untuk menambahkan teks ke posisi tertentu di dokumen tujuan?
Ya, Anda dapat menambahkan teks ke posisi mana pun dengan menavigasi ke node yang diinginkan di dokumen tujuan.

### Bagaimana jika saya perlu menambahkan teks dari bookmark ke bagian baru?
Anda dapat membuat bagian baru di dokumen tujuan dan menambahkan teks di sana.