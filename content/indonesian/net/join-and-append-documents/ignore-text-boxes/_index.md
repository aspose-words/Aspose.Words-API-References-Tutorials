---
title: Abaikan Kotak Teks
linktitle: Abaikan Kotak Teks
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menambahkan dokumen sambil mengabaikan pemformatan kotak teks menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/join-and-append-documents/ignore-text-boxes/
---

Tutorial ini menjelaskan cara menggunakan Aspose.Words untuk .NET untuk menambahkan dokumen sambil mempertahankan format kotak teks. Kode sumber yang disediakan menunjukkan cara mengatur opsi format impor untuk menyertakan kotak teks selama proses penambahan.

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

## Langkah 3: Siapkan opsi format impor

 Buat sebuah instance dari`ImportFormatOptions` kelas dan atur`IgnoreTextBoxes`properti ke`false`. Hal ini memastikan bahwa kotak teks disertakan selama proses penambahan sambil mempertahankan formatnya.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
```

## Langkah 4: Tambahkan konten kotak teks

 Membuat`NodeImporter`objek dan menggunakannya untuk mengimpor node kotak teks dari dokumen sumber ke dokumen tujuan. Ulangi setiap paragraf dalam dokumen sumber dan impor ke dokumen tujuan.

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, true);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## Langkah 5: Simpan dokumen tujuan

Terakhir, simpan dokumen tujuan yang telah dimodifikasi menggunakan`Save` metode`Document` obyek.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```

Ini menyelesaikan implementasi penambahan dokumen sambil mempertahankan pemformatan kotak teks menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber untuk Abaikan Kotak Teks menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Pertahankan format kotak teks sumber saat mengimpor.
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, true);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```