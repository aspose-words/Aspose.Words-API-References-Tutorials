---
title: Format Aturan Horizontal Dalam Dokumen Word
linktitle: Format Aturan Horizontal Dalam Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara memformat aturan horizontal di dokumen Word menggunakan Aspose.Words untuk .NET. Panduan langkah demi langkah.
type: docs
weight: 10
url: /id/net/add-content-using-documentbuilder/horizontal-rule-format/
---
Dalam contoh komprehensif ini, Anda akan mempelajari cara memformat aturan horizontal di dokumen Word menggunakan Aspose.Words untuk .NET. Kami akan memandu Anda melalui proses dan memberi Anda cuplikan kode C# yang diperlukan. Di akhir panduan ini, Anda akan dapat menyesuaikan perataan, lebar, tinggi, warna, dan properti aturan horizontal lainnya.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
- Aspose.Words untuk perpustakaan .NET diinstal pada sistem Anda.

## Langkah 1: Buat DocumentBuilder dan Sisipkan Aturan Horizontal
Untuk memulai, buat objek DocumentBuilder dan gunakan metode InsertHorizontalRule untuk menyisipkan aturan horizontal:

```csharp
DocumentBuilder builder = new DocumentBuilder();
Shape shape = builder.InsertHorizontalRule();
```

## Langkah 2: Akses Format Aturan Horizontal
Selanjutnya, akses properti HorizontalRuleFormat dari objek Bentuk untuk mengambil opsi pemformatan:

```csharp
HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
```

## Langkah 3: Sesuaikan Opsi Pemformatan
Sekarang, Anda dapat menyesuaikan berbagai opsi pemformatan untuk aturan horizontal. Misalnya, Anda dapat menyesuaikan perataan, lebar, tinggi, warna, dan bayangan:

```csharp
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;
```

## Langkah 4: Simpan Dokumen
Setelah memformat aturan horizontal, simpan dokumen ke file menggunakan metode Simpan pada objek Dokumen:

```csharp
builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

### Contoh Kode Sumber untuk Format Aturan Horizontal menggunakan Aspose.Words untuk .NET
Berikut adalah kode sumber lengkap untuk memformat aturan horizontal menggunakan Aspose.Words untuk .NET:

```csharp
DocumentBuilder builder = new DocumentBuilder();

Shape shape = builder.InsertHorizontalRule();

HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;

builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

Ingatlah untuk menyesuaikan kode sesuai dengan kebutuhan spesifik Anda dan tingkatkan dengan fungsionalitas tambahan sesuai kebutuhan.

## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara memformat aturan horizontal dalam dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah dan memanfaatkan kode sumber yang disediakan, kini Anda dapat menyesuaikan tampilan aturan horizontal untuk menyempurnakan tata letak visual dokumen Anda.

Bereksperimenlah dengan opsi pemformatan berbeda untuk mendapatkan gaya dan efek yang diinginkan untuk aturan horizontal Anda.

### FAQ untuk format aturan horizontal di dokumen Word

#### T: Dapatkah saya menerapkan warna berbeda pada aturan horizontal?

J: Tentu saja! Dengan Aspose.Words untuk .NET, Anda dapat dengan mudah menyesuaikan warna aturan horizontal dengan mengatur properti Warna ke nilai warna yang diinginkan. Ini memungkinkan Anda mencocokkan aturan horizontal dengan desain keseluruhan dokumen Anda.

#### Q: Apakah mungkin untuk mengatur lebar dan tinggi aturan horizontal?

J: Ya, Anda memiliki kendali penuh atas lebar dan tinggi mistar horizontal. Dengan memodifikasi properti widthpercent dan height, Anda dapat mencapai dimensi yang diinginkan untuk aturan horizontal.

#### T: Dapatkah saya mengubah perataan aturan horizontal dalam dokumen?

J: Tentu saja! Aspose.Words untuk .NET memungkinkan Anda menentukan perataan aturan horizontal menggunakan properti Alignment. Anda dapat memilih dari berbagai opsi seperti Tengah, Kiri, Kanan, dan Rata.

#### T: Dapatkah saya menerapkan bayangan atau warna latar belakang pada aturan horizontal?

A: Ya, Anda dapat menambahkan bayangan atau warna latar belakang pada aturan horizontal. Secara default, properti NoShade disetel ke true, namun Anda dapat menyetelnya ke false dan menentukan bayangan menggunakan metode yang sesuai.

#### T: Dapatkah saya menyisipkan beberapa aturan horizontal dalam satu dokumen?

J: Tentu saja! Anda dapat menyisipkan beberapa aturan horizontal dalam dokumen Word menggunakan Aspose.Words untuk .NET. Cukup ulangi langkah-langkah dalam tutorial sesuai kebutuhan untuk menambahkan aturan horizontal sebanyak yang Anda perlukan.