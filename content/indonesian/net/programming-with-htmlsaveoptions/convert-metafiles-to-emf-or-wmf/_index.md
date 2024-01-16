---
title: Konversi Metafile Ke Emf Atau Wmf
linktitle: Konversi Metafile Ke Emf Atau Wmf
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk mengonversi metafile ke format EMF atau WMF saat mengonversi dokumen ke HTML dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-htmlsaveoptions/convert-metafiles-to-emf-or-wmf/
---

Dalam tutorial ini, kami akan memandu Anda melalui kode sumber C# untuk mengonversi metafile ke format EMF atau WMF dengan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda mengonversi gambar dalam format metafile ke format yang lebih kompatibel seperti EMF atau WMF saat mengonversi dokumen ke HTML.

## Langkah 1: Pengaturan Proyek

Untuk memulai, buat proyek C# baru di IDE favorit Anda. Pastikan perpustakaan Aspose.Words untuk .NET direferensikan dalam proyek Anda.

## Langkah 2: Memasukkan gambar ke dalam dokumen

Pada langkah ini, kita akan memasukkan gambar ke dalam dokumen yang akan dikonversi. Gunakan kode berikut untuk menyisipkan gambar dari sumber data menggunakan tag HTML:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an image as is: ");
builder.InsertHtml(
	@"<img src=""data:image/png;base64,
		iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
		C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
		AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
		REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
		ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
		vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");
```

 Kode ini membuat sebuah instance dari`Document` Dan`DocumentBuilder` untuk membuat dokumen tersebut. Ini menyisipkan`<img>` tag ke dalam dokumen dengan gambar berkode base64.

## Langkah 3: Tetapkan opsi penyimpanan HTML

Sekarang kita akan mengatur opsi penyimpanan HTML, termasuk format metafile yang akan digunakan untuk gambar. Gunakan kode berikut:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };
```

 Kode ini membuat sebuah instance dari`HtmlSaveOptions` dan set`MetafileFormat` ke`HtmlMetafileFormat.EmfOrWmf` untuk menentukan bahwa metafile harus dikonversi ke format EMF atau WMF saat mengonversi ke HTML.

## Langkah 4: Mengonversi dan menyimpan dokumen ke HTML

Terakhir, kami akan mengonversi dokumen ke HTML menggunakan opsi simpan HTML yang telah ditentukan sebelumnya. Gunakan kode berikut:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);
```

Kode ini mengubah dokumen menjadi HTML dan menyimpannya ke file dengan metafile yang dikonversi dalam format EMF atau WMF tergantung pada kumpulan opsi penyimpanan.

### Contoh kode sumber untuk Mengonversi Metafiles Ke Emf Atau Wmf menggunakan Aspose.Words untuk .NET

```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Here is an image as is: ");
	builder.InsertHtml(
		@"<img src=""data:image/png;base64,
			iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
			C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
			AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
			REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
			ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
			vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);

```

 Pastikan untuk menentukan jalur yang benar ke direktori dokumen di`dataDir` variabel.

Anda sekarang telah mempelajari cara mengonversi metafile ke format EMF atau WMF saat mengonversi dokumen ke HTML menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah yang disediakan dalam tutorial ini, Anda dapat dengan mudah mengelola metafile dalam dokumen HTML yang dikonversi.