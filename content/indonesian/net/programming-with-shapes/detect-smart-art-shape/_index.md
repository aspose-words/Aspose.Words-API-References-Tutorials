---
title: Deteksi Bentuk Seni Cerdas
linktitle: Deteksi Bentuk Seni Cerdas
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mendeteksi bentuk Smart Art di dokumen Word menggunakan Aspose.Words untuk .NET, yang mengidentifikasi representasi grafis.
type: docs
weight: 10
url: /id/net/programming-with-shapes/detect-smart-art-shape/
---

Tutorial ini menjelaskan cara mendeteksi bentuk Smart Art di dokumen Word menggunakan Aspose.Words untuk .NET. Bentuk Smart Art adalah representasi grafis yang digunakan untuk menyajikan informasi dan ide secara visual.

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
 Muat dokumen Word menggunakan`Document` konstruktor, meneruskan jalur ke dokumen sebagai parameter.

```csharp
Document doc = new Document(dataDir + "Smart Art.docx");
```

## Langkah 3: Deteksi Bentuk Seni Cerdas
 Iterasi melalui tipe node anak`Shape` dalam dokumen menggunakan`GetChildNodes`metode. Periksa apakah setiap bentuk memiliki Smart Art menggunakan`HasSmart Art` Properti.

```csharp
int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
```

## Langkah 4: Keluarkan Hasilnya
Cetak hitungan bentuk dengan Smart Art terdeteksi di dokumen.

```csharp
Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

### Contoh kode sumber untuk Deteksi Bentuk Seni Cerdas menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Smart Art.docx");
	int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
	Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

Itu dia! Anda telah berhasil mendeteksi bentuk Smart Art di dokumen Word Anda menggunakan Aspose.Words untuk .NET.