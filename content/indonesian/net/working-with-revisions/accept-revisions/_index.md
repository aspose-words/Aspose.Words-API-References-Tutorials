---
title: Terima Ulasan
linktitle: Terima Ulasan
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menerima revisi dokumen Word menggunakan Aspose.Words untuk .NET
type: docs
weight: 10
url: /id/net/working-with-revisions/accept-revisions/
---

Dalam tutorial ini, kami akan memandu Anda dalam menerima revisi pada dokumen Word menggunakan fitur Terima Revisi Aspose.Words untuk .NET. Ikuti langkah-langkah di bawah ini untuk memahami kode sumber dan menerima perubahan pada dokumen.

## Langkah 1: Menambah dan Mengedit Konten Dokumen

Dalam contoh ini, kita membuat dokumen dan menambahkan konten. Kami menggunakan beberapa paragraf untuk menggambarkan perubahan dan revisi. Begini caranya:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

// Tambahkan teks ke paragraf pertama, lalu tambahkan dua paragraf lagi.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2.");
body.AppendParagraph("Paragraph 3.");
```

## Langkah 2: Lacak ulasan dan tambahkan ulasan

Kami mengaktifkan pelacakan revisi dan menambahkan revisi ke dokumen. Begini caranya:

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);

// Paragraf ini adalah revisi dan akan memiliki tanda "IsInsertRevision" yang sesuai.
para = body.AppendParagraph("Paragraph 4.");
Assert.True(para.IsInsertRevision);
```

## Langkah 3: Hapus paragraf dan kelola revisinya

Kami menghapus satu paragraf dan memeriksa revisi yang disimpan. Begini caranya:

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// Saat kami melacak revisi, paragraf tersebut masih ada di dokumen, dan tanda "IsDeleteRevision" akan disetel
// dan akan ditampilkan sebagai ulasan di Microsoft Word, hingga kami menerima atau menolak semua ulasan.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);
```

## Langkah 4: Terima Perubahan

Kami menerima semua perubahan pada dokumen. Begini caranya:

```csharp
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);
```

## Langkah 5: Berhenti melacak ulasan

Kami akan berhenti melacak revisi sehingga perubahan pada dokumen tidak lagi muncul sebagai revisi. Begini caranya:

```csharp
doc.StopTrackRevisions();
```
## Langkah 6: Menyimpan dokumen

 Setelah memasukkan kolom formulir input teks, simpan dokumen ke lokasi yang diinginkan menggunakan`Save` metode. Pastikan untuk memberikan jalur file yang sesuai:

```csharp
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```

### Contoh kode sumber untuk Terima Revisi menggunakan Aspose.Words untuk .NET

Berikut kode sumber lengkap untuk menerima perubahan dokumen menggunakan Aspose.Words for .NET:


```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

// Tambahkan teks ke paragraf pertama, lalu tambahkan dua paragraf lagi.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2. ");
body.AppendParagraph("Paragraph 3. ");

//Kami memiliki tiga paragraf, tidak ada satupun yang terdaftar sebagai revisi apa pun
// Jika kami menambah/menghapus konten apa pun dalam dokumen saat melacak revisi,
// mereka akan ditampilkan seperti itu di dokumen dan dapat diterima/ditolak.
doc.StartTrackRevisions("John Doe", DateTime.Now);

// Paragraf ini adalah revisi dan akan memiliki tanda "IsInsertRevision" yang sesuai.
para = body.AppendParagraph("Paragraph 4. ");
Assert.True(para.IsInsertRevision);

// Dapatkan kumpulan paragraf dokumen dan hapus satu paragraf.
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// Karena kami melacak revisi, paragraf yang masih ada di dokumen, akan memiliki set "IsDeleteRevision".
// dan akan ditampilkan sebagai revisi di Microsoft Word, hingga kami menerima atau menolak semua revisi.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);

// Paragraf revisi yang dihapus akan dihapus setelah kami menerima perubahan.
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);

// Menghentikan pelacakan revisi membuat teks ini tampak seperti teks biasa.
// Revisi tidak dihitung pada saat perubahan dokumen.
doc.StopTrackRevisions();

// Simpan dokumennya.
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```
## Kesimpulan

Dalam tutorial ini, kita mempelajari cara menerima revisi dalam dokumen Word menggunakan fitur Terima Revisi Aspose.Words untuk .NET. Kami telah mengikuti langkah-langkah untuk menambah dan mengedit konten dokumen, melacak revisi, menghapus paragraf yang direvisi, menerima semua perubahan, dan berhenti melacak revisi. Sekarang Anda dapat menerapkan pengetahuan ini untuk mengelola revisi dokumen Word Anda secara efektif menggunakan Aspose.Words untuk .NET.

### FAQ

#### T: Bagaimana cara mengaktifkan pelacakan revisi di Aspose.Words untuk .NET?

#### Solusi 1:

 J: Untuk mengaktifkan pelacakan revisi di Aspose.Words untuk .NET, gunakan`StartTrackRevisions` metode`Document` objek dan tentukan nama penulis dan tanggal mulai untuk pelacakan revisi.

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);
```

#### Solusi 2:

 J: Anda juga dapat mengaktifkan pelacakan revisi menggunakan`Document` konstruktor yang menerima`trackRevisions` Dan`author` parameter.

```csharp
Document doc = new Document("document.docx", new LoadOptions { TrackRevisions = true, Author = "John Doe" });
```

#### T: Bagaimana cara menerima semua perubahan dalam dokumen dengan Aspose.Words untuk .NET?

 J: Gunakan`AcceptAllRevisions` metode`Document` keberatan untuk menerima semua perubahan yang dilakukan pada dokumen.

```csharp
doc.AcceptAllRevisions();
```

#### T: Bagaimana cara menyimpan dokumen yang diubah dengan revisi yang diterima?

 Menggunakan`Save` metode`Document` keberatan untuk menyimpan dokumen yang dimodifikasi dengan revisi yang diterima. Pastikan untuk memberikan jalur file yang benar.

```csharp
doc.Save("path/to/the/document.docx");
```

#### T: Bagaimana cara berhenti melacak revisi di Aspose.Words untuk .NET?

 J: Gunakan`StopTrackRevisions` metode`Document` keberatan untuk menghentikan revisi pelacakan.

```csharp
doc.StopTrackRevisions();
```

#### T: Bagaimana cara menghapus paragraf yang direvisi dalam dokumen dengan Aspose.Words untuk .NET?

 J: Untuk menghapus paragraf yang direvisi dalam dokumen, Anda dapat menggunakan`Remove` metode pengumpulan paragraf.

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Paragraph para = paragraphs[2];
para.Remove();
```