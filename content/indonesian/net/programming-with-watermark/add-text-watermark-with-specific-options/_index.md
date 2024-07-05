---
title: Tambahkan Tanda Air Teks Dengan Opsi Tertentu
linktitle: Tambahkan Tanda Air Teks Dengan Opsi Tertentu
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menambahkan tanda air teks dengan opsi spesifik menggunakan Aspose.Words untuk .NET. Panduan langkah demi langkah.
type: docs
weight: 10
url: /id/net/programming-with-watermark/add-text-watermark-with-specific-options/
---

Dalam tutorial ini, kami akan memandu Anda tentang cara menambahkan tanda air teks dengan opsi spesifik menggunakan Aspose.Words untuk .NET. Tanda air teks adalah teks yang ditumpangkan pada dokumen untuk menunjukkan bahwa dokumen tersebut adalah rancangan, rahasia, dll.

## Langkah 1: Menggunakan pembuat dokumen

Pertama, kita akan menggunakan pembuat dokumen untuk menambahkan konten ke dokumen kita.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Memuat dokumen

Kami akan memuat dokumen yang ada menggunakan jalur dokumen.

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## Langkah 3: Tambahkan tanda air teks dengan opsi spesifik

 Kami akan membuat sebuah instance dari`TextWatermarkOptions`kelas dan atur opsi yang diinginkan untuk tanda air teks.

```csharp
TextWatermarkOptions options = new TextWatermarkOptions()
{
FontFamily = "Arial",
FontSize = 36,
Color = Color.Black,
Layout = WatermarkLayout.Horizontal,
IsSemitrasparent = false
};

doc.Watermark.SetText("Test", options);
```

## Langkah 4: Simpan dokumen

Terakhir, kita dapat menyimpan dokumen dengan tambahan tanda air teks.

```csharp
	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
```

### Contoh kode sumber untuk menambahkan tanda air teks dengan opsi khusus dengan Aspose.Words untuk .NET

```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Document.docx");

	TextWatermarkOptions options = new TextWatermarkOptions()
	{
		FontFamily = "Arial",
		FontSize = 36,
		Color = Color.Black,
		Layout = WatermarkLayout.Horizontal,
		IsSemitrasparent = false
	};

	doc.Watermark.SetText("Test", options);

	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
	
```

Selamat! Anda sekarang telah mempelajari cara menambahkan tanda air teks dengan opsi spesifik menggunakan Aspose.Words untuk .NET.

