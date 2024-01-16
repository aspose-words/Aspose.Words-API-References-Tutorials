---
title: Konversi Metafile Ke Svg
linktitle: Konversi Metafile Ke Svg
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk mengonversi metafile ke format SVG saat mengonversi dokumen ke HTML dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-htmlsaveoptions/convert-metafiles-to-svg/
---

Dalam tutorial ini, kami akan memandu Anda melalui kode sumber C# untuk mengonversi metafile ke format SVG dengan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda mengonversi metafile ke format SVG saat mengonversi dokumen ke HTML.

## Langkah 1: Pengaturan Proyek

Untuk memulai, buat proyek C# baru di IDE favorit Anda. Pastikan perpustakaan Aspose.Words untuk .NET direferensikan dalam proyek Anda.

## Langkah 2: Memasukkan gambar SVG ke dalam dokumen

Pada langkah ini, kita akan memasukkan gambar SVG ke dalam dokumen yang akan dikonversi. Gunakan kode berikut untuk menyisipkan gambar SVG menggunakan tag HTML:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an SVG image: ");
builder.InsertHtml(
	@"<svg height='210' width='500'>
	<polygon points='100,10 40,198 190,78 10,78 160,198' 
		style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
</svg> ");
```

 Kode ini membuat sebuah instance dari`Document` Dan`DocumentBuilder` untuk membuat dokumen tersebut. Ini menyisipkan a`<svg>` tag yang berisi a`<polygon>` elemen dengan atribut untuk menentukan bentuk dan gaya gambar SVG.

## Langkah 3: Tetapkan opsi penyimpanan HTML

Sekarang kita akan mengatur opsi penyimpanan HTML, menentukan bahwa metafile harus dikonversi ke format SVG. Gunakan kode berikut:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };
```

 Kode ini membuat sebuah instance dari`HtmlSaveOptions` dan set`MetafileFormat` ke`HtmlMetafileFormat.Svg` untuk menentukan bahwa metafile harus dikonversi ke format SVG saat mengonversi ke HTML.

## Langkah 4: Mengonversi dan menyimpan dokumen ke HTML

Terakhir, kita akan mengonversi dokumen ke HTML menggunakan opsi penyimpanan HTML yang ditentukan sebelumnya. Gunakan kode berikut:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
```

Kode ini mengubah dokumen menjadi HTML dan menyimpannya ke file dengan metafile yang dikonversi ke SVG.

### Contoh kode sumber untuk Konversi Metafiles Ke Svg menggunakan Aspose.Words untuk .NET

```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Write("Here is an SVG image: ");
	builder.InsertHtml(
		@"<svg height='210' width='500'>
		<polygon points='100,10 40,198 190,78 10,78 160,198' 
			style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
	</svg> ");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
	
```
