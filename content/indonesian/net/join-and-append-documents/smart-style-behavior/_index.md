---
title: Perilaku Gaya Cerdas
linktitle: Perilaku Gaya Cerdas
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mempertahankan perilaku gaya cerdas saat menggabungkan dan menambahkan dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/join-and-append-documents/smart-style-behavior/
---

Tutorial ini akan memandu Anda melalui proses penggunaan fitur Smart Style Behavior Aspose.Words untuk .NET. Fitur ini memungkinkan Anda untuk menggabungkan dan menambahkan dokumen Word sambil mempertahankan perilaku gaya cerdas.

## Prasyarat

Sebelum memulai, pastikan Anda memiliki hal berikut:

1. Aspose.Words untuk .NET diinstal. Anda dapat mendownloadnya dari situs Aspose atau menginstalnya melalui NuGet.
2. Visual Studio atau lingkungan pengembangan C# lainnya.

## Langkah 1: Inisialisasi Direktori Dokumen

 Pertama, Anda perlu menyetel jalur ke direktori dokumen Anda. Ubah nilai`dataDir` variabel ke jalur di mana dokumen Anda berada.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Muat Dokumen Sumber dan Tujuan

Selanjutnya, Anda perlu memuat dokumen sumber dan tujuan menggunakan Aspose.Words`Document` kelas. Perbarui nama file di`Document` konstruktor sesuai dengan nama dokumen Anda.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Langkah 3: Masukkan Page Break di Dokumen Tujuan

 Untuk memastikan bahwa konten yang ditambahkan muncul pada halaman baru di dokumen tujuan, Anda dapat menyisipkan hentian halaman menggunakan a`DocumentBuilder`.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## Langkah 4: Tetapkan Opsi Perilaku Gaya Cerdas

Untuk mengaktifkan perilaku gaya cerdas selama operasi penambahan, Anda perlu membuat sebuah instance`ImportFormatOptions` dan atur`SmartStyleBehavior`properti ke`true`.

```csharp
ImportFormatOptions options = new ImportFormatOptions { SmartStyleBehavior = true };
```

## Langkah 5: Tambahkan Dokumen Sumber ke Dokumen Tujuan

 Sekarang, Anda dapat menambahkan dokumen sumber ke dokumen tujuan menggunakan`InsertDocument` metode`DocumentBuilder` kelas. Menggunakan`ImportFormatMode.UseDestinationStyles` parameter dan lewati`ImportFormatOptions` objek untuk mempertahankan perilaku gaya cerdas.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## Langkah 6: Simpan Dokumen Akhir

 Terakhir, simpan dokumen gabungan dengan mengaktifkan fitur Smart Style Behavior menggunakan`Save` metode`Document` kelas.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.SmartStyleBehavior.docx");
```

### Contoh kode sumber untuk Smart Style Behavior menggunakan Aspose.Words untuk .NET

Berikut kode sumber lengkap untuk fitur "Smart Style Behavior" di C# menggunakan Aspose.Words untuk .NET:
 
```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	DocumentBuilder builder = new DocumentBuilder(dstDoc);
	builder.MoveToDocumentEnd();
	builder.InsertBreak(BreakType.PageBreak);
	ImportFormatOptions options = new ImportFormatOptions { SmartStyleBehavior = true };
	builder.InsertDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
	builder.Document.Save(dataDir + "JoinAndAppendDocuments.SmartStyleBehavior.docx");
```

Itu dia! Anda telah berhasil mengimplementasikan fitur Smart Style Behavior menggunakan Aspose.Words untuk .NET. Dokumen akhir akan berisi konten gabungan dengan perilaku gaya cerdas yang dipertahankan.