---
title: Tambahkan Dengan Opsi Format Impor
linktitle: Tambahkan Dengan Opsi Format Impor
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menambahkan dokumen dengan opsi format impor menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/join-and-append-documents/append-with-import-format-options/
---

Tutorial ini menjelaskan cara menggunakan Aspose.Words untuk .NET untuk menambahkan konten satu dokumen ke dokumen lain dengan opsi format impor. Kode sumber yang disediakan menunjukkan cara membuka dokumen sumber dan tujuan, menentukan opsi format impor, dan menambahkan dokumen sumber ke dokumen tujuan.

## Langkah 1: Siapkan proyek

Pastikan Anda memiliki prasyarat berikut:

-  Aspose.Words untuk perpustakaan .NET diinstal. Anda dapat mengunduhnya dari[Aspose.Releases]https://releases.aspose.com/words/net/ atau gunakan manajer paket NuGet untuk menginstalnya.
- Jalur direktori dokumen tempat dokumen sumber dan tujuan berada.

## Langkah 2: Buka dokumen sumber dan tujuan

 Buka dokumen sumber dan tujuan menggunakan`Document` konstruktor kelas. Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source with list.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Langkah 3: Tentukan opsi format impor

 Buat sebuah instance dari`ImportFormatOptions` kelas untuk menentukan opsi format impor. Dalam contoh ini, kami menggunakan`KeepSourceNumbering` milik untuk memastikan penomoran dari dokumen sumber digunakan jika terjadi bentrok dengan dokumen tujuan.

```csharp
ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
```

## Langkah 4: Tambahkan dokumen sumber ke dokumen tujuan

 Menggunakan`AppendDocument` metode dokumen tujuan untuk menambahkan dokumen sumber. Lulus`ImportFormatMode.UseDestinationStyles` sebagai parameter kedua untuk menggunakan gaya dan pemformatan dokumen tujuan.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## Langkah 5: Simpan dokumen tujuan

Terakhir, simpan dokumen tujuan yang telah dimodifikasi menggunakan`Save` metode`Document` obyek.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendWithImportFormatOptions.docx");
```

Ini menyelesaikan implementasi penambahan dokumen dengan opsi format impor menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber untuk Opsi Format Tambahkan Dengan Impor menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source with list.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Tentukan bahwa jika penomoran bertentangan dalam dokumen sumber dan tujuan,
	// maka penomoran dari dokumen sumber akan digunakan.
	ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);

```