---
title: Tautan
linktitle: Tautan
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyisipkan tautan dengan Aspose.Words untuk .NET. Panduan langkah demi langkah.
type: docs
weight: 10
url: /id/net/working-with-markdown/link/
---

Dalam contoh ini, kami akan memandu Anda tentang cara menggunakan fitur tautan dengan Aspose.Words untuk .NET. Tautan digunakan untuk membuat referensi yang dapat diklik ke situs web atau dokumen lain.

## Langkah 1: Menggunakan pembuat dokumen

Pertama, kita akan menggunakan pembuat dokumen untuk menambahkan konten ke dokumen kita.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Langkah 2: Memasukkan tautan

 Kita dapat menyisipkan tautan menggunakan`InsertHyperlink` metode pembuat dokumen. Kita perlu menentukan teks link, di sini "Aspose", serta URL tujuan.

```csharp
builder.InsertHyperlink("Aspose", "https://www.aspose.com", salah);
```

### Contoh kode sumber untuk tautan dengan Aspose.Words untuk .NET


```csharp
// Gunakan pembuat dokumen untuk menambahkan konten ke dokumen.
DocumentBuilder builder = new DocumentBuilder();

// Sisipkan tautan.
builder.InsertHyperlink("Aspose", "https://www.aspose.com", salah);
```
Selamat! Anda sekarang telah mempelajari cara menggunakan fitur tautan dengan Aspose.Words untuk .NET.


### FAQ

#### T: Bagaimana cara menautkan ke URL di Aspose.Words?

 J: Untuk menautkan ke alamat URL di Aspose.Words, Anda dapat menggunakan`<a>` tandai dengan`href` atribut yang berisi alamat URL. Misalnya, Anda bisa menggunakan`<a href="https://www.aspose.com">Click Here</a>` untuk hyperlink ke URL "https://www.example.com" dengan teks tampilan "Klik di sini".

#### T: Apakah mungkin untuk menautkan ke bookmark internal di Aspose.Words?

 A: Ya, dimungkinkan untuk menautkan ke bookmark internal di Aspose.Words. Anda dapat menggunakan`<a>` tandai dengan`href` atribut yang berisi nama bookmark yang diawali dengan tanda pagar (#). Misalnya,`<a href="#bookmark1">Go to bookmark 1</a>` akan tertaut ke bookmark bernama "bookmark1" di dokumen.

#### T: Bagaimana cara mengkustomisasi teks tampilan tautan di Aspose.Words?

 J: Untuk menyesuaikan teks tampilan tautan di Aspose.Words, Anda dapat mengubah konten di antara`<a>` tag. Misalnya,`<a href="https://www.aspose.com">Click here</a>` akan menampilkan teks "Klik di sini" sebagai hyperlink.

#### T: Dapatkah saya menentukan target untuk tautan di Aspose.Words?

A: Ya, Anda dapat menentukan target untuk tautan di Aspose.Words menggunakan`target` atribut dari`<a>` menandai. Misalnya,`<a href="https://www.aspose.com" target="_blank">Open in new window</a>` akan membuka tautan di jendela atau tab baru.