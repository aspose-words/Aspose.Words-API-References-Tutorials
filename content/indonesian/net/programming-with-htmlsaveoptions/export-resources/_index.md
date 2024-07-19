---
title: Ekspor Sumber Daya
linktitle: Ekspor Sumber Daya
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk mengekspor sumber daya dokumen saat menyimpan sebagai HTML dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-htmlsaveoptions/export-resources/
---

Dalam tutorial ini, kami akan memandu Anda melalui kode sumber C# untuk mengekspor sumber daya dokumen dengan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda mengekspor sumber daya, seperti font, sebagai file eksternal saat menyimpan dokumen dalam format HTML.

## Langkah 1: Pengaturan Proyek

Untuk memulai, buat proyek C# baru di IDE favorit Anda. Pastikan perpustakaan Aspose.Words untuk .NET direferensikan dalam proyek Anda.

## Langkah 2: Memuat dokumen

Pada langkah ini, kita akan memuat dokumen yang akan diekspor. Gunakan kode berikut untuk memuat dokumen dari direktori tertentu:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Kode ini membuat sebuah instance dari`Document` dengan memuat dokumen dari direktori yang ditentukan.

## Langkah 3: Mengonfigurasi opsi cadangan HTML

Sekarang kita akan mengonfigurasi opsi penyimpanan HTML untuk mengekspor sumber daya dokumen. Gunakan kode berikut:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
CssStyleSheetType = CssStyleSheetType.External,
ExportFontResources=true,
ResourceFolder = ArtifactsDir + "Resources",
ResourceFolderAlias = "http://contoh.com/resources"
};
```

 Kode ini membuat sebuah instance dari`HtmlSaveOptions` dan menetapkan opsi berikut:

- `CssStyleSheetType` diatur ke`CssStyleSheetType.External` untuk mengekspor style sheet CSS ke file eksternal.
- `ExportFontResources` diatur ke`true` untuk mengekspor sumber daya font.
- `ResourceFolder` menentukan direktori tujuan tempat sumber daya akan disimpan.
- `ResourceFolderAlias`menentukan alias URL yang akan digunakan untuk mengakses sumber daya.

## Langkah 4: Mengonversi dan menyimpan dokumen ke HTML

Terakhir, kami akan mengonversi dokumen ke HTML menggunakan opsi penyimpanan HTML yang dikonfigurasi sebelumnya. Gunakan kode berikut:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
```

Kode ini mengubah dokumen menjadi HTML dan menyimpan sumber daya ke direktori tertentu, menggunakan alias URL yang ditentukan.

### Contoh kode sumber untuk Ekspor Sumber Daya menggunakan Aspose.Words untuk .NET

```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External,
		ExportFontResources = true,
		ResourceFolder = ArtifactsDir + "Resources",
		ResourceFolderAlias = "http://contoh.com/resources"
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
  
```

 Pastikan untuk menentukan jalur yang benar ke direktori dokumen di`dataDir` variabel.