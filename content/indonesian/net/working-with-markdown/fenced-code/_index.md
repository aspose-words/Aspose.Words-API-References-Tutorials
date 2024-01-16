---
title: Kode Berpagar
linktitle: Kode Berpagar
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menggunakan fitur kode berpagar dengan Aspose.Words untuk .NET Panduan langkah demi langkah.
type: docs
weight: 10
url: /id/net/working-with-markdown/fenced-code/
---

Dalam contoh ini, kami akan memandu Anda tentang cara menggunakan fitur kode berpagar dengan Aspose.Words untuk .NET. kode berpagar digunakan untuk mewakili blok kode dengan format tertentu.

## Langkah 1: Menggunakan pembuat dokumen

Pertama, kita akan menggunakan pembuat dokumen untuk menambahkan konten ke dokumen kita.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Langkah 2: Menambahkan gaya untuk kode berpagar

 Kami akan menambahkan gaya khusus untuk kode berpagar menggunakan`Styles.Add` metode`Document` obyek. Dalam contoh ini, kita membuat gaya yang disebut "FencedCode" untuk kode berpagar.

```csharp
Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
```

## Langkah 3: Menambahkan kode berpagar tanpa info

Sekarang kita dapat menambahkan blok kode berpagar tanpa string informasi menggunakan gaya khusus "FencedCode".

```csharp
builder.Writeln("This is an fenced code");
```

## Langkah 4: Tambahkan kode berpagar dengan string info

Kita juga dapat menambahkan blok kode berpagar dengan serangkaian informasi menggunakan gaya khusus lainnya. Dalam contoh ini, kita membuat gaya yang disebut "FencedCode.C#" untuk mewakili blok kode C#.

```csharp
Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### Contoh kode sumber untuk Kode Berpagar menggunakan Aspose.Words untuk .NET

```csharp
// Gunakan pembuat dokumen untuk menambahkan konten ke dokumen.
DocumentBuilder builder = new DocumentBuilder();

Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
builder.Writeln("This is an fenced code");

Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### FAQ

#### T: Apa yang dimaksud dengan kode yang dibatasi dalam Markdown?

J: Kode yang dibatasi dalam Markdown adalah metode pemformatan yang digunakan untuk menampilkan kode dalam dokumen Markdown. Ini terdiri dari membingkai kode dengan pembatas tertentu.

#### T: Apa manfaat kode yang dibatasi dalam Markdown?

J: Kode yang dibatasi dalam Markdown meningkatkan keterbacaan kode dan memudahkan pembaca untuk memahaminya. Ini juga memungkinkan pelestarian penyorotan sintaksis di beberapa editor Markdown.

#### T: Apa perbedaan antara kode yang dipisahkan dan yang menjorok ke dalam Markdown?

J: Kode yang dibatasi menggunakan pembatas khusus untuk mengapit kode, sedangkan kode yang diindentasi melibatkan indentasi setiap baris kode dengan spasi atau tab.

#### T: Apakah kode yang dibatasi dalam Markdown didukung oleh semua editor Markdown?

J: Dukungan untuk kode yang dibatasi dalam Markdown mungkin berbeda antar editor Markdown. Periksa dokumentasi spesifik penerbit Anda untuk memastikannya.

