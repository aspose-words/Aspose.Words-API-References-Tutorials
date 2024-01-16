---
title: Sisipkan Gambar Sebaris Dalam Dokumen Word
linktitle: Sisipkan Gambar Sebaris Dalam Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyisipkan gambar sebaris di dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/add-content-using-documentbuilder/insert-inline-image/
---
Dalam tutorial komprehensif ini, Anda akan mempelajari cara menyisipkan gambar sebaris ke dalam dokumen Word menggunakan Aspose.Words untuk .NET. Kami akan memandu Anda melalui proses dan memberi Anda cuplikan kode C# yang diperlukan. Di akhir panduan ini, Anda akan dapat menambahkan gambar langsung ke teks dokumen Anda.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
- Aspose.Words untuk perpustakaan .NET diinstal pada sistem Anda.

## Langkah 1: Buat Dokumen Baru dan DocumentBuilder
Untuk memulai, buat dokumen baru menggunakan kelas Dokumen dan inisialisasi objek DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 2: Sisipkan Gambar Sebaris
Selanjutnya, gunakan metode InsertImage dari kelas DocumentBuilder untuk menyisipkan gambar sebaris ke dalam dokumen. Berikan jalur file gambar sebagai parameter:

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## Langkah 3: Simpan Dokumen
Setelah menyisipkan gambar sebaris, simpan dokumen ke file menggunakan metode Simpan dari kelas Dokumen:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

### Contoh Kode Sumber untuk Menyisipkan Gambar Sebaris menggunakan Aspose.Words untuk .NET
Berikut kode sumber lengkap untuk menyisipkan gambar sebaris menggunakan Aspose.Words for .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertImage(ImagesDir + "Transparent background logo.png");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara menyisipkan gambar sebaris ke dalam dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah dan memanfaatkan kode sumber yang disediakan, kini Anda dapat menambahkan gambar dengan lancar ke dalam teks dokumen Anda.

Gambar sebaris berguna untuk berbagai skenario, seperti menambahkan ilustrasi, logo, atau elemen visual lainnya langsung ke alur dokumen.

### FAQ untuk menyisipkan gambar sebaris di dokumen Word

#### T: Dapatkah saya mengubah ukuran gambar sebaris dalam dokumen Word?

J: Ya, Anda dapat mengubah ukuran gambar sebaris menggunakan Aspose.Words untuk .NET. Setelah menyisipkan gambar, Anda dapat memanipulasi ukurannya dengan menyesuaikan properti lebar dan tinggi objek Bentuk yang mewakili gambar.

#### T: Apakah mungkin menambahkan teks alternatif ke gambar sebaris untuk tujuan aksesibilitas?

J: Ya, Anda dapat menambahkan teks alternatif ke gambar sebaris untuk meningkatkan aksesibilitas. Aspose.Words untuk .NET mendukung penambahan teks alternatif ke gambar, memungkinkan pembaca layar dan teknologi bantu lainnya mendeskripsikan konten gambar kepada pengguna tunanetra.

#### T: Dapatkah saya menerapkan pemformatan atau gaya pada gambar sebaris?

J: Tentu saja! Aspose.Words untuk .NET menyediakan opsi pemformatan ekstensif untuk gambar sebaris. Anda dapat menerapkan berbagai gaya, batas, efek, dan atribut pemformatan lainnya pada gambar agar sesuai dengan desain visual dokumen Anda.

#### T: Apakah Aspose.Words untuk .NET mendukung penyisipan gambar dari aliran atau array byte?

J: Ya, Anda dapat menyisipkan gambar sebaris dari aliran atau array byte menggunakan Aspose.Words untuk .NET. Hal ini memungkinkan Anda untuk bekerja dengan gambar yang diambil dari sumber eksternal atau gambar yang dihasilkan secara dinamis.

#### T: Dapatkah saya menyisipkan gambar pada posisi tertentu dalam konten teks?

J: Ya, kelas DocumentBuilder di Aspose.Words untuk .NET memberikan kontrol yang tepat atas posisi penyisipan gambar sebaris. Anda dapat menentukan lokasi persisnya di dalam teks tempat gambar harus disisipkan.