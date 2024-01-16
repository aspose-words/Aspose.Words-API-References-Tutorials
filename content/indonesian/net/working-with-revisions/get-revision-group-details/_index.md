---
title: Dapatkan Detail Grup Revisi
linktitle: Dapatkan Detail Grup Revisi
second_title: API Pemrosesan Dokumen Aspose.Words
description: Dapatkan detail grup revisi dalam dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-revisions/get-revision-group-details/
---

Dalam panduan langkah demi langkah ini, kami akan menunjukkan kepada Anda cara mendapatkan detail sekelompok revisi dalam dokumen Word menggunakan Aspose.Words untuk .NET. Kami akan memberi Anda kode sumber lengkap dan menunjukkan cara memformat keluaran penurunan harga.

## Langkah 1: Memuat dokumen

Langkah pertama adalah mengunggah dokumen yang berisi revisi.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Langkah 2: Telusuri revisi

Selanjutnya, kita akan menelusuri revisi yang ada di dokumen dan menampilkan detailnya, seperti jenis, penulis, tanggal, dan teks yang direvisi.

```csharp
foreach (Revision revision in doc.Revisions)
{
     string groupText = revision.Group != null
         ? "Revision group text: " + revision.Group.Text
         : "The revision does not belong to any group";

     Console.WriteLine("Type: " + revision.RevisionType);
     Console.WriteLine("Author: " + revision.Author);
     Console.WriteLine("Date: " + revision.DateTime);
     Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
     Console.WriteLine(groupText);
}
```


### Contoh kode sumber untuk Dapatkan Detail Grup Revisi menggunakan Aspose.Words untuk .NET

Berikut source code lengkap untuk mendapatkan detail kumpulan revisi pada suatu dokumen menggunakan Aspose.Words for .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach (Revision revision in doc.Revisions)
{
	 string groupText = revision.Group != null
		 ? "Revision group text: " + revision.Group.Text
		 : "The revision does not belong to any group";

	 Console.WriteLine("Type: " + revision.RevisionType);
	 Console.WriteLine("Author: " + revision.Author);
	 Console.WriteLine("Date: " + revision.DateTime);
	 Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
	 Console.WriteLine(groupText);
}
```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara mendapatkan detail sekelompok revisi dalam dokumen Word menggunakan Aspose.Words untuk .NET. Dengan menggunakan loop dan properti yang sesuai, kami dapat menampilkan detail seperti jenis revisi, penulis, tanggal, dan teks yang direvisi. Aspose.Words untuk .NET menawarkan banyak fitur canggih untuk memanipulasi dokumen Word, termasuk manajemen revisi. Anda sekarang dapat menggunakan pengetahuan ini untuk mendapatkan detail grup revisi ke dalam dokumen Word Anda sendiri menggunakan Aspose.Words untuk .NET.

### FAQ

#### T: Bagaimana cara memuat dokumen dengan revisi ke Aspose.Words untuk .NET?

 J: Gunakan`Document`kelas Aspose.Words untuk .NET untuk memuat dokumen dari file yang berisi revisi. Anda dapat menentukan jalur dokumen lengkap.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### T: Bagaimana cara mendapatkan detail grup revisi di Aspose.Words untuk .NET?

 J: Telusuri revisi dokumen menggunakan loop dan akses properti setiap revisi untuk mendapatkan detail yang Anda inginkan. Anda dapat menggunakan`RevisionType`, `Author`, `DateTime` Dan`ParentNode` properti untuk mendapatkan masing-masing jenis revisi, penulis, tanggal dan teks revisi.

```csharp
foreach (Revision revision in doc.Revisions)
{
      Console.WriteLine("Type: " + revision.RevisionType

);
      Console.WriteLine("Author: " + revision.Author);
      Console.WriteLine("Date: " + revision.DateTime);
      Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
}
```

#### T: Bagaimana cara memeriksa apakah suatu revisi termasuk dalam grup di Aspose.Words untuk .NET?

 J: Gunakan`Group` properti dari`Revision` objek untuk memeriksa apakah revisi milik grup. Jika`Group` properti adalah`null`artinya revisi tersebut bukan milik kelompok manapun.

```csharp
if (revision.Group != null)
{
      // Revisi milik grup
}
else
{
      // Revisi tersebut bukan milik kelompok mana pun
}
```