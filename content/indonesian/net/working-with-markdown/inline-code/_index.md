---
title: Kode Sebaris
linktitle: Kode Sebaris
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyejajarkan kode dengan Aspose.Words untuk .NET Panduan langkah demi langkah.
type: docs
weight: 10
url: /id/net/working-with-markdown/inline-code/
---

Dalam contoh ini, kami akan memandu Anda tentang cara menggunakan fitur kode sebaris dengan Aspose.Words untuk .NET. Kode Inline digunakan untuk merepresentasikan potongan kode di dalam paragraf secara visual.

## Langkah 1: Menggunakan pembuat dokumen

Pertama, kita akan menggunakan pembuat dokumen untuk menambahkan konten ke dokumen kita.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Langkah 2: Tambahkan gaya untuk kode sebaris

 Kami akan menambahkan gaya khusus untuk kode sebaris menggunakan`Styles.Add` metode`Document` obyek. Dalam contoh ini, kita membuat gaya yang disebut "InlineCode" untuk kode inline dengan backtick default.

```csharp
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
```

## Langkah 3: Tambahkan kode sebaris

Sekarang kita dapat menambahkan kode sebaris menggunakan gaya khusus "InlineCode". Dalam contoh ini, kita menambahkan dua bagian teks dengan jumlah backtick yang berbeda.

```csharp
builder.Writeln("Text with InlineCode style with 1 backtick");
```

```csharp
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backticks");
```


### Contoh kode sumber untuk Inline Code dengan Aspose.Words untuk .NET

```csharp
// Gunakan pembuat dokumen untuk menambahkan konten ke dokumen.
DocumentBuilder builder = new DocumentBuilder();

// Jumlah backtick terlewatkan, satu backtick akan digunakan secara default.
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
builder.Writeln("Text with InlineCode style with 1 backtick");

// Akan ada 3 backtick.
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backtick");
```

Selamat! Anda sekarang telah mempelajari cara menggunakan fungsionalitas kode sebaris dengan Aspose.Words untuk .NET.


### FAQ

#### T: Bagaimana cara menggunakan kode sebaris di Aspose.Words?

 J: Untuk menggunakan kode sebaris di Aspose.Words, Anda dapat menggunakan tag yang sesuai untuk mengelilingi teks yang akan diformat sebagai kode sebaris. Misalnya, Anda dapat menggunakan`<code>` atau`<kbd>` tag untuk mengelilingi teks untuk diformat sebagai kode sebaris.

#### T: Apakah mungkin untuk menentukan font atau warna kode sebaris di Aspose.Words?

 A: Ya, Anda dapat menentukan font atau warna kode inline di Aspose.Words. Anda dapat menggunakan`Font.Name`Dan`Font.Color` properti dari`Run` objek untuk mengatur font dan warna kode sebaris. Misalnya, Anda bisa menggunakan`run.Font.Name = "Courier New"` untuk menentukan font untuk kode sebaris dan`run.Font.Color = Color.Blue`untuk menentukan warnanya.

#### T: Bisakah saya menggunakan kode sebaris dalam paragraf yang berisi elemen teks lain?

 A: Ya, Anda dapat menggunakan kode inline dalam paragraf yang berisi elemen teks lainnya. Anda dapat membuat banyak`Run` objek untuk mewakili bagian paragraf yang berbeda, lalu gunakan tag kode sebaris untuk memformat bagian tertentu saja sebagai kode sebaris. Kemudian Anda dapat menambahkannya ke paragraf menggunakan`Paragraph.AppendChild(run)` metode.