---
title: Tautan otomatis
linktitle: Tautan otomatis
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyisipkan tautan otomatis dengan Aspose.Words untuk .NET Panduan langkah demi langkah.
type: docs
weight: 10
url: /id/net/working-with-markdown/autolink/
---

Dalam contoh ini, kami akan menjelaskan cara menggunakan fitur "Tautan Otomatis" dengan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda memasukkan hyperlink ke dalam dokumen Anda secara otomatis.

## Langkah 1: Menggunakan pembuat dokumen

Pertama, kita akan menggunakan pembuat dokumen untuk menambahkan konten ke dokumen kita.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Langkah 2: Memasukkan hyperlink

 Kita dapat menyisipkan hyperlink menggunakan`InsertHyperlink` metode pembuat dokumen. Kami menentukan URL dan teks yang akan ditampilkan untuk tautan tersebut.

```csharp
builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", salah);
```

## Langkah 3: Memasukkan alamat email sebagai tautan

Kita juga dapat memasukkan alamat email sebagai link menggunakan awalan "mailto:". Ini akan memungkinkan pengguna mengeklik tautan untuk membuka klien email default mereka.

```csharp
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```

## Langkah 4: Menyimpan dokumen

Terakhir, kita bisa menyimpan dokumen dalam format yang diinginkan.

### Contoh Source Code untuk Autolink menggunakan Aspose.Words for .NET


```csharp
// Gunakan pembuat dokumen untuk menambahkan konten ke dokumen.
DocumentBuilder builder = new DocumentBuilder();

// Sisipkan hyperlink.
builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", salah);
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```


Selamat! Anda sekarang telah mempelajari cara menggunakan fitur "Tautan Otomatis" dengan Aspose.Words untuk .NET.


### FAQ

#### T: Bagaimana cara membuat tautan otomatis ke alamat URL di Aspose.Words?

A: Untuk membuat tautan otomatis ke alamat URL di Aspose.Words, Anda dapat menggunakan`<a>` tandai dengan`href` atribut yang berisi alamat URL. Misalnya, Anda bisa menggunakan`<a href="https://www.aspose.com">https://www.aspose.com</a>` untuk secara otomatis menautkan ke "https: //www.aspose.com".

#### T: Apakah mungkin untuk menyesuaikan teks tampilan tautan otomatis di Aspose.Words?

 A: Ya, Anda dapat menyesuaikan teks tampilan tautan otomatis di Aspose.Words. Daripada menggunakan alamat URL sebagai teks tampilan, Anda dapat menggunakan teks lain dengan mengganti konten di antara`<a>` tag. Misalnya, Anda bisa menggunakan`<a href="https://www.aspose.com">Click here</a>` untuk menampilkan teks "Klik di sini" sebagai tautan otomatis.

#### T: Bagaimana cara menambahkan atribut tambahan ke tautan otomatis di Aspose.Words?

 A: Untuk menambahkan atribut tambahan pada tautan otomatis di Aspose.Words, Anda dapat menggunakan atribut HTML tambahan di dalamnya`<a>` menandai. Misalnya, Anda bisa menggunakan`<a href="https://www.aspose.com" target="_blank">Link</a>` untuk membuka tautan di jendela atau tab baru menggunakan` attribute target="_blank"`.