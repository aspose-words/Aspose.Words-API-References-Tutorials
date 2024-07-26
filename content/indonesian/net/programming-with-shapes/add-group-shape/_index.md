---
title: Tambahkan Bentuk Grup
linktitle: Tambahkan Bentuk Grup
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menambahkan bentuk grup dengan beberapa bentuk ke dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-shapes/add-group-shape/
---

Tutorial ini menjelaskan cara menambahkan bentuk grup yang berisi beberapa bentuk ke dokumen Word menggunakan Aspose.Words untuk .NET. Bentuk grup memungkinkan Anda menggabungkan dan memanipulasi beberapa bentuk sebagai satu kesatuan.

## Prasyarat
Untuk mengikuti tutorial ini, Anda perlu memiliki yang berikut ini:

- Aspose.Words untuk perpustakaan .NET diinstal.
- Pengetahuan dasar tentang C# dan Pemrosesan Kata dengan dokumen Word.

## Langkah 1: Siapkan Direktori Dokumen
 Mulailah dengan menyiapkan jalur ke direktori dokumen Anda. Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori tempat Anda ingin menyimpan dokumen.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Buat Dokumen Baru dan GroupShape
 Buat instance baru dari`Document` kelas dan`GroupShape` keberatan untuk bekerja dengan dokumen tersebut.

```csharp
Document doc = new Document();
doc.EnsureMinimum();
GroupShape groupShape = new GroupShape(doc);
```

## Langkah 3: Buat dan Tambahkan Bentuk ke GroupShape
 Buat bentuk individual seperti`accentBorderShape`Dan`actionButtonShape` menggunakan`Shape` kelas. Sesuaikan propertinya sesuai keinginan. Tambahkan bentuk-bentuk ini ke`groupShape` obyek.

```csharp
Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1) { Width = 100, Height = 100 };
groupShape.AppendChild(accentBorderShape);

Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
{
    Left = 100,
    Width = 100,
    Height = 200
};
groupShape.AppendChild(actionButtonShape);
```

## Langkah 4: Tetapkan Dimensi untuk GroupShape
 Atur lebar, tinggi, dan ukuran koordinat untuk`groupShape`.

```csharp
groupShape.Width = 200;
groupShape.Height = 200;
groupShape.CoordSize = new Size(200, 200);
```

## Langkah 5: Masukkan GroupShape ke dalam Dokumen
 Membuat`DocumentBuilder` objek dan masukkan`groupShape` ke dalam dokumen menggunakan`InsertNode` metode.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(groupShape);
```

## Langkah 6: Simpan Dokumen
 Simpan dokumen ke direktori yang ditentukan menggunakan`Save` metode. Berikan nama file yang diinginkan dengan ekstensi file yang sesuai. Dalam contoh ini, kami menyimpan dokumen sebagai "WorkingWithShapes.AddGroupShape.docx".

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

### Contoh kode sumber untuk Tambahkan Bentuk Grup menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	doc.EnsureMinimum();
	GroupShape groupShape = new GroupShape(doc);
	Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1) { Width = 100, Height = 100 };
	groupShape.AppendChild(accentBorderShape);
	Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
	{
		Left = 100, Width = 100, Height = 200
	};
	groupShape.AppendChild(actionButtonShape);
	groupShape.Width = 200;
	groupShape.Height = 200;
	groupShape.CoordSize = new Size(200, 200);
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertNode(groupShape);
	doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

Itu dia! Anda telah berhasil menambahkan bentuk grup yang berisi beberapa bentuk ke dokumen Word Anda menggunakan Aspose.W