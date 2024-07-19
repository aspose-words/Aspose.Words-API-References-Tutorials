---
title: Revisi Bentuk
linktitle: Revisi Bentuk
second_title: API Pemrosesan Dokumen Aspose.Words
description: Merevisi bentuk dalam dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-revisions/shape-revision/
---

Dalam panduan langkah demi langkah ini, kami akan memandu Anda tentang cara membuat revisi pada bentuk di dokumen Word menggunakan Aspose.Words untuk .NET. Kami akan memberi Anda kode sumber lengkap dan menunjukkan cara memformat keluaran penurunan harga.

## Langkah 1: Membuat dokumen dan menambahkan bentuk

Langkah pertama adalah membuat dokumen baru dan menambahkan bentuk.

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Langkah 2: Lacak revisi dan tambahkan bentuk lain

Kami akan mengaktifkan pelacakan revisi dan menambahkan bentuk lain.

```csharp
doc.StartTrackRevisions("John Doe");

shape = new Shape(doc, ShapeType.Sun);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Langkah 3: Dapatkan koleksi bentuk dan periksa revisinya

Kita akan mendapatkan koleksi bentuk dari dokumen dan memeriksa revisi yang terkait dengan setiap bentuk.

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

## Langkah 4: Memeriksa Revisi Pemindahan Bentuk

Kami akan memuat dokumen yang ada yang berisi revisi perpindahan bentuk dan memeriksa revisi terkait.

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```

### Contoh kode sumber untuk Shape Revision menggunakan Aspose.Words untuk .NET

Berikut source code lengkap untuk melakukan revisi bentuk pada dokumen menggunakan Aspose.Words for .NET:

```csharp
Document doc = new Document();

//Sisipkan bentuk sebaris tanpa melacak revisi.
Assert.False(doc.TrackRevisions);
Shape shape = new Shape(doc, ShapeType.Cube);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// Mulai lacak revisi dan kemudian masukkan bentuk lain.
doc.StartTrackRevisions("John Doe");
shape = new Shape(doc, ShapeType.Sun);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

// Dapatkan koleksi bentuk dokumen yang hanya mencakup dua bentuk yang kami tambahkan.
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// Hapus bentuk pertama.
shapes[0].Remove();

// Karena kita menghapus bentuk tersebut saat perubahan sedang dilacak, bentuk tersebut dihitung sebagai revisi penghapusan.
Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

// Dan kami menyisipkan bentuk lain sambil melacak perubahan, sehingga bentuk tersebut akan dihitung sebagai revisi sisipan.
Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);

// Dokumen memiliki satu bentuk yang dipindahkan, namun revisi pemindahan bentuk akan memiliki dua contoh bentuk tersebut.
// Yang satu akan menjadi bentuk di tempat tujuan kedatangannya dan yang lainnya akan menjadi bentuk di lokasi aslinya.
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

// Ini perpindahannya ke revisi, juga bentuk di tujuan kedatangannya.
Assert.False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

// Ini merupakan perpindahan dari revisi yaitu bentuk pada lokasi aslinya.
Assert.True(shapes[1].IsMoveFromRevision);
Assert.False(shapes[1].IsMoveToRevision);
```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara merevisi bentuk di dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti langkah-langkah pembuatan dokumen, mengaktifkan pelacakan revisi, memeriksa revisi yang terkait dengan setiap bentuk, dan memeriksa revisi untuk memindahkan bentuk, kami berhasil mengelola revisi. Aspose.Words for .NET menawarkan API yang kuat untuk Pemrosesan Kata dengan ulasan dan formulir di dokumen Word.

### FAQ

#### T: Bagaimana cara membuat dokumen baru dan menambahkan bentuk di Aspose.Words untuk .NET?

A: Untuk membuat dokumen baru dan menambahkan bentuk di Aspose.Words untuk .NET, Anda dapat menggunakan kode berikut. Di sini kita menambahkan dua bentuk, kubus dan matahari, ke bagian pertama dokumen:

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

#### T: Bagaimana cara mengaktifkan pelacakan revisi di Aspose.Words untuk .NET?

 J: Untuk mengaktifkan pelacakan revisi di Aspose.Words untuk .NET, Anda dapat menggunakan`StartTrackRevisions` metode`Document` obyek. Metode ini mengambil nama pembuat revisi sebagai parameter:

```csharp
doc.StartTrackRevisions("John Doe");
```

#### T: Bagaimana cara memeriksa revisi yang terkait dengan setiap bentuk dalam dokumen Aspose.Words untuk .NET?

J: Untuk memeriksa revisi yang terkait dengan setiap bentuk dalam dokumen Aspose.Words untuk .NET, Anda bisa mendapatkan kumpulan bentuk dokumen menggunakan`GetChildNodes` metode dengan`NodeType.Shape` tipe simpul. Kemudian Anda dapat mengakses setiap bentuk`IsDeleteRevision`, `IsInsertRevision`, `IsMoveFromRevision` , Dan`IsMoveToRevision` properti untuk menentukan jenis revisi apa yang dikaitkan dengan bentuk:

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

#### T: Bagaimana cara memeriksa revisi perpindahan bentuk dalam dokumen Aspose.Words untuk .NET?

 J: Untuk memeriksa revisi perpindahan bentuk dalam dokumen Aspose.Words untuk .NET, Anda dapat memuat dokumen yang sudah ada yang berisi revisi perpindahan bentuk. Kemudian Anda dapat mengakses setiap bentuk`IsMoveFromRevision`Dan`IsMoveToRevision` properti untuk menentukan apakah ia sedang dipindahkan dan jika demikian, dari mana dan ke mana:

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```