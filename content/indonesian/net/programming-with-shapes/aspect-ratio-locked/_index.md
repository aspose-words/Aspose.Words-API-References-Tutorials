---
title: Rasio Aspek Terkunci
linktitle: Rasio Aspek Terkunci
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengunci atau membuka kunci rasio aspek bentuk di dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-shapes/aspect-ratio-locked/
---

Tutorial ini menjelaskan cara mengunci atau membuka kunci rasio aspek bentuk dalam dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengunci rasio aspek, Anda dapat mempertahankan proporsi asli bentuk saat mengubah ukurannya.

## Prasyarat
Untuk mengikuti tutorial ini, Anda harus memiliki yang berikut ini:

- Aspose.Words untuk perpustakaan .NET diinstal.
- Pengetahuan dasar tentang C# dan Pemrosesan Kata dengan dokumen Word.

## Langkah 1: Siapkan Direktori Dokumen
 Mulailah dengan menyiapkan jalur ke direktori dokumen Anda. Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori tempat Anda ingin menyimpan dokumen.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Buat Dokumen Baru dan DocumentBuilder
 Buat instance baru dari`Document` kelas dan a`DocumentBuilder`keberatan untuk bekerja dengan dokumen tersebut.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 3: Sisipkan Bentuk Gambar
 Menggunakan`InsertImage` metode`DocumentBuilder` objek untuk menyisipkan bentuk gambar ke dalam dokumen. Berikan jalur ke file gambar sebagai parameter.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## Langkah 4: Kunci atau Buka Kunci Rasio Aspek
 Mengatur`AspectRatioLocked` properti bentuk ke`true` atau`false` untuk mengunci atau membuka kunci rasio aspek.

```csharp
shape.AspectRatioLocked = false; //Buka kunci rasio aspek
```

## Langkah 5: Simpan Dokumen
 Simpan dokumen ke direktori yang ditentukan menggunakan`Save` metode. Berikan nama file yang diinginkan dengan ekstensi file yang sesuai. Dalam contoh ini, kami menyimpan dokumen sebagai "WorkingWithShapes.AspectRatioLocked.docx".

```csharp
doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

### Contoh kode sumber untuk Rasio Aspek Terkunci menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

Itu dia! Anda telah berhasil mengunci atau membuka kunci rasio aspek bentuk di dokumen Word Anda menggunakan Aspose.Words untuk .NET.