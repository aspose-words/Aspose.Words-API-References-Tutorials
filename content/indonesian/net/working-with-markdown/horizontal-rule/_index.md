---
title: Aturan Horisontal
linktitle: Aturan Horisontal
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyisipkan aturan horizontal dengan Aspose.Words untuk .NET Panduan langkah demi langkah.
type: docs
weight: 10
url: /id/net/working-with-markdown/horizontal-rule/
---

Dalam contoh ini, kami akan menunjukkan cara menggunakan fitur aturan horizontal dengan Aspose.Words untuk .NET. Aturan Horizontal digunakan untuk memisahkan bagian dokumen secara visual.

## Langkah 1: Menggunakan pembuat dokumen

Pertama, kita akan menggunakan pembuat dokumen untuk menambahkan konten ke dokumen kita.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Langkah 2: Memasukkan aturan horizontal

 Kita dapat menyisipkan aturan horizontal menggunakan`InsertHorizontalRule` metode pembuat dokumen.

```csharp
builder. InsertHorizontalRule();
```

## Contoh kode sumber untuk aturan horizontal dengan Aspose.Words untuk .NET

```csharp
// Gunakan pembuat dokumen untuk menambahkan konten ke dokumen.
DocumentBuilder builder = new DocumentBuilder();

// Sisipkan aturan horizontal.
builder.InsertHorizontalRule();
```

Selamat! Anda sekarang telah mempelajari cara menggunakan fitur aturan horizontal dengan Aspose.Words untuk .NET.


### FAQ

#### T: Bagaimana cara membuat penggaris horizontal di Markdown?

A: Untuk membuat penggaris horizontal di Markdown, Anda dapat menggunakan salah satu simbol berikut pada baris kosong: tiga tanda bintang (\***), tiga garis (\---), atau tiga garis bawah (\___).

#### T: Bisakah saya menyesuaikan tampilan penggaris horizontal di Markdown?

J: Dalam Markdown standar, tidak ada cara untuk menyesuaikan tampilan penggaris horizontal. Namun, beberapa editor dan ekstensi Markdown tingkat lanjut menawarkan fitur penyesuaian tambahan.

#### T: Apakah penggaris horizontal didukung oleh semua editor Markdown?

J: Ya, sebagian besar editor penurunan harga mendukung penggaris horizontal. Namun, sebaiknya periksa dokumentasi vendor spesifik Anda untuk memastikannya didukung.

#### T: Elemen apa lagi yang bisa saya buat di Markdown?

J: Selain penggaris horizontal, Anda dapat membuat judul, paragraf, daftar, link, gambar, tabel, dan lainnya di Markdown.