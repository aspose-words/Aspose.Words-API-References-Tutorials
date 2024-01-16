---
title: Perbarui Gambar Seni Cerdas
linktitle: Perbarui Gambar Seni Cerdas
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara memperbarui gambar Smart Art di dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-shapes/update-smart-art-drawing/
---

Tutorial ini menjelaskan cara memperbarui gambar Smart Art di dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengulangi bentuk-bentuk di dokumen dan memeriksa apakah bentuk-bentuk tersebut memiliki Smart Art, Anda dapat memperbarui gambar Smart Art untuk mencerminkan perubahan apa pun yang dibuat pada datanya.

## Prasyarat
Untuk mengikuti tutorial ini, Anda harus memiliki yang berikut ini:

- Aspose.Words untuk perpustakaan .NET diinstal.
- Pengetahuan dasar tentang C# dan Pemrosesan Kata dengan dokumen Word.

## Langkah 1: Siapkan Direktori Dokumen
 Mulailah dengan menyiapkan jalur ke direktori dokumen Anda. Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori tempat dokumen Anda berada.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Muat Dokumen
Muat dokumen Word yang berisi gambar Smart Art menggunakan`Document` konstruktor kelas.

```csharp
Document doc = new Document(dataDir + "SmartArt.docx");
```

## Langkah 3: Perbarui Gambar Seni Cerdas
 Iterasi melalui bentuk-bentuk dalam dokumen menggunakan`GetChildNodes` metode dengan`NodeType.Shape` parameter. Periksa apakah setiap bentuk memiliki Smart Art menggunakan`HasSmartArt` properti, dan jika benar, hubungi`UpdateSmartArtDrawing` metode untuk memperbarui gambar Smart Art.

```csharp
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```


### Contoh kode sumber untuk Memperbarui Smart Art Drawing menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "SmartArt.docx");
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```

Itu dia! Anda telah berhasil memperbarui gambar Smart Art di dokumen Word Anda menggunakan Aspose.Words untuk .NET.