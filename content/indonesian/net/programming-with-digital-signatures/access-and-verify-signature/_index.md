---
title: Akses Dan Verifikasi Tanda Tangan Di Dokumen Word
linktitle: Akses Dan Verifikasi Tanda Tangan Di Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengakses dan memverifikasi tanda tangan digital di dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-digital-signatures/access-and-verify-signature/
---
Dalam tutorial ini, kami akan memandu Anda melalui langkah-langkah untuk menggunakan fitur verifikasi akses dan tanda tangan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda mengakses tanda tangan digital di dokumen Word dan memverifikasi validitasnya. Ikuti langkah-langkah di bawah ini:

## Langkah 1: Memuat dokumen dan mengakses tanda tangan

Mulailah dengan mengunggah dokumen yang berisi tanda tangan digital:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Digitally signed.docx");
```

## Langkah 2: Telusuri Tanda Tangan Digital

Gunakan loop untuk mengulang semua tanda tangan digital dalam dokumen:

```csharp
foreach (DigitalSignature signature in doc.DigitalSignatures)
{
	// Akses informasi tanda tangan
	Console.WriteLine("* Signature Found *");
	Console.WriteLine("Is valid: " + signature.IsValid);
	// Properti ini hanya tersedia dalam dokumen MS Word.
	Console.WriteLine("Reason for signing: " + signature.Comments); 
	Console.WriteLine("Time of signing: " + signature.SignTime);
	Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
	Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
	Console.WriteLine();
}
```

Pastikan untuk menyesuaikan pesan tampilan sesuai dengan kebutuhan Anda.

### Contoh kode sumber untuk Akses dan Verifikasi Tanda Tangan menggunakan Aspose.Words untuk .NET

Berikut source code lengkap untuk akses dan verifikasi tanda tangan menggunakan Aspose.Words for .NET:

```csharp
	
	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Digitally signed.docx");

	foreach (DigitalSignature signature in doc.DigitalSignatures)
	{
		Console.WriteLine("* Signature Found *");
		Console.WriteLine("Is valid: " + signature.IsValid);
		// Properti ini hanya tersedia dalam dokumen MS Word.
		Console.WriteLine("Reason for signing: " + signature.Comments); 
		Console.WriteLine("Time of signing: " + signature.SignTime);
		Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
		Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
		Console.WriteLine();
	}

```

Dengan mengikuti langkah-langkah ini, Anda akan dapat dengan mudah mengakses dan memverifikasi tanda tangan digital di dokumen Word Anda dengan Aspose.Words untuk .NET.

## Kesimpulan

Dalam tutorial ini, kami menjelajahi fitur mengakses dan memverifikasi tanda tangan digital di dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti langkah-langkah yang disediakan, Anda dapat dengan mudah memuat dokumen, mengakses tanda tangan digitalnya, dan memverifikasi validitasnya. Kemampuan untuk mengakses dan memverifikasi tanda tangan digital memberikan cara untuk memastikan integritas dan keaslian dokumen Word Anda. Aspose.Words for .NET menawarkan API yang kuat untuk Pemrosesan Kata dengan tanda tangan digital, memungkinkan Anda mengotomatiskan proses verifikasi dan meningkatkan keamanan dokumen Anda.

### FAQ

#### T: Apa yang dimaksud dengan tanda tangan digital dalam dokumen Word?

J: Tanda tangan digital dalam dokumen Word adalah tanda tangan elektronik yang menyediakan cara untuk mengautentikasi integritas dan asal dokumen. Dokumen tersebut dibuat menggunakan sertifikat digital dan algoritme kriptografi, sehingga penerima dapat memverifikasi bahwa dokumen tersebut tidak diubah dan berasal dari sumber tepercaya.

#### T: Bagaimana cara mengakses tanda tangan digital di dokumen Word menggunakan Aspose.Words untuk .NET?

J: Untuk mengakses tanda tangan digital di dokumen Word menggunakan Aspose.Words untuk .NET, Anda dapat mengikuti langkah-langkah berikut:
1.  Muat dokumen menggunakan`Document` kelas dan tentukan jalur ke file dokumen.
2.  Gunakan loop untuk mengulangi`DigitalSignatures` pengumpulan dokumen. Setiap iterasi mewakili tanda tangan digital.

#### T: Informasi apa yang dapat saya akses dari tanda tangan digital di dokumen Word?

A: Dari tanda tangan digital di dokumen Word, Anda dapat mengakses berbagai informasi, seperti:
- Validitas: Periksa apakah tanda tangan itu valid.
- Komentar: Dapatkan alasan penandatanganan yang ditentukan oleh penandatangan.
- Waktu Masuk: Dapatkan waktu saat dokumen ditandatangani.
- Nama Subjek: Mengambil nama penandatangan atau subjek sertifikat.
- Nama Penerbit: Dapatkan nama penerbit sertifikat.

#### T: Bisakah saya memverifikasi validitas tanda tangan digital di dokumen Word menggunakan Aspose.Words untuk .NET?

 J: Ya, Anda dapat memverifikasi validitas tanda tangan digital di dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengakses`IsValid` properti dari`DigitalSignature` objek, Anda dapat menentukan apakah tanda tangan itu sah atau tidak.

#### T: Bagaimana cara memverifikasi validitas tanda tangan digital di dokumen Word menggunakan Aspose.Words untuk .NET?

J: Untuk memverifikasi validitas tanda tangan digital di dokumen Word menggunakan Aspose.Words for .NET, Anda dapat mengikuti langkah-langkah berikut:
1.  Akses`DigitalSignatures` pengumpulan dokumen.
2.  Ulangi masing-masing`DigitalSignature` objek dalam koleksi.
3.  Menggunakan`IsValid` properti dari`DigitalSignature` keberatan untuk memeriksa apakah tanda tangannya sah.

#### T: Bisakah saya mengambil komentar atau alasan penandatanganan dari tanda tangan digital di dokumen Word?

J: Ya, Anda dapat mengambil komentar atau alasan penandatanganan dari tanda tangan digital di dokumen Word. Itu`Comments` properti dari`DigitalSignature` objek menyediakan akses ke komentar yang ditentukan oleh penandatangan selama proses penandatanganan.

#### T: Jenis dokumen apa yang didukung fitur verifikasi tanda tangan di Aspose.Words untuk .NET?

J: Fitur verifikasi tanda tangan di Aspose.Words for .NET mendukung verifikasi tanda tangan digital di dokumen Word dengan format file DOCX. Anda dapat menggunakan fitur ini untuk memverifikasi tanda tangan di file DOCX.

#### T: Bagaimana cara mengakses detail sertifikat tanda tangan digital di dokumen Word menggunakan Aspose.Words untuk .NET?

 J: Untuk mengakses detail sertifikat tanda tangan digital di dokumen Word menggunakan Aspose.Words untuk .NET, Anda dapat mengakses`CertificateHolder` properti dari`DigitalSignature` obyek. Dari`CertificateHolder` objek, Anda dapat mengambil berbagai detail sertifikat, seperti nama subjek dan nama penerbit.

#### T: Bisakah saya mengkustomisasi tampilan atau pemrosesan tanda tangan digital di dokumen Word menggunakan Aspose.Words untuk .NET?

 J: Ya, Anda dapat menyesuaikan tampilan atau pemrosesan tanda tangan digital di dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengakses properti dan metode`DigitalSignature` objek, Anda dapat mengekstrak informasi yang diinginkan, melakukan validasi tambahan, atau mengintegrasikan proses verifikasi tanda tangan ke dalam alur kerja aplikasi Anda.

#### T: Apakah mungkin untuk memverifikasi beberapa tanda tangan digital dalam dokumen Word menggunakan Aspose.Words untuk .NET?

 J: Ya, verifikasi beberapa tanda tangan digital dalam dokumen Word dapat dilakukan menggunakan Aspose.Words untuk .NET. Dengan mengulangi melalui`DigitalSignatures` kumpulan dokumen, Anda dapat mengakses dan memverifikasi setiap tanda tangan digital satu per satu.

