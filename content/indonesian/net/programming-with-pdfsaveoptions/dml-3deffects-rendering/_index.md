---
title: Render Efek 3D DML 3D dalam Dokumen PDF
linktitle: Render Efek 3D DML 3D dalam Dokumen PDF
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengaktifkan rendering efek DML 3D saat mengonversi ke PDF dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-pdfsaveoptions/dml-3deffects-rendering/
---

Dalam tutorial ini, kami akan memandu Anda melalui langkah-langkah untuk mengaktifkan rendering efek DML 3D saat mengonversi ke PDF dengan Aspose.Words untuk .NET. Ini menjaga efek 3D dalam dokumen PDF yang dihasilkan. Ikuti langkah-langkah di bawah ini:

## Langkah 1: Memuat dokumen

Mulailah dengan mengunggah dokumen yang ingin Anda konversi ke PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Pastikan untuk menentukan jalur yang benar ke dokumen Anda.

## Langkah 2: Konfigurasikan opsi penyimpanan PDF

Buat instance kelas PdfSaveOptions dan aktifkan rendering efek DML 3D tingkat lanjut:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };
```

Opsi ini mempertahankan efek 3D dalam dokumen PDF yang dihasilkan.

## Langkah 3: Konversi Dokumen ke PDF

 Menggunakan`Save` metode untuk mengonversi dokumen ke PDF dengan menentukan opsi penyimpanan:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
```

Pastikan untuk menentukan jalur yang benar untuk menyimpan PDF yang dikonversi.

### Contoh kode sumber untuk Dml 3DEffects Rendering menggunakan Aspose.Words untuk .NET

```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
	 
```

Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah mengaktifkan rendering efek DML 3D saat mengonversi ke PDF dengan Aspose.Words untuk .NET.

## Kesimpulan

Dalam tutorial ini, kami menjelaskan cara mengaktifkan rendering efek DML 3D saat mengonversi ke PDF dengan Aspose.Words untuk .NET. Dengan mengikuti langkah-langkah yang dijelaskan, Anda dapat dengan mudah menyimpan efek 3D dalam dokumen PDF yang dihasilkan. Gunakan fitur ini untuk mempertahankan efek visual penting dari dokumen asli Anda.


### Pertanyaan yang Sering Diajukan

#### T: Apa yang dimaksud dengan rendering efek DML 3D dalam dokumen PDF?
J: Merender efek DML 3D dalam dokumen PDF mengacu pada kemampuan untuk mempertahankan efek 3D saat mengonversi dokumen ke format PDF. Ini mempertahankan efek visual dan memastikan bahwa dokumen PDF yang dihasilkan terlihat seperti dokumen aslinya.

#### T: Bagaimana cara mengaktifkan rendering efek DML 3D saat mengonversi ke PDF dengan Aspose.Words untuk .NET?
J: Untuk mengaktifkan rendering efek DML 3D saat mengonversi ke PDF dengan Aspose.Words untuk .NET, ikuti langkah-langkah berikut:

 Buat sebuah instance dari`Document` kelas yang menentukan jalur ke dokumen Word.

 Buat sebuah instance dari`PdfSaveOptions` kelas dan atur`Dml3DEffectsRenderingMode`properti ke`Dml3DEffectsRenderingMode.Advanced` untuk mengaktifkan rendering efek DML 3D tingkat lanjut.

 Menggunakan`Save` metode`Document`kelas untuk menyimpan dokumen dalam format PDF dengan menentukan opsi penyimpanan.

#### T: Bagaimana cara memeriksa apakah efek DML 3D telah dirender dalam dokumen PDF yang dihasilkan?
J: Untuk memeriksa apakah efek DML 3D telah dirender dalam dokumen PDF yang dihasilkan, buka file PDF dengan penampil PDF yang kompatibel, seperti Adobe Acrobat Reader, dan periksa dokumen tersebut. Anda akan melihat efek 3D seperti yang muncul di dokumen aslinya.



