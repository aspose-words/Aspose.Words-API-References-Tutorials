---
title: Muat Pdf Terenkripsi
linktitle: Muat Pdf Terenkripsi
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk memuat PDF terenkripsi menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-pdfloadoptions/load-encrypted-pdf/
---

Saat Memproses Kata dengan dokumen PDF di aplikasi .NET Anda, mungkin perlu memuat file PDF yang dilindungi kata sandi. Aspose.Words untuk .NET adalah perpustakaan canggih yang menyediakan fungsionalitas untuk memuat dokumen PDF terenkripsi. Pada artikel ini, kami akan memandu Anda langkah demi langkah untuk memahami dan menggunakan fitur ini.

## Memahami Memuat Fitur PDF Terenkripsi

Fitur Muat PDF Terenkripsi dari Aspose.Words untuk .NET memungkinkan Anda memuat file PDF yang dilindungi kata sandi. Anda dapat menentukan kata sandi saat memuat dokumen sehingga Anda dapat mengakses kontennya dan memanipulasinya sesuai kebutuhan.

## Langkah 1: Memuat Dokumen PDF Terenkripsi

Langkah pertama adalah memuat dokumen PDF terenkripsi ke dalam aplikasi Anda. Berikut cara melakukannya:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document doc = new Document(dataDir + "Document.pdf");
```

 Pastikan untuk menentukan jalur yang benar ke file PDF terenkripsi di`dataDir` variabel.

## Langkah 2: Mengenkripsi Dokumen PDF

 Jika Anda juga ingin mengenkripsi dokumen PDF Anda, Anda dapat melakukannya menggunakan`PdfSaveOptions` kelas dan menentukan detail enkripsi:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
EncryptionDetails = new PdfEncryptionDetails("Aspose", null)
};

```

Ini akan membuat versi dokumen PDF terenkripsi di direktori yang ditentukan.

## Langkah 3: Menyimpan Dokumen PDF Terenkripsi

Setelah mengunggah dan mengenkripsi dokumen PDF secara opsional, Anda dapat menyimpannya dalam format lain atau memprosesnya lebih lanjut sesuai kebutuhan spesifik Anda.

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", saveOptions);
```

## Langkah 5: Memuat Dokumen PDF Terenkripsi dengan Kata Sandi

Pemeliharaan

Namun, jika Anda ingin memuat dokumen PDF terenkripsi dengan kata sandi, Anda harus menggunakan`PdfLoadOptions` kelas dan tentukan kata sandi saat memuat dokumen:

```csharp
PdfLoadOptions loadOptions = new PdfLoadOptions { Password = "Aspose", LoadFormat = LoadFormat.Pdf };

doc = new Document(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", loadOptions);
```

 Pastikan untuk memberikan kata sandi yang benar di`Password` variabel.

### Contoh Kode Sumber untuk Memuat PDF Terenkripsi menggunakan Aspose.Words untuk .NET

```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Pdf Document.pdf");

	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		EncryptionDetails = new PdfEncryptionDetails("Aspose", null)
	};

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", saveOptions);

	PdfLoadOptions loadOptions = new PdfLoadOptions { Password = "Aspose", LoadFormat = LoadFormat.Pdf };

	doc = new Document(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", loadOptions);
        
```

## Kesimpulan

Dalam artikel ini, kami menjelajahi cara menggunakan fitur Load Encrypted PDF dari Aspose.Words untuk .NET. Anda mempelajari cara mengunggah file PDF terenkripsi, cara mengenkripsi dokumen PDF, cara mengunggah PDF terenkripsi dengan kata sandi, dan cara menghasilkan keluaran dalam format penurunan harga. Fitur ini sangat berguna saat Memproses Kata dengan dokumen PDF yang aman.


