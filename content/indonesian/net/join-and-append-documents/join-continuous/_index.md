---
title: Bergabunglah dengan Berkelanjutan
linktitle: Bergabunglah dengan Berkelanjutan
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menggabungkan dua dokumen secara terus-menerus sambil mempertahankan pemformatan menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/join-and-append-documents/join-continuous/
---

Tutorial ini menjelaskan cara menggabungkan dua dokumen secara terus menerus menggunakan Aspose.Words for .NET. Kode sumber yang disediakan menunjukkan cara menambahkan dokumen ke akhir dokumen lain sambil mempertahankan format aslinya.

## Langkah 1: Siapkan proyek

Pastikan Anda memiliki prasyarat berikut:

-  Aspose.Words untuk perpustakaan .NET diinstal. Anda dapat mengunduhnya dari[Aspose.Releases]https://releases.aspose.com/words/net/ atau gunakan manajer paket NuGet untuk menginstalnya.
- Jalur direktori dokumen tempat dokumen sumber dan tujuan berada.

## Langkah 2: Buka dokumen sumber dan tujuan

 Buka dokumen sumber dan tujuan menggunakan`Document` konstruktor kelas. Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Langkah 3: Siapkan permulaan bagian berkelanjutan

 Untuk membuat dokumen sumber muncul tepat setelah isi dokumen tujuan, atur`SectionStart` properti bagian pertama dalam dokumen sumber ke`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Langkah 4: Tambahkan dokumen sumber

 Tambahkan dokumen sumber ke dokumen tujuan menggunakan`AppendDocument` metode`Document` kelas. Atur mode format impor ke`ImportFormatMode.KeepSourceFormatting` untuk mempertahankan gaya asli dari dokumen sumber.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Langkah 5: Simpan dokumen yang dimodifikasi

 Terakhir, simpan dokumen tujuan yang telah dimodifikasi menggunakan`Save` metode`Document` obyek.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```

Ini menyelesaikan implementasi penggabungan dua dokumen secara terus menerus menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber untuk Gabung Berkelanjutan menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Jadikan dokumen muncul tepat setelah isi dokumen tujuan.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Tambahkan dokumen sumber menggunakan gaya asli yang ditemukan di dokumen sumber.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```