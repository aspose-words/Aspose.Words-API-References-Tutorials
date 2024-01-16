---
title: Sisipkan Bidang Menggunakan Pembuat Bidang
linktitle: Sisipkan Bidang Menggunakan Pembuat Bidang
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara Menyisipkan bidang khusus ke dalam dokumen Word Anda dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-fields/insert-field-using-field-builder/
---

Berikut adalah panduan langkah demi langkah untuk menjelaskan kode sumber C# di bawah ini, yang menggunakan fitur "Sisipkan Bidang menggunakan FieldBuilder" dari Aspose.Words untuk .NET. Pastikan untuk mengikuti setiap langkah dengan hati-hati untuk mendapatkan hasil yang diinginkan.

## Langkah 1: Pengaturan Direktori Dokumen

Dalam kode yang diberikan, Anda harus menentukan direktori dokumen Anda. Ganti nilai "DIREKTORI DOKUMEN ANDA" dengan jalur yang sesuai ke direktori dokumen Anda.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Membuat dokumen

Kita mulai dengan membuat dokumen baru.

```csharp
Document doc = new Document();
```

## Langkah 3: Membangun bidang IF menggunakan FieldBuilder

Kami menggunakan kelas FieldBuilder untuk membuat bidang IF dengan dua bidang MERGEFIELD yang bertumpuk. Dalam contoh ini, kolom IF menampilkan nama depan dan belakang berdasarkan suatu kondisi.

```csharp
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));
```

## Langkah 4: Memasukkan kolom IF ke dalam dokumen

 Kami menggunakan`BuildAndInsert()` metode untuk membuat dan menyisipkan bidang IF di lokasi tertentu dalam dokumen.

```csharp
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();
```

### Contoh kode sumber untuk menyisipkan bidang menggunakan FieldBuilder dengan Aspose.Words untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Pembuatan dokumen.
Document doc = new Document();

// Konstruksi bidang IF menggunakan FieldBuilder.
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));

// Masukkan bidang IF ke dalam dokumen.
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();

doc.Save(dataDir + "InsertFieldWithFieldBuilder.docx");
```

Dalam contoh ini, kita membuat dokumen baru, membuat kolom IF dengan kolom MERGEFIELD bertumpuk, lalu menyisipkan kolom tersebut ke dalam dokumen di lokasi tertentu. Dokumen tersebut kemudian disimpan dengan nama file tertentu.

### FAQ

#### T: Apa yang dimaksud dengan konstruktor bidang di Aspose.Words?

J: Pembuat Bidang di Aspose.Words adalah alat yang ampuh untuk membuat dan memanipulasi bidang dalam dokumen Word. Ia menawarkan fitur-fitur canggih untuk membuat dan menyesuaikan bidang, termasuk memasukkan kode bidang dan mengelola opsi pemformatan.

#### T: Jenis bidang apa yang dapat disisipkan menggunakan pembuat bidang?

J: Pembuat bidang di Aspose.Words memungkinkan Anda menyisipkan berbagai jenis bidang ke dalam dokumen Word. Berikut adalah beberapa contoh tipe bidang yang umum digunakan:

- MERGEFIELD: digunakan untuk menggabungkan data dari sumber eksternal.
- TANGGAL: menampilkan tanggal sekarang.
- HALAMAN: menampilkan nomor halaman saat ini.
- IF: memungkinkan untuk mengkondisikan tampilan suatu konten sesuai dengan suatu kondisi.
- TOC: secara otomatis menghasilkan daftar isi berdasarkan gaya judul dokumen.

#### T: Bagaimana cara menyesuaikan bidang yang disisipkan dengan pembuat bidang?

J: Pembuat bidang menawarkan opsi penyesuaian untuk bidang yang disisipkan. Anda dapat menggunakan metode dan properti konstruktor bidang untuk mengatur opsi seperti pemformatan bidang, argumen, sakelar, dan nilai default. Misalnya, Anda dapat mengatur format tanggal, format angka, pemisah ribuan, dll.
  