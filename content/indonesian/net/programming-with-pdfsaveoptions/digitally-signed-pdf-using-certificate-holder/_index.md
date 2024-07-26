---
title: Tambahkan Tanda Tangan Digital ke PDF menggunakan Pemegang Sertifikat
linktitle: Tambahkan Tanda Tangan Digital ke PDF menggunakan Pemegang Sertifikat
second_title: API Pemrosesan Dokumen Aspose.Words
description: Amankan file PDF Anda dengan tanda tangan digital menggunakan Aspose.Words untuk .NET. Ikuti panduan langkah demi langkah ini untuk menambahkan tanda tangan digital ke PDF Anda dengan mudah.
type: docs
weight: 10
url: /id/net/programming-with-pdfsaveoptions/digitally-signed-pdf-using-certificate-holder/
---
## Perkenalan

Pernahkah Anda bertanya-tanya bagaimana cara mengamankan dokumen PDF Anda dengan tanda tangan digital? Nah, Anda berada di tempat yang tepat! Tanda tangan digital setara dengan tanda tangan tulisan tangan modern, yang menawarkan cara untuk memverifikasi keaslian dan integritas dokumen digital. Dalam tutorial ini, kami akan menunjukkan cara menambahkan tanda tangan digital ke PDF menggunakan Aspose.Words untuk .NET. Kami akan membahas semuanya mulai dari menyiapkan lingkungan Anda hingga mengeksekusi kode langkah demi langkah. Di akhir panduan ini, Anda akan memiliki PDF yang ditandatangani secara digital, aman dan andal.

## Prasyarat

Sebelum kita mulai, ada beberapa hal yang Anda perlukan:

1.  Aspose.Words for .NET: Pastikan Anda telah menginstal Aspose.Words for .NET. Anda dapat mengunduhnya dari[Asumsikan situs web](https://releases.aspose.com/words/net/).
2. File Sertifikat: Anda memerlukan file sertifikat .pfx untuk menandatangani PDF. Jika tidak memilikinya, Anda dapat membuat sertifikat yang ditandatangani sendiri untuk tujuan pengujian.
3. Visual Studio: Tutorial ini mengasumsikan Anda menggunakan Visual Studio sebagai lingkungan pengembangan Anda.
4. Pengetahuan Dasar tentang C#: Keakraban dengan pemrograman C# dan .NET sangat penting.

## Impor Namespace

Pertama, mari impor namespace yang diperlukan. Ini penting untuk mengakses kelas dan metode yang diperlukan untuk manipulasi dokumen dan tanda tangan digital.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
using System;
```

Mari kita bagi prosesnya menjadi langkah-langkah sederhana dan mudah dikelola.

## Langkah 1: Siapkan Proyek Anda

Buat proyek C# baru di Visual Studio. Tambahkan referensi ke Aspose.Words untuk .NET. Anda dapat melakukan ini melalui NuGet Package Manager dengan mencari "Aspose.Words" dan menginstalnya.

## Langkah 2: Muat atau Buat Dokumen

Anda memerlukan dokumen untuk ditandatangani. Anda dapat memuat dokumen yang sudah ada atau membuat dokumen baru. Untuk tutorial ini, kita akan membuat dokumen baru dan menambahkan beberapa contoh teks.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Tambahkan beberapa teks ke dokumen.
builder.Writeln("Test Signed PDF.");
```

## Langkah 3: Tentukan Detail Tanda Tangan Digital

Sekarang saatnya menyiapkan detail tanda tangan digital. Anda harus menentukan jalur ke file sertifikat .pfx Anda, alasan penandatanganan, lokasi, dan tanggal penandatanganan.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
    DigitalSignatureDetails = new PdfDigitalSignatureDetails(
        CertificateHolder.Create(dataDir + "morzal.pfx", "your_password"), "reason", "location",
        DateTime.Now)
};
```

 Mengganti`"your_password"` dengan kata sandi untuk file .pfx Anda.

## Langkah 4: Simpan Dokumen sebagai PDF yang Ditandatangani Secara Digital

Terakhir, simpan dokumen sebagai PDF dengan tanda tangan digital.

```csharp
doc.Save(dataDir + "DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
```

Dan itu saja! Dokumen Anda sekarang ditandatangani dan disimpan sebagai PDF.

## Kesimpulan

Tanda tangan digital adalah alat yang ampuh untuk memastikan integritas dan keaslian dokumen Anda. Dengan Aspose.Words untuk .NET, menambahkan tanda tangan digital ke file PDF Anda sangatlah mudah dan efisien. Dengan mengikuti panduan langkah demi langkah ini, Anda dapat mengamankan dokumen PDF Anda dan memberikan ketenangan pikiran kepada penerima mengenai keasliannya. Selamat membuat kode!

## FAQ

### Apa itu tanda tangan digital?
Tanda tangan digital adalah bentuk tanda tangan elektronik yang memverifikasi keaslian dan integritas dokumen digital.

### Apakah saya memerlukan sertifikat untuk menambahkan tanda tangan digital?
Ya, Anda memerlukan file sertifikat .pfx untuk menambahkan tanda tangan digital ke PDF Anda.

### Bisakah saya membuat sertifikat yang ditandatangani sendiri untuk pengujian?
Ya, Anda dapat membuat sertifikat yang ditandatangani sendiri untuk tujuan pengujian. Namun, untuk penggunaan produksi, disarankan untuk mendapatkan sertifikat dari otoritas sertifikat tepercaya.

### Apakah Aspose.Words untuk .NET gratis?
 Aspose.Words untuk .NET adalah produk komersial, tetapi Anda dapat mengunduh uji coba gratis dari .NET[Asumsikan situs web](https://releases.aspose.com/).

### Bisakah saya menggunakan Aspose.Words untuk .NET untuk menandatangani jenis dokumen lain?
Ya, Aspose.Words for .NET dapat digunakan untuk menandatangani berbagai jenis dokumen, tidak hanya PDF.