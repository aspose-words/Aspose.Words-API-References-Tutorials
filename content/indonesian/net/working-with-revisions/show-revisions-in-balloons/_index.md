---
title: Tampilkan Revisi Dalam Balon
linktitle: Tampilkan Revisi Dalam Balon
second_title: API Pemrosesan Dokumen Aspose.Words
description: Tampilkan revisi dalam balon dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-revisions/show-revisions-in-balloons/
---

Dalam panduan langkah demi langkah ini, kami akan menunjukkan kepada Anda cara menampilkan revisi balon di dokumen Word menggunakan Aspose.Words untuk .NET. Kami akan memberi Anda kode sumber lengkap dan menunjukkan cara memformat keluaran penurunan harga.

## Langkah 1: Memuat dokumen

Langkah pertama adalah mengunggah dokumen yang berisi revisi.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## Langkah 2: Konfigurasikan opsi tampilan ulasan

Kami akan mengonfigurasi opsi tampilan untuk membuat revisi terlihat di balon.

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;
```

## Langkah 3: Simpan dokumen dalam format PDF

Terakhir, kami akan menyimpan dokumen sebagai PDF dengan revisi yang ditampilkan dalam balon.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## Format keluaran penurunan harga

Outputnya dapat diformat dalam penurunan harga untuk meningkatkan keterbacaan. Misalnya :

```markdown
- Revisions are Showed in bubbles with revision bars on the right side.
```

### Contoh kode sumber untuk Tampilkan Revisi Dalam Balon menggunakan Aspose.Words untuk .NET

Berikut kode sumber lengkap untuk menampilkan revisi balon pada dokumen menggunakan Aspose.Words for .NET:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(MyDir + "Revisions.docx");

// Render menyisipkan revisi sebaris, menghapus, dan memformat revisi dalam balon.
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
// Merender bilah revisi di sisi kanan halaman.
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;

doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara menampilkan revisi dalam balon di dokumen Word menggunakan Aspose.Words untuk .NET. Dengan menggunakan opsi tampilan yang sesuai, kami dapat membuat revisi terlihat dalam gelembung dengan bilah revisi di sisi kanan. Aspose.Words untuk .NET menawarkan banyak fitur canggih untuk memanipulasi dokumen Word, termasuk manajemen revisi. Sekarang Anda dapat menggunakan pengetahuan ini untuk memperlihatkan revisi balon di dokumen Word Anda sendiri menggunakan Aspose.Words untuk .NET.


### FAQ

#### T: Bagaimana cara mengunggah dokumen di Aspose.Words untuk .NET?

 J: Gunakan`Document` kelas Aspose.Words untuk .NET untuk memuat dokumen dari file. Anda dapat menentukan jalur dokumen lengkap.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Q: Bagaimana cara menampilkan revisi pada balon dengan Aspose.Words untuk .NET?

 J: Gunakan`ShowInBalloons` properti dari`RevisionOptions` objek untuk mengonfigurasi tampilan revisi dalam balon. Anda dapat mengaktifkan properti ini`ShowInBalloons.FormatAndDelete` untuk menampilkan revisi dalam balon dengan penghapusan dan revisi format.

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
```

#### T: Bagaimana cara menyimpan dokumen dalam format PDF dengan Aspose.Words untuk .NET?

 J: Gunakan`Save` metode`Document` keberatan untuk menyimpan dokumen dalam format PDF. Anda harus menentukan jalur tujuan lengkap dengan ekstensi ".pdf".

```csharp
doc.Save("path/to/destination/document.pdf");
```