---
title: Hapus Komentar Di File Pdf
linktitle: Hapus Komentar Di File Pdf
second_title: API Pemrosesan Dokumen Aspose.Words
description: Hapus komentar dalam file PDF dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-revisions/remove-comments-in-pdf/
---

Dalam panduan langkah demi langkah ini, kami akan memberi tahu Anda cara menghapus komentar di file PDF menggunakan Aspose.Words untuk .NET. Kami akan memberi Anda kode sumber lengkap dan menunjukkan cara memformat keluaran penurunan harga.

## Langkah 1: Memuat dokumen

Langkah pertama adalah memuat dokumen yang berisi komentar.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## Langkah 2: Sembunyikan komentar di PDF

Kami akan mengonfigurasi opsi tata letak untuk menyembunyikan komentar saat membuat PDF.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

## Langkah 3: Simpan dokumen sebagai PDF

Terakhir, kami akan menyimpan dokumen dalam format PDF dengan menghapus komentar.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## Format keluaran penurunan harga

Outputnya dapat diformat dalam penurunan harga untuk meningkatkan keterbacaan. Misalnya :

```markdown
- Comments are hidden in the generated PDF.
```

### Contoh kode sumber untuk Menghapus Komentar Di Pdf menggunakan Aspose.Words untuk .NET

Berikut source code lengkap untuk menghapus komentar di file PDF menggunakan Aspose.Words for .NET:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");

// Sembunyikan komentar di PDF.
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;

doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara menghapus komentar dari file PDF menggunakan Aspose.Words untuk .NET. Dengan menggunakan opsi tata letak yang sesuai, kami dapat menyembunyikan komentar saat membuat PDF. Aspose.Words untuk .NET menawarkan fleksibilitas besar untuk memanipulasi file Word dan mengonversinya ke format berbeda, termasuk PDF. Anda sekarang dapat menerapkan pengetahuan ini untuk menghapus komentar di file PDF Anda menggunakan Aspose.Words untuk .NET.

### FAQ untuk menghapus komentar dalam file pdf

#### T: Bagaimana cara mengunggah dokumen di Aspose.Words untuk .NET?

 J: Gunakan`Document` kelas Aspose.Words untuk .NET untuk memuat dokumen dari file. Anda dapat menentukan jalur dokumen lengkap.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### T: Bagaimana cara menyembunyikan komentar dalam PDF yang dihasilkan dengan Aspose.Words untuk .NET?

 J: Gunakan`CommentDisplayMode` properti dari`LayoutOptions` objek untuk mengonfigurasi bagaimana komentar ditampilkan saat membuat PDF. Untuk menyembunyikan komentar, setel properti ini ke`CommentDisplayMode.Hide`.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

#### T: Bagaimana cara menyimpan dokumen sebagai PDF dengan Aspose.Words untuk .NET?

 J: Gunakan`Save` metode`Document` keberatan untuk menyimpan dokumen dalam format PDF. Tentukan jalur lengkap file PDF.

```csharp
doc.Save("path/to/the/file.pdf");
```