---
title: Teks tebal
linktitle: Teks tebal
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menebalkan teks dengan Aspose.Words untuk .NET Panduan langkah demi langkah.
type: docs
weight: 10
url: /id/net/working-with-markdown/bold-text/
---

Dalam contoh ini, kami akan memberi tahu Anda cara menebalkan teks dengan Aspose.Words untuk .NET. Teks yang dicetak tebal membuatnya lebih terlihat dan membuatnya lebih menonjol.

## Langkah 1: Menggunakan pembuat dokumen

Pertama, kita akan menggunakan pembuat dokumen untuk menambahkan konten ke dokumen kita.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Langkah 2: Teks Tebal

 Kita dapat menebalkan teks dengan mengatur pembuat dokumen`Font.Bold`properti ke`true`.

```csharp
builder.Font.Bold = true;
```

## Langkah 3: Tambahkan konten ke dokumen

 Sekarang kita dapat menambahkan konten ke dokumen menggunakan metode pembuat dokumen, seperti`Writeln`, yang menambahkan sebaris teks.

```csharp
builder.Writeln("This text will be bold");
```

## Contoh Kode Sumber untuk Teks Tebal menggunakan Aspose.Words untuk .NET


```csharp
// Gunakan pembuat dokumen untuk menambahkan konten ke dokumen.
DocumentBuilder builder = new DocumentBuilder();

// Buatlah teks menjadi tebal.
builder.Font.Bold = true;
builder.Writeln("This text will be Bold");  
```

Selamat! Anda sekarang telah mempelajari cara menebalkan teks dengan Aspose.Words untuk .NET.


### FAQ

#### T: Bagaimana cara membuat teks tebal di Aspose.Words?

 A: Untuk membuat teks tebal di Aspose.Words, Anda dapat menggunakan`Font.Bold` properti dari`Run`obyek. Anda dapat mengatur properti ini menjadi`true` untuk menebalkan teks tertentu. Misalnya, Anda bisa menggunakan`run.Font.Bold=true` untuk menebalkan teks di dalamnya`Run` obyek.

#### Q: Apakah mungkin untuk menebalkan beberapa bagian teks dalam satu paragraf?

 J: Ya, Anda dapat menebalkan beberapa bagian teks dalam satu paragraf menggunakan beberapa paragraf`Run` objek. Anda dapat membuat banyak`Run` objek dan atur`Font.Bold`properti ke`true` untuk setiap objek untuk menebalkan bagian teks yang diinginkan. Kemudian Anda dapat menambahkannya ke paragraf menggunakan`Paragraph.AppendChild(run)` metode.

#### T: Bisakah saya menebalkan teks yang ada di tabel atau sel di Aspose.Words?

 A: Ya, Anda dapat menebalkan teks yang ada di tabel atau sel di Aspose.Words. Anda dapat menavigasi ke sel atau paragraf yang Anda inginkan menggunakan metode yang sesuai dan kemudian menerapkan pemformatan tebal menggunakan`Font.Bold` properti dari`Run` atau`Paragraph` obyek.