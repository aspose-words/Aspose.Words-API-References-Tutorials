---
title: Tambahkan Awalan Nama Kelas Css
linktitle: Tambahkan Awalan Nama Kelas Css
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk menambahkan awalan nama kelas CSS saat mengonversi dokumen ke HTML dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-htmlsaveoptions/add-css-class-name-prefix/
---

Dalam tutorial ini, kami akan memandu Anda melalui kode sumber C# untuk menambahkan awalan nama kelas CSS dengan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda menambahkan awalan khusus ke nama kelas CSS yang dihasilkan saat mengonversi dokumen ke HTML.

## Langkah 1: Pengaturan Proyek

Untuk memulai, buat proyek C# baru di IDE favorit Anda. Pastikan perpustakaan Aspose.Words untuk .NET direferensikan dalam proyek Anda.

## Langkah 2: Memuat dokumen

Pada langkah ini, kita akan memuat dokumen Word yang ingin kita konversi ke HTML. Gunakan kode berikut untuk memuat dokumen:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Mengganti`"YOUR DOCUMENTS DIRECTORY"` dengan jalur sebenarnya dari direktori tempat dokumen Anda berada.

## Langkah 3: Tetapkan opsi penyimpanan HTML

Sekarang mari kita atur opsi penyimpanan HTML, termasuk tipe stylesheet CSS dan awalan nama kelas CSS. Gunakan kode berikut:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
     CssStyleSheetType = CssStyleSheetType.External,
     CssClassNamePrefix = "pfx_"
};
```

 Kode ini membuat sebuah instance dari`HtmlSaveOptions` dan set`CssStyleSheetType` ke`CssStyleSheetType.External`untuk menghasilkan style sheet CSS eksternal, dan`CssClassNamePrefix` ke`"pfx_"` untuk awalan`"pfx_"` untuk memberi nama kelas CSS.

## Langkah 4: Mengonversi dan menyimpan dokumen ke HTML

Terakhir, kita akan mengonversi dokumen ke HTML menggunakan opsi penyimpanan HTML yang ditentukan sebelumnya. Gunakan kode berikut:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
```

Kode ini mengubah dokumen menjadi HTML dan menyimpannya ke file dengan awalan nama kelas CSS ditambahkan.

### Contoh kode sumber untuk Tambahkan Awalan Nama Kelas Css menggunakan Aspose.Words untuk .NET

```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External, CssClassNamePrefix = "pfx_"
	};
	
	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);

```

 Pastikan untuk menentukan jalur dokumen yang benar di`dataDir` variabel.

Anda sekarang telah mempelajari cara menambahkan awalan nama kelas CSS saat mengonversi dokumen ke HTML menggunakan Aspose.Words untuk .NET. Mengikuti langkah panduan langkah demi langkah yang disediakan dalam tutorial ini, Anda dapat menyesuaikan nama kelas CSS dalam dokumen HTML yang dikonversi.