---
title: Tampilkan Sembunyikan Konten yang Ditandai di Dokumen Word
linktitle: Tampilkan Sembunyikan Konten yang Ditandai di Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menampilkan atau menyembunyikan konten yang ditandai secara dinamis di dokumen Word menggunakan Aspose.Words untuk .NET dengan panduan langkah demi langkah yang komprehensif ini.
type: docs
weight: 10
url: /id/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

## Perkenalan

Hai! Pernahkah Anda ingin mengontrol visibilitas konten tertentu dalam dokumen Word berdasarkan kondisi tertentu? Dengan Aspose.Words untuk .NET, Anda dapat secara dinamis menampilkan atau menyembunyikan konten yang ditandai hanya dengan beberapa baris kode. Dalam tutorial ini, saya akan memandu Anda melalui proses langkah demi langkah, memastikan Anda memahami setiap bagian kode. Pada akhirnya, Anda akan menjadi ahli dalam memanipulasi bookmark di dokumen Word. Mari kita mulai!

## Prasyarat

Sebelum kita masuk ke tutorialnya, pastikan Anda memiliki semua yang Anda butuhkan:

1. Pengetahuan Dasar C#: Anda harus terbiasa dengan sintaks dan konsep C#.
2.  Aspose.Words untuk .NET: Unduh[Di Sini](https://releases.aspose.com/words/net/) . Jika Anda belum siap untuk membeli, Anda bisa mulai dengan a[uji coba gratis](https://releases.aspose.com/).
3. Visual Studio: Versi terbaru apa pun dapat digunakan, tetapi disarankan menggunakan versi terbaru.
4. .NET Framework: Pastikan itu diinstal pada mesin Anda.

Siap untuk memulai? Besar! Mari kita mulai dengan mengimpor namespace yang diperlukan.

## Impor Namespace

Untuk menggunakan Aspose.Words untuk .NET, kita perlu mengimpor namespace yang diperlukan. Langkah ini memastikan kita memiliki akses ke semua kelas dan metode yang akan kita gunakan.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

Namespace ini sangat penting untuk bekerja dengan dokumen Word dan memanipulasi kontennya.

## Langkah 1: Menyiapkan Dokumen

Pertama, mari buat dokumen Word baru dan pembuat dokumen. Pembuat dokumen membantu kita menambahkan dan memanipulasi konten dalam dokumen dengan mudah.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Pada langkah ini, kami menginisialisasi dokumen baru dan pembuat dokumen. Hal ini menyiapkan lingkungan kami untuk operasi lebih lanjut.

## Langkah 2: Menambahkan Konten yang Ditandai

Selanjutnya, kita akan menambahkan beberapa konten ke dokumen dan membuat bookmark di sekitarnya. Bookmark ini akan membantu kami mengidentifikasi dan memanipulasi konten.

```csharp
builder.Write("This is some text before the bookmark.");
builder.StartBookmark("MyBookmark");
builder.Write("This is the bookmarked content.");
builder.EndBookmark("MyBookmark");
builder.Write("This is some text after the bookmark.");
```

 Di sini, kami menambahkan beberapa teks sebelum dan sesudah konten yang ditandai. Itu`StartBookmark` Dan`EndBookmark` metode menentukan batas-batas bookmark.

## Langkah 3: Memasukkan Bidang Bersyarat

Untuk mengontrol visibilitas konten yang ditandai, kami akan menggunakan bidang bersyarat. Bidang ini akan memeriksa suatu kondisi dan menampilkan atau menyembunyikan konten yang sesuai.

```csharp
builder.MoveToDocumentEnd();
Field field = builder.InsertField("IF \"", null);
builder.MoveTo(field.Start.NextSibling);
builder.InsertField("MERGEFIELD MyBookmark", null);
builder.Write("\" = \"true\" \"Visible\" \"Hidden\"");
```

Pada langkah ini, kita menyisipkan kolom IF yang memeriksa nilai bookmark. Jika nilainya "benar", maka akan ditampilkan "Terlihat"; jika tidak, ia akan menampilkan "Tersembunyi".

## Langkah 4: Menata Ulang Node

Selanjutnya, kita perlu mengatur ulang node untuk memastikan logika kondisional berlaku dengan benar pada konten yang ditandai.

```csharp
Bookmark bm = doc.Range.Bookmarks["MyBookmark"];
Node currentNode = field.Start;
bool flag = true;

while (currentNode != null && flag)
{
    if (currentNode.NodeType == NodeType.Run && currentNode.ToString(SaveFormat.Text).Trim() == "\"")
        flag = false;

    Node nextNode = currentNode.NextSibling;
    bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
    currentNode = nextNode;
}

Node endNode = bm.BookmarkEnd;
flag = true;

while (currentNode != null && flag)
{
    if (currentNode.NodeType == NodeType.FieldEnd)
        flag = false;

    Node nextNode = currentNode.NextSibling;
    bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
    endNode = currentNode;
    currentNode = nextNode;
}
```

Di sini, kami memindahkan node untuk memastikan kondisinya mencakup konten yang ditandai dengan benar.

## Langkah 5: Menjalankan Penggabungan Surat

Terakhir, kita akan menjalankan gabungan surat untuk menetapkan nilai bookmark dan menentukan apakah konten harus ditampilkan atau disembunyikan.

```csharp
doc.MailMerge.Execute(new[] { "MyBookmark" }, new object[] { "true" });
```

Langkah ini menetapkan nilai bookmark menjadi "true", yang akan membuat konten terlihat berdasarkan kondisi kita.

## Langkah 6: Menyimpan Dokumen

Setelah semua manipulasi, langkah terakhir adalah menyimpan dokumen yang dimodifikasi.

```csharp
doc.Save("ShowHideBookmarkedContent.docx");
```

Di sini, kami menyimpan dokumen dengan nama file deskriptif untuk menunjukkan perubahan.

## Kesimpulan

 Dan itu saja! Anda telah berhasil mempelajari cara menampilkan atau menyembunyikan konten yang ditandai di dokumen Word menggunakan Aspose.Words untuk .NET. Tutorial ini mencakup pembuatan dokumen, menambahkan bookmark, menyisipkan bidang bersyarat, mengatur ulang node, dan mengeksekusi gabungan surat. Aspose.Words menawarkan banyak fitur, jadi jangan ragu untuk menjelajahinya[dokumentasi API](https://reference.aspose.com/words/net/) untuk kemampuan yang lebih maju.

## FAQ

### 1. Apa itu Aspose.Words untuk .NET?

Aspose.Words untuk .NET adalah perpustakaan canggih yang memungkinkan pengembang membuat, memodifikasi, dan mengonversi dokumen Word secara terprogram. Ini banyak digunakan untuk tugas otomatisasi dokumen.

### 2. Bisakah saya menggunakan Aspose.Words untuk .NET secara gratis?

 Anda dapat mencoba Aspose.Words untuk .NET menggunakan a[uji coba gratis](https://releases.aspose.com/). Untuk penggunaan jangka panjang, Anda harus membeli lisensi.

### 3. Bagaimana cara mengubah properti bookmark lainnya?

 Aspose.Words memungkinkan Anda memanipulasi berbagai properti bookmark, seperti teks dan lokasinya. Mengacu kepada[dokumentasi API](https://reference.aspose.com/words/net/) untuk petunjuk rinci.

### 4. Bagaimana cara mendapatkan dukungan untuk Aspose.Words untuk .NET?

Anda bisa mendapatkan dukungan dengan mengunjungi[Asumsikan forum dukungan](https://forum.aspose.com/c/words/8).

### 5. Bisakah saya memanipulasi jenis konten lain dengan Aspose.Words untuk .NET?

Ya, Aspose.Words untuk .NET mendukung berbagai jenis manipulasi konten, termasuk teks, gambar, tabel, dan lainnya.