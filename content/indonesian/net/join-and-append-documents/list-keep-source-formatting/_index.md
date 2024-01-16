---
title: Daftar Simpan Pemformatan Sumber
linktitle: Daftar Simpan Pemformatan Sumber
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mempertahankan pemformatan daftar saat menggabungkan dan menambahkan dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/join-and-append-documents/list-keep-source-formatting/
---

Tutorial ini akan memandu Anda melalui proses penggunaan fitur Pemformatan Sumber Daftar dari Aspose.Words untuk .NET. Fitur ini memungkinkan Anda untuk menggabungkan dan menambahkan dokumen Word sambil mempertahankan format sumber daftar.

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
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Langkah 3: Atur Dokumen Sumber agar Mengalir Terus Menerus

 Untuk memastikan bahwa konten dari dokumen sumber mengalir terus menerus saat ditambahkan ke dokumen tujuan, Anda perlu mengaturnya`SectionStart` properti bagian pertama dalam dokumen sumber ke`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Langkah 4: Tambahkan Dokumen Sumber ke Dokumen Tujuan

 Sekarang, Anda dapat menambahkan dokumen sumber ke dokumen tujuan menggunakan`AppendDocument` metode`Document` kelas. Itu`ImportFormatMode.KeepSourceFormatting`parameter memastikan bahwa pemformatan sumber, termasuk pemformatan daftar, dipertahankan selama operasi penambahan.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Langkah 5: Simpan Dokumen Akhir

 Terakhir, simpan dokumen yang digabungkan dengan fitur List Keep Source Formatting yang diaktifkan menggunakan`Save` metode`Document` kelas.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

### Contoh kode sumber untuk Pemformatan Sumber Daftar Simpan menggunakan Aspose.Words untuk .NET 

Berikut kode sumber lengkap untuk fitur Pemformatan Sumber Daftar di C# menggunakan Aspose.Words untuk .NET:

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Tambahkan konten dokumen agar mengalir terus menerus.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

Itu dia! Anda telah berhasil mengimplementasikan fitur Pemformatan Sumber Daftar menggunakan Aspose.Words untuk .NET. Dokumen akhir akan berisi konten yang digabungkan dengan format daftar dokumen sumber yang dipertahankan.