---
title: Daftar Berpoin
linktitle: Daftar Berpoin
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara membuat dan mengkustomisasi daftar berpoin di dokumen Word menggunakan Aspose.Words untuk .NET dengan panduan langkah demi langkah ini.
type: docs
weight: 10
url: /id/net/working-with-markdown/bulleted-list/
---
## Perkenalan

Siap terjun ke dunia Aspose.Words untuk .NET? Hari ini, kita akan memandu pembuatan daftar poin di dokumen Word Anda. Baik Anda mengatur ide, membuat daftar item, atau hanya menambahkan sedikit struktur ke dokumen Anda, daftar berpoin sangat berguna. Jadi, mari kita mulai!

## Prasyarat

Sebelum kita terjun ke kesenangan coding, pastikan Anda memiliki semua yang Anda butuhkan:

1.  Aspose.Words untuk .NET: Pastikan Anda telah menginstal perpustakaan Aspose.Words. Jika Anda belum memilikinya, Anda bisa[unduh di sini](https://releases.aspose.com/words/net/).
2. Lingkungan Pengembangan: Lingkungan pengembangan AC# seperti Visual Studio.
3. Pengetahuan C# Dasar: Pemahaman dasar tentang pemrograman C# akan membantu Anda mengikutinya.

## Impor Namespace

Hal pertama yang pertama, mari impor namespace yang diperlukan. Ini seperti menyiapkan panggung agar kode kita berjalan dengan lancar.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Lists;
```

Sekarang, mari kita bagi prosesnya menjadi langkah-langkah yang mudah dan dapat dikelola.

## Langkah 1: Buat Dokumen Baru

Baiklah, mari kita mulai dengan membuat dokumen baru. Di sinilah semua keajaiban akan terjadi.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Langkah 2: Terapkan Format Daftar Poin

Selanjutnya, kita akan menerapkan format daftar poin. Ini memberi tahu dokumen bahwa kita akan memulai daftar poin.

```csharp
builder.ListFormat.ApplyBulletDefault();
```

## Langkah 3: Sesuaikan Daftar Poin

Di sini, kami akan menyesuaikan daftar poin sesuai keinginan kami. Untuk contoh ini, kita akan menggunakan tanda hubung (-) sebagai poinnya.

```csharp
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";
```

## Langkah 4: Tambahkan Item Daftar

Sekarang, mari tambahkan beberapa item ke daftar poin kita. Di sinilah Anda bisa berkreasi dan menambahkan konten apa pun yang Anda butuhkan.

```csharp
builder.Writeln("Item 1");
builder.Writeln("Item 2");
```

## Langkah 5: Tambahkan Sub-Item

Agar lebih menarik, mari tambahkan beberapa sub-item di bawah "Item 2". Ini membantu dalam mengatur subpoin.

```csharp
builder.ListFormat.ListIndent();
builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
builder.ListFormat.ListOutdent(); // Kembali ke tingkat daftar utama
```

## Kesimpulan

Dan itu dia! Anda baru saja membuat daftar poin di dokumen Word menggunakan Aspose.Words untuk .NET. Ini adalah proses yang mudah, namun sangat ampuh untuk mengatur dokumen Anda. Baik Anda membuat daftar sederhana atau daftar bertingkat yang kompleks, Aspose.Words siap membantu Anda.

Jangan ragu untuk bereksperimen dengan gaya dan format daftar yang berbeda sesuai kebutuhan Anda. Selamat membuat kode!

## FAQ

### Bisakah saya menggunakan simbol poin yang berbeda dalam daftar?
    Ya, Anda dapat menyesuaikan simbol poin dengan mengubah`NumberFormat` milik.

### Bagaimana cara menambahkan lebih banyak tingkat lekukan?
    Gunakan`ListIndent` metode untuk menambahkan lebih banyak level dan`ListOutdent` untuk kembali ke level yang lebih tinggi.

### Apakah mungkin untuk menggabungkan daftar poin dan nomor?
   Sangat! Anda dapat beralih antara format poin dan angka menggunakan`ApplyNumberDefault`Dan`ApplyBulletDefault` metode.

### Bisakah saya menata teks di item daftar?
    Ya, Anda dapat menerapkan gaya, font, dan pemformatan yang berbeda pada teks dalam item daftar menggunakan`Font` properti dari`DocumentBuilder`.

### Bagaimana cara membuat daftar poin multi-kolom?
   Anda bisa menggunakan pemformatan tabel untuk membuat daftar multi-kolom, di mana setiap sel berisi daftar berpoin terpisah.