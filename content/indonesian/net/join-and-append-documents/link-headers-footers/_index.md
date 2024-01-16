---
title: Tautan Header Footer
linktitle: Tautan Header Footer
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menautkan header dan footer saat menggabungkan dan menambahkan dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/join-and-append-documents/link-headers-footers/
---

Tutorial ini akan memandu Anda melalui proses penggunaan fitur Link Headers Footers Aspose.Words untuk .NET. Fitur ini memungkinkan Anda untuk menggabungkan dan menambahkan beberapa dokumen Word sambil menghubungkan header dan footer dokumen sumber ke bagian sebelumnya di dokumen tujuan.

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

## Langkah 3: Atur Dokumen yang Ditambahkan agar Muncul di Halaman Baru

 Untuk memastikan bahwa konten dari dokumen sumber muncul di halaman baru di dokumen tujuan, Anda perlu mengaturnya`SectionStart` properti bagian pertama dalam dokumen sumber ke`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## Langkah 4: Tautkan Header dan Footer ke Bagian Sebelumnya

Untuk menautkan header dan footer dokumen sumber ke bagian sebelumnya di dokumen tujuan, Anda dapat menggunakan`LinkToPrevious` metode`HeadersFooters` koleksi. Dengan lewat`true` sebagai parameternya, Anda mengganti header atau footer yang ada di dokumen sumber.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
```

## Langkah 5: Tambahkan Dokumen Sumber ke Dokumen Tujuan

 Sekarang, Anda dapat menambahkan dokumen sumber ke dokumen tujuan menggunakan`AppendDocument` metode`Document` kelas. Itu`ImportFormatMode.KeepSourceFormatting` parameter memastikan bahwa pemformatan sumber dipertahankan selama operasi penambahan.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Langkah 6: Simpan Dokumen Akhir

 Terakhir, simpan dokumen gabungan dengan header dan footer tertaut menggunakan`Save` metode`Document` kelas.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

### Contoh kode sumber untuk Link Header Footer menggunakan Aspose.Words untuk .NET 

Berikut kode sumber lengkap untuk fitur "Link Headers Footers" di C# menggunakan Aspose.Words untuk .NET:


```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Atur dokumen yang ditambahkan agar muncul di halaman baru.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	// Tautkan header dan footer di dokumen sumber ke bagian sebelumnya.
	// Ini akan mengesampingkan header atau footer apa pun yang sudah ditemukan di dokumen sumber.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

Itu dia! Anda telah berhasil mengimplementasikan fitur Link Headers Footers menggunakan Aspose.Words untuk .NET. Dokumen akhir akan berisi konten gabungan dengan header dan footer dari dokumen sumber yang ditautkan ke bagian sebelumnya di dokumen tujuan.