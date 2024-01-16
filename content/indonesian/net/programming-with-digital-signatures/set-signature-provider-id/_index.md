---
title: Tetapkan Id Penyedia Tanda Tangan Di Dokumen Word
linktitle: Tetapkan Id Penyedia Tanda Tangan Di Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengatur ID penyedia tanda tangan di dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-digital-signatures/set-signature-provider-id/
---
Dalam tutorial ini, kami akan memandu Anda melalui langkah-langkah untuk menggunakan fitur Tetapkan ID Penyedia Tanda Tangan dengan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda menentukan ID penyedia tanda tangan untuk baris tanda tangan di dokumen Word. Ikuti langkah-langkah di bawah ini:

## Langkah 1: Memuat dokumen dan mengakses baris tanda tangan

Mulailah dengan mengunggah dokumen yang berisi baris tanda tangan:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## Langkah 2: Mengatur Opsi Tanda Tangan

Buat instance kelas SignOptions dan atur opsi penandatanganan, termasuk ID penyedia:

```csharp
SignOptions signOptions = new SignOptions
{
ProviderId = signatureLine.ProviderId,
 SignatureLineId = signatureLine.Id
};
```

## Langkah 3: Menandatangani dokumen

Untuk menandatangani dokumen, Anda harus menggunakan kelas DigitalSignatureUtil dan menentukan sertifikat penandatanganan:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);
```

Pastikan untuk menentukan jalur yang benar untuk dokumen, sertifikat, dan dokumen yang ditandatangani.

### Contoh kode sumber untuk Menetapkan Id Penyedia Tanda Tangan menggunakan Aspose.Words untuk .NET

Berikut source code lengkap untuk mengatur ID penyedia tanda tangan dengan Aspose.Words for .NET:

```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Signature line.docx");

	SignatureLine signatureLine =
		((Shape) doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;

	SignOptions signOptions = new SignOptions
	{
		ProviderId = signatureLine.ProviderId, SignatureLineId = signatureLine.Id
	};

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");

	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
		dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);

```

Selesaikan ID Penyedia Tanda Tangan di dokumen Word Anda dengan Aspose.Words untuk .NET.


## Kesimpulan

Dalam tutorial ini, kita mempelajari cara mengatur ID penyedia tanda tangan untuk baris tanda tangan di dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti langkah-langkah yang disediakan, Anda dapat dengan mudah memuat dokumen, mengakses baris tanda tangan, mengatur ID penyedia, dan menandatangani dokumen. Kemampuan untuk mengatur ID penyedia tanda tangan membantu membangun identitas dan kepercayaan penandatangan, sehingga meningkatkan keamanan dan integritas dokumen Word Anda. Aspose.Words for .NET menyediakan API yang kuat untuk Pemrosesan Kata dengan tanda tangan digital, memungkinkan Anda menyesuaikan dan mengelola proses tanda tangan dengan mudah.

### FAQ untuk mengatur id penyedia tanda tangan di dokumen Word

#### T: Apa yang dimaksud dengan ID penyedia tanda tangan di dokumen Word?

J: ID penyedia tanda tangan di dokumen Word adalah pengidentifikasi unik yang menentukan penyedia tanda tangan digital. Ini membantu mengidentifikasi entitas atau organisasi yang bertanggung jawab untuk membuat dan mengelola tanda tangan digital.

#### T: Bagaimana cara mengatur ID penyedia tanda tangan untuk baris tanda tangan di dokumen Word menggunakan Aspose.Words untuk .NET?

J: Untuk mengatur ID penyedia tanda tangan untuk baris tanda tangan di dokumen Word menggunakan Aspose.Words untuk .NET, Anda dapat mengikuti langkah-langkah berikut:
1.  Muat dokumen menggunakan`Document` kelas dan tentukan jalur ke file dokumen.
2.  Akses baris tanda tangan menggunakan metode atau properti yang sesuai. Misalnya, Anda bisa menggunakan`GetChild` metode untuk mengambil bentuk garis tanda tangan.
3. Ambil ID penyedia dari baris tanda tangan.
4.  Buat sebuah instance dari`SignOptions` kelas dan atur`ProviderId` properti ke ID penyedia yang diambil.
5.  Menggunakan`DigitalSignatureUtil.Sign` metode untuk menandatangani dokumen, memberikan parameter yang diperlukan termasuk`SignOptions` obyek.

#### T: Bagaimana cara mengakses baris tanda tangan di dokumen Word menggunakan Aspose.Words untuk .NET?

 J: Untuk mengakses baris tanda tangan di dokumen Word menggunakan Aspose.Words untuk .NET, Anda bisa menggunakan metode atau properti yang sesuai untuk mengambil bentuk garis tanda tangan dari struktur dokumen. Misalnya, Anda dapat menggunakan`GetChild` metode dengan parameter yang sesuai untuk mendapatkan bentuk garis tanda tangan yang diinginkan.

#### T: Bisakah saya mengatur ID penyedia tanda tangan untuk beberapa baris tanda tangan di dokumen Word?

 J: Ya, Anda dapat mengatur ID penyedia tanda tangan untuk beberapa baris tanda tangan di dokumen Word. Anda dapat mengulangi kumpulan baris tanda tangan dalam dokumen dan mengatur ID penyedia untuk setiap baris tanda tangan satu per satu menggunakan`SignOptions.ProviderId` Properti.

#### Q: Apa tujuan dari ID penyedia tanda tangan di dokumen Word?

J: ID penyedia tanda tangan di dokumen Word bertujuan untuk mengidentifikasi entitas atau organisasi yang bertanggung jawab membuat dan mengelola tanda tangan digital. Ini membantu membangun keaslian dan kepercayaan tanda tangan digital dengan mengaitkannya dengan penyedia tertentu.

#### T: Jenis sertifikat digital apa yang dapat digunakan untuk mengatur ID penyedia tanda tangan di dokumen Word?

J: Anda dapat menggunakan sertifikat digital X.509 dengan informasi penyedia yang sesuai untuk mengatur ID penyedia tanda tangan di dokumen Word. Sertifikat digital harus diterbitkan oleh otoritas sertifikat (CA) tepercaya dan berisi metadata yang diperlukan untuk mengidentifikasi penyedia.