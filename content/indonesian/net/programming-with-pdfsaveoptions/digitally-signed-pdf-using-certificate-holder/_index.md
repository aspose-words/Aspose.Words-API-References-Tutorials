---
title: Tambahkan Tanda Tangan Digital ke PDF menggunakan Pemegang Sertifikat
linktitle: Tambahkan Tanda Tangan Digital ke PDF menggunakan Pemegang Sertifikat
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menambahkan Tanda Tangan Digital ke PDF menggunakan Pemegang Sertifikat dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-pdfsaveoptions/digitally-signed-pdf-using-certificate-holder/
---

Dalam tutorial ini, kami akan memandu Anda melalui langkah-langkah menambahkan tanda tangan digital ke PDF menggunakan pemegang sertifikat dengan Aspose.Words untuk .NET. Tanda tangan digital menambahkan lapisan keamanan dan integritas pada dokumen PDF. Ikuti langkah-langkah di bawah ini:

## Langkah 1: Membuat dokumen dan menambahkan konten

Mulailah dengan membuat instance kelas Dokumen:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 2: Tambahkan konten ke dokumen

 Kemudian gunakan`DocumentBuilder`untuk menambahkan konten ke dokumen. Misalnya, untuk menambahkan paragraf yang berisi teks "Test Signed PDF", gunakan`Writeln` metode:

```csharp
builder.Writeln("Test Signed PDF.");
```

Anda dapat menambahkan item konten lainnya sesuai kebutuhan.

## Langkah 3: Tetapkan opsi penyimpanan PDF

Buat instance kelas PdfSaveOptions dan tentukan detail tanda tangan digital:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
	DigitalSignatureDetails = new PdfDigitalSignatureDetails(
		CertificateHolder.Create(MyDir + "morzal.pfx", "aw"), "reason", "location",
		DateTime.Now)
};
```

Pastikan untuk menentukan jalur yang benar ke sertifikat Anda dan kata sandi terkait. Anda juga dapat menyesuaikan alasan dan lokasi tanda tangan.

## Langkah 4: Simpan Dokumen sebagai PDF yang Ditandatangani Secara Digital

 Menggunakan`Save` metode untuk menyimpan dokumen sebagai PDF dengan menentukan opsi penyimpanan:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
```

Pastikan untuk menentukan jalur yang benar untuk menyimpan PDF yang ditandatangani secara digital.

Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah membuat PDF yang ditandatangani secara digital dengan sertifikat menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber untuk Pdf yang Ditandatangani Secara Digital Menggunakan Pemegang Sertifikat menggunakan Aspose.Words untuk .NET

Berikut kode sumber lengkap untuk menandatangani Pdf secara digital menggunakan pemegang sertifikat dari dokumen menggunakan Aspose.Words untuk .NET:

```csharp

            // Jalur ke direktori dokumen.
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);
            
            builder.Writeln("Test Signed PDF.");

            PdfSaveOptions saveOptions = new PdfSaveOptions
            {
                DigitalSignatureDetails = new PdfDigitalSignatureDetails(
                    CertificateHolder.Create(MyDir + "morzal.pfx", "aw"), "reason", "location",
                    DateTime.Now)
            };

            doc.Save(dataDir + "WorkingWithPdfSaveOptions.DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
            
        
```
## Kesimpulan

Dalam tutorial ini, kami menjelajahi langkah-langkah untuk menambahkan tanda tangan digital ke dokumen PDF menggunakan sertifikat dengan Aspose.Words untuk .NET. Tanda tangan digital menambahkan lapisan keamanan dan integritas pada dokumen, sehingga menjamin keasliannya dan memungkinkan untuk mendeteksi modifikasi selanjutnya. Dengan mengikuti langkah-langkah yang diberikan, Anda dapat dengan mudah membuat PDF yang ditandatangani secara digital menggunakan sertifikat dengan Aspose.Words untuk .NET.

### Pertanyaan yang Sering Diajukan

#### T: Apa itu tanda tangan digital dan mengapa penting dalam dokumen PDF?
J: Tanda tangan digital adalah teknik keamanan yang membantu memastikan keaslian, integritas, dan non-penyangkalan dokumen elektronik, seperti file PDF. Ia menggunakan sertifikat digital untuk menambahkan lapisan keamanan pada dokumen, yang membantu memverifikasi identitas penulis dan mendeteksi perubahan selanjutnya pada konten.

#### T: Bagaimana cara menambahkan tanda tangan digital ke dokumen PDF menggunakan sertifikat dengan Aspose.Words untuk .NET?
J: Untuk menambahkan tanda tangan digital ke dokumen PDF menggunakan sertifikat dengan Aspose.Words untuk .NET, ikuti langkah-langkah berikut:

 Buat sebuah instance dari`Document` kelas untuk mewakili dokumen.

 Menggunakan`DocumentBuilder` kelas untuk menambahkan konten yang diinginkan ke dokumen.

 Buat sebuah instance dari`PdfSaveOptions` kelas dan tentukan detail tanda tangan digital menggunakan`PdfDigitalSignatureDetails` kelas. Anda harus memberikan jalur ke sertifikat (`CertificateHolder.Create`), kata sandi terkait, serta alasan penandatanganan dan lokasi.

 Menggunakan`Save` metode untuk menyimpan dokumen dalam format PDF dengan menentukan opsi penyimpanan.

#### T: Bagaimana cara mendapatkan sertifikat untuk menambahkan tanda tangan digital ke dokumen PDF?
J: Untuk mendapatkan sertifikat guna menambahkan tanda tangan digital ke dokumen PDF, Anda biasanya dapat menghubungi otoritas sertifikat (CA) atau penyedia layanan kepercayaan. Entitas ini menerbitkan sertifikat digital setelah memverifikasi identitas Anda dan memvalidasi permintaan Anda. Setelah Anda memperoleh sertifikat, Anda dapat menggunakannya di aplikasi Anda untuk menambahkan tanda tangan digital ke dokumen PDF.

#### T: Apakah detail tanda tangan digital dapat disesuaikan, seperti alasan dan lokasi?
 J: Ya, Anda dapat menyesuaikan detail tanda tangan digital dengan menentukan alasan dan lokasi tanda tangan. Dalam contoh kode yang disediakan, Anda dapat mengubah nilai`reason`Dan`location` parameter saat membuat`PdfDigitalSignatureDetails` obyek. Pastikan untuk memberikan informasi yang sesuai untuk setiap parameter untuk mencerminkan alasan dan lokasi tanda tangan di dokumen PDF Anda.