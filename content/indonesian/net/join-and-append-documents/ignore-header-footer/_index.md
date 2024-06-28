---
title: Abaikan Header Footer
linktitle: Abaikan Header Footer
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menambahkan dokumen sambil mengabaikan konten header dan footer menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/join-and-append-documents/ignore-header-footer/
---

Tutorial ini menjelaskan cara menggunakan Aspose.Words untuk .NET untuk menambahkan dokumen sambil mengabaikan konten header dan footer. Kode sumber yang disediakan menunjukkan cara menyiapkan opsi format impor untuk mengecualikan header dan footer selama proses penambahan.

## Langkah 1: Siapkan proyek

Pastikan Anda memiliki prasyarat berikut:

-  Aspose.Words untuk perpustakaan .NET diinstal. Anda dapat mengunduhnya dari[Aspose.Releases]https://releases.aspose.com/words/net/ atau gunakan manajer paket NuGet untuk menginstalnya.
- Jalur direktori dokumen tempat dokumen sumber dan tujuan berada.

## Langkah 2: Buka dokumen sumber dan tujuan

 Buka dokumen sumber dan tujuan menggunakan`Document` konstruktor kelas. Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDocument = new Document(dataDir + "Document source.docx");
Document dstDocument = new Document(dataDir + "Northwind traders.docx");
```

## Langkah 3: Siapkan opsi format impor

 Buat sebuah instance dari`ImportFormatOptions` kelas dan atur`IgnoreHeaderFooter`properti ke`false`. Hal ini memastikan bahwa konten header dan footer disertakan selama proses penambahan.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
```

## Langkah 4: Tambahkan dokumen sumber ke dokumen tujuan

 Menggunakan`AppendDocument` metode dokumen tujuan untuk menambahkan dokumen sumber. Lulus`ImportFormatMode.KeepSourceFormatting`sebagai parameter kedua dan opsi format impor sebagai parameter ketiga.

```csharp
dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## Langkah 5: Simpan dokumen tujuan

Terakhir, simpan dokumen tujuan yang telah dimodifikasi menggunakan`Save` metode`Document` obyek.

```csharp
dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```

Ini menyelesaikan implementasi penambahan dokumen sambil mengabaikan konten header dan footer menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber untuk Abaikan Header Footer menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDocument = new Document(dataDir + "Document source.docx");
	Document dstDocument = new Document(dataDir + "Northwind traders.docx");
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
	dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
	dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```