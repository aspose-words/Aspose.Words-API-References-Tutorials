---
title: Membuat Dan Menandatangani Baris Tanda Tangan Baru
linktitle: Membuat Dan Menandatangani Baris Tanda Tangan Baru
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara membuat dan menandatangani baris tanda tangan baru di dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-digital-signatures/creating-and-signing-new-signature-line/
---
Dalam tutorial ini, kami akan memandu Anda melalui langkah-langkah untuk menggunakan fitur membuat dan menandatangani baris tanda tangan baru dengan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda menyisipkan baris tanda tangan di dokumen Word, mengatur opsi khusus, dan menandatangani dokumen. Ikuti langkah-langkah di bawah ini:

## Langkah 1: Membuat Dokumen dan Generator

Mulailah dengan membuat instance kelas Dokumen dan objek DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 2: Memasukkan baris tanda tangan

Gunakan metode InsertSignatureLine() pada objek DocumentBuilder untuk menyisipkan baris tanda tangan baru ke dalam dokumen:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## Langkah 3: Simpan dokumen

Simpan dokumen yang diubah:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

Pastikan untuk menentukan jalur dan nama file yang benar untuk menyimpan dokumen.

## Langkah 4: Menandatangani dokumen

Untuk menandatangani dokumen, Anda perlu mengatur opsi tanda tangan dan menggunakan kelas DigitalSignatureUtil:

```csharp
SignOptions signOptions = new SignOptions
{
	SignatureLineId = signatureLine.Id,
	SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
	dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);
```

Pastikan untuk menentukan jalur yang benar untuk dokumen, gambar garis tanda tangan, dan dokumen yang ditandatangani.

### Contoh kode sumber untuk Membuat Dan Menandatangani Baris Tanda Tangan Baru menggunakan Aspose.Words untuk .NET

Berikut kode sumber lengkap untuk membuat dan menandatangani baris tanda tangan baru dengan Aspose.Words untuk .NET:

```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
	
	doc.Save(dataDir + "SignDocuments.SignatureLine.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
		dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);

```

Dengan mengikuti langkah-langkah ini, Anda akan dapat dengan mudah membuat dan menandatangani baris tanda tangan baru di dokumen Word Anda dengan Aspose.Words untuk .NET.

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara membuat dan menandatangani baris tanda tangan baru di dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti langkah-langkah yang disediakan, Anda dapat dengan mudah menyisipkan baris tanda tangan ke dalam dokumen Anda, menyesuaikan opsinya, dan menandatangani dokumen menggunakan sertifikat digital. Menambahkan baris tanda tangan dan tanda tangan digital ke dokumen Anda akan meningkatkan keaslian dan integritasnya, menjadikannya lebih aman dan tepercaya. Aspose.Words untuk .NET menyediakan API yang kuat untuk Pemrosesan Kata dengan tanda tangan dan sertifikat digital di dokumen Word, memungkinkan Anda mengotomatiskan proses penandatanganan dan memastikan validitas dokumen Anda.

### FAQ

#### T: Apa yang dimaksud dengan baris tanda tangan di dokumen Word?

J: Baris tanda tangan di dokumen Word adalah placeholder yang menunjukkan di mana tanda tangan harus ditempatkan. Biasanya mencakup nama, judul, dan tanggal, dan menyediakan ruang untuk tanda tangan tulisan tangan atau digital.

#### T: Bagaimana cara membuat baris tanda tangan di dokumen Word menggunakan Aspose.Words untuk .NET?

A: Untuk membuat baris tanda tangan di dokumen Word menggunakan Aspose.Words for .NET, Anda dapat mengikuti langkah-langkah berikut:
1.  Buat sebuah instance dari`Document` kelas dan a`DocumentBuilder` obyek.
2.  Menggunakan`InsertSignatureLine` metode`DocumentBuilder` objek untuk memasukkan baris tanda tangan baru ke dalam dokumen.
3. Simpan dokumen yang diubah.

#### T: Dapatkah saya menyesuaikan opsi baris tanda tangan, seperti nama, judul, dan tanggal?

 J: Ya, Anda dapat menyesuaikan opsi garis tanda tangan. Itu`SignatureLineOptions` kelas menyediakan properti untuk mengatur opsi yang diinginkan, seperti`Signer`, `SignerTitle`, `ShowDate`, dll. Anda dapat mengubah properti ini sebelum menyisipkan baris tanda tangan.

#### T: Bagaimana cara menandatangani dokumen setelah membuat baris tanda tangan?

 J: Untuk menandatangani dokumen setelah membuat baris tanda tangan, Anda perlu mengatur opsi tanda tangan dan menggunakan`DigitalSignatureUtil` kelas. Berikut langkah-langkahnya:
1.  Mengatur`SignatureLineId` properti di`SignOptions` keberatan dengan ID baris tanda tangan.
2.  Mengatur`SignatureLineImage` properti di`SignOptions` keberatan dengan gambar tanda tangan yang ingin Anda gunakan.
3.  Muat sertifikat penandatanganan menggunakan`CertificateHolder` kelas.
4.  Menggunakan`DigitalSignatureUtil.Sign` metode untuk menandatangani dokumen, memberikan parameter yang diperlukan.

#### Q: Bisakah saya menggunakan gambar tanda tangan digital untuk menandatangani dokumen?

 A: Ya, Anda dapat menggunakan gambar tanda tangan digital untuk menandatangani dokumen. Untuk melakukan ini, Anda perlu menyediakan file gambar di`SignOptions` objek menggunakan`SignatureLineImage`Properti. Gambar bisa dalam format gambar apa pun yang didukung, seperti JPEG, PNG, atau EMF.

#### T: Apa tujuan membuat dan menandatangani baris tanda tangan baru di dokumen Word?

J: Membuat dan menandatangani baris tanda tangan baru di dokumen Word menggunakan Aspose.Words untuk .NET memungkinkan Anda menambahkan placeholder untuk tanda tangan lalu menandatangani dokumen menggunakan sertifikat digital. Proses ini memastikan keaslian dan integritas dokumen, memberikan bukti persetujuan atau persetujuan.

#### T: Bisakah saya membuat dan menandatangani beberapa baris tanda tangan di dokumen Word menggunakan Aspose.Words untuk .NET?

J: Ya, Anda dapat membuat dan menandatangani beberapa baris tanda tangan di dokumen Word menggunakan Aspose.Words untuk .NET. Setiap baris tanda tangan dapat memiliki ID dan opsi uniknya sendiri. Anda dapat mengulangi langkah-langkah untuk membuat dan menandatangani baris tanda tangan tambahan di dokumen.

#### T: Dapatkah saya mengubah baris tanda tangan atau menambahkan informasi tambahan setelah ditandatangani?

J: Setelah baris tanda tangan ditandatangani, baris tersebut menjadi bagian dari konten dokumen dan tidak dapat diubah secara terpisah. Namun, Anda dapat menambahkan informasi atau konten tambahan setelah baris tanda tangan yang ditandatangani.

#### T: Dapatkah saya memverifikasi tanda tangan digital dari dokumen yang berisi baris tanda tangan?

 J: Ya, Aspose.Words untuk .NET menyediakan fungsionalitas untuk memverifikasi tanda tangan digital dokumen yang berisi baris tanda tangan. Anda dapat menggunakan`DigitalSignatureUtil.Verify` metode untuk memeriksa keabsahan dan keaslian tanda tangan digital.

#### T: Format file apa yang didukung Aspose.Words for .NET untuk membuat dan menandatangani baris tanda tangan?

J: Aspose.Words untuk .NET mendukung pembuatan dan penandatanganan baris tanda tangan dalam format file DOCX. Anda dapat membuat dan menandatangani baris tanda tangan di file DOCX menggunakan metode dan kelas yang disediakan.