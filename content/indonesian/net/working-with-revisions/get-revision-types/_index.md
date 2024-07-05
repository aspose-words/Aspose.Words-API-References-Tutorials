---
title: Dapatkan Jenis Kata Revisi
linktitle: Dapatkan Jenis Kata Revisi
second_title: API Pemrosesan Dokumen Aspose.Words
description: Dapatkan revisi jenis kata dalam dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-revisions/get-revision-types/
---

Dalam panduan langkah demi langkah ini, kami akan memberi tahu Anda cara mendapatkan revisi jenis kata dalam dokumen Word menggunakan Aspose.Words untuk .NET. Kami akan memberi Anda kode sumber lengkap dan menunjukkan cara memformat keluaran penurunan harga.

## Langkah 1: Memuat dokumen

Langkah pertama adalah mengunggah dokumen yang berisi revisi.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Langkah 2: Telusuri paragraf

Selanjutnya, kita akan menelusuri paragraf dokumen dan memeriksa jenis revisi kata yang terkait dengan setiap paragraf.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     if (paragraphs[i].IsMoveFromRevision)
         Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
     if (paragraphs[i].IsMoveToRevision)
         Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

### Contoh kode sumber untuk Dapatkan Jenis Revisi menggunakan Aspose.Words untuk .NET

Berikut kode sumber lengkap untuk mendapatkan tipe revisi dalam dokumen menggunakan Aspose.Words untuk .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
	 if (paragraphs[i].IsMoveFromRevision)
		 Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
	 if (paragraphs[i].IsMoveToRevision)
		 Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara mendapatkan revisi jenis kata dalam dokumen Word menggunakan Aspose.Words untuk .NET. Kami mengikuti langkah-langkah untuk memuat dokumen, menelusuri paragraf, dan memeriksa jenis ulasan kata yang terkait dengan setiap paragraf. Sekarang Anda dapat menerapkan pengetahuan ini untuk menganalisis ulasan kata di dokumen Word Anda sendiri menggunakan Aspose.Words untuk .NET.

### FAQ untuk mendapatkan revisi jenis kata

#### T: Bagaimana cara mengunggah dokumen di Aspose.Words untuk .NET?

 J: Gunakan`Document` kelas Aspose.Words untuk .NET untuk memuat dokumen dari file. Anda dapat menentukan jalur dokumen lengkap.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### T: Bagaimana cara mengulang paragraf dalam dokumen di Aspose.Words untuk .NET?

 J: Gunakan`Paragraphs` milik bagian dokumen untuk mendapatkan kumpulan paragraf. Anda kemudian dapat menggunakan loop untuk mengulang setiap paragraf.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     // Proses setiap paragraf di sini
}
```

#### T: Bagaimana cara memeriksa apakah paragraf telah dipindahkan (dihapus) di Aspose.Words untuk .NET?

 A: Gunakan paragraf`IsMoveFromRevision`properti untuk memeriksa apakah sudah dipindahkan (dihapus).

```csharp
if (paragraph. IsMove

FromRevision)
{
     // Paragraf telah dipindahkan (dihapus)
}
```

#### T: Bagaimana cara memeriksa apakah paragraf telah dipindahkan (dimasukkan) di Aspose.Words untuk .NET?

 A: Gunakan paragraf`IsMoveToRevision` properti untuk memeriksa apakah sudah dipindahkan (dimasukkan).

```csharp
if (paragraph.IsMoveToRevision)
{
     // Paragraf telah dipindahkan (dimasukkan)
}
```