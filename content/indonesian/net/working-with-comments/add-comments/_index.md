---
title: Tambahkan Komentar
linktitle: Tambahkan Komentar
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menambahkan komentar ke dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-comments/add-comments/
---

Dalam tutorial komprehensif ini, Anda akan mempelajari cara menambahkan komentar ke dokumen Word menggunakan Aspose.Words untuk .NET. Kami akan memandu Anda melalui proses dan memberi Anda cuplikan kode C# yang diperlukan. Di akhir panduan ini, Anda akan dapat menyisipkan komentar dan menyesuaikan kontennya di dokumen Anda.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
- Aspose.Words untuk perpustakaan .NET diinstal pada sistem Anda.

## Langkah 1: Buat Dokumen Baru dan DocumentBuilder
Untuk memulai, buat dokumen baru menggunakan kelas Dokumen dan inisialisasi objek DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 2: Tambahkan Konten ke Dokumen
Selanjutnya, tambahkan konten yang diinginkan ke dokumen menggunakan objek DocumentBuilder. Dalam contoh ini, kami menambahkan beberapa teks:

```csharp
builder.Write("Some text is added.");
```

## Langkah 3: Buat Komentar dan Tambahkan Konten
Untuk menambahkan komentar, buatlah sebuah instance dari kelas Comment, lewati objek Dokumen, nama penulis, inisial penulis, dan tanggal sekarang:

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
```

Selanjutnya, tambahkan komentar ke paragraf saat ini:

```csharp
builder.CurrentParagraph.AppendChild(comment);
```

Tambahkan konten ke komentar, seperti paragraf dan teks:

```csharp
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));
```

## Langkah 4: Simpan Dokumen
Setelah menambahkan komentar dan isinya, simpan dokumen ke file menggunakan metode Simpan dari kelas Dokumen:

```csharp
doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## Contoh Kode Sumber untuk Menambahkan Komentar menggunakan Aspose.Words untuk .NET
Berikut source code lengkap untuk menambahkan komentar menggunakan Aspose.Words for .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text is added.");

Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
builder.CurrentParagraph.AppendChild(comment);

comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara menambahkan komentar ke dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah dan memanfaatkan kode sumber yang disediakan, kini Anda dapat menyisipkan komentar dan menyesuaikan kontennya di dokumen Anda.

Komentar berguna untuk berkolaborasi, memberikan informasi tambahan, atau membuat catatan dalam dokumen. Bereksperimenlah dengan nama penulis, inisial, dan konten komentar yang berbeda untuk memenuhi kebutuhan spesifik Anda.

### FAQ

#### T: Bagaimana cara menambahkan komentar di dokumen Aspose.Words for .NET?

J: Untuk menambahkan komentar di dokumen Aspose.Words for .NET, Anda perlu mengikuti langkah-langkah yang disebutkan dalam tutorial.

#### T: Bisakah saya memformat teks komentar di Aspose.Words untuk .NET?

J: Ya, Anda dapat memformat teks komentar di Aspose.Words untuk .NET menggunakan properti pemformatan yang tersedia.

#### T: Bagaimana cara mengambil semua komentar yang ada dalam dokumen?

J: Anda dapat mengambil semua komentar yang ada dalam dokumen menggunakan`Document.Comments` Properti.

#### T: Dapatkah saya menghapus komentar tertentu di Aspose.Words untuk .NET?

 J: Ya, Anda dapat menghapus komentar tertentu di Aspose.Words untuk .NET menggunakan`Comment.Remove` metode.

#### T: Bagaimana cara mengubah teks komentar yang sudah ada di Aspose.Words untuk .NET?

 J: Untuk mengubah teks komentar yang ada di Aspose.Words untuk .NET, Anda dapat mengakses`Comment.Text` milik yang bersangkutan`Comment` objek dan memodifikasi teks sesuai kebutuhan.