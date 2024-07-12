---
title: Buat Baris Tanda Tangan Baru Dan Tetapkan Id Penyedia
linktitle: Buat Baris Tanda Tangan Baru Dan Tetapkan Id Penyedia
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara membuat baris tanda tangan baru dan mengatur ID penyedia di dokumen Word menggunakan Aspose.Words untuk .NET. Panduan langkah demi langkah.
type: docs
weight: 10
url: /id/net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
---
## Perkenalan

Hai, penggemar teknologi! Pernah bertanya-tanya bagaimana cara menambahkan baris tanda tangan di dokumen Word Anda secara terprogram? Nah, hari ini kita akan mendalami hal itu menggunakan Aspose.Words untuk .NET. Panduan ini akan memandu Anda melalui setiap langkah, membuatnya sangat mudah untuk membuat baris tanda tangan baru dan mengatur ID penyedia di dokumen Word Anda. Baik Anda mengotomatiskan pemrosesan dokumen atau hanya ingin menyederhanakan alur kerja Anda, tutorial ini siap membantu Anda.

## Prasyarat

Sebelum kita mengotori tangan kita, pastikan kita memiliki semua yang kita butuhkan:

1.  Aspose.Words untuk .NET: Jika Anda belum melakukannya, unduhlah[Di Sini](https://releases.aspose.com/words/net/).
2. Lingkungan Pengembangan: Visual Studio atau lingkungan pengembangan C# lainnya.
3. .NET Framework: Pastikan Anda telah menginstal .NET Framework.
4. Sertifikat PFX: Untuk menandatangani dokumen, Anda memerlukan sertifikat PFX. Anda bisa mendapatkannya dari otoritas sertifikat tepercaya.

## Impor Namespace

Hal pertama yang pertama, mari impor namespace yang diperlukan dalam proyek C# Anda:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Signing;
using System;
```

Baiklah, mari kita langsung ke seluk beluknya. Berikut rincian detail setiap langkah untuk membuat baris tanda tangan baru dan menetapkan ID penyedia.

## Langkah 1: Buat Dokumen Baru

Untuk memulai, kita perlu membuat dokumen Word baru. Ini akan menjadi kanvas untuk garis tanda tangan kita.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Dalam cuplikan ini, kami menginisialisasi yang baru`Document` dan sebuah`DocumentBuilder` . Itu`DocumentBuilder` membantu kami menambahkan elemen ke dokumen kami.

## Langkah 2: Tentukan Opsi Garis Tanda Tangan

Selanjutnya, kita menentukan opsi untuk baris tanda tangan kita. Ini termasuk nama penandatangan, jabatan, email, dan detail lainnya.

```csharp
SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
    Signer = "vderyushev",
    SignerTitle = "QA",
    Email = "vderyushev@aspose.com",
    ShowDate = true,
    DefaultInstructions = false,
    Instructions = "Please sign here.",
    AllowComments = true
};
```

Opsi ini mempersonalisasi garis tanda tangan, menjadikannya jelas dan profesional.

## Langkah 3: Masukkan Baris Tanda Tangan

Dengan menetapkan pilihan kita, sekarang kita dapat memasukkan baris tanda tangan ke dalam dokumen.

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

 Di sini, itu`InsertSignatureLine` metode menambahkan baris tanda tangan, dan kami menetapkan ID penyedia unik ke dalamnya.

## Langkah 4: Simpan Dokumen

Setelah menyisipkan baris tanda tangan, mari kita simpan dokumennya.

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

Ini menyimpan dokumen Anda dengan baris tanda tangan yang baru ditambahkan.

## Langkah 5: Siapkan Opsi Penandatanganan

Sekarang, kita perlu menyiapkan opsi untuk menandatangani dokumen. Ini termasuk ID baris tanda tangan, ID penyedia, komentar, dan waktu penandatanganan.

```csharp
SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    ProviderId = signatureLine.ProviderId,
    Comments = "Document was signed by vderyushev",
    SignTime = DateTime.Now
};
```

Opsi ini memastikan dokumen ditandatangani dengan rincian yang benar.

## Langkah 6: Buat Pemegang Sertifikat

Untuk menandatangani dokumen, kami akan menggunakan sertifikat PFX. Mari buat pemegang sertifikat untuk itu.

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

 Pastikan untuk mengganti`"morzal.pfx"` dengan file sertifikat Anda yang sebenarnya dan`"aw"` dengan kata sandi sertifikat Anda.

## Langkah 7: Tandatangani Dokumen

Terakhir, kami menandatangani dokumen menggunakan utilitas tanda tangan digital.

```csharp
DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
    dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);
```

Ini menandatangani dokumen dan menyimpannya sebagai file baru.

## Kesimpulan

Dan itu dia! Anda telah berhasil membuat baris tanda tangan baru dan mengatur ID penyedia di dokumen Word menggunakan Aspose.Words untuk .NET. Pustaka yang kuat ini membuatnya sangat mudah untuk mengelola dan mengotomatiskan tugas pemrosesan dokumen. Cobalah dan lihat bagaimana ini dapat menyederhanakan alur kerja Anda.

## FAQ

### Bisakah saya menyesuaikan tampilan garis tanda tangan?
Sangat! Anda dapat mengubah berbagai opsi di`SignatureLineOptions` untuk memenuhi kebutuhan Anda.

### Bagaimana jika saya tidak memiliki sertifikat PFX?
Anda harus mendapatkannya dari otoritas sertifikat tepercaya. Ini penting untuk menandatangani dokumen secara digital.

### Bisakah saya menambahkan beberapa baris tanda tangan ke dokumen?
Ya, Anda dapat menambahkan baris tanda tangan sebanyak yang diperlukan dengan mengulangi proses penyisipan dengan opsi berbeda.

### Apakah Aspose.Words untuk .NET kompatibel dengan .NET Core?
Ya, Aspose.Words untuk .NET mendukung .NET Core, menjadikannya serbaguna untuk lingkungan pengembangan yang berbeda.

### Seberapa amankah tanda tangan digital?
Tanda tangan digital yang dibuat dengan Aspose.Words sangat aman, asalkan Anda menggunakan sertifikat yang valid dan tepercaya.