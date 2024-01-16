---
title: Hapus Properti Dokumen Kustom
linktitle: Hapus Properti Dokumen Kustom
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk menghapus properti khusus dari dokumen dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-document-properties/remove-custom-document-properties/
---

Dalam tutorial ini, kami akan memandu Anda melalui kode sumber C# untuk menghapus properti khusus dari dokumen dengan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda menghapus properti khusus tertentu dari dokumen.

## Langkah 1: Pengaturan Proyek

Untuk memulai, buat proyek C# baru di IDE favorit Anda. Pastikan perpustakaan Aspose.Words untuk .NET direferensikan dalam proyek Anda.

## Langkah 2: Memuat dokumen

Pada langkah ini, kita akan memuat dokumen Word yang ingin kita hapus properti kustomnya. Gunakan kode berikut untuk memuat dokumen:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Mengganti`"YOUR DOCUMENTS DIRECTORY"` dengan jalur sebenarnya dari direktori tempat dokumen Anda berada.

## Langkah 3: Menghapus properti khusus

Sekarang mari kita hapus properti khusus tertentu dari dokumen. Gunakan kode berikut:

```csharp
doc.CustomDocumentProperties.Remove("Authorized Date");
```

Kode ini menghapus properti khusus "Tanggal Resmi" dari dokumen. Anda dapat mengganti "Tanggal Resmi" dengan nama properti khusus yang ingin Anda hapus.

### Contoh kode sumber untuk Menghapus Properti Dokumen Kustom menggunakan Aspose.Words untuk .NET

```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	doc.CustomDocumentProperties.Remove("Authorized Date");
	
```

 Pastikan untuk menentukan jalur dokumen yang benar di`dataDir` variabel.

Anda sekarang telah mempelajari cara menghapus properti khusus dari dokumen menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah yang disediakan dalam tutorial ini, Anda dapat dengan mudah menghapus properti khusus dari dokumen Anda sendiri.