---
title: Pertahankan Penomoran Sumber
linktitle: Pertahankan Penomoran Sumber
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menambahkan dokumen sambil mempertahankan format penomoran sumber di Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/join-and-append-documents/keep-source-numbering/
---

Tutorial ini menjelaskan cara menambahkan dokumen sumber ke dokumen tujuan sambil mempertahankan format penomoran asli paragraf bernomor menggunakan Aspose.Words untuk .NET.

## Langkah 1: Siapkan proyek

Pastikan Anda memiliki prasyarat berikut:

-  Aspose.Words untuk perpustakaan .NET diinstal. Anda dapat mengunduhnya dari[Aspose.Releases]https://releases.aspose.com/words/net/ atau gunakan manajer paket NuGet untuk menginstalnya.
- Jalur direktori dokumen tempat dokumen sumber dan tujuan akan disimpan.

## Langkah 2: Buat dokumen tujuan dan sumber

 Buat contoh dari`Document` untuk dokumen tujuan dan sumber.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Langkah 3: Pertahankan penomoran sumber saat mengimpor

 Untuk mempertahankan format penomoran paragraf bernomor dari dokumen sumber, buatlah sebuah instance dari`ImportFormatOptions` dan atur`KeepSourceNumbering` ke`true` . Gunakan`NodeImporter` untuk mengimpor node dari dokumen sumber ke dokumen tujuan, dengan menentukan`ImportFormatMode.KeepSourceFormatting` dan itu`importFormatOptions`.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## Langkah 4: Impor dan tambahkan paragraf

Ulangi paragraf-paragraf dalam dokumen sumber dan impor setiap paragraf ke dalam dokumen tujuan menggunakan`importer`. Tambahkan node yang diimpor ke badan dokumen tujuan.

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, false);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## Langkah 5: Simpan dokumen yang dimodifikasi

 Simpan dokumen yang dimodifikasi menggunakan`Save` metode`Document` obyek.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```

Ini menyelesaikan implementasi penambahan dokumen sumber ke dokumen tujuan sambil mempertahankan format penomoran asli menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber untuk Pertahankan Penomoran Sumber menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Pertahankan format daftar sumber saat mengimpor paragraf bernomor.
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, false);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```