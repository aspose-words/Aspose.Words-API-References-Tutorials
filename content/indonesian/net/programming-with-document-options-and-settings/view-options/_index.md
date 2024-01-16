---
title: Lihat Opsi
linktitle: Lihat Opsi
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk mengonfigurasi opsi tampilan dokumen dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-document-options-and-settings/view-options/
---

Dalam tutorial ini, kami akan memandu Anda melalui kode sumber C# untuk mengonfigurasi opsi tampilan dengan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda untuk menyesuaikan mode tampilan dan tingkat zoom dalam dokumen.

## Langkah 1: Pengaturan Proyek

Untuk memulai, buat proyek C# baru di IDE favorit Anda. Pastikan perpustakaan Aspose.Words untuk .NET direferensikan dalam proyek Anda.

## Langkah 2: Memuat dokumen

Pada langkah ini, kita akan memuat dokumen Word yang ingin kita konfigurasi opsi tampilannya. Gunakan kode berikut untuk memuat dokumen:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Mengganti`"YOUR DOCUMENTS DIRECTORY"` dengan jalur sebenarnya dari direktori tempat dokumen Anda berada.

## Langkah 3: Mengonfigurasi opsi tampilan

Sekarang kita akan mengkonfigurasi opsi tampilan dokumen. Gunakan kode berikut untuk mengatur mode tampilan dan tingkat zoom:

```csharp
doc.ViewOptions.ViewType = ViewType.PageLayout;
doc.ViewOptions.ZoomPercent = 50;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
```

Kode ini menyetel mode tampilan ke "PageLayout" dan tingkat zoom menjadi 50%.

### Contoh kode sumber untuk Opsi Tampilan menggunakan Aspose.Words untuk .NET

```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	doc.ViewOptions.ViewType = ViewType.PageLayout;
	doc.ViewOptions.ZoomPercent = 50;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
    
```

 Pastikan untuk menentukan jalur dokumen yang benar di`dataDir` variabel.

Anda sekarang telah mempelajari cara mengonfigurasi opsi tampilan dokumen menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah yang disediakan dalam tutorial ini, Anda dapat dengan mudah menyesuaikan tampilan dokumen Anda sendiri.