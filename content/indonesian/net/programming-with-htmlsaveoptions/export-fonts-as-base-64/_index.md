---
title: Ekspor Font Sebagai Basis 64
linktitle: Ekspor Font Sebagai Basis 64
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk mengekspor font base 64 saat menyimpan dokumen dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-htmlsaveoptions/export-fonts-as-base-64/
---

Dalam tutorial ini, kami akan memandu Anda melalui kode sumber C# untuk mengekspor font base 64 dengan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda mengekspor font sebagai data base 64 saat menyimpan dokumen dalam format HTML.

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

Sekarang kita akan mengkonfigurasi opsi penyimpanan HTML untuk mengekspor font base 64. Gunakan kode berikut:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };
```

 Kode ini membuat sebuah instance dari`HtmlSaveOptions` dan set`ExportFontsAsBase64` ke`true` untuk menentukan bahwa font harus diekspor sebagai data base 64 saat disimpan sebagai HTML.

## Langkah 4: Mengonversi dan menyimpan dokumen ke HTML

Terakhir, kami akan mengonversi dokumen ke HTML menggunakan opsi penyimpanan HTML yang dikonfigurasi sebelumnya. Gunakan kode berikut:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
```

Kode ini mengubah dokumen menjadi HTML dan menyimpannya ke file dengan font yang diekspor sebagai data base 64.

### Contoh kode sumber untuk Ekspor Font Sebagai Basis 64 menggunakan Aspose.Words untuk .NET

```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);

```

 Pastikan untuk menentukan jalur yang benar ke direktori dokumen di`dataDir` variabel.

Anda sekarang telah mempelajari cara mengekspor font base 64 saat menyimpan dokumen sebagai HTML menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah yang disediakan dalam tutorial ini, Anda dapat dengan mudah mengekspor font dengan aman dan tertanam dalam dokumen HTML Anda.