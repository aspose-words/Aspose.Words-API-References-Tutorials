---
title: Ekspor Url Cid Untuk Sumber Daya Mhtml
linktitle: Ekspor Url Cid Untuk Sumber Daya Mhtml
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk mengekspor URL CID sumber daya MHTML saat menyimpan dokumen dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-htmlsaveoptions/export-cid-urls-for-mhtml-resources/
---

Dalam tutorial ini, kami akan memandu Anda melalui kode sumber C# untuk mengekspor URL CID untuk sumber daya MHTML dengan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda mengekspor URL CID sumber daya MHTML saat menyimpan dokumen dalam format MHTML.

## Langkah 1: Pengaturan Proyek

Untuk memulai, buat proyek C# baru di IDE favorit Anda. Pastikan perpustakaan Aspose.Words untuk .NET direferensikan dalam proyek Anda.

## Langkah 2: Memuat dokumen

Pada langkah ini, kita akan memuat dokumen yang akan diekspor. Gunakan kode berikut untuk memuat dokumen dari direktori tertentu:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Content-ID.docx");
```

 Kode ini membuat sebuah instance dari`Document` dengan memuat dokumen dari direktori yang ditentukan.

## Langkah 3: Mengonfigurasi opsi cadangan HTML

Sekarang kita akan mengonfigurasi opsi penyimpanan HTML untuk mengekspor URL CID sumber daya MHTML. Gunakan kode berikut:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
{
PrettyFormat = true,
ExportCidUrlsForMhtmlResources = true
};
```

 Kode ini membuat sebuah instance dari`HtmlSaveOptions` dengan format penyimpanan diatur ke MHTML. Ini juga memungkinkan ekspor URL CID sumber daya MHTML dengan pengaturan`ExportCidUrlsForMhtmlResources` ke`true`.

## Langkah 4: Mengonversi dan menyimpan dokumen ke MHTML

Terakhir, kami akan mengonversi dokumen ke MHTML menggunakan opsi penyimpanan HTML yang dikonfigurasi sebelumnya. Gunakan kode berikut:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);
```

Kode ini mengonversi dokumen menjadi MHTML dan menyimpannya ke file dengan URL CID sumber daya MHTML yang diekspor.

### Contoh kode sumber untuk Ekspor Url Cid Untuk Sumber Daya Mhtml menggunakan Aspose.Words untuk .NET

```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Content-ID.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
	{
		PrettyFormat = true, ExportCidUrlsForMhtmlResources = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);

```

 Pastikan untuk menentukan jalur yang benar ke direktori dokumen di`dataDir` variabel.

Anda sekarang telah mempelajari cara mengekspor URL CID sumber daya MHTML saat menyimpan dokumen dalam format MHTML menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah yang disediakan dalam tutorial ini, Anda dapat dengan mudah mengelola URL CID di dokumen MHTML yang diekspor.

