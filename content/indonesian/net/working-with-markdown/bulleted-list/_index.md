---
title: Daftar Berpoin
linktitle: Daftar Berpoin
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara membuat daftar berpoin dengan Aspose.Words untuk .NET Panduan langkah demi langkah.
type: docs
weight: 10
url: /id/net/working-with-markdown/bulleted-list/
---

Dalam tutorial ini, kami akan memberi tahu Anda cara membuat daftar berpoin dengan Aspose.Words untuk .NET. Daftar berpoin digunakan untuk membuat daftar item tanpa menggunakan penomoran.

## Langkah 1: Menggunakan pembuat dokumen

Pertama, kita akan menggunakan pembuat dokumen untuk menambahkan konten ke dokumen kita.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Langkah 2: Menerapkan Daftar Berpoin Default

 Kita dapat menerapkan daftar poin default menggunakan pembuat dokumen`ApplyBulletDefault` metode.

```csharp
builder.ListFormat.ApplyBulletDefault();
```

## Langkah 3: Menyesuaikan Format Poin

 Kita dapat menyesuaikan format poin dengan mengakses properti`ListFormat.List.ListLevels[0]`. Dalam contoh ini, kita menggunakan tanda hubung "-" sebagai tanda peluru.

```csharp
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";
```

## Langkah 4: Menambahkan item ke daftar

 Sekarang kita dapat menambahkan item ke daftar poin menggunakan pembuat dokumen`Writeln` metode.

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## Langkah 5: Menghapus lekukan dari daftar

 Jika kita ingin membuat sublist, kita dapat menambah indentasinya menggunakan`ListFormat.ListIndent()` metode. Dalam contoh ini, kami menambahkan sublist ke item 2a dan 2b.

```csharp
builder.ListFormat.ListIndent();
builder. Writeln("Element 2a");
builder.Writeln("Element 2b");
```
### Contoh kode sumber untuk Daftar Berpoin menggunakan Aspose.Words untuk .NET


```csharp
// Gunakan pembuat dokumen untuk menambahkan konten ke dokumen.
DocumentBuilder builder = new DocumentBuilder();

builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";

builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();

builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

Selamat! Anda sekarang telah mempelajari cara membuat daftar berpoin dengan Aspose.Words untuk .NET.

### FAQ

#### T: Bagaimana cara membuat daftar berpoin di Markdown?

J: Untuk membuat daftar berpoin di Markdown, awali setiap item daftar dengan simbol poin (`-`, `*` , atau`+`), diikuti dengan spasi.

#### T: Bisakah Anda menyusun daftar poin di Markdown?

J: Ya, daftar berpoin dapat disarangkan di Markdown dengan menambahkan empat spasi offset di depan setiap item daftar yang disarangkan.

#### T: Bagaimana cara menyesuaikan simbol poin?

J: Dalam Markdown standar, simbol poin sudah ditentukan sebelumnya. Namun, beberapa editor Markdown memungkinkan Anda menyesuaikannya menggunakan ekstensi tertentu.

#### T: Apakah daftar berpoin di Markdown mendukung indentasi?

J: Ya, daftar berpoin dalam lekukan dukungan penurunan harga. Anda dapat menambahkan shift ke kiri menggunakan spasi atau tab.

#### T: Dapatkah tautan atau teks sebaris ditambahkan ke item daftar?

J: Ya, Anda dapat menambahkan link atau teks sebaris ke item daftar menggunakan sintaks penurunan harga yang sesuai.
