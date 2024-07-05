---
title: Judul Seteks
linktitle: Judul Seteks
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menggunakan judul Setext untuk memformat dokumen Anda dengan Aspose.Words for .NET Panduan langkah demi langkah.
type: docs
weight: 10
url: /id/net/working-with-markdown/setext-heading/
---

Dalam tutorial ini, kami akan memandu Anda tentang cara menggunakan fitur Setext Heading dengan Aspose.Words untuk .NET. Setext Heading adalah metode alternatif untuk memformat judul dalam dokumen Markdown.

## Langkah 1: Menggunakan pembuat dokumen

Pertama, kita akan menggunakan pembuat dokumen untuk menambahkan konten ke dokumen kita.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
DocumentBuilder builder = new DocumentBuilder();
```

## Langkah 2: Menggunakan gaya judul Setext

Kita akan menggunakan gaya paragraf default "Judul 1" untuk membuat judul tingkat 1 di dokumen kita.

```csharp
builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

## Langkah 3: Mengatur Ulang Gaya

Kami mengatur ulang gaya font yang diterapkan sebelumnya untuk menghindari kombinasi gaya antar paragraf yang tidak diinginkan.

```csharp
builder.Font.Bold = false;
builder.Font.Italic = false;
```

## Langkah 4: Menyesuaikan Tingkat Judul Setext

Kita dapat menyesuaikan tingkat judul Setext dengan menambahkan gaya paragraf baru berdasarkan gaya judul yang ada. Dalam contoh ini, kita membuat gaya "SetextHeading1" berdasarkan gaya "Heading 1" untuk mewakili judul level 1 dalam format Setext.

```csharp
Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Title Setext level 1");
```

## Langkah 5: Menyimpan dokumen

Terakhir, kita bisa menyimpan dokumen dalam format yang diinginkan.

```csharp
builder.Document.Save(dataDir + "Test.md");
```

### Contoh kode sumber untuk judul Setext dengan Aspose.Words untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Gunakan pembuat dokumen untuk menambahkan konten ke dokumen.
DocumentBuilder builder = new DocumentBuilder();

builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");

// Reset gaya dari paragraf sebelumnya agar tidak menggabungkan gaya antar paragraf.
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Setext Heading level 1");

builder.ParagraphFormat.Style = builder.Document.Styles["Heading 3"];
builder.Writeln("This is an H3 tag");

// Reset gaya dari paragraf sebelumnya agar tidak menggabungkan gaya antar paragraf.
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading2 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading2");
builder.ParagraphFormat.Style = setexHeading2;
builder.Document.Styles["SetextHeading2"].BaseStyleName = "Heading 3";

// Level Heading Setex akan direset menjadi 2 jika paragraf dasar memiliki level Heading lebih besar dari 2.
builder.Writeln("Setext Heading level 2");


builder.Document.Save(dataDir + "Test.md");
```

### FAQ

#### T: Apa itu header Setext Markdown?

J: Header Setext Markdown adalah cara alternatif untuk membuat judul dalam dokumen Markdown. Ini menggunakan karakter garis bawah (= atau -) untuk menunjukkan tingkat judul yang berbeda.

#### T: Bagaimana cara menggunakan header Setext Markdown?

J: Untuk menggunakan judul Setext Markdown, tempatkan garis bawah di bawah teks judul. Gunakan tanda sama dengan (=) untuk header level 1 dan tanda hubung (-) untuk header level 2.

#### T: Apakah ada batasan dalam menggunakan header Setext Markdown?

J: Judul Setext Markdown memiliki batasan dalam hal hierarki judul dan tidak berbeda secara visual seperti judul Markdown standar.

#### T: Dapatkah saya menyesuaikan tampilan header Setext Markdown?

J: Dalam Markdown standar, tidak dimungkinkan untuk menyesuaikan tampilan header Setext Markdown. Mereka memiliki tampilan yang telah ditentukan berdasarkan karakter garis bawah yang digunakan.

#### T: Apakah header Setext Markdown didukung oleh semua editor Markdown?

J: Dukungan untuk header Setext Markdown mungkin berbeda antar editor Markdown. Periksa dokumentasi spesifik penerbit Anda untuk memastikannya.