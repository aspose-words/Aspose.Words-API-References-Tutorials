---
title: Membuat Dan Menandatangani Baris Tanda Tangan Baru
linktitle: Membuat Dan Menandatangani Baris Tanda Tangan Baru
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara membuat dan menandatangani baris tanda tangan secara digital di dokumen Word menggunakan Aspose.Words untuk .NET dengan tutorial langkah demi langkah ini. Sempurna untuk otomatisasi dokumen.
type: docs
weight: 10
url: /id/net/programming-with-digital-signatures/creating-and-signing-new-signature-line/
---
## Perkenalan

Hai! Jadi, Anda memiliki dokumen Word dan Anda perlu menambahkan baris tanda tangan lalu menandatanganinya secara digital. Kedengarannya rumit? Sama sekali tidak! Berkat Aspose.Words untuk .NET, Anda dapat mencapainya dengan lancar hanya dengan beberapa baris kode. Dalam tutorial ini, kami akan memandu Anda melalui seluruh proses mulai dari menyiapkan lingkungan hingga menyimpan dokumen Anda dengan tanda tangan baru yang keren. Siap? Ayo selami!

## Prasyarat

Sebelum kita beralih ke kode, pastikan Anda memiliki semua yang Anda butuhkan:
1.  Aspose.Words untuk .NET - Anda bisa[Unduh di sini](https://releases.aspose.com/words/net/).
2. Lingkungan Pengembangan .NET - Visual Studio sangat disarankan.
3. Dokumen untuk Ditandatangani - Buat dokumen Word sederhana atau gunakan yang sudah ada.
4.  File Sertifikat - Ini diperlukan untuk tanda tangan digital. Anda dapat menggunakan a`.pfx` mengajukan.
5. Gambar untuk Garis Tanda Tangan - Opsional, file gambar untuk tanda tangan.

## Impor Namespace

Pertama, kita perlu mengimpor namespace yang diperlukan. Langkah ini penting karena menyiapkan lingkungan untuk menggunakan fungsionalitas Aspose.Words.

```csharp
using System;
using System.IO;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Saving;
using Aspose.Words.Signing;
```

## Langkah 1: Menyiapkan Direktori Dokumen

Setiap proyek membutuhkan awal yang baik. Mari siapkan jalur ke direktori dokumen Anda. Di sinilah dokumen Anda akan disimpan dan diambil.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Membuat Dokumen Baru

Sekarang, mari buat dokumen Word baru menggunakan Aspose.Words. Ini akan menjadi kanvas tempat kita menambahkan baris tanda tangan.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 3: Memasukkan Garis Tanda Tangan

 Ini adalah dimana keajaiban terjadi. Kami memasukkan baris tanda tangan ke dalam dokumen kami menggunakan`DocumentBuilder` kelas.

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## Langkah 4: Menyimpan Dokumen dengan Garis Tanda Tangan

Setelah baris tanda tangan terpasang, kita perlu menyimpan dokumen tersebut. Ini adalah langkah perantara sebelum kami melanjutkan penandatanganannya.

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

## Langkah 5: Menyiapkan Opsi Penandatanganan

Sekarang, mari siapkan opsi untuk menandatangani dokumen. Ini termasuk menentukan ID baris tanda tangan dan gambar yang akan digunakan.

```csharp
SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    SignatureLineImage = File.ReadAllBytes(dataDir + "Enhanced Windows MetaFile.emf")
};
```

## Langkah 6: Memuat Sertifikat

Tanda tangan digital memerlukan sertifikat. Di sini, kita memuat file sertifikat yang akan digunakan untuk menandatangani dokumen.

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

## Langkah 7: Menandatangani Dokumen

 Ini adalah langkah terakhir. Kami menggunakan`DigitalSignatureUtil`kelas untuk menandatangani dokumen. Dokumen yang ditandatangani disimpan dengan nama baru.

```csharp
DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
    dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);
```

## Kesimpulan

Dan itu dia! Dengan langkah-langkah ini, Anda telah berhasil membuat dokumen Word baru, menambahkan baris tanda tangan, dan menandatanganinya secara digital menggunakan Aspose.Words untuk .NET. Ini adalah alat canggih yang membuat otomatisasi dokumen menjadi mudah. Baik Anda berurusan dengan kontrak, perjanjian, atau dokumen formal apa pun, metode ini memastikan dokumen tersebut ditandatangani dan diautentikasi dengan aman.

## FAQ

### Bisakah saya menggunakan format gambar lain untuk baris tanda tangan?
Ya, Anda dapat menggunakan berbagai format gambar seperti PNG, JPG, BMP, dll.

###  Apakah perlu menggunakan a`.pfx` file for the certificate?
 Iya`.pfx` file adalah format umum untuk menyimpan informasi kriptografi termasuk sertifikat dan kunci pribadi.

### Bisakah saya menambahkan beberapa baris tanda tangan dalam satu dokumen?
Sangat! Anda dapat menyisipkan beberapa baris tanda tangan dengan mengulangi langkah penyisipan untuk setiap tanda tangan.

### Bagaimana jika saya tidak memiliki sertifikat digital?
Anda harus mendapatkan sertifikat digital dari otoritas sertifikat tepercaya atau membuatnya menggunakan alat seperti OpenSSL.

### Bagaimana cara memverifikasi tanda tangan digital pada dokumen?
Anda dapat membuka dokumen yang ditandatangani di Word dan membuka detail tanda tangan untuk memverifikasi keaslian dan integritas tanda tangan.