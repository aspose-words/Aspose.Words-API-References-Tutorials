---
title: Tetapkan Id Penyedia Tanda Tangan Di Dokumen Word
linktitle: Tetapkan Id Penyedia Tanda Tangan Di Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Tetapkan ID Penyedia Tanda Tangan dengan aman di dokumen Word menggunakan Aspose.Words untuk .NET. Ikuti panduan terperinci kami sepanjang 2000 kata untuk menandatangani dokumen Anda secara digital.
type: docs
weight: 10
url: /id/net/programming-with-digital-signatures/set-signature-provider-id/
---
## Perkenalan

Hai! Jadi, Anda punya dokumen Word luar biasa yang memerlukan tanda tangan digital, bukan? Namun bukan sembarang tanda tangan—Anda perlu menyetel ID Penyedia Tanda Tangan tertentu. Baik Anda menangani dokumen hukum, kontrak, atau dokumen apa pun, menambahkan tanda tangan digital yang aman sangatlah penting. Dalam tutorial ini, saya akan memandu Anda melalui seluruh proses pengaturan ID Penyedia Tanda Tangan di dokumen Word menggunakan Aspose.Words untuk .NET. Siap? Ayo selami!

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal berikut:

1. Aspose.Words untuk .NET Library: Jika Anda belum melakukannya,[Unduh di sini](https://releases.aspose.com/words/net/).
2. Lingkungan Pengembangan: Visual Studio atau IDE apa pun yang kompatibel dengan C#.
3. Dokumen Word: Dokumen dengan baris tanda tangan (`Signature line.docx`).
4.  Sertifikat Digital: A`.pfx` file sertifikat (misalnya,`morzal.pfx`).
5. Pengetahuan Dasar C#: Dasar-dasarnya saja—jangan khawatir, kami siap membantu!

Sekarang, mari beraksi!

## Impor Namespace

Hal pertama yang pertama, pastikan Anda menyertakan namespace yang diperlukan dalam proyek Anda. Ini penting untuk mengakses perpustakaan Aspose.Words dan kelas terkait.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.DigitalSignatures;
```

Baiklah, mari kita bagi menjadi langkah-langkah sederhana dan mudah dicerna.

## Langkah 1: Muat Dokumen Word Anda

Langkah pertama adalah memuat dokumen Word Anda yang berisi baris tanda tangan. Dokumen ini akan dimodifikasi untuk menyertakan tanda tangan digital dengan ID Penyedia Tanda Tangan yang ditentukan.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");
```

 Di sini, kami menentukan direktori tempat dokumen Anda berada. Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke dokumen Anda.

## Langkah 2: Akses Jalur Tanda Tangan

Selanjutnya, kita perlu mengakses baris tanda tangan di dalam dokumen. Garis tanda tangan disematkan sebagai objek bentuk di dokumen Word.

```csharp
SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

 Baris kode ini mendapatkan bentuk pertama di badan bagian pertama dokumen dan mengubahnya menjadi a`SignatureLine` obyek.

## Langkah 3: Siapkan Opsi Masuk

Sekarang, kita membuat opsi tanda, yang mencakup ID Penyedia dan ID Baris Tanda Tangan dari baris tanda tangan yang diakses.

```csharp
SignOptions signOptions = new SignOptions
{
    ProviderId = signatureLine.ProviderId,
    SignatureLineId = signatureLine.Id
};
```

Opsi ini akan digunakan saat menandatangani dokumen untuk memastikan ID Penyedia Tanda Tangan yang benar telah ditetapkan.

## Langkah 4: Muat Sertifikat

 Untuk menandatangani dokumen secara digital, Anda memerlukan sertifikat. Inilah cara Anda memuat`.pfx` mengajukan:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

 Mengganti`"aw"` dengan kata sandi untuk file sertifikat Anda jika ada.

## Langkah 5: Tandatangani Dokumen

 Terakhir, saatnya menandatangani dokumen menggunakan`DigitalSignatureUtil.Sign` metode.

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
    dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);
```

 Ini menandatangani dokumen Anda dan menyimpannya sebagai file baru,`Digitally signed.docx`.

## Kesimpulan

Dan itu dia! Anda telah berhasil menetapkan ID Penyedia Tanda Tangan di dokumen Word menggunakan Aspose.Words untuk .NET. Proses ini tidak hanya mengamankan dokumen Anda tetapi juga memastikan dokumen tersebut mematuhi standar tanda tangan digital. Sekarang, lanjutkan dan coba dengan dokumen Anda. Ada pertanyaan? Lihat FAQ di bawah atau klik[Asumsikan forum dukungan](https://forum.aspose.com/c/words/8).

## FAQ

### Apa itu ID Penyedia Tanda Tangan?

ID Penyedia Tanda Tangan secara unik mengidentifikasi penyedia tanda tangan digital, memastikan keaslian dan keamanan.

### Bisakah saya menggunakan file .pfx untuk penandatanganan?

Bisa, asalkan sertifikat digitalnya valid. Pastikan Anda memiliki kata sandi yang benar jika dilindungi.

### Bagaimana cara mendapatkan file .pfx?

Anda dapat memperoleh file .pfx dari Certificate Authority (CA) atau membuatnya menggunakan alat seperti OpenSSL.

### Bisakah saya menandatangani banyak dokumen sekaligus?

Ya, Anda dapat mengulang beberapa dokumen dan menerapkan proses penandatanganan yang sama untuk masing-masing dokumen.

### Bagaimana jika saya tidak memiliki baris tanda tangan di dokumen saya?

Anda harus memasukkan baris tanda tangan terlebih dahulu. Aspose.Words menyediakan metode untuk menambahkan baris tanda tangan secara terprogram.
