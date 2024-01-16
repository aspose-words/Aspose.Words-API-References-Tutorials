---
title: Menandatangani Dokumen Word Terenkripsi
linktitle: Menandatangani Dokumen Word Terenkripsi
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menandatangani dokumen kata terenkripsi secara digital dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-digital-signatures/signing-encrypted-document/
---
Dalam tutorial ini, kami akan memandu Anda melalui langkah-langkah untuk menggunakan fitur penandatanganan dokumen Word terenkripsi dengan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda menandatangani dokumen Word secara digital yang dienkripsi menggunakan kata sandi dekripsi. Ikuti langkah-langkah di bawah ini:

## Langkah 1: Mengatur Opsi Tanda Tangan

Buat instance kelas SignOptions dan atur kata sandi dekripsi:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionpassword" };
```

Pastikan untuk menentukan kata sandi dekripsi yang benar untuk dokumen terenkripsi Anda.

## Langkah 2: Memuat sertifikat

Mulailah dengan memuat sertifikat penandatanganan menggunakan kelas CertificateHolder:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Pastikan untuk menentukan jalur yang benar ke sertifikat Anda dan kata sandi terkait.

## Langkah 3: Menandatangani dokumen terenkripsi

Gunakan kelas DigitalSignatureUtil untuk menandatangani dokumen terenkripsi:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
	certHolder, signOptions);
```

Pastikan untuk menentukan jalur yang benar untuk dokumen terenkripsi, dokumen yang ditandatangani, dan sertifikat.

### Contoh kode sumber untuk Menandatangani Dokumen Terenkripsi menggunakan Aspose.Words untuk .NET

Berikut kode sumber lengkap untuk menandatangani dokumen terenkripsi dengan Aspose.Words untuk .NET:

```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionPassword" };

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
		certHolder, signOptions);
	

```
Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah menandatangani dokumen Word terenkripsi dengan Aspose.Words untuk .NET.

## Kesimpulan

Dalam tutorial ini, kami menjelajahi proses penandatanganan dokumen Word terenkripsi menggunakan Aspose.Words untuk .NET. Dengan memberikan kata sandi dekripsi dan sertifikat penandatanganan, kita dapat menambahkan tanda tangan digital ke dokumen terenkripsi. Menandatangani dokumen terenkripsi memastikan keaslian dan integritasnya, memberikan lapisan keamanan tambahan. Aspose.Words untuk .NET memungkinkan Anda menandatangani dokumen terenkripsi dan menjaga keamanan dan kepercayaan file Word Anda.

### FAQ

#### T: Apa yang dimaksud dengan penandatanganan dokumen di Aspose.Words untuk .NET?

J: Penandatanganan dokumen di Aspose.Words untuk .NET mengacu pada proses penandatanganan dokumen Word secara digital untuk memastikan keaslian, integritas, dan non-penyangkalan. Ini melibatkan penambahan tanda tangan digital ke dokumen menggunakan sertifikat.

#### T: Apa yang dimaksud dengan dokumen Word terenkripsi?

J: Dokumen Word terenkripsi adalah dokumen yang telah dienkripsi menggunakan kata sandi. Enkripsi adalah tindakan keamanan yang melindungi konten dokumen dengan mengacaknya dan membuatnya tidak dapat dibaca tanpa kata sandi dekripsi yang benar.

#### T: Bagaimana cara menandatangani dokumen Word terenkripsi menggunakan Aspose.Words untuk .NET?

J: Untuk menandatangani dokumen Word terenkripsi menggunakan Aspose.Words untuk .NET, Anda perlu memberikan kata sandi dekripsi bersama dengan sertifikat penandatanganan. Ikuti langkah ini:
1.  Tetapkan kata sandi dekripsi di`SignOptions` obyek.
2.  Muat sertifikat penandatanganan menggunakan`CertificateHolder` kelas.
3.  Menggunakan`DigitalSignatureUtil.Sign` metode untuk menandatangani dokumen terenkripsi, memberikan parameter yang diperlukan.

#### T: Apa tujuan menandatangani dokumen terenkripsi?

J: Menandatangani dokumen terenkripsi dengan Aspose.Words untuk .NET memungkinkan Anda menambahkan tanda tangan digital ke dokumen meskipun dokumen tersebut dienkripsi. Ini memberikan lapisan keamanan tambahan dan memastikan keaslian dan integritas konten terenkripsi. Hal ini memungkinkan penerima untuk memverifikasi asal dokumen dan mendeteksi adanya gangguan.

#### T: Dapatkah saya menandatangani dokumen terenkripsi tanpa memberikan kata sandi dekripsi?

J: Tidak, untuk menandatangani dokumen terenkripsi, Anda harus memberikan kata sandi dekripsi yang benar. Kata sandi dekripsi diperlukan untuk mengakses dan mengubah konten terenkripsi dokumen sebelum menerapkan tanda tangan digital.

#### T: Dapatkah saya menandatangani dokumen Word terenkripsi menggunakan sertifikat apa pun?

J: Untuk menandatangani dokumen Word terenkripsi menggunakan Aspose.Words untuk .NET, Anda memerlukan sertifikat X.509 yang valid. Sertifikat dapat diperoleh dari otoritas sertifikat (CA) tepercaya atau sertifikat yang ditandatangani sendiri dapat digunakan untuk tujuan pengujian.

#### T: Dapatkah saya menandatangani beberapa dokumen Word terenkripsi menggunakan sertifikat yang sama?

 J: Ya, Anda bisa menandatangani beberapa dokumen Word terenkripsi menggunakan sertifikat yang sama. Setelah Anda memuat sertifikat menggunakan`CertificateHolder` kelas, Anda dapat menggunakannya kembali untuk menandatangani beberapa dokumen terenkripsi.

#### T: Dapatkah saya memverifikasi tanda tangan digital dari dokumen terenkripsi yang ditandatangani?

 J: Ya, Aspose.Words untuk .NET menyediakan fungsionalitas untuk memverifikasi tanda tangan digital dari dokumen terenkripsi yang ditandatangani. Anda dapat menggunakan`DigitalSignatureUtil.Verify` metode untuk memeriksa keabsahan dan keaslian tanda tangan digital.

#### T: Format file apa yang didukung Aspose.Words for .NET untuk menandatangani dokumen terenkripsi?

 J: Aspose.Words untuk .NET mendukung penandatanganan dokumen Word terenkripsi dalam format file DOCX. Anda dapat menandatangani file DOCX terenkripsi menggunakan`DigitalSignatureUtil.Sign` metode bersama dengan kata sandi dan sertifikat dekripsi yang diperlukan.

#### T: Bagaimana pengaruh penandatanganan dokumen terenkripsi terhadap enkripsi?

J: Menandatangani dokumen terenkripsi dengan Aspose.Words untuk .NET tidak memengaruhi enkripsi dokumen. Enkripsi tetap utuh, dan tanda tangan digital ditambahkan ke konten terenkripsi. Tanda tangan digital memberikan keamanan dan verifikasi tambahan tanpa mengorbankan enkripsi yang diterapkan pada dokumen.