---
title: Komentar Terselesaikan Dan Balasan
linktitle: Komentar Terselesaikan Dan Balasan
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengatasi komentar dan balasannya di dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-comments/comment-resolved-and-replies/
---

Dalam tutorial komprehensif ini, Anda akan mempelajari cara mengatasi komentar dan balasannya di dokumen Word menggunakan Aspose.Words untuk .NET. Kami akan memandu Anda melalui proses dan memberi Anda cuplikan kode C# yang diperlukan. Di akhir panduan ini, Anda akan dapat mengelola resolusi komentar dan memperbarui status komentar serta balasannya.

## Prasyarat
Sebelum kita mulai, pastikan Anda memiliki prasyarat berikut:
- Aspose.Words untuk perpustakaan .NET diinstal pada sistem Anda.

## Langkah 1: Muat Dokumen dan Akses Komentar
Untuk memulai, muat dokumen yang berisi komentar menggunakan kelas Dokumen dan akses koleksi komentar:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);
```

## Langkah 2: Selesaikan Komentar dan Balasannya
Selanjutnya, ulangi komentar dan balasannya untuk menandainya sebagai terselesaikan:

```csharp
Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}
```

Dalam kode di atas, kita mengakses komentar induk dan mengulangi balasannya. Kami dapat mengambil ID komentar induk dan status resolusinya. Kemudian, kami memperbarui tanda "Selesai" pada setiap balasan komentar untuk menunjukkan penyelesaian.

## Langkah 3: Simpan Dokumen
Setelah menyelesaikan komentar dan memperbarui statusnya, simpan dokumen yang dimodifikasi ke file menggunakan metode Simpan dari kelas Dokumen:

```csharp
doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```

### Contoh Kode Sumber untuk Menyelesaikan Komentar dan Balasannya menggunakan Aspose.Words untuk .NET
Berikut adalah kode sumber lengkap untuk menyelesaikan komentar dan balasannya menggunakan Aspose.Words for .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);

Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}

doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```
Ingatlah untuk menyesuaikan kode sesuai dengan kebutuhan spesifik Anda, termasuk jalur file dokumen dan penyesuaian tambahan

## Kesimpulan
Selamat! Anda telah berhasil mempelajari cara mengatasi komentar dan balasannya di dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah dan memanfaatkan kode sumber yang disediakan, kini Anda dapat mengelola resolusi komentar dan memperbarui status komentar dan balasannya sesuai dengan kebutuhan Anda.

Resolusi komentar membantu dalam melacak dan mengelola umpan balik dalam dokumen. Bereksperimenlah dengan berbagai status komentar dan sesuaikan untuk meningkatkan proses kolaborasi dan peninjauan di dokumen Anda.

### FAQ

#### T: Bagaimana cara mengatasi komentar di Aspose.Words untuk .NET?

 J: Untuk mengatasi komentar di Aspose.Words untuk .NET, Anda dapat menggunakan`Comment.Resolve` metode yang menentukan`Comment` objek yang ingin Anda selesaikan. Ini akan menandai komentar sebagai terselesaikan dan menyembunyikannya di dokumen akhir.

#### T: Bagaimana cara menambahkan balasan ke komentar yang diselesaikan di Aspose.Words untuk .NET?

 J: Meskipun komentar yang diselesaikan disembunyikan secara default di dokumen akhir, Anda masih dapat menambahkan balasan ke komentar yang diselesaikan menggunakan`Comment.AddReply`metode yang menentukan teks balasan dan di mana Anda ingin menambahkannya.

#### T: Bagaimana cara melihat komentar yang terselesaikan di Aspose.Words untuk .NET?

 J: Secara default, komentar yang terselesaikan disembunyikan di dokumen akhir. Namun, Anda dapat menampilkannya dengan menggunakan`CommentOptions.ShowResolvedComments` properti dari`Document` objek dan menyetelnya ke`true`.

#### T: Bagaimana cara menyembunyikan semua komentar, termasuk balasan, di Aspose.Words untuk .NET?

 J: Untuk menyembunyikan semua komentar, termasuk balasan, di Aspose.Words untuk .NET, Anda dapat menggunakan`CommentOptions.CommentDisplayMode` properti dari`Document` objek dan atur ke`CommentDisplayMode.None`.

#### T: Dapatkah saya mengedit teks komentar yang diselesaikan di Aspose.Words untuk .NET?

 J: Ya, Anda dapat mengedit teks komentar yang diselesaikan di Aspose.Words untuk .NET dengan mengakses`Comment.Text` milik yang bersangkutan`Comment` objek dan memodifikasi teks sesuai kebutuhan.