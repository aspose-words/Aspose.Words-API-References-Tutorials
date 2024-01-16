---
title: Mulai Ulang Penomoran Halaman
linktitle: Mulai Ulang Penomoran Halaman
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara memulai ulang penomoran halaman saat menggabungkan dan menambahkan dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/join-and-append-documents/restart-page-numbering/
---

Tutorial ini akan memandu Anda melalui proses penggunaan fitur Mulai Ulang Penomoran Halaman Aspose.Words untuk .NET. Fitur ini memungkinkan Anda untuk menggabungkan dan menambahkan dokumen Word sambil memulai ulang penomoran halaman di dokumen sumber.

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

## Langkah 3: Atur Dokumen Sumber untuk Memulai Ulang Penomoran Halaman

 Untuk memulai ulang penomoran halaman di dokumen sumber, Anda perlu menyetel`SectionStart` properti bagian pertama dalam dokumen sumber ke`SectionStart.NewPage` dan atur`RestartPageNumbering`properti ke`true`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
```

## Langkah 4: Tambahkan Dokumen Sumber ke Dokumen Tujuan

 Sekarang, Anda dapat menambahkan dokumen sumber ke dokumen tujuan menggunakan`AppendDocument` metode`Document` kelas. Itu`ImportFormatMode.KeepSourceFormatting` parameter memastikan bahwa pemformatan sumber dipertahankan selama operasi penambahan.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Langkah 5: Simpan Dokumen Akhir

 Terakhir, simpan dokumen yang digabungkan dengan fitur Mulai Ulang Penomoran Halaman yang diaktifkan menggunakan`Save` metode`Document` kelas.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RestartPageNumbering.docx");
```

### Contoh kode sumber untuk Mulai Ulang Penomoran Halaman menggunakan Aspose.Words untuk .NET

Berikut kode sumber lengkap untuk fitur "Restart Page Numbering" di C# menggunakan Aspose.Words untuk .NET:
 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RestartPageNumbering.docx");
```

Itu dia! Anda telah berhasil mengimplementasikan fitur Restart Page Numbering menggunakan Aspose.Words for .NET. Dokumen akhir akan berisi konten gabungan dengan penomoran halaman yang dimulai ulang di dokumen sumber.