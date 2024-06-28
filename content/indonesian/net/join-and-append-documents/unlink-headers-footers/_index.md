---
title: Putuskan tautan Header Footer
linktitle: Putuskan tautan Header Footer
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menggabungkan dan menambahkan dokumen Word sambil memutuskan tautan header dan footer menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/join-and-append-documents/unlink-headers-footers/
---

Tutorial ini akan memandu Anda melalui proses penggunaan fitur Unlink Headers Footers Aspose.Words untuk .NET. Fitur ini memungkinkan Anda untuk menggabungkan dan menambahkan dokumen Word sambil memutuskan tautan header dan footer dari dokumen sumber.

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

Selanjutnya, Anda perlu memuat dokumen sumber dan tujuan menggunakan Aspose.Words.`Document` kelas. Perbarui nama file di`Document` konstruktor sesuai dengan nama dokumen Anda.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Langkah 3: Putuskan tautan Header dan Footer di Dokumen Sumber

 Untuk memutuskan tautan header dan footer di dokumen sumber agar tidak melanjutkan header dan footer dokumen tujuan, Anda perlu mengatur`LinkToPrevious` properti dari`HeadersFooters` koleksi di bagian pertama dokumen sumber untuk`false`.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Langkah 4: Tambahkan Dokumen Sumber ke Dokumen Tujuan

 Sekarang, Anda dapat menambahkan dokumen sumber ke dokumen tujuan menggunakan`AppendDocument` metode`Document` kelas. Itu`ImportFormatMode.KeepSourceFormatting` parameter memastikan bahwa pemformatan sumber dipertahankan selama operasi penambahan.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Langkah 5: Simpan Dokumen Akhir

 Terakhir, simpan dokumen yang digabungkan dengan fitur Unlink Headers Footers yang diaktifkan menggunakan`Save` metode`Document` kelas.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

### Contoh kode sumber untuk Unlink Headers Footers menggunakan Aspose.Words untuk .NET

Berikut kode sumber lengkap untuk fitur "Batalkan Tautan Header Footer" di C# menggunakan Aspose.Words untuk .NET:

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Putuskan tautan header dan footer di dokumen sumber untuk menghentikan hal ini
	// dari melanjutkan header dan footer dokumen tujuan.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

Itu dia! Anda telah berhasil mengimplementasikan fitur Unlink Headers Footers menggunakan Aspose.Words untuk .NET. Dokumen akhir akan berisi konten yang digabungkan dengan header dan footer dari dokumen sumber yang tidak ditautkan dari dokumen tujuan.