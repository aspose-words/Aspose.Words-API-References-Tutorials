---
title: Daftar pesanan
linktitle: Daftar pesanan
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara membuat daftar berurutan dengan Aspose.Words untuk .NET Panduan langkah demi langkah.
type: docs
weight: 10
url: /id/net/working-with-markdown/ordered-list/
---

Dalam contoh ini, kami akan menjelaskan cara menggunakan fungsionalitas daftar terurut dengan Aspose.Words untuk .NET. Daftar Terurut memungkinkan Anda mengatur item secara berurutan dengan angka.

## Langkah 1: Menggunakan pembuat dokumen

Pertama, kita akan menggunakan pembuat dokumen untuk membuat dokumen baru.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 2: Menerapkan format daftar terurut

 Kami akan menerapkan format daftar terurut menggunakan pembuat dokumen`ApplyBulletDefault`metode. Kita juga dapat menyesuaikan format penomoran dengan masuk ke level daftar dan mengatur format yang kita inginkan.

```csharp
builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";
```

## Langkah 3: Menambahkan item ke daftar

 Kita dapat menambahkan item ke daftar menggunakan pembuat dokumen`Writeln` metode.

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## Langkah 4: Buat indentasi daftar

 Kita dapat membuat indentasi daftar menggunakan pembuat dokumen`ListIndent` metode.

```csharp
builder.ListFormat.ListIndent();
builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

## Langkah 5: Menyimpan dokumen

Terakhir, kita bisa menyimpan dokumen dalam format yang diinginkan.

### Contoh kode sumber untuk daftar terurut dengan Aspose.Words untuk .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";

builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();

builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

Selamat! Anda sekarang telah mempelajari cara menggunakan fitur daftar terurut dengan Aspose.Words untuk .NET.


### FAQ

#### T: Bagaimana cara membuat daftar terurut di Markdown?

A: Untuk membuat daftar terurut dalam Markdown, awali setiap item daftar dengan nomor diikuti dengan titik (`1.`, `2.`, `3.`), diikuti dengan spasi.

#### T: Bisakah kita menyusun daftar yang diurutkan di Markdown?

J: Ya, dimungkinkan untuk menyusun daftar yang diurutkan dalam Markdown dengan menambahkan empat spasi offset di depan setiap item daftar yang disarangkan.

#### T: Bagaimana cara menyesuaikan penomoran daftar yang dipesan?

J: Dalam Markdown standar, penomoran daftar terurut dihasilkan secara otomatis. Namun, beberapa editor Markdown mengizinkan Anda menyesuaikannya menggunakan ekstensi tertentu.

#### T: Apakah daftar yang diurutkan dalam Markdown mendukung indentasi?

A: Ya, daftar yang diurutkan dalam lekukan dukungan penurunan harga. Anda dapat menambahkan shift ke kiri menggunakan spasi atau tab.

#### T: Dapatkah tautan atau teks sebaris ditambahkan ke item daftar?

J: Ya, Anda dapat menambahkan link atau teks sebaris ke item daftar menggunakan sintaks penurunan harga yang sesuai.