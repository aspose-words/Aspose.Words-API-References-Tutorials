---
title: Atur Posisi Catatan Kaki dan Catatan Akhir
linktitle: Atur Posisi Catatan Kaki dan Catatan Akhir
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengatur posisi catatan kaki dan catatan akhir di dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-footnote-and-endnote/set-footnote-and-end-note-position/
---

Dalam tutorial langkah demi langkah ini, kami akan memandu Anda tentang cara menggunakan Aspose.Words untuk .NET untuk mengatur posisi catatan kaki dan catatan akhir dalam dokumen Word. Kami akan menjelaskan kode sumber C# yang disediakan dan menunjukkan cara mengimplementasikannya di proyek Anda sendiri.

 Untuk memulai, pastikan Anda telah menginstal dan menyiapkan Aspose.Words untuk .NET di lingkungan pengembangan Anda. Jika Anda belum melakukannya, unduh dan instal perpustakaan dari[Aspose.Rilis]https://releases.aspose.com/words/net/.

## Langkah 1: Menginisialisasi Objek Dokumen

 Pertama, inisialisasi`Document` objek dengan memberikan jalur ke dokumen sumber Anda:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");
```

## Langkah 2: Mengatur Posisi Catatan Kaki dan Catatan Akhir

 Selanjutnya, akses`FootnoteOptions` Dan`EndnoteOptions`properti dokumen untuk mengatur posisi catatan kaki dan catatan akhir. Pada contoh ini, kita atur posisi catatan kaki berada di bawah teks dan posisi catatan akhir berada di akhir bagian:

```csharp
doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;
```

## Langkah 3: Menyimpan Dokumen

Terakhir, simpan dokumen yang dimodifikasi:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

Itu dia! Anda telah berhasil mengatur posisi catatan kaki dan catatan akhir dalam dokumen Word menggunakan Aspose.Words for .NET.

### Contoh kode sumber untuk Mengatur Posisi Catatan Kaki dan Catatan Akhir menggunakan Aspose.Words untuk .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");

doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

Jangan ragu untuk menggunakan kode ini di proyek Anda sendiri dan memodifikasinya sesuai dengan kebutuhan spesifik Anda.

### FAQ

#### T: Bagaimana cara memposisikan catatan kaki dan catatan akhir di Aspose.Words?

 A: Untuk memposisikan catatan kaki dan catatan akhir di Aspose.Words, Anda perlu menggunakan`FootnoteOptions` kelas dan`Position` Properti. Anda dapat mengatur properti ini ke nilai apa pun yang Anda inginkan, misalnya`BottomOfPage` (di bagian bawah halaman) atau`EndOfSection` (di akhir bagian).

#### Q: Apakah posisi catatan kaki dan catatan akhir dapat disesuaikan untuk setiap halaman atau bagian dokumen?

A: Ya, posisi catatan kaki dan catatan akhir dapat disesuaikan untuk setiap halaman atau bagian dokumen. Anda dapat menggunakan bagian Aspose.Words dan metode manipulasi halaman untuk menentukan posisi tertentu untuk catatan kaki dan catatan akhir.

#### T: Bagaimana cara menghapus catatan kaki atau catatan akhir dari dokumen?

 A: Untuk menghapus catatan kaki atau catatan akhir dari dokumen di Aspose.Words, Anda dapat menggunakan metode yang sesuai seperti`RemoveAllFootnotes` untuk menghapus semua catatan kaki atau`RemoveAllEndnotes` untuk menghapus semua catatan akhir. Pastikan untuk menyimpan dokumen setelah melakukan operasi ini.

#### Q: Apakah catatan kaki dan catatan akhir dapat ditempatkan di luar margin halaman?

Tidak, secara default catatan kaki dan catatan akhir tidak dapat ditempatkan di luar margin halaman di Aspose.Words. Namun, Anda dapat menyesuaikan margin dokumen untuk memberikan lebih banyak ruang untuk catatan kaki dan catatan akhir jika diperlukan.

#### T: Apakah catatan kaki dan catatan akhir dapat disesuaikan dengan font atau gaya pemformatan tertentu?

J: Ya, Anda dapat menyesuaikan catatan kaki dan catatan akhir dengan font atau gaya pemformatan tertentu di Aspose.Words. Anda dapat menggunakan metode dan properti yang tersedia untuk menerapkan gaya font, warna, ukuran font, dll. Catatan kaki dan catatan akhir.