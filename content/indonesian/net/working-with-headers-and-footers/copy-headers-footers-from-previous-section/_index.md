---
title: Salin Header Footer Dari Bagian Sebelumnya
linktitle: Salin Header Footer Dari Bagian Sebelumnya
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyalin header dan footer dari bagian sebelumnya di dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-headers-and-footers/copy-headers-footers-from-previous-section/
---

Dalam tutorial langkah demi langkah ini, kami akan memandu Anda tentang cara menyalin header dan footer dari bagian sebelumnya di dokumen Word menggunakan Aspose.Words untuk .NET. Kami akan menjelaskan kode sumber C# yang disediakan dan menunjukkan cara mengimplementasikannya di proyek Anda sendiri.

 Untuk memulai, pastikan Anda telah menginstal dan menyiapkan Aspose.Words untuk .NET di lingkungan pengembangan Anda. Jika Anda belum melakukannya, unduh dan instal perpustakaan dari[Aspose.Rilis]https://releases.aspose.com/words/net/.

## Langkah 1: Mengakses Bagian Sebelumnya

 Pertama, ambil bagian sebelumnya dengan mengakses`PreviousSibling` properti bagian saat ini:

```csharp
Section previousSection = (Section)section.PreviousSibling;
```

## Langkah 2: Memeriksa Bagian Sebelumnya

Selanjutnya, periksa apakah bagian sebelumnya ada. Jika tidak ada bagian sebelumnya, kami cukup mengembalikan:

```csharp
if (previousSection == null)
    return;
```

## Langkah 3: Menghapus dan Menyalin Header dan Footer

Untuk menyalin header dan footer dari bagian sebelumnya ke bagian saat ini, kami menghapus header dan footer yang ada di bagian saat ini dan kemudian mengulangi header dan footer dari bagian sebelumnya untuk menambahkan salinan kloning ke bagian saat ini:

```csharp
section.HeadersFooters.Clear();

foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    section.HeadersFooters.Add(headerFooter.Clone(true));
```

## Langkah 4: Menyimpan Dokumen

Terakhir, simpan dokumen yang dimodifikasi:

```csharp
doc.Save("OutputDocument.docx");
```

Itu dia! Anda telah berhasil menyalin header dan footer dari bagian sebelumnya ke bagian saat ini di dokumen Word menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber untuk Menyalin Header Footer Dari Bagian Sebelumnya menggunakan Aspose.Words untuk .NET

```csharp
Section previousSection = (Section)section.PreviousSibling;

if (previousSection == null)
    return;

section.HeadersFooters.Clear();

foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    section.HeadersFooters.Add(headerFooter.Clone(true));

doc.Save("OutputDocument.docx");
```

Jangan ragu untuk menggunakan kode ini di proyek Anda sendiri dan memodifikasinya sesuai dengan kebutuhan spesifik Anda.

### FAQ

#### T: Bagaimana cara menyalin header dan footer dari bagian sebelumnya ke Aspose.Words?

 A: Untuk menyalin header dan footer dari bagian sebelumnya ke Aspose.Words, Anda dapat menggunakan`CopyHeadersFootersFromPreviousSection()` metode pada saat ini`Section`obyek. Ini akan menyalin header dan footer dari bagian sebelumnya ke bagian saat ini.

#### T: Apakah mungkin untuk menyalin hanya header atau footer dari bagian sebelumnya di Aspose.Words?

 A: Ya, dimungkinkan untuk menyalin hanya header atau footer dari bagian sebelumnya di Aspose.Words. Untuk ini, Anda dapat menggunakan`CopyHeaderFromPreviousSection()` Dan`CopyFooterFromPreviousSection()` metode saat ini`Section` objek untuk secara khusus menyalin header atau footer dari bagian sebelumnya ke bagian saat ini.

#### T: Apakah menyalin header dan footer dari bagian sebelumnya akan menggantikan header dan footer yang ada di bagian saat ini?

J: Ya, menyalin header dan footer dari bagian sebelumnya akan menggantikan header dan footer yang ada di bagian saat ini. Jika Anda ingin mempertahankan header dan footer yang ada dan menambahkannya ke header dan footer yang disalin, Anda perlu melakukan operasi tambahan untuk menggabungkan konten.

#### T: Bagaimana cara memeriksa apakah suatu bagian memiliki header atau footer dari bagian sebelumnya di Aspose.Words?

A: Untuk memeriksa apakah suatu bagian memiliki header atau footer dari bagian sebelumnya di Aspose.Words, Anda dapat menggunakan`HasHeader` Dan`HasFooter` properti di`Section` objek untuk menentukan apakah header header atau footer ada. Jika`HasHeader` atau`HasFooter` kembali`false`, artinya tidak ada header atau footer dari bagian sebelumnya di bagian ini.