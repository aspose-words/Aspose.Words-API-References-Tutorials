---
title: Akses Versi Revisi
linktitle: Akses Versi Revisi
second_title: API Pemrosesan Dokumen Aspose.Words
description: Akses versi revisi dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-revisions/access-revised-version/
---

Dalam panduan langkah demi langkah ini, kami akan menunjukkan kepada Anda cara mengakses versi revisi dokumen Word menggunakan Aspose.Words untuk .NET. Kami akan memberi Anda kode sumber lengkap dan menunjukkan cara memformat keluaran penurunan harga.

## Langkah 1: Memuat dokumen

Langkah pertama adalah mengunggah dokumen yang berisi revisi.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();
```

## Langkah 2: Akses versi revisi

Kami sekarang akan beralih ke versi dokumen yang telah direvisi.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

## Langkah 3: Telusuri revisi

Selanjutnya, kita akan menelusuri revisi yang ada dalam dokumen dan menampilkan informasi spesifik untuk paragraf yang merupakan item daftar.

```csharp
foreach (Revision revision in doc.Revisions)
{
     if (revision.ParentNode.NodeType == NodeType.Paragraph)
     {
         Paragraph paragraph = (Paragraph)revision.ParentNode;
         if (paragraph.IsListItem)
         {
             Console.WriteLine(paragraph.ListLabel.LabelString);
             Console.WriteLine(paragraph.ListFormat.ListLevel);
         }
     }
}
```

### Contoh kode sumber untuk Access Versi Revisi menggunakan Aspose.Words untuk .NET

Berikut adalah kode sumber lengkap untuk mengakses versi revisi dokumen menggunakan Aspose.Words for .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();

// Beralih ke versi dokumen yang direvisi.
doc.RevisionsView = RevisionsView.Final;

foreach (Revision revision in doc.Revisions)
{
	 if (revision.ParentNode.NodeType == NodeType.Paragraph)
	 {
		 Paragraph paragraph = (Paragraph)revision.ParentNode;
		 if (paragraph.IsListItem)
		 {
			 Console.WriteLine(paragraph.ListLabel.LabelString);
			 Console.WriteLine(paragraph.ListFormat.ListLevel);
		 }
	 }
}
```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara mengakses versi revisi dokumen Word menggunakan Aspose.Words untuk .NET. Dengan memuat dokumen, menavigasi ke versi revisi, dan menelusuri revisi, kami dapat memperoleh informasi spesifik untuk paragraf yang merupakan item daftar. Aspose.Words untuk .NET menawarkan fitur canggih untuk memanipulasi dokumen Word, termasuk akses ke ulasan. Anda sekarang dapat menggunakan pengetahuan ini untuk mengakses versi revisi dokumen Word Anda menggunakan Aspose.Words untuk .NET.

### FAQ

#### T: Bagaimana cara memuat dokumen dengan revisi ke Aspose.Words untuk .NET?

 J: Gunakan`Document` kelas Aspose.Words untuk .NET untuk memuat dokumen dari file yang berisi revisi. Anda dapat menentukan jalur dokumen lengkap.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### T: Bagaimana cara mengakses versi revisi dokumen di Aspose.Words untuk .NET?

 J: Gunakan`RevisionsView` properti dari`Document` keberatan untuk mengakses versi revisi dokumen. Anda dapat mengatur nilai`RevisionsView`properti ke`RevisionsView.Final` untuk menampilkan versi final tanpa revisi.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

#### T: Bagaimana cara menelusuri revisi dokumen di Aspose.Words untuk .NET?

J: Gunakan a`foreach` loop untuk mengulangi revisi yang ada dalam dokumen. Anda dapat menggunakan`Revisions` properti dari`Document` keberatan untuk mendapatkan kumpulan semua revisi dokumen.

```csharp
foreach (Revision revision in doc.Revisions)
{
     // Proses setiap revisi di sini
}
```

#### T: Bagaimana cara memeriksa apakah paragraf merupakan item daftar di Aspose.Words untuk .NET?

 J: Gunakan`IsListItem` properti dari`Paragraph` keberatan untuk memeriksa apakah suatu paragraf merupakan item daftar. Itu`IsListItem` pengembalian properti`true` jika paragraf tersebut adalah item daftar, jika tidak maka paragraf akan dikembalikan`false`.

```csharp
if (paragraph.IsListItem)
{
     // Paragraf adalah item daftar
}
else
{
     // Paragraf tersebut bukan merupakan item daftar
}
```