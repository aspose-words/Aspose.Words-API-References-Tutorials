---
title: Tetapkan Opsi Catatan Akhir
linktitle: Tetapkan Opsi Catatan Akhir
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengatur opsi catatan akhir di dokumen Word menggunakan Aspose.Words untuk .NET. Tutorial langkah demi langkah dengan contoh kode sumber.
type: docs
weight: 10
url: /id/net/working-with-footnote-and-endnote/set-endnote-options/
---

Dalam tutorial langkah demi langkah ini, kami akan memandu Anda tentang cara menggunakan Aspose.Words untuk .NET untuk mengatur opsi catatan akhir di dokumen Word. Kami akan menjelaskan kode sumber C# yang disediakan dan menunjukkan cara mengimplementasikannya di proyek Anda sendiri.

 Untuk memulai, pastikan Anda telah menginstal dan menyiapkan Aspose.Words untuk .NET di lingkungan pengembangan Anda. Jika Anda belum melakukannya, unduh dan instal perpustakaan dari[Aspose.Rilis]https://releases.aspose.com/words/net/.

## Langkah 1: Menginisialisasi Objek Dokumen

 Pertama, inisialisasi`Document` objek dengan memberikan jalur ke dokumen sumber Anda:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Langkah 2: Menginisialisasi Objek DocumentBuilder

 Selanjutnya, inisialisasi`DocumentBuilder` objek untuk melakukan operasi pada dokumen:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 3: Menambahkan Teks dan Catatan Akhir

 Menggunakan`Write` metode`DocumentBuilder` objek untuk menambahkan teks ke dokumen, dan`InsertFootnote` metode untuk memasukkan catatan akhir:

```csharp
builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");
```

## Langkah 4: Mengatur Opsi Catatan Akhir

 Akses`EndnoteOptions`properti dokumen untuk mengubah opsi catatan akhir. Dalam contoh ini, kami menetapkan aturan restart untuk memulai ulang pada setiap halaman dan posisinya di akhir bagian:

```csharp
EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;
```

## Langkah 5: Menyimpan Dokumen

Terakhir, simpan dokumen yang dimodifikasi:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

Itu dia! Anda telah berhasil mengatur opsi catatan akhir di dokumen Word menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber untuk Mengatur Opsi Catatan Akhir menggunakan Aspose.Words untuk .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");

EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

Jangan ragu untuk menggunakan kode ini di proyek Anda sendiri dan memodifikasinya sesuai dengan kebutuhan spesifik Anda.

### FAQ

#### T: Bagaimana cara menata gaya catatan akhir di Aspose.Words?

 J: Untuk menata catatan akhir di Aspose.Words, Anda dapat menggunakan`EndnoteOptions` kelas dan`SeparatorNoteTextStyle` Properti. Anda dapat menentukan gaya font, ukuran, warna, dll. untuk catatan akhir menggunakan properti ini.

#### T: Apakah mungkin untuk menyesuaikan penomoran catatan akhir dalam dokumen?

 J: Ya, dimungkinkan untuk menyesuaikan penomoran catatan akhir dalam dokumen. Anda dapat menggunakan`RestartRule`Dan`NumberStyle` properti dari`EndnoteOptions` kelas untuk menentukan aturan restart tertentu dan gaya penomoran.

#### T: Bagaimana cara memposisikan catatan akhir dalam dokumen?

J: Untuk memposisikan catatan akhir dalam dokumen, Anda dapat menggunakan`Position` properti dari`EndnoteOptions` kelas. Anda dapat menentukan apakah catatan akhir harus ditempatkan di bagian bawah setiap halaman, di akhir setiap bagian, atau di akhir dokumen.

#### T: Dapatkah saya menyesuaikan format penomoran catatan akhir?

 A: Ya, Anda dapat menyesuaikan format penomoran catatan akhir di Aspose.Words. Menggunakan`NumberFormat` properti dari`EndnoteOptions` class untuk mengatur format yang diinginkan, seperti angka arab, angka romawi, huruf, dll.

#### T: Apakah mungkin untuk melanjutkan penomoran catatan akhir antar bagian dokumen?

 J: Ya, dimungkinkan untuk melanjutkan penomoran catatan akhir antar bagian dokumen. Menggunakan`RestartRule` properti dari`EndnoteOptions` kelas dan atur ke`RestartContinuous` untuk memungkinkan penomoran berlanjut antar bagian.