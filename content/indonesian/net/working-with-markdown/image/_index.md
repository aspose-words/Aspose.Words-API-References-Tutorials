---
title: Gambar
linktitle: Gambar
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyisipkan dan menyesuaikan gambar dengan Aspose.Words untuk .NET Panduan langkah demi langkah.
type: docs
weight: 10
url: /id/net/working-with-markdown/image/
---

Dalam contoh ini, kami akan menjelaskan cara menggunakan fitur gambar dengan Aspose.Words untuk .NET. Gambar memungkinkan Anda menyisipkan ilustrasi dan grafik ke dalam dokumen.

## Langkah 1: Menggunakan pembuat dokumen

Pertama, kita akan menggunakan pembuat dokumen untuk menambahkan konten ke dokumen kita.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Langkah 2: Memasukkan gambar

 Kita dapat menyisipkan gambar menggunakan`Shape` kelas dan menentukan jenis gambar, di sini`ShapeType.Image` Kami juga mengatur jenis bungkus gambar`WrapType.Inline`.

```csharp
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape. WrapType = WrapType. Inline;
```

## Langkah 3: Kustomisasi Gambar

 Kami menyesuaikan gambar dengan menentukan jalur lengkapnya, misalnya`"/attachment/1456/pic001.png"`, dan menambahkan judul pada gambar.

```csharp
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "Title";
```

### Contoh kode sumber untuk gambar dengan Aspose.Words untuk .NET

```csharp
// Gunakan pembuat dokumen untuk menambahkan konten ke dokumen.
DocumentBuilder builder = new DocumentBuilder();

// Sisipkan gambar.
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape.WrapType = WrapType.Inline;
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "title";
builder.InsertNode(shape);
```

Selamat! Anda sekarang telah mempelajari cara menggunakan fitur gambar dengan Aspose.Words untuk .NET.


### FAQ

#### T: Bagaimana cara menyisipkan gambar dari file lokal ke Aspose.Words?

 A: Untuk menyisipkan gambar dari file lokal ke Aspose.Words, Anda dapat menggunakan`Shape` kelas dan`InsertImage` metode.

#### T: Bisakah saya menyisipkan gambar dari URL di Aspose.Words?

 A: Ya, Anda dapat menyisipkan gambar dari URL di Aspose.Words. Anda dapat menggunakan hal yang sama`InsertImage` metode dan tentukan URL gambar alih-alih jalur file lokal.

#### T: Bagaimana cara mengubah ukuran gambar di Aspose.Words?

 A: Untuk mengubah ukuran gambar di Aspose.Words, Anda dapat menggunakan`Width` Dan`Height` properti dari`Shape` obyek.

#### T: Dapatkah saya menerapkan filter pada gambar di Aspose.Words?

A: Ya, Anda dapat menerapkan filter pada gambar di Aspose.Words. Misalnya, Anda dapat menerapkan filter buram pada gambar menggunakan`ApplyGaussianBlur` metode`Shape` obyek.

#### T: Bagaimana cara mengganti satu gambar dengan gambar lain di Aspose.Words?

 A: Untuk mengganti satu gambar dengan gambar lainnya di Aspose.Words, Anda dapat menggunakan`Replace` metode`Shape` kelas. Metode ini mengambil parameter tersebut`Shape` objek gambar yang akan diganti dan`Shape` objek gambar baru.