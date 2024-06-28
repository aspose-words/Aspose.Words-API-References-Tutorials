---
title: Ubah Spasi dan Indentasi Paragraf Asia di Dokumen Word
linktitle: Ubah Spasi dan Indentasi Paragraf Asia di Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengubah spasi dan indentasi paragraf Asia di dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/document-formatting/change-asian-paragraph-spacing-and-indents/
---
Dalam tutorial ini, kami akan memandu Anda tentang cara mengubah spasi dan indentasi paragraf Asia menggunakan Aspose.Words untuk .NET. Ikuti langkah-langkah di bawah ini untuk memahami kode sumber dan menerapkan perubahan.

## Langkah 1: Memuat dokumen

Untuk memulai, tentukan direktori untuk dokumen Anda dan muat dokumen yang berisi tipografi Asia ke dalam objek Dokumen. Begini caranya:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## Langkah 2: Mengubah spasi dan indentasi paragraf

Kami sekarang akan mengubah spasi dan indentasi paragraf pertama dokumen Asia. Begini caranya:

```csharp
ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
format.CharacterUnitLeftIndent = 10; // Perbarui ParagraphFormat.LeftIndent
format.CharacterUnitRightIndent = 10; // Perbarui ParagraphFormat.RightIndent
format.CharacterUnitFirstLineIndent = 20; //Perbarui ParagraphFormat.FirstLineIndent
format.LineUnitBefore = 5; // Perbarui ParagraphFormat.SpaceBefore
format.LineUnitAfter = 10; // Perbarui ParagraphFormat.SpaceAfter
```

## Langkah 3: Menyimpan dokumen

 Setelah memasukkan kolom formulir input teks, simpan dokumen ke lokasi yang diinginkan menggunakan`Save` metode. Pastikan untuk memberikan jalur file yang sesuai:

```csharp
doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");
```

### Contoh kode sumber untuk Mengubah Spasi dan Indentasi Paragraf Asia menggunakan Aspose.Words untuk .NET

Berikut source code lengkap fitur Edit Spasi dan Indentasi Paragraf Asia dengan Aspose.Words for .NET:

```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
	format.CharacterUnitLeftIndent = 10;       // ParagraphFormat.LeftIndent akan diperbarui.
	format.CharacterUnitRightIndent = 10;      // ParagraphFormat.RightIndent akan diperbarui.
	format.CharacterUnitFirstLineIndent = 20;  // ParagraphFormat.FirstLineIndent akan diperbarui.
	format.LineUnitBefore = 5;                 // ParagraphFormat.SpaceBefore akan diperbarui
	format.LineUnitAfter = 10;                 // ParagraphFormat.SpaceAfter akan diperbarui

	doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");

```

Dengan kode ini Anda akan dapat mengubah spasi dan indentasi paragraf Asia menggunakan Aspose.Words untuk .NET.

## Kesimpulan

 Dalam tutorial ini, kita mempelajari cara mengubah spasi dan indentasi paragraf Asia menggunakan Aspose.Words untuk .NET. Dengan memodifikasi properti yang relevan dari`ParagraphFormat`kita dapat mengontrol tata letak dan tampilan paragraf Asia di dokumen Word. Fitur ini berguna untuk menyesuaikan format teks dengan karakter Asia dan mencapai presentasi visual yang diinginkan dalam dokumen dengan konten bahasa campuran.

### FAQ

#### T: Apa yang dilakukan fitur "Ubah Spasi dan Indentasi Paragraf Asia" di Aspose.Words untuk .NET?

J: Fitur "Ubah Spasi dan Indentasi Paragraf Asia" di Aspose.Words untuk .NET memungkinkan Anda mengubah properti spasi dan indentasi paragraf Asia di dokumen Word. Anda dapat menyesuaikan nilai indentasi kiri dan kanan, indentasi baris pertama, spasi sebelum, dan spasi setelah untuk mengontrol tata letak dan tampilan paragraf.

#### T: Bagaimana cara mengubah spasi dan indentasi paragraf Asia menggunakan Aspose.Words untuk .NET?

 A: Untuk mengubah spasi dan indentasi paragraf Asia, Anda perlu mengakses`ParagraphFormat`paragraf target dan memodifikasi properti yang relevan. Dalam contoh kode yang diberikan, kita mengakses paragraf pertama dokumen dan mengaturnya`CharacterUnitLeftIndent`, `CharacterUnitRightIndent`, `CharacterUnitFirstLineIndent`, `LineUnitBefore` , Dan`LineUnitAfter` properti untuk mengatur jarak dan indentasi.

#### T: Dapatkah saya menerapkan perubahan ini pada paragraf lain dalam dokumen?

 J: Ya, Anda dapat menerapkan perubahan ini pada paragraf lain dalam dokumen dengan mengakses masing-masing paragraf`ParagraphFormat` objek. Kode contoh menargetkan paragraf pertama dokumen, tetapi Anda dapat mengubah paragraf lain dengan menyesuaikan indeks di`Paragraphs` koleksi atau menggunakan kriteria lain untuk memilih paragraf yang diinginkan.