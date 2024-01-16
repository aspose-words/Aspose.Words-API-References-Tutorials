---
title: Sisipkan Break In Dokumen Word
linktitle: Sisipkan Break In Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyisipkan hentian halaman di dokumen Word menggunakan Aspose.Words untuk .NET. Panduan langkah demi langkah.
type: docs
weight: 10
url: /id/net/add-content-using-documentbuilder/insert-break/
---
Dalam contoh komprehensif ini, Anda akan mempelajari cara menyisipkan hentian halaman ke dalam dokumen Word menggunakan metode InsertBreak di Aspose.Words untuk .NET. Kami akan memandu Anda melalui proses dan memberi Anda cuplikan kode C# yang diperlukan. Di akhir panduan ini, Anda akan dapat mengontrol hentian halaman dalam dokumen Anda.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
- Aspose.Words untuk perpustakaan .NET diinstal pada sistem Anda.

## Langkah 1: Buat Dokumen Baru dan DocumentBuilder
Untuk memulai, buat dokumen baru menggunakan kelas Dokumen dan inisialisasi objek DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 2: Sisipkan Konten dan Hentian Halaman
Selanjutnya, gunakan metode Writeln dari kelas DocumentBuilder untuk menambahkan konten ke dokumen. Untuk menyisipkan hentian halaman, gunakan metode InsertBreak dengan parameter BreakType.PageBreak:

```csharp
builder.Writeln("This is page 1.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 2.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 3.");
```

## Langkah 3: Simpan Dokumen
Setelah memasukkan konten dan hentian halaman, simpan dokumen ke file menggunakan metode Simpan dari kelas Dokumen:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertBreak.docx");
```

### Contoh Kode Sumber untuk Insert Break menggunakan Aspose.Words untuk .NET
Berikut source code lengkap untuk menyisipkan page break menggunakan Aspose.Words for .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("This is page 1.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 2.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 3.");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertBreak.docx");
```

Ingatlah untuk menyesuaikan kode sesuai dengan kebutuhan spesifik Anda dan tingkatkan dengan fungsionalitas tambahan sesuai kebutuhan.


## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara menyisipkan hentian halaman ke dalam dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah dan memanfaatkan kode sumber yang disediakan, kini Anda dapat mengontrol penomoran halaman dan tata letak dokumen Anda dengan menyisipkan hentian halaman pada posisi yang diinginkan.

### FAQ

#### T: Bisakah saya menyisipkan jenis jeda lain selain hentian halaman?

J: Tentu saja! Aspose.Words untuk .NET mendukung berbagai jenis hentian, termasuk hentian halaman, hentian kolom, dan hentian bagian. Anda dapat menggunakan metode InsertBreak dengan parameter BreakType yang berbeda untuk memasukkan tipe break yang diinginkan.

#### T: Bisakah saya menyisipkan hentian halaman di bagian tertentu pada dokumen?

J: Ya, Anda dapat menyisipkan hentian halaman di lokasi tertentu dalam dokumen. Dengan menggunakan DocumentBuilder, Anda dapat mengontrol penempatan hentian halaman berdasarkan konten dan struktur dokumen Anda.

#### T: Apakah hentian halaman akan dipertahankan saat menyimpan dokumen dalam format file berbeda?

J: Ya, hentian halaman yang disisipkan menggunakan Aspose.Words untuk .NET dipertahankan saat menyimpan dokumen dalam format file berbeda, seperti DOCX, PDF, atau RTF. Hal ini memastikan penomoran halaman dan tata letak yang konsisten di berbagai format file.

#### T: Dapatkah saya menyesuaikan tampilan hentian halaman?

J: Hentian halaman tidak terlihat dalam dokumen itu sendiri, namun Anda dapat menyesuaikan format dan tata letak konten sebelum dan sesudah hentian halaman untuk mengontrol tampilan dokumen.

#### T: Apakah Aspose.Words untuk .NET cocok untuk aplikasi desktop dan web?

J: Ya, Aspose.Words for .NET adalah perpustakaan serbaguna yang cocok untuk aplikasi desktop dan web. Baik Anda sedang membangun aplikasi Windows atau sistem berbasis web, Anda dapat mengintegrasikan perpustakaan dengan mudah.