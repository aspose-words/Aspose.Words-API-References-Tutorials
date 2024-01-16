---
title: Kontrol Konten Kotak Teks Kaya
linktitle: Kontrol Konten Kotak Teks Kaya
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara membuat kontrol konten kotak teks kaya di dokumen Word menggunakan Aspose.Words for .NET yang mengaktifkan pemformatan dan gaya teks.
type: docs
weight: 10
url: /id/net/programming-with-sdt/rich-text-box-content-control/
---

Tutorial ini menunjukkan cara membuat kontrol konten kotak teks kaya di dokumen Word menggunakan Aspose.Words untuk .NET. Kontrol konten kotak teks kaya memungkinkan pengguna memasukkan dan memformat teks dengan berbagai gaya dan opsi pemformatan.

## Prasyarat
Untuk mengikuti tutorial ini, Anda harus memiliki yang berikut ini:

- Aspose.Words untuk perpustakaan .NET diinstal.
- Pengetahuan dasar tentang C# dan Pemrosesan Kata dengan dokumen Word.

## Langkah 1: Siapkan Direktori Dokumen
 Mulailah dengan menyiapkan jalur ke direktori dokumen Anda. Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori tempat Anda ingin menyimpan dokumen.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Buat Dokumen dan StructuredDocumentTag
 Buat instance baru dari`Document` kelas dan a`StructuredDocumentTag` untuk mewakili kontrol konten kotak teks kaya. Menentukan`SdtType.RichText` sebagai tipe dan`MarkupLevel.Block` sebagai tingkat markup untuk membuat kotak teks kaya tingkat blok.

```csharp
Document doc = new Document();
StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
```

## Langkah 3: Buat dan Format Konten Teks Kaya
Buat paragraf dan jalankan untuk mewakili konten teks kaya. Atur opsi teks dan pemformatan seperti warna, font, dll.

```csharp
Paragraph para = new Paragraph(doc);
Run run = new Run(doc);
run.Text = "Hello World";
run.Font.Color = Color.Green;
para.Runs.Add(run);
```

## Langkah 4: Tambahkan Konten Teks Kaya ke Kontrol Konten
Tambahkan paragraf dengan konten teks kaya ke`ChildNodes` kumpulan kontrol konten kotak teks kaya.

```csharp
sdtRichText.ChildNodes.Add(para);
```

## Langkah 5: Tambahkan Kontrol Konten ke Dokumen
 Tambahkan kontrol konten kotak teks kaya ke badan dokumen dengan menggunakan`AppendChild` metode isi bagian pertama dokumen.

```csharp
doc.FirstSection.Body.AppendChild(sdtRichText);
```

## Langkah 6: Simpan Dokumen
 Simpan dokumen ke direktori yang ditentukan menggunakan`Save` metode. Berikan nama file yang diinginkan dengan ekstensi file yang sesuai. Dalam contoh ini, kami menyimpan dokumen sebagai "WorkingWithSdt.RichTextBoxContentControl.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

### Contoh kode sumber untuk Kontrol Konten Kotak Teks Kaya menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
	Paragraph para = new Paragraph(doc);
	Run run = new Run(doc);
	run.Text = "Hello World";
	run.Font.Color = Color.Green;
	para.Runs.Add(run);
	sdtRichText.ChildNodes.Add(para);
	doc.FirstSection.Body.AppendChild(sdtRichText);
	doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

Itu dia! Anda telah berhasil membuat kontrol konten kotak teks kaya di dokumen Word Anda menggunakan Aspose.Words untuk .NET.