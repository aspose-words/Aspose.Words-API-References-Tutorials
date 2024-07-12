---
title: Tambahkan Sudut Terpotong
linktitle: Tambahkan Sudut Terpotong
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menambahkan bentuk dengan sudut yang dipotong ke dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-shapes/add-corners-snipped/
---

 Tutorial ini menjelaskan cara menambahkan bentuk dengan sudut yang dipotong ke dokumen Word menggunakan Aspose.Words untuk .NET. Bentuk potongan sudut dapat disesuaikan dan disisipkan menggunakan`InsertShape` metode.

## Prasyarat
Untuk mengikuti tutorial ini, Anda harus memiliki yang berikut ini:

- Aspose.Words untuk perpustakaan .NET diinstal.
- Pengetahuan dasar tentang C# dan Pemrosesan Kata dengan dokumen Word.

## Langkah 1: Siapkan Direktori Dokumen
 Mulailah dengan menyiapkan jalur ke direktori dokumen Anda. Mengganti`"YOUR DOCUMENT DIRECTORY"`dengan jalur sebenarnya ke direktori tempat Anda ingin menyimpan dokumen.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Buat Dokumen Baru dan DocumentBuilder
 Buat instance baru dari`Document` kelas dan a`DocumentBuilder` keberatan untuk bekerja dengan dokumen tersebut.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 3: Masukkan Bentuk Potongan Sudut
 Menggunakan`InsertShape` metode`DocumentBuilder` objek untuk menyisipkan bentuk dengan sudut terpotong. Tentukan tipe bentuk (dalam hal ini,`ShapeType.TopCornersSnipped`) dan berikan ukuran bentuk yang diinginkan.

```csharp
builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
```

## Langkah 4: Simpan Dokumen
 Simpan dokumen ke direktori yang ditentukan menggunakan`Save`metode. Berikan nama file yang diinginkan dengan ekstensi file yang sesuai. Dalam contoh ini, kami menyimpan dokumen sebagai "WorkingWithShapes.AddCornersSnipped.docx".

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);
```

### Contoh kode sumber untuk Tambahkan Sudut yang Dipotong menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
	{
		Compliance = OoxmlCompliance.Iso29500_2008_Transitional
	};
	doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);

```

Itu dia! Anda telah berhasil menambahkan bentuk potongan sudut ke dokumen Word Anda menggunakan Aspose.Words untuk .NET.