---
title: Selesaikan Nama Font
linktitle: Selesaikan Nama Font
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk mengatasi nama font yang hilang saat mengonversi ke HTML dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-htmlsaveoptions/resolve-font-names/
---

Dalam tutorial ini, kami akan memandu Anda melalui kode sumber C# untuk mengatasi nama font yang hilang dengan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda untuk secara otomatis mengatasi nama font yang hilang saat mengonversi dokumen ke HTML.

## Langkah 1: Pengaturan Proyek

Untuk memulai, buat proyek C# baru di IDE favorit Anda. Pastikan perpustakaan Aspose.Words untuk .NET direferensikan dalam proyek Anda.

## Langkah 2: Memuat dokumen

Pada langkah ini, kita akan memuat dokumen yang akan diproses. Gunakan kode berikut untuk memuat dokumen dari direktori tertentu:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Missing font.docx");
```

 Kode ini membuat sebuah instance dari`Document` dengan memuat dokumen dari direktori yang ditentukan.

## Langkah 3: Mengonfigurasi opsi cadangan HTML

Sekarang kita akan mengonfigurasi opsi penyimpanan HTML untuk mengatasi nama font yang hilang selama konversi. Gunakan kode berikut:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
PrettyFormat = true,
ResolveFontNames=true
};
```

 Kode ini membuat sebuah instance dari`HtmlSaveOptions`dan mengatur`ResolveFontNames` pilihan untuk`true`untuk mengatasi nama font yang hilang saat mengonversi ke HTML. Juga`PrettyFormat` opsi diatur ke`true` untuk mendapatkan kode HTML yang diformat dengan baik.

## Langkah 4: Mengonversi dan menyimpan dokumen ke HTML

Terakhir, kami akan mengonversi dokumen ke HTML menggunakan opsi penyimpanan HTML yang dikonfigurasi sebelumnya. Gunakan kode berikut:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);
```

Kode ini mengubah dokumen menjadi HTML dengan secara otomatis menyelesaikan nama font yang hilang, dan menyimpan file HTML yang dikonversi ke direktori yang ditentukan.

### Contoh kode sumber untuk Menyelesaikan Nama Font menggunakan Aspose.Words untuk .NET

```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Missing font.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		PrettyFormat = true, ResolveFontNames = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);

```

 Pastikan untuk menentukan jalur yang benar ke direktori dokumen di`dataDir` variabel.