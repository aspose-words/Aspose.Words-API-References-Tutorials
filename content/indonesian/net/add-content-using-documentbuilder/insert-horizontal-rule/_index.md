---
title: Sisipkan Aturan Horizontal Dalam Dokumen Word
linktitle: Sisipkan Aturan Horizontal Dalam Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyisipkan aturan horizontal di dokumen Word menggunakan Aspose.Words untuk .NET. Panduan langkah demi langkah.
type: docs
weight: 10
url: /id/net/add-content-using-documentbuilder/insert-horizontal-rule/
---
Dalam contoh komprehensif ini, Anda akan mempelajari cara menyisipkan aturan horizontal ke dalam dokumen Word menggunakan Aspose.Words untuk .NET. Kami akan memandu Anda melalui proses dan memberi Anda cuplikan kode C# yang diperlukan. Di akhir panduan ini, Anda akan dapat menambahkan aturan horizontal ke dokumen Anda untuk pemisahan dan pengorganisasian visual.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
- Aspose.Words untuk perpustakaan .NET diinstal pada sistem Anda.

## Langkah 1: Buat Dokumen Baru dan DocumentBuilder
Untuk memulai, buat dokumen baru menggunakan kelas Dokumen dan inisialisasi objek DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 2: Masukkan Aturan Horizontal
Selanjutnya, gunakan metode Writeln dari kelas DocumentBuilder untuk menambahkan teks deskriptif dan kemudian menyisipkan aturan horizontal:

```csharp
builder.Writeln("Insert a horizontal rule shape into the document.");
builder.InsertHorizontalRule();
```

## Langkah 3: Simpan Dokumen
Setelah memasukkan aturan horizontal, simpan dokumen ke file menggunakan metode Simpan dari kelas Dokumen:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHorizontalRule.docx");
```

### Contoh Kode Sumber untuk Menyisipkan Aturan Horizontal menggunakan Aspose.Words untuk .NET
Berikut source code lengkap untuk menyisipkan aturan horizontal menggunakan Aspose.Words for .NET:
Aturan horizontal berguna untuk berbagai skenario, seperti membagi bagian, membuat jeda visual, atau menyorot informasi penting.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Insert a horizontal rule shape into the document.");
builder.InsertHorizontalRule();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHorizontalRule.docx");
```

Ingatlah untuk menyesuaikan kode sesuai dengan kebutuhan spesifik Anda dan tingkatkan dengan fungsionalitas tambahan sesuai kebutuhan.

## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara menyisipkan aturan horizontal ke dalam dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah dan memanfaatkan kode sumber yang disediakan, kini Anda dapat memisahkan dan mengatur dokumen secara visual menggunakan aturan horizontal.

### FAQ untuk menyisipkan aturan horizontal di dokumen Word

#### T: Dapatkah saya menyesuaikan tampilan aturan horizontal?

J: Ya, tentu saja! Aspose.Words untuk .NET menyediakan berbagai properti untuk menyesuaikan tampilan aturan horizontal. Anda dapat menyesuaikan lebar, tinggi, perataan, warna, dan bayangan agar sesuai dengan estetika dokumen Anda.

#### T: Dapatkah saya menambahkan beberapa aturan horizontal dalam satu dokumen?

J: Tentu saja! Anda dapat menyisipkan aturan horizontal sebanyak yang diperlukan dalam dokumen Word menggunakan Aspose.Words untuk .NET. Cukup ulangi proses penyisipan untuk menambahkan beberapa jeda visual atau pemisah bagian.

#### T: Apakah aturan horizontal kompatibel dengan format file lain, seperti PDF?

J: Ya, aturan horizontal yang disisipkan menggunakan Aspose.Words untuk .NET kompatibel dengan berbagai format file, termasuk DOCX dan PDF. Ini berarti Anda dapat mengekspor dokumen Anda dalam format berbeda dengan tetap mempertahankan aturan horizontal.

#### T: Dapatkah saya menyisipkan aturan horizontal secara terprogram pada posisi tertentu dalam dokumen?

J: Tentu saja! Aspose.Words untuk .NET memungkinkan Anda memposisikan aturan horizontal di lokasi tertentu dalam dokumen secara terprogram. Anda dapat mengontrol penempatannya berdasarkan konten dan struktur dokumen Anda.

#### T: Apakah Aspose.Words untuk .NET cocok untuk aplikasi desktop dan web?

J: Ya, Aspose.Words untuk .NET serbaguna dan dapat digunakan di aplikasi desktop dan web. Baik Anda sedang membangun aplikasi Windows atau sistem berbasis web, Anda dapat mengintegrasikan perpustakaan dengan mudah.