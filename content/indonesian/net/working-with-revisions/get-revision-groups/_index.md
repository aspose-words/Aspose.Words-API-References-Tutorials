---
title: Dapatkan Grup Revisi
linktitle: Dapatkan Grup Revisi
second_title: API Pemrosesan Dokumen Aspose.Words
description: Dapatkan grup revisi dalam dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-revisions/get-revision-groups/
---

Dalam panduan langkah demi langkah ini, kami akan memberi tahu Anda cara mendapatkan grup revisi dalam dokumen Word menggunakan Aspose.Words untuk .NET. Kami akan memberi Anda kode sumber lengkap dan menunjukkan cara memformat keluaran penurunan harga.

## Langkah 1: Memuat dokumen

Langkah pertama adalah mengunggah dokumen yang berisi revisi.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Langkah 2: Telusuri Grup Revisi

Selanjutnya, kita akan menelusuri grup revisi yang ada dalam dokumen dan menampilkan detailnya, seperti penulis, jenis revisi, dan teks yang direvisi.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
     Console.WriteLine(group.Text);
}
```


### Contoh kode sumber untuk Dapatkan Grup Revisi menggunakan Aspose.Words untuk .NET

Berikut kode sumber lengkap untuk mendapatkan grup revisi dalam dokumen menggunakan Aspose.Words for .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach(RevisionGroup group in doc.Revisions.Groups)
{
	 Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
	 Console.WriteLine(group.Text);
}
```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara mendapatkan grup revisi dalam dokumen Word menggunakan Aspose.Words untuk .NET. Kami mengikuti langkah-langkah untuk memuat dokumen dan menelusuri grup ulasan, menampilkan detail seperti penulis dan jenis ulasan. Anda sekarang dapat menerapkan pengetahuan ini untuk menganalisis revisi dokumen Word Anda sendiri menggunakan Aspose.Words untuk .NET.

### FAQ

#### T: Bagaimana cara mengunggah dokumen di Aspose.Words untuk .NET?

 J: Gunakan`Document` kelas Aspose.Words untuk .NET untuk memuat dokumen dari file. Anda dapat menentukan jalur dokumen lengkap.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### T: Bagaimana cara menelusuri grup revisi dalam dokumen di Aspose.Words untuk .NET?

 J: Gunakan`Groups` milik dokumen`Revisions` objek untuk mendapatkan koleksi kelompok revisi. Anda kemudian dapat menggunakan loop untuk mengulang setiap grup ulasan.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     // Proses setiap grup ulasan di sini
}
```

#### T: Bagaimana cara mendapatkan penulis grup ulasan di Aspose.Words untuk .NET?

 J: Gunakan`Author` properti dari`RevisionGroup` objek untuk mendapatkan penulis grup revisi.

```csharp
string author = group.Author;
```

#### T: Bagaimana cara mendapatkan tipe revisi grup revisi di Aspose.Words untuk .NET?

 J: Gunakan`RevisionType` properti dari`RevisionGroup`objek untuk mendapatkan tipe revisi grup.

```csharp
string revisionType = group.RevisionType;
```