---
title: Komentar Jangkar
linktitle: Komentar Jangkar
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengaitkan balasan komentar ke teks tertentu di dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-comments/anchor-comment/
---

Dalam tutorial komprehensif ini, Anda akan mempelajari cara mengaitkan balasan komentar ke teks tertentu di dokumen Word menggunakan Aspose.Words untuk .NET. Kami akan memandu Anda melalui proses dan memberi Anda cuplikan kode C# yang diperlukan. Di akhir panduan ini, Anda akan dapat mengaitkan komentar dengan teks tertentu di dokumen Anda.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
- Aspose.Words untuk perpustakaan .NET diinstal pada sistem Anda.

## Langkah 1: Buat Dokumen Baru dan Tambahkan Teks
Untuk memulai, buat dokumen baru menggunakan kelas Dokumen dan tambahkan teks yang diinginkan:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

Paragraph para1 = new Paragraph(doc);
Run run1 = new Run(doc, "Some ");
Run run2 = new Run(doc, "text ");
para1.AppendChild(run1);
para1.AppendChild(run2);
doc.FirstSection.Body.AppendChild(para1);

Paragraph para2 = new Paragraph(doc);
Run run3 = new Run(doc, "is ");
Run run4 = new Run(doc, "added ");
para2.AppendChild(run3);
para2.AppendChild(run4);
doc.FirstSection.Body.AppendChild(para2);
```

## Langkah 2: Buat Komentar dan Tambahkan Rentang Komentar
Selanjutnya, buat komentar dan kaitkan dengan teks tertentu menggunakan objek CommentRangeStart dan CommentRangeEnd:

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);
```

## Langkah 3: Simpan Dokumen
Setelah mengaitkan komentar ke teks tertentu, simpan dokumen ke file menggunakan metode Simpan dari kelas Dokumen:

```csharp
doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");
```

### Contoh Kode Sumber untuk Balasan Komentar Jangkar menggunakan Aspose.Words untuk .NET
Berikut adalah kode sumber lengkap untuk menahan balasan komentar menggunakan Aspose.Words untuk .NET:

```csharp
// Buat sebuah instance dari Dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document();

// Buat tiga objek Jalankan.
// Dua yang pertama menjalankan beberapa teks, sedangkan yang ketiga menjalankan Komentar

Paragraph para1 = new Paragraph(doc);
Run run1 = new Run(doc, "Some ");
Run run2 = new Run(doc, "text ");
para1.AppendChild(run1);
para1.AppendChild(run2);
doc.FirstSection.Body.AppendChild(para1);

Paragraph para2 = new Paragraph(doc);
Run run3 = new Run(doc, "is ");
Run run4 = new Run(doc, "added ");
para2.AppendChild(run3);
para2.AppendChild(run4);
doc.FirstSection.Body.AppendChild(para2);

Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

// Masing-masing objek Run memiliki objek CommentRangeStart dan CommentRangeEnd terkait.

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);

doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");	
```

### FAQ

#### T: Apa yang dimaksud dengan jangkar komentar di Aspose.Words untuk .NET?

J: Di Aspose.Words untuk .NET, jangkar komentar adalah penanda yang menghubungkan komentar ke lokasi tertentu dalam dokumen.

#### T: Bagaimana cara menambahkan jangkar komentar di dokumen Aspose.Words untuk .NET?

J: Untuk menambahkan jangkar komentar di dokumen Aspose.Words for .NET, ikuti langkah-langkah yang disebutkan dalam tutorial.

#### T: Bagaimana cara mengakses jangkar komentar yang ada di Aspose.Words untuk .NET?

 J: Anda dapat mengakses jangkar komentar yang ada di Aspose.Words untuk .NET menggunakan`Comment.Anchor` Properti.

#### T: Bisakah saya menambahkan jangkar komentar di Aspose.Words untuk .NET?

 J: Ya, Anda dapat menghapus jangkar komentar di Aspose.Words untuk .NET menggunakan`Comment.Remove` metode.

#### T: Bagaimana cara mengedit teks komentar yang ditautkan ke jangkar komentar di Aspose.Words untuk .NET?

 J: Untuk mengubah teks komentar yang terikat pada jangkar komentar di Aspose.Words untuk .NET, Anda dapat mengakses`Comment.Text` milik yang bersangkutan`Comment` objek dan memodifikasi teks sesuai kebutuhan.

