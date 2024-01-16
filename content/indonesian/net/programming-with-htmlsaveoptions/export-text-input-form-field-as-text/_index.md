---
title: Ekspor Bidang Formulir Input Teks Sebagai Teks
linktitle: Ekspor Bidang Formulir Input Teks Sebagai Teks
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk mengekspor bidang formulir input teks sebagai teks biasa dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-htmlsaveoptions/export-text-input-form-field-as-text/
---

Dalam tutorial ini, kami akan memandu Anda melalui kode sumber C# untuk mengekspor bidang formulir input teks sebagai teks biasa dengan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda mengekspor kolom formulir input teks sebagai teks yang dapat dibaca, daripada mengekspornya sebagai elemen input HTML.

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

Sekarang kita akan mengonfigurasi opsi penyimpanan HTML untuk mengekspor bidang formulir input teks sebagai teks biasa. Gunakan kode berikut:

```csharp
string imagesDir = Path. Combine(ArtifactsDir, "Images");

// Folder yang ditentukan harus ada dan kosong.
if (Directory.Exists(imagesDir))
Directory. Delete(imagesDir, true);

Directory.CreateDirectory(imagesDir);

HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
ExportTextInputFormFieldAsText = true,
ImagesFolder = imagesDir
};
```

 Kode ini membuat sebuah instance dari`HtmlSaveOptions`dan mengatur`ExportTextInputFormFieldAsText` pilihan untuk`true` untuk mengekspor bidang formulir masukan teks sebagai teks biasa. Selain itu, ini menentukan folder tempat gambar yang diekstraksi akan disimpan.

## Langkah 4: Mengonversi dan menyimpan dokumen ke HTML

Terakhir, kami akan mengonversi dokumen ke HTML menggunakan opsi penyimpanan HTML yang dikonfigurasi sebelumnya. Gunakan kode berikut:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);
```

Kode ini mengubah dokumen menjadi HTML dengan mengekspor kolom formulir input teks sebagai teks biasa, dan menyimpan file HTML yang diekspor ke direktori yang ditentukan.

### Contoh kode sumber untuk Bidang Formulir Input Teks Ekspor Sebagai Teks menggunakan Aspose.Words untuk .NET


```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	string imagesDir = Path.Combine(ArtifactsDir, "Images");

	// Folder yang ditentukan harus ada dan harus kosong.
	if (Directory.Exists(imagesDir))
		Directory.Delete(imagesDir, true);

	Directory.CreateDirectory(imagesDir);

	// Tetapkan opsi untuk mengekspor bidang formulir sebagai teks biasa, bukan sebagai elemen masukan HTML.
	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		ExportTextInputFormFieldAsText = true, ImagesFolder = imagesDir
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);

```

 Pastikan untuk menentukan jalur yang benar ke direktori dokumen di`dataDir` variabel.