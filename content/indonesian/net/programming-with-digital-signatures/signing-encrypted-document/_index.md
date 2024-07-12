---
title: Menandatangani Dokumen Word Terenkripsi
linktitle: Menandatangani Dokumen Word Terenkripsi
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menandatangani dokumen Word terenkripsi menggunakan Aspose.Words untuk .NET dengan panduan langkah demi langkah yang mendetail ini. Sempurna untuk pengembang.
type: docs
weight: 10
url: /id/net/programming-with-digital-signatures/signing-encrypted-document/
---
## Perkenalan

Pernah bertanya-tanya bagaimana cara menandatangani dokumen Word terenkripsi? Hari ini, kita akan menjalani proses ini menggunakan Aspose.Words untuk .NET. Bersiaplah dan bersiaplah untuk tutorial yang mendetail, menarik, dan menyenangkan!

## Prasyarat

Sebelum mendalami kodenya, pastikan Anda memiliki semua yang Anda perlukan:

1.  Aspose.Words untuk .NET: Unduh dan instal dari[Di Sini](https://releases.aspose.com/words/net/).
2. Visual Studio: Pastikan Anda telah menginstalnya.
3. Sertifikat yang Valid: Anda memerlukan file sertifikat .pfx.
4. Pengetahuan Dasar C#: Memahami dasar-dasarnya akan membuat tutorial ini lebih lancar.

## Impor Namespace

Pertama, mari impor namespace yang diperlukan. Ini sangat penting untuk mengakses fungsionalitas Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
using Aspose.Words.DigitalSignatures;
```

Sekarang, mari kita bagi prosesnya menjadi langkah-langkah sederhana dan mudah dilakukan.

## Langkah 1: Menyiapkan Proyek Anda

Hal pertama yang pertama, siapkan proyek Visual Studio Anda. Buka Visual Studio dan buat Aplikasi Konsol C# baru. Beri nama sesuatu yang deskriptif seperti "SignEncryptedWordDoc".

## Langkah 2: Menambahkan Aspose.Words ke Proyek Anda

Selanjutnya, kita perlu menambahkan Aspose.Words ke proyek Anda. Ada beberapa cara untuk melakukan ini, namun menggunakan NuGet adalah yang paling sederhana. 

1. Buka Konsol Manajer Paket NuGet dari Alat > Manajer Paket NuGet > Konsol Manajer Paket.
2. Jalankan perintah berikut:

```powershell
Install-Package Aspose.Words
```

## Langkah 3: Mempersiapkan Direktori Dokumen

Anda memerlukan direktori untuk menyimpan dokumen dan sertifikat Word Anda. Mari kita buat satu.

1. Buat direktori di komputer Anda. Untuk mempermudah, sebut saja "Direktori Dokumen".
2. Tempatkan dokumen Word Anda (misalnya, "Document.docx") dan sertifikat .pfx Anda (misalnya, "morzal.pfx") di direktori ini.

## Langkah 4: Menulis Kode

 Sekarang, mari selami kodenya. Bukalah`Program.cs` file dan mulai dengan menyiapkan jalur ke direktori dokumen Anda dan menginisialisasi`SignOptions` dengan kata sandi dekripsi.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionPassword" };
```

## Langkah 5: Memuat Sertifikat

 Selanjutnya, muat sertifikat Anda menggunakan`CertificateHolder`kelas. Ini memerlukan jalur ke file .pfx dan kata sandi sertifikat.

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

## Langkah 6: Menandatangani Dokumen

 Terakhir, gunakan`DigitalSignatureUtil.Sign` metode untuk menandatangani dokumen Word terenkripsi Anda. Metode ini memerlukan file input, file output, pemegang sertifikat, dan opsi tanda.

```csharp
DigitalSignatureUtil.Sign(
    dataDir + "Document.docx",
    dataDir + "DigitallySignedDocument.docx",
    certHolder,
    signOptions);
```

## Langkah 7: Menjalankan Kode

Simpan file Anda dan jalankan proyek. Jika semuanya sudah diatur dengan benar, Anda akan melihat dokumen yang Anda tandatangani di direktori yang ditentukan.

## Kesimpulan

Dan itu dia! Anda telah berhasil menandatangani dokumen Word terenkripsi menggunakan Aspose.Words untuk .NET. Dengan perpustakaan canggih ini, penandatanganan digital menjadi mudah, bahkan untuk file terenkripsi. Selamat membuat kode!

## FAQ

### Bisakah saya menggunakan jenis sertifikat lain?
Ya, Aspose.Words mendukung berbagai jenis sertifikat, asalkan formatnya benar.

### Apakah mungkin untuk menandatangani banyak dokumen sekaligus?
Sangat! Anda dapat menelusuri kumpulan dokumen dan menandatangani masing-masing dokumen secara terprogram.

### Bagaimana jika saya lupa kata sandi dekripsi?
Sayangnya, tanpa kata sandi dekripsi, Anda tidak akan dapat menandatangani dokumen tersebut.

### Bisakah saya menambahkan tanda tangan yang terlihat pada dokumen?
Ya, Aspose.Words memungkinkan Anda menambahkan tanda tangan digital yang terlihat juga.

### Apakah ada cara untuk memverifikasi tanda tangan?
 Ya, Anda dapat menggunakan`DigitalSignatureUtil.Verify` metode untuk memverifikasi tanda tangan.