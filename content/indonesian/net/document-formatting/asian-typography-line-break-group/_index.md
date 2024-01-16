---
title: Grup Pemutusan Garis Tipografi Asia Dalam Dokumen Word
linktitle: Grup Pemutusan Garis Tipografi Asia Dalam Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menggunakan grup pemisah baris Tipografi Asia di dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/document-formatting/asian-typography-line-break-group/
---
Dalam tutorial ini, kami akan menunjukkan kepada Anda cara menggunakan grup pemisah baris Tipografi Asia dalam fitur dokumen Word dengan Aspose.Words untuk .NET. Ikuti langkah-langkah di bawah ini untuk memahami kode sumber dan menerapkan perubahan pemformatan.

## Langkah 1: Memuat dokumen

Untuk memulai, tentukan direktori untuk dokumen Anda dan muat dokumen yang berisi tipografi Asia ke dalam objek Dokumen. Begini caranya:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## Langkah 2: Pengaturan Tipografi Asia

Kami sekarang akan mengkonfigurasi pengaturan tipografi Asia untuk paragraf pertama dokumen. Begini caranya:

```csharp
ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
format. FarEastLineBreakControl = false;
format. WordWrap = true;
format. HangingPunctuation = false;
```

## Langkah 3: Menyimpan dokumen

 Setelah memasukkan kolom formulir input teks, simpan dokumen ke lokasi yang diinginkan menggunakan`Save` metode. Pastikan untuk memberikan jalur file yang sesuai:

```csharp
doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
```

### Contoh kode sumber untuk Grup Pemutus Garis Tipografi Asia menggunakan Aspose.Words untuk .NET

Berikut adalah kode sumber lengkap fitur Asian Typography Line Break Group dengan Aspose.Words for .NET:

```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
	format.FarEastLineBreakControl = false;
	format.WordWrap = true;
	format.HangingPunctuation = false;

	doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
	
```
Dengan kode ini Anda akan dapat menerapkan grup pemisah baris Tipografi Asia menggunakan Aspose.Words untuk .NET.

## Kesimpulan

 Dalam tutorial ini, kita menjelajahi fitur "Grup Pemutus Garis Tipografi Asia" di Aspose.Words untuk .NET. Dengan mengkonfigurasi`FarEastLineBreakControl`, `WordWrap` , Dan`HangingPunctuation` properti dari`ParagraphFormat`, kami dapat mengontrol perilaku putusnya garis untuk tipografi Asia di dokumen Word. Fitur ini berguna untuk menangani karakter Asia dan memastikan jeda baris dan pembungkusan kata yang tepat dalam dokumen dengan konten bahasa campuran.

### FAQ

#### T: Apa yang dimaksud dengan fitur "Grup Pemutus Garis Tipografi Asia" di Aspose.Words untuk .NET?

J: Fitur "Grup Pemutus Garis Tipografi Asia" di Aspose.Words untuk .NET memungkinkan Anda mengontrol perilaku pemutusan garis untuk tipografi Asia di dokumen Word. Secara khusus, ini mempengaruhi bagaimana garis dipecah dan dibungkus ketika berhadapan dengan karakter Asia dalam paragraf.

#### T: Bagaimana cara mengaktifkan "Grup Pemutus Garis Tipografi Asia" di Aspose.Words untuk .NET?

 J: Untuk mengaktifkan "Grup Pemutus Garis Tipografi Asia", Anda perlu mengonfigurasi`FarEastLineBreakControl`, `WordWrap` , Dan`HangingPunctuation` properti dari`ParagraphFormat` untuk paragraf yang relevan dalam dokumen Anda. Pengaturan`FarEastLineBreakControl` ke`false` memastikan bahwa karakter Asia diperlakukan serupa dengan karakter Latin terkait pemutusan baris.`WordWrap` mulai`true` mengaktifkan pembungkusan kata untuk tipografi Asia, dan`HangingPunctuation` mulai`false` mencegah tanda baca menggantung di teks Asia.

#### T: Dapatkah saya menerapkan "Grup Pemutus Garis Tipografi Asia" pada paragraf tertentu dalam dokumen?

J: Ya, Anda dapat menerapkan pengaturan "Grup Pemutus Garis Tipografi Asia" ke paragraf tertentu dalam dokumen Word. Dalam kode contoh, pengaturan diterapkan pada paragraf pertama dokumen. Anda dapat menyesuaikan kode untuk menargetkan paragraf lain sesuai kebutuhan dengan mengaksesnya melalui`Paragraphs` kumpulan bagian yang relevan dalam dokumen.