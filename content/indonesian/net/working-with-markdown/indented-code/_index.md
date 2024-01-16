---
title: Kode Indentasi
linktitle: Kode Indentasi
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menggunakan kode indentasi dengan Aspose.Words untuk .NET Panduan langkah demi langkah.
type: docs
weight: 10
url: /id/net/working-with-markdown/indented-code/
---

Dalam contoh ini, kami akan menjelaskan cara menggunakan fitur kode indentasi dengan Aspose.Words untuk .NET. Kode berindentasi digunakan untuk merepresentasikan blok kode secara visual dengan format tertentu.

## Langkah 1: Menggunakan pembuat dokumen

Pertama, kita akan menggunakan pembuat dokumen untuk menambahkan konten ke dokumen kita.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Langkah 2: Tambahkan gaya untuk kode yang menjorok ke dalam

 Kami akan menambahkan gaya khusus untuk kode indentasi menggunakan`Styles.Add` metode`Document` obyek. Dalam contoh ini, kita membuat gaya yang disebut "IndentedCode" untuk kode yang diindentasi.

```csharp
Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
```

## Langkah 3: Tambahkan kode yang menjorok ke dalam

Sekarang kita dapat menambahkan blok kode indentasi menggunakan gaya kustom "IndentedCode".

```csharp
builder.Writeln("This is an indented code block");
```

### Contoh kode sumber untuk kode indentasi dengan Aspose.Words untuk .NET

```csharp
// Gunakan pembuat dokumen untuk menambahkan konten ke dokumen.
DocumentBuilder builder = new DocumentBuilder();

Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
builder.Writeln("This is an indented code");
```

Selamat! Anda sekarang telah mempelajari cara menggunakan fitur kode indentasi dengan Aspose.Words untuk .NET.


### FAQ

#### T: Apa yang dimaksud dengan kode indentasi di Markdown?

A: Kode indentasi dalam Markdown adalah metode pemformatan yang digunakan untuk menampilkan kode dalam dokumen Markdown. Ini terdiri dari mengindentasi setiap baris kode dengan spasi atau tab.

#### T: Bagaimana cara menggunakan kode indentasi di Markdown?

J: Untuk menggunakan kode indentasi dalam Markdown, indentasi setiap baris kode dengan spasi atau tab.

#### T: Apa keuntungan kode indentasi di Markdown?

J: Kode yang menjorok ke dalam di Markdown meningkatkan keterbacaan kode dan memudahkan pembaca untuk memahaminya.

#### T: Apa perbedaan antara kode indentasi dan blok kode di Markdown?

J: Kode berindentasi digunakan untuk cuplikan kode kecil yang disisipkan ke dalam teks, sedangkan blok kode digunakan untuk menampilkan potongan kode lebih besar dalam format terpisah.

#### T: Apakah kode yang menjorok ke dalam Markdown didukung oleh semua editor Markdown?

J: Dukungan untuk kode indentasi di Markdown mungkin berbeda antar editor Markdown. Periksa dokumentasi spesifik penerbit Anda untuk memastikannya.