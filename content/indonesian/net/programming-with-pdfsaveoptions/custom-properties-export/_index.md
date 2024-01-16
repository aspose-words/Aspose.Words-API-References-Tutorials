---
title: Ekspor Properti Kustom dalam Dokumen PDF
linktitle: Ekspor Properti Kustom dalam Dokumen PDF
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengekspor properti khusus saat mengonversi dokumen ke PDF dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-pdfsaveoptions/custom-properties-export/
---

Dalam tutorial ini, kami akan memandu Anda melalui langkah-langkah untuk mengekspor properti kustom dokumen dalam dokumen PDF menggunakan Aspose.Words untuk .NET. Mengekspor properti khusus memungkinkan Anda memasukkan informasi tambahan ke dalam dokumen PDF yang dihasilkan. Ikuti langkah-langkah di bawah ini:

## Langkah 1: Membuat Dokumen dan Menambahkan Properti Kustom

Mulailah dengan membuat instance kelas Dokumen:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Langkah 2: Tambahkan properti khusus
 Selanjutnya, tambahkan properti khusus yang diinginkan. Misalnya, untuk menambahkan properti "Perusahaan" dengan nilai "Aspose", gunakan`Add` metode pengumpulan CustomDocumentProperties:

```csharp
doc.CustomDocumentProperties.Add("Company", "Aspose");
```

Anda dapat menambahkan properti khusus sebanyak yang diperlukan.

## Langkah 3: Tetapkan opsi ekspor PDF

Buat instance kelas PdfSaveOptions dan tentukan cara mengekspor properti khusus:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };
```

Opsi ini mengontrol ekspor properti khusus saat mengonversi ke PDF.

## Langkah 4: Konversi Dokumen ke PDF

 Menggunakan`Save` metode untuk mengonversi dokumen ke PDF dengan menentukan opsi konversi:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);
```

Pastikan untuk menentukan jalur yang benar untuk menyimpan PDF yang dikonversi.

### Contoh kode sumber untuk Ekspor Properti Kustom menggunakan Aspose.Words untuk .NET

Berikut adalah kode sumber lengkap untuk mengekspor properti khusus dari dokumen menggunakan Aspose.Words untuk .NET:


```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	doc.CustomDocumentProperties.Add("Company", "Aspose");

	PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);

```

Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah mengekspor properti kustom dokumen saat mengonversi ke PDF dengan Aspose.Words untuk .NET.


## Kesimpulan

Dalam tutorial ini, kami menjelaskan cara mengekspor properti kustom dari dokumen ke dokumen PDF menggunakan Aspose.Words untuk .NET. Dengan mengikuti langkah-langkah yang dijelaskan, Anda dapat dengan mudah memasukkan informasi tambahan dalam dokumen PDF yang dihasilkan dengan mengekspor properti kustom dokumen. Manfaatkan fitur Aspose.Words untuk .NET untuk mempersonalisasi dan memperkaya dokumen PDF Anda dengan mengekspor properti khusus.

### Pertanyaan yang Sering Diajukan

#### T: Apa yang dimaksud dengan mengekspor properti khusus ke dokumen PDF?
J: Mengekspor properti khusus ke dokumen PDF memungkinkan informasi tambahan disertakan dalam dokumen PDF yang dihasilkan. Properti khusus adalah metadata khusus untuk dokumen Anda, seperti tag, kata kunci, atau kredensial. Dengan mengekspor properti khusus ini, Anda dapat membuatnya tersedia bagi pengguna saat melihat dokumen PDF.

#### T: Bagaimana cara mengekspor properti kustom dokumen ke dokumen PDF menggunakan Aspose.Words untuk .NET?
J: Untuk mengekspor properti kustom dokumen ke dokumen PDF menggunakan Aspose.Words untuk .NET, ikuti langkah-langkah berikut:

 Buat sebuah instance dari`Document` kelas.

 Tambahkan properti khusus yang diinginkan menggunakan`CustomDocumentProperties` koleksi. Misalnya, gunakan`Add` metode untuk menambahkan properti "Perusahaan" dengan nilai "Aspose".

 Buat sebuah instance dari`PdfSaveOptions` kelas dan tentukan cara mengekspor properti khusus menggunakan`CustomPropertiesExport` Properti. Itu`PdfCustomPropertiesExport.Standard` value mengekspor properti khusus sesuai dengan pengaturan default.

 Menggunakan`Save` metode`Document` kelas untuk mengonversi dokumen ke PDF dengan menentukan opsi konversi.

#### T: Bagaimana cara mengakses properti khusus dokumen PDF?
J: Untuk mengakses properti khusus dokumen PDF, Anda dapat menggunakan pembaca PDF kompatibel yang mendukung tampilan properti dokumen. Pembaca PDF yang paling umum, seperti Adobe Acrobat Reader, menyediakan akses ke metadata dan properti dokumen PDF. Biasanya Anda dapat menemukan opsi ini di menu "File" atau dengan mengklik kanan dokumen dan memilih "Properties".