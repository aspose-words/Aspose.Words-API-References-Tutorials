---
title: Centang Kotak Jenis Kontrol Konten
linktitle: Centang Kotak Jenis Kontrol Konten
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara membuat Kontrol Konten Tipe Kotak Centang di dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-sdt/check-box-type-content-control/
---

Tutorial ini menjelaskan cara membuat Kontrol Konten Tipe Kotak Centang di dokumen Word menggunakan Aspose.Words untuk .NET. Kontrol konten kotak centang memungkinkan pengguna memilih atau mengosongkan kotak centang dalam dokumen.

## Prasyarat
Untuk mengikuti tutorial ini, Anda harus memiliki yang berikut ini:

- Aspose.Words untuk perpustakaan .NET diinstal.
- Pengetahuan dasar tentang C# dan Pemrosesan Kata dengan dokumen Word.

## Langkah 1: Siapkan Direktori Dokumen
 Mulailah dengan menyiapkan jalur ke direktori dokumen Anda. Mengganti`"YOUR DOCUMENT DIRECTORY"`dengan jalur sebenarnya ke direktori tempat Anda ingin menyimpan dokumen.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Buat Dokumen dan DocumentBuilder
 Buat instance baru dari`Document` kelas dan a`DocumentBuilder` untuk membangun konten dokumen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 3: Tambahkan Kontrol Konten Jenis Kotak Centang
 Membuat`StructuredDocumentTag` dengan`SdtType.Checkbox` untuk mewakili kontrol konten kotak centang. Menentukan`MarkupLevel.Inline` untuk menempatkannya di dalam teks.

```csharp
StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
builder.InsertNode(sdtCheckBox);
```

## Langkah 4: Simpan Dokumen
 Simpan dokumen ke direktori yang ditentukan menggunakan`Save`metode. Berikan nama file yang diinginkan dengan ekstensi file yang sesuai. Dalam contoh ini, kami menyimpan dokumen sebagai "WorkingWithSdt.CheckBoxTypeContentControl.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

### Contoh kode sumber untuk Kontrol Konten Tipe Kotak Centang menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
	builder.InsertNode(sdtCheckBox);
	doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

Itu dia! Anda telah berhasil membuat Kontrol Konten Tipe Kotak Centang di dokumen Word Anda menggunakan Aspose.Words untuk .NET.