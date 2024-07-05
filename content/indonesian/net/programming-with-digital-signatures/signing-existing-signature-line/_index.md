---
title: Menandatangani Baris Tanda Tangan yang Ada Di Dokumen Word
linktitle: Menandatangani Baris Tanda Tangan yang Ada Di Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menandatangani baris tanda tangan yang ada di dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-digital-signatures/signing-existing-signature-line/
---
Dalam tutorial ini, kami akan memandu Anda melalui langkah-langkah untuk menggunakan fitur tanda tangan dari baris tanda tangan yang ada dengan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda menandatangani secara digital baris tanda tangan yang sudah ada di dokumen Word. Ikuti langkah-langkah di bawah ini:

## Langkah 1: Memuat dokumen dan mengakses baris tanda tangan

Mulailah dengan mengunggah dokumen yang berisi baris tanda tangan yang ada:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## Langkah 2: Mengatur Opsi Tanda Tangan

Buat instance kelas SignOptions dan atur opsi tanda tangan, termasuk ID baris tanda tangan dan gambar garis tanda tangan:

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};
```

Pastikan untuk menentukan jalur yang benar ke gambar garis tanda tangan.

## Langkah 3: Memuat sertifikat

Mulailah dengan memuat sertifikat penandatanganan menggunakan kelas CertificateHolder:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Pastikan untuk menentukan jalur yang benar ke sertifikat Anda dan kata sandi terkait.

## Langkah 4: Menandatangani baris tanda tangan yang ada

Gunakan kelas DigitalSignatureUtil untuk menandatangani baris tanda tangan yang ada:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
```

Pastikan untuk menentukan jalur yang benar untuk dokumen sumber, dokumen yang ditandatangani, dan sertifikat.

### Contoh kode sumber untuk Menandatangani Baris Tanda Tangan yang Ada menggunakan Aspose.Words untuk .NET

Berikut adalah kode sumber lengkap untuk menandatangani baris tanda tangan yang ada dengan Aspose.Words untuk .NET:


```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Signature line.docx");
	
	SignatureLine signatureLine =
		((Shape) doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
		dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
	

```

Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah menandatangani baris tanda tangan yang ada di dokumen Word dengan Aspose.Words untuk .NET.

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara menandatangani baris tanda tangan yang ada di dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti langkah-langkah yang disediakan, Anda dapat dengan mudah memuat dokumen, mengakses baris tanda tangan yang ada, mengatur opsi penandatanganan, dan menandatangani dokumen. Kemampuan untuk menandatangani baris tanda tangan yang ada memberikan cara mudah untuk menambahkan tanda tangan digital ke area yang telah ditentukan sebelumnya di dokumen Word Anda, memastikan integritas dan autentikasi dokumen. Aspose.Words for .NET menawarkan API yang kuat untuk Pemrosesan Kata dengan tanda tangan digital, memungkinkan Anda menyesuaikan proses penandatanganan dan meningkatkan keamanan dokumen Word Anda.

### FAQ

#### T: Apa yang dimaksud dengan baris tanda tangan yang ada di dokumen Word?

J: Baris tanda tangan yang ada di dokumen Word adalah area yang telah ditentukan sebelumnya di mana tanda tangan dapat ditempatkan. Biasanya diwakili oleh bentuk atau objek dalam dokumen dan berfungsi sebagai ruang khusus bagi penandatangan untuk menambahkan tanda tangan digitalnya.

#### T: Bagaimana cara menandatangani baris tanda tangan yang ada di dokumen Word menggunakan Aspose.Words untuk .NET?

J: Untuk menandatangani baris tanda tangan yang ada di dokumen Word menggunakan Aspose.Words untuk .NET, Anda dapat mengikuti langkah-langkah berikut:
1.  Muat dokumen menggunakan`Document` kelas dan tentukan jalur ke file dokumen.
2.  Akses baris tanda tangan yang ada menggunakan metode atau properti yang sesuai. Misalnya, Anda bisa menggunakan`GetChild` metode untuk mengambil bentuk garis tanda tangan.
3.  Buat sebuah instance dari`SignOptions` kelas dan atur`SignatureLineId` properti ke ID baris tanda tangan yang ada.
4.  Mengatur`SignatureLineImage` properti dari`SignOptions` kelas ke gambar yang mewakili tanda tangan digital.
5.  Muat sertifikat penandatanganan menggunakan`CertificateHolder` kelas dan berikan sertifikat dan kata sandi yang diperlukan.
6.  Menggunakan`DigitalSignatureUtil.Sign` metode untuk menandatangani dokumen, memberikan parameter yang diperlukan termasuk`SignOptions` obyek.

#### T: Bagaimana cara mengakses baris tanda tangan yang ada di dokumen Word menggunakan Aspose.Words untuk .NET?

 J: Untuk mengakses baris tanda tangan yang ada di dokumen Word menggunakan Aspose.Words untuk .NET, Anda bisa menggunakan metode atau properti yang sesuai untuk mengambil bentuk garis tanda tangan dari struktur dokumen. Misalnya, Anda dapat menggunakan`GetChild` metode dengan parameter yang sesuai untuk mendapatkan bentuk garis tanda tangan yang diinginkan.

#### T: Dapatkah saya menyesuaikan tampilan tanda tangan digital pada baris tanda tangan yang sudah ada?

A: Ya, Anda dapat menyesuaikan tampilan tanda tangan digital pada baris tanda tangan yang ada dengan menyediakan file gambar yang mewakili tanda tangan tersebut. Gambar dapat berupa logo, tanda tangan tulisan tangan, atau representasi grafis lainnya dari tanda tangan tersebut. Anda dapat mengatur`SignatureLineImage` properti dari`SignOptions` kelas ke byte file gambar.

#### T: Bisakah saya menandatangani beberapa baris tanda tangan yang ada di dokumen Word?
 J: Ya, Anda bisa menandatangani beberapa baris tanda tangan yang ada di dokumen Word. Anda harus mengikuti langkah-langkah untuk setiap baris tanda tangan satu per satu, mengatur yang sesuai`SignatureLineId` Dan`SignatureLineImage` nilai-nilai di`SignOptions` objek untuk setiap baris tanda tangan.

#### T: Apa format file gambar untuk tanda tangan digital di baris tanda tangan yang sudah ada?

 A: File gambar tanda tangan digital pada baris tanda tangan yang ada bisa dalam berbagai format, seperti PNG, JPEG, BMP, atau GIF. Anda dapat menentukan jalur file atau membaca byte file gambar dan menetapkannya ke`SignatureLineImage` properti dari`SignOptions` kelas.
