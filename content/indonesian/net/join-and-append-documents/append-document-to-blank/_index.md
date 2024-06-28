---
title: Tambahkan Dokumen Ke Kosong
linktitle: Tambahkan Dokumen Ke Kosong
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menambahkan dokumen ke dokumen tujuan kosong di Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/join-and-append-documents/append-document-to-blank/
---

Tutorial ini menjelaskan cara menggunakan Aspose.Words untuk .NET untuk menambahkan konten satu dokumen ke dokumen tujuan kosong. Kode sumber yang disediakan menunjukkan cara membuat dokumen baru, menghapus kontennya, dan kemudian menambahkan dokumen sumber ke dalamnya.

## Langkah 1: Siapkan proyek

Pastikan Anda memiliki prasyarat berikut:

-  Aspose.Words untuk perpustakaan .NET diinstal. Anda dapat mengunduhnya dari[Aspose.Releases]https://releases.aspose.com/words/net/ atau gunakan manajer paket NuGet untuk menginstalnya.
- Jalur direktori dokumen tempat dokumen sumber dan tujuan berada.

## Langkah 2: Buat dokumen tujuan baru

 Buat yang baru`Document` objek untuk dokumen tujuan.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document();
```

## Langkah 3: Hapus konten yang ada dari dokumen tujuan

 Untuk memastikan dokumen tujuan bersih, hapus semua konten yang ada dari dokumen menggunakan`RemoveAllChildren` metode.

```csharp
dstDoc.RemoveAllChildren();
```

## Langkah 4: Tambahkan dokumen sumber ke dokumen tujuan

 Tambahkan konten dokumen sumber ke dokumen tujuan menggunakan`AppendDocument` metode dengan`ImportFormatMode.KeepSourceFormatting` pilihan.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Langkah 5: Simpan dokumen tujuan

Terakhir, simpan dokumen tujuan yang telah dimodifikasi menggunakan`Save` metode`Document` obyek.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");
```

Ini menyelesaikan implementasi penambahan dokumen ke dokumen tujuan kosong menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber untuk Menambahkan Dokumen Ke Kosong menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document();
	// Dokumen tujuan tidak kosong, seringkali menyebabkan halaman kosong muncul sebelum dokumen yang dilampirkan.
	// Hal ini disebabkan dokumen dasar memiliki bagian yang kosong dan dokumen baru dimulai pada halaman berikutnya.
	// Hapus semua konten dari dokumen tujuan sebelum menambahkan.
	dstDoc.RemoveAllChildren();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");

```