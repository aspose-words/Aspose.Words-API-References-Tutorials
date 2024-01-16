---
title: Sisipkan Dokumen Dengan Pembuat
linktitle: Sisipkan Dokumen Dengan Pembuat
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyisipkan dokumen di akhir dokumen lain menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/join-and-append-documents/insert-document-with-builder/
---

 Tutorial ini menjelaskan cara menggunakan Aspose.Words untuk .NET untuk menyisipkan dokumen ke dokumen lain menggunakan`DocumentBuilder` kelas. Kode sumber yang disediakan menunjukkan cara menyisipkan dokumen di akhir dokumen lain sambil mempertahankan format sumber.

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

## Langkah 3: Inisialisasi DocumentBuilder

 Buat instance baru dari`DocumentBuilder` kelas dan meneruskan dokumen tujuan sebagai parameter.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
```

## Langkah 4: Posisikan DocumentBuilder

 Memindahkan`DocumentBuilder` ke akhir dokumen menggunakan`MoveToDocumentEnd` metode. Sisipkan hentian halaman untuk memisahkan konten yang ada dari dokumen yang disisipkan.

```csharp
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## Langkah 5: Masukkan dokumen sumber

 Menggunakan`InsertDocument` metode`DocumentBuilder` kelas untuk memasukkan dokumen sumber ke dalam dokumen tujuan. Atur mode format impor ke`ImportFormatMode.KeepSourceFormatting` untuk mempertahankan format sumber.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Langkah 6: Simpan dokumen yang dimodifikasi

 Terakhir, simpan dokumen tujuan yang telah dimodifikasi menggunakan`Save` metode`Document` obyek.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```

Ini menyelesaikan implementasi penyisipan dokumen ke dokumen lain menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber untuk Sisipkan Dokumen Dengan Pembuat menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	DocumentBuilder builder = new DocumentBuilder(dstDoc);
	builder.MoveToDocumentEnd();
	builder.InsertBreak(BreakType.PageBreak);
	builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```