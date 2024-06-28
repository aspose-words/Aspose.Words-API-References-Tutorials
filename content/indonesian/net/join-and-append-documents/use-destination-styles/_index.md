---
title: Gunakan Gaya Tujuan
linktitle: Gunakan Gaya Tujuan
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menggabungkan dan menambahkan dokumen Word sambil menerapkan gaya dokumen tujuan menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/join-and-append-documents/use-destination-styles/
---

Tutorial ini akan memandu Anda melalui proses penggunaan fitur Gunakan Gaya Tujuan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda untuk menggabungkan dan menambahkan dokumen Word sambil menerapkan gaya dokumen tujuan.

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

## Langkah 3: Tambahkan Dokumen Sumber dengan Gaya Tujuan

 Untuk menambahkan dokumen sumber ke dokumen tujuan sambil menerapkan gaya dokumen tujuan, Anda dapat menggunakan`AppendDocument` metode`Document` kelas dengan`ImportFormatMode.UseDestinationStyles` parameter.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## Langkah 4: Simpan Dokumen Akhir

 Terakhir, simpan dokumen yang digabungkan dengan fitur Gunakan Gaya Tujuan yang diaktifkan menggunakan`Save` metode`Document` kelas.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UseDestinationStyles.docx");
```

### Contoh kode sumber untuk Menggunakan Gaya Tujuan menggunakan Aspose.Words untuk .NET

Berikut kode sumber lengkap untuk fitur "Gunakan Gaya Tujuan" di C# menggunakan Aspose.Words untuk .NET:

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Tambahkan dokumen sumber menggunakan gaya dokumen tujuan.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UseDestinationStyles.docx");
```

Itu dia! Anda telah berhasil mengimplementasikan fitur Gunakan Gaya Tujuan menggunakan Aspose.Words untuk .NET. Dokumen akhir akan berisi konten gabungan dengan gaya dokumen tujuan yang diterapkan.