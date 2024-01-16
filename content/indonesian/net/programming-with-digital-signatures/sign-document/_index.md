---
title: Tanda tangani Dokumen Word
linktitle: Tanda tangani Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menandatangani dokumen Word secara digital dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-digital-signatures/sign-document/
---
Dalam tutorial ini, kami akan memandu Anda melalui langkah-langkah untuk menggunakan fitur penandatanganan dokumen dengan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda menandatangani dokumen Word secara digital menggunakan sertifikat. Ikuti langkah-langkah di bawah ini:

## Langkah 1: Memuat sertifikat

Mulailah dengan memuat sertifikat penandatanganan menggunakan kelas CertificateHolder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Pastikan untuk menentukan jalur yang benar ke sertifikat Anda dan kata sandi terkait.

## Langkah 2: Menandatangani dokumen

Gunakan kelas DigitalSignatureUtil untuk menandatangani dokumen:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
	certHolder);
```

Pastikan untuk menentukan jalur yang benar untuk dokumen sumber dan dokumen yang ditandatangani.

### Contoh kode sumber untuk Menandatangani Dokumen menggunakan Aspose.Words untuk .NET

Berikut kode sumber lengkap untuk menandatangani dokumen dengan Aspose.Words for .NET:

```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
		certHolder);

```

Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah menandatangani dokumen Word dengan Aspose.Words untuk .NET.

## Kesimpulan

 Dalam tutorial ini, kita menjelajahi fitur penandatanganan dokumen di Aspose.Words untuk .NET. Dengan memuat sertifikat penandatanganan dan menggunakan`DigitalSignatureUtil.Sign` metodenya, kita dapat menandatangani dokumen Word secara digital. Penandatanganan dokumen memberikan otentikasi dan memastikan integritas konten dokumen, menjadikannya fitur berharga untuk manajemen dokumen yang aman dan tepercaya.

### FAQ untuk dokumen kata tanda tangan

#### T: Apa yang dimaksud dengan penandatanganan dokumen di Aspose.Words untuk .NET?

J: Penandatanganan dokumen di Aspose.Words untuk .NET mengacu pada proses penandatanganan dokumen Word secara digital menggunakan sertifikat. Fitur ini menambahkan tanda tangan digital pada dokumen, memberikan keaslian, integritas, dan tidak dapat disangkalnya konten dokumen.

#### T: Bagaimana cara memuat sertifikat penandatanganan di Aspose.Words untuk .NET?

 J: Untuk memuat sertifikat penandatanganan di Aspose.Words untuk .NET, Anda dapat menggunakan`CertificateHolder` kelas. Buat sebuah contoh dari`CertificateHolder` dengan memberikan jalur ke file sertifikat dan kata sandi terkait. Berikut ini contohnya:

```csharp
CertificateHolder certHolder = CertificateHolder.Create("path/to/certificate.pfx", "password");
```

Pastikan untuk memberikan jalur yang benar ke sertifikat Anda dan kata sandi terkait.

#### T: Bagaimana cara menandatangani dokumen Word menggunakan Aspose.Words untuk .NET?

 J: Untuk menandatangani dokumen Word menggunakan Aspose.Words untuk .NET, Anda dapat menggunakan`DigitalSignatureUtil` kelas. Hubungi`Sign` metode, menyediakan jalur ke dokumen sumber, jalur ke dokumen yang ditandatangani (keluaran), dan`CertificateHolder` obyek. Berikut ini contohnya:

```csharp
DigitalSignatureUtil.Sign("path/to/source/document.docx", "path/to/signed/document.docx", certHolder);
```

Pastikan Anda memberikan jalur yang benar untuk dokumen sumber dan dokumen yang ditandatangani (keluaran).

#### Q: Apa tujuan penandatanganan dokumen?

J: Penandatanganan dokumen berfungsi sebagai metode untuk memastikan keaslian dan integritas suatu dokumen. Dengan menandatangani dokumen secara digital, Anda dapat memberikan bukti asal-usulnya, memverifikasi bahwa isinya tidak diubah, dan menetapkan non-penyangkalan. Penandatanganan dokumen biasanya digunakan untuk dokumen hukum, keuangan, dan sensitif.

#### T: Bisakah saya menggunakan sertifikat apa pun untuk penandatanganan dokumen di Aspose.Words untuk .NET?

J: Untuk penandatanganan dokumen di Aspose.Words untuk .NET, Anda perlu menggunakan sertifikat X.509 yang valid. Sertifikat ini dapat diperoleh dari otoritas sertifikat (CA) tepercaya atau sertifikat yang ditandatangani sendiri dapat digunakan untuk tujuan pengujian.

#### T: Format file apa yang didukung Aspose.Words for .NET untuk penandatanganan dokumen?

 J: Aspose.Words untuk .NET mendukung penandatanganan dokumen untuk dokumen Word dalam format file DOCX. Anda dapat menandatangani file DOCX menggunakan`DigitalSignatureUtil` kelas dan sertifikat yang sesuai.

#### T: Dapatkah saya menandatangani beberapa dokumen Word menggunakan sertifikat yang sama?

J: Ya, Anda bisa menandatangani beberapa dokumen Word menggunakan sertifikat yang sama. Setelah Anda memuat sertifikat menggunakan`CertificateHolder` kelas, Anda dapat menggunakannya kembali untuk menandatangani beberapa dokumen dengan memanggil`DigitalSignatureUtil.Sign` metode dengan sumber berbeda dan jalur dokumen yang ditandatangani.

#### Q: Apakah penandatanganan dokumen mengubah dokumen asli?

J: Penandatanganan dokumen dengan Aspose.Words untuk .NET tidak mengubah dokumen asli. Sebaliknya, ini membuat salinan dokumen yang ditandatangani secara digital, sehingga dokumen aslinya tetap utuh. Salinan yang ditandatangani secara digital berisi tanda tangan digital tambahan, yang memastikan integritas isi dokumen.

#### T: Dapatkah saya memverifikasi tanda tangan digital dari dokumen yang ditandatangani menggunakan Aspose.Words untuk .NET?

 J: Ya, Aspose.Words untuk .NET menyediakan fungsionalitas untuk memverifikasi tanda tangan digital dari dokumen yang ditandatangani. Anda dapat menggunakan`DigitalSignatureUtil.Verify` metode untuk memeriksa keabsahan dan keaslian tanda tangan digital.