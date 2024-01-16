---
title: Dicoret
linktitle: Dicoret
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menerapkan gaya teks coretan dengan Aspose.Words for .NET Panduan langkah demi langkah.
type: docs
weight: 10
url: /id/net/working-with-markdown/strikethrough/
---


Dalam contoh ini, kami akan memandu Anda tentang cara menerapkan gaya teks yang dicoret menggunakan Aspose.Words untuk .NET. Teks yang dicoret digunakan untuk menunjukkan bahwa teks tersebut dihapus atau tidak berlaku lagi.

## Langkah 1: Menggunakan pembuat dokumen

Pertama, kita akan menggunakan pembuat dokumen untuk menambahkan konten ke dokumen kita.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Langkah 2: Terapkan gaya teks yang dicoret

Kami akan mengaktifkan gaya teks dicoret dengan mengatur`StrikeThrough` properti dari`Font` objek untuk`true`.

```csharp
builder.Font.StrikeThrough = true;
```

## Langkah 3: Tambahkan teks yang dicoret

 Kita sekarang dapat menambahkan teks yang dicoret menggunakan pembuat dokumen`Writeln` metode.

```csharp
builder.Writeln("This text will be StrikeThrough");
```


### Contoh kode sumber untuk teks yang dicoret dengan Aspose.Words untuk .NET

```csharp
// Gunakan pembuat dokumen untuk menambahkan konten ke dokumen.
DocumentBuilder builder = new DocumentBuilder();

// Buat teksnya dicoret.
builder.Font.StrikeThrough = true;
builder.Writeln("This text will be StrikeThrough");
```

Selamat! Anda sekarang telah mempelajari cara menerapkan gaya teks coretan dengan Aspose.Words untuk .NET.

### FAQ

#### T: Bagaimana cara menambahkan teks yang dicoret di Aspose.Words?

 A: Untuk menambahkan teks yang dicoret di Aspose.Words, Anda dapat menggunakan`Font.StrikeThrough` properti dari`Run` obyek. Anda dapat mengatur properti ini menjadi`true` untuk menambahkan teks yang dicoret ke teks tertentu. Misalnya, Anda bisa menggunakan`run.Font.StrikeThrough=true` untuk menambahkan teks yang dicoret ke dalam`Run` obyek.

#### Q: Apakah mungkin untuk menambahkan teks yang dicoret ke beberapa bagian teks dalam paragraf yang sama?

 J: Ya, Anda dapat menambahkan teks yang dicoret ke beberapa bagian teks dalam satu paragraf dengan menggunakan beberapa bagian`Run` objek. Anda dapat membuat banyak`Run` objek dan atur`Font.StrikeThrough`properti ke`true` untuk setiap objek untuk menambahkan teks yang dicoret ke bagian teks yang diinginkan. Kemudian Anda dapat menambahkannya ke paragraf menggunakan`Paragraph.AppendChild(run)` metode.

#### T: Bisakah saya menambahkan teks yang dicoret ke teks yang ada di tabel atau sel di Aspose.Words?

 A: Ya, Anda dapat menambahkan teks yang dicoret ke teks yang ada di tabel atau sel di Aspose.Words. Anda dapat melompat ke sel atau paragraf yang Anda inginkan menggunakan metode yang sesuai dan kemudian menerapkan pemformatan teks yang dicoret menggunakan`Font.StrikeThrough` properti dari`Run` atau`Paragraph` obyek.