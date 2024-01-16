---
title: Tambahkan Properti Dokumen Kustom
linktitle: Tambahkan Properti Dokumen Kustom
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk menambahkan properti khusus ke dokumen dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-document-properties/add-custom-document-properties/
---

Dalam tutorial ini, kami akan memandu Anda melalui kode sumber C# untuk menambahkan properti khusus ke dokumen dengan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda menambahkan informasi khusus ke dokumen.

## Langkah 1: Pengaturan Proyek

Untuk memulai, buat proyek C# baru di IDE favorit Anda. Pastikan perpustakaan Aspose.Words untuk .NET direferensikan dalam proyek Anda.

## Langkah 2: Memuat dokumen

Pada langkah ini, kita akan memuat dokumen Word yang ingin kita tambahkan properti kustomnya. Gunakan kode berikut untuk memuat dokumen:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Mengganti`"YOUR DOCUMENTS DIRECTORY"` dengan jalur sebenarnya dari direktori tempat dokumen Anda berada.

## Langkah 3: Tambahkan properti khusus

Sekarang mari tambahkan properti khusus ke dokumen. Gunakan kode berikut untuk menambahkan properti:

```csharp
CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;

if (customDocumentProperties["Authorized"] != null) return;

customDocumentProperties.Add("Authorized", true);
customDocumentProperties.Add("Authorized By", "John Smith");
customDocumentProperties.Add("Authorized Date", DateTime.Today);
customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
customDocumentProperties.Add("Authorized Amount", 123.45);
```

Kode ini pertama-tama memeriksa apakah properti "Resmi" sudah ada di properti khusus. Jika ada, prosesnya terhenti. Jika tidak, properti kustom akan ditambahkan ke dokumen.

### Contoh kode sumber untuk Menambahkan Properti Dokumen Kustom menggunakan Aspose.Words untuk .NET

```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");

	CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;
	
	if (customDocumentProperties["Authorized"] != null) return;
	
	customDocumentProperties.Add("Authorized", true);
	customDocumentProperties.Add("Authorized By", "John Smith");
	customDocumentProperties.Add("Authorized Date", DateTime.Today);
	customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
	customDocumentProperties.Add("Authorized Amount", 123.45);

```

 Pastikan untuk menentukan jalur dokumen yang benar di`dataDir` variabel.

Anda sekarang telah mempelajari cara menambahkan properti khusus ke dokumen menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah yang disediakan dalam tutorial ini, Anda dapat dengan mudah menambahkan properti kustom Anda sendiri ke dokumen Anda.