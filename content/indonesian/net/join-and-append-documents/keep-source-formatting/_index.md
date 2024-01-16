---
title: Pertahankan Pemformatan Sumber
linktitle: Pertahankan Pemformatan Sumber
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menambahkan dokumen sumber ke dokumen tujuan sambil mempertahankan format asli menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/join-and-append-documents/keep-source-formatting/
---

Tutorial ini menunjukkan cara menambahkan dokumen sumber ke dokumen tujuan sambil mempertahankan format asli dokumen sumber menggunakan Aspose.Words untuk .NET.

## Langkah 1: Siapkan proyek

Pastikan Anda memiliki prasyarat berikut:

-  Aspose.Words untuk perpustakaan .NET diinstal. Anda dapat mengunduhnya dari[Aspose.Releases]https://releases.aspose.com/words/net/ atau gunakan manajer paket NuGet untuk menginstalnya.
- Jalur direktori dokumen tempat dokumen sumber dan tujuan akan disimpan.

## Langkah 2: Buat dokumen tujuan dan sumber

 Buat contoh dari`Document` untuk dokumen tujuan dan sumber.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document dstDoc = new Document();
dstDoc.FirstSection.Body.AppendParagraph("Destination document text.");

Document srcDoc = new Document();
srcDoc.FirstSection.Body.AppendParagraph("Source document text.");
```

## Langkah 3: Tambahkan dokumen sumber ke dokumen tujuan

 Menggunakan`AppendDocument` metode dokumen tujuan untuk menambahkan dokumen sumber. Lulus`ImportFormatMode.KeepSourceFormatting` sebagai mode format impor untuk mempertahankan format asli dokumen sumber.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Langkah 4: Simpan dokumen yang dimodifikasi

 Simpan dokumen yang dimodifikasi menggunakan`Save` metode`Document` obyek.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```

Ini menyelesaikan implementasi penambahan dokumen sumber ke dokumen tujuan sambil mempertahankan format asli menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber untuk Keep Source Formatting menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document dstDoc = new Document();
	dstDoc.FirstSection.Body.AppendParagraph("Destination document text. ");
	Document srcDoc = new Document();
	srcDoc.FirstSection.Body.AppendParagraph("Source document text. ");
	// Tambahkan dokumen sumber ke dokumen tujuan.
	// Lewati mode format untuk mempertahankan format asli dokumen sumber saat mengimpornya.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```