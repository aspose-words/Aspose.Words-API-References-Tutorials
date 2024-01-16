---
title: Dapatkan Poin Batas Bentuk Aktual
linktitle: Dapatkan Poin Batas Bentuk Aktual
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengambil batas sebenarnya dari suatu bentuk dalam titik (satuan pengukuran) dalam dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-shapes/get-actual-shape-bounds-points/
---

Tutorial ini menjelaskan cara mengambil batas sebenarnya dari suatu bentuk dalam titik (satuan pengukuran) dalam dokumen Word menggunakan Aspose.Words untuk .NET. Batasnya mewakili ukuran dan posisi bentuk dalam dokumen.

## Prasyarat
Untuk mengikuti tutorial ini, Anda harus memiliki yang berikut ini:

- Aspose.Words untuk perpustakaan .NET diinstal.
- Pengetahuan dasar tentang C# dan Pemrosesan Kata dengan dokumen Word.

## Langkah 1: Buat Dokumen Baru dan DocumentBuilder
 Buat instance baru dari`Document` kelas dan a`DocumentBuilder` keberatan untuk bekerja dengan dokumen tersebut.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 2: Sisipkan Bentuk Gambar
 Menggunakan`InsertImage` metode`DocumentBuilder` objek untuk menyisipkan bentuk gambar ke dalam dokumen. Berikan jalur ke file gambar sebagai parameter.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
shape.AspectRatioLocked = false;
```

## Langkah 3: Ambil Titik Batas Bentuk Aktual
 Akses bentuknya`ShapeRenderer` menggunakan`GetShapeRenderer` metode. Kemudian, ambil batas sebenarnya dari bentuk tersebut dalam bentuk titik menggunakan`BoundsInPoints` Properti.

```csharp
Console.Write("\nGets the actual bounds of the shape in points: ");
Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```


### Contoh kode sumber untuk Mendapatkan Poin Batas Bentuk Aktual menggunakan Aspose.Words untuk .NET 

```csharp
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	Console.Write("\nGets the actual bounds of the shape in points: ");
	Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```

Itu dia! Anda telah berhasil mengambil batas sebenarnya dari suatu bentuk dalam titik di dokumen Word Anda menggunakan Aspose.Words untuk .NET.