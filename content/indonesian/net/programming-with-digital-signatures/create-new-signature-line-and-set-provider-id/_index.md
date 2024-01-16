---
title: Buat Baris Tanda Tangan Baru Dan Tetapkan Id Penyedia
linktitle: Buat Baris Tanda Tangan Baru Dan Tetapkan Id Penyedia
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara membuat baris tanda tangan baru dan mengatur ID penyedia di dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
---
Dalam tutorial ini, kami akan memandu Anda melalui langkah-langkah untuk menggunakan fitur Buat Baris Tanda Tangan Baru dan Tetapkan ID Penyedia dengan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda menyisipkan baris tanda tangan di dokumen Word, mengatur opsi khusus, dan menandatangani dokumen. Ikuti langkah-langkah di bawah ini:

## Langkah 1: Membuat Dokumen dan Generator

Mulailah dengan membuat instance kelas Dokumen dan objek DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 2: Mengatur Opsi Garis Tanda Tangan

Buat instance kelas SignatureLineOptions dan atur opsi yang diinginkan:

```csharp
SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
Sign = "vderyushev",
SignerTitle = "QA",
Email = "vderyushev@aspose.com",
ShowDate=true,
Default Instructions = false,
Instructions = "Please sign here.",
AllowComments = true
};
```

## Langkah 3: Memasukkan baris tanda tangan

Gunakan metode InsertSignatureLine() pada objek DocumentBuilder untuk menyisipkan baris tanda tangan ke dalam dokumen:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
```

## Langkah 4: Tetapkan ID Penyedia

Tetapkan ID penyedia untuk baris tanda tangan menggunakan properti ProviderId:

```csharp
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

Pastikan untuk menentukan ID penyedia yang benar untuk kasus penggunaan Anda.

## Langkah 5: Simpan Dokumen

Simpan dokumen yang diubah:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

Pastikan untuk menentukan jalur dan nama file yang benar untuk menyimpan dokumen.

## Langkah 6: Menandatangani dokumen

Untuk menandatangani dokumen, Anda perlu mengatur opsi tanda tangan dan menggunakan kelas DigitalSignatureUtil:

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
ProviderId = signatureLine.ProviderId,
Comments = "Document was signed by vderyushev",
SignTime = DateTime.Now
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
	dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions)
```

Pastikan untuk menentukan jalur yang benar untuk dokumen, sertifikat, dan dokumen yang ditandatangani.

### Contoh kode sumber untuk Membuat Baris Tanda Tangan Baru dan Menetapkan Id Penyedia menggunakan Aspose.Words untuk .NET

Berikut kode sumber lengkap untuk membuat baris tanda tangan baru dan mengatur ID penyedia dengan Aspose.Words untuk .NET:

```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

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

	SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
	signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
	
	doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		ProviderId = signatureLine.ProviderId,
		Comments = "Document was signed by vderyushev",
		SignTime = DateTime.Now
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
		dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);

```

Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah membuat baris tanda tangan baru dan mengatur ID penyedia di dokumen Word Anda dengan Aspose.Words untuk .NET.

## Kesimpulan

Dalam tutorial ini, kita menjelajahi fitur membuat baris tanda tangan baru dan mengatur ID penyedia di dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti langkah-langkah yang disediakan, Anda dapat dengan mudah menyisipkan baris tanda tangan dengan opsi khusus dan mengaitkannya dengan penyedia tertentu menggunakan ID penyedia. Menambahkan baris tanda tangan dan menyesuaikan informasi penyedia akan meningkatkan keaslian dan kepercayaan dokumen Anda. Aspose.Words untuk .NET menyediakan API yang kuat untuk Pemrosesan Kata dengan baris tanda tangan dan sertifikat digital di dokumen Word, memungkinkan Anda mengotomatiskan proses penandatanganan dan memastikan validitas dokumen Anda.

### FAQ

#### T: Apa yang dimaksud dengan ID penyedia di baris tanda tangan?

J: ID penyedia di baris tanda tangan adalah pengidentifikasi unik yang mewakili penyedia tanda tangan digital. Ini membantu mengidentifikasi sumber atau organisasi yang bertanggung jawab atas tanda tangan tersebut.

#### T: Bagaimana cara membuat baris tanda tangan baru di dokumen Word menggunakan Aspose.Words untuk .NET?

A: Untuk membuat baris tanda tangan baru di dokumen Word menggunakan Aspose.Words untuk .NET, Anda dapat mengikuti langkah-langkah berikut:
1.  Buat sebuah instance dari`Document` kelas dan a`DocumentBuilder` obyek.
2.  Buat sebuah instance dari`SignatureLineOptions` kelas dan atur opsi garis tanda tangan yang diinginkan.
3.  Menggunakan`InsertSignatureLine` metode`DocumentBuilder` objek untuk memasukkan baris tanda tangan ke dalam dokumen.

#### T: Dapatkah saya menyesuaikan opsi baris tanda tangan, seperti nama penandatangan, jabatan, dan instruksi?

 J: Ya, Anda dapat menyesuaikan opsi baris tanda tangan. Itu`SignatureLineOptions` kelas menyediakan properti untuk mengatur opsi yang diinginkan, seperti`Signer`, `SignerTitle`, `Instructions`, `AllowComments`, dll. Anda dapat mengubah properti ini sebelum menyisipkan baris tanda tangan.

#### Q: Apa tujuan menyetel ID penyedia untuk baris tanda tangan?

J: Menetapkan ID penyedia untuk baris tanda tangan membantu mengidentifikasi sumber atau organisasi yang bertanggung jawab atas tanda tangan digital. Hal ini memungkinkan Anda untuk mengaitkan tanda tangan dengan penyedia atau entitas tertentu, memberikan informasi tambahan tentang asal dan kepercayaan tanda tangan tersebut.

#### T: Bagaimana cara mengatur ID penyedia untuk baris tanda tangan menggunakan Aspose.Words untuk .NET?

J: Untuk mengatur ID penyedia baris tanda tangan menggunakan Aspose.Words untuk .NET, Anda dapat mengikuti langkah-langkah berikut:
1.  Setelah memasukkan baris tanda tangan, akses`ProviderId` properti dari`SignatureLine` obyek.
2.  Mengatur`ProviderId` properti ke nilai ID penyedia yang diinginkan menggunakan`Guid` tipe data.

#### T: Bisakah saya menandatangani dokumen setelah membuat baris tanda tangan baru dan mengatur ID penyedia?

 A: Ya, setelah membuat baris tanda tangan baru dan mengatur ID penyedia, Anda dapat menandatangani dokumen tersebut. Untuk menandatangani dokumen, Anda perlu mengatur opsi tanda tangan, termasuk ID baris tanda tangan, ID penyedia, komentar, dan waktu penandatanganan. Kemudian, gunakan`DigitalSignatureUtil.Sign` metode untuk menandatangani dokumen menggunakan sertifikat digital.

#### T: Bisakah saya menentukan ID penyedia spesifik untuk setiap baris tanda tangan di dokumen Word?

J: Ya, Anda bisa menentukan ID penyedia spesifik untuk setiap baris tanda tangan di dokumen Word. Setelah memasukkan setiap baris tanda tangan, Anda dapat mengatur ID penyedia untuk baris tanda tangan tersebut dengan mengakses`ProviderId` milik masing-masing`SignatureLine` obyek.

#### T: Bagaimana cara menyimpan dokumen yang diubah setelah membuat baris tanda tangan baru dan mengatur ID penyedia?

 A: Untuk menyimpan dokumen yang dimodifikasi setelah membuat baris tanda tangan baru dan mengatur ID penyedia, Anda dapat menggunakan`Save` metode`Document` obyek. Tentukan jalur dan nama file yang benar untuk menyimpan dokumen.

#### T: Format file apa yang didukung Aspose.Words for .NET untuk membuat dan menandatangani baris tanda tangan?

J: Aspose.Words untuk .NET mendukung pembuatan dan penandatanganan baris tanda tangan dalam format file DOCX. Anda dapat membuat dan menandatangani baris tanda tangan di file DOCX menggunakan metode dan kelas yang disediakan.

#### T: Dapatkah saya mengubah ID penyedia atau opsi lain pada baris tanda tangan setelah ditandatangani?

J: Setelah baris tanda tangan ditandatangani, baris tersebut menjadi bagian dari konten dokumen dan tidak dapat diubah secara terpisah. Modifikasi apa pun pada baris tanda tangan, seperti mengubah ID penyedia atau opsi lainnya, memerlukan penghapusan tanda tangan yang ada dan membuat baris tanda tangan baru.