---
title: Kontrol Konten Kotak Kombo
linktitle: Kontrol Konten Kotak Kombo
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara membuat Kontrol Konten Kotak Kombo di dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-sdt/combo-box-content-control/
---

Tutorial ini menjelaskan cara membuat Kontrol Konten Kotak Kombo di dokumen Word menggunakan Aspose.Words untuk .NET. Kontrol konten kotak kombo memungkinkan pengguna memilih item dari daftar dropdown.

## Prasyarat
Untuk mengikuti tutorial ini, Anda harus memiliki yang berikut ini:

- Aspose.Words untuk perpustakaan .NET diinstal.
- Pengetahuan dasar tentang C# dan Pemrosesan Kata dengan dokumen Word.

## Langkah 1: Siapkan Direktori Dokumen
 Mulailah dengan menyiapkan jalur ke direktori dokumen Anda. Mengganti`"YOUR DOCUMENT DIRECTORY"`dengan jalur sebenarnya ke direktori tempat Anda ingin menyimpan dokumen.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Buat Dokumen dan StructuredDocumentTag
 Buat instance baru dari`Document` kelas dan a`StructuredDocumentTag` untuk mewakili kontrol konten kotak kombo. Menentukan`SdtType.ComboBox` sebagai tipe dan`MarkupLevel.Block` sebagai tingkat markup untuk membuat kotak kombo tingkat blok.

```csharp
Document doc = new Document();
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
```

## Langkah 3: Tambahkan Item ke Kotak Kombo
 Tambahkan item ke kotak kombo dengan menggunakan`ListItems` properti dari`StructuredDocumentTag` . Setiap item diwakili oleh sebuah`SdtListItem` objek, yang mengambil teks tampilan dan nilai. Dalam contoh ini, kita menambahkan tiga item ke kotak kombo.

```csharp
sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
```

## Langkah 4: Tambahkan StructuredDocumentTag ke Dokumen
 Tambahkan kontrol konten kotak kombo ke isi dokumen dengan menggunakan`AppendChild` metode isi bagian pertama dokumen.

```csharp
doc.FirstSection.Body.AppendChild(sdt);
```

## Langkah 5: Simpan Dokumen
 Simpan dokumen ke direktori yang ditentukan menggunakan`Save` metode. Berikan nama file yang diinginkan dengan ekstensi file yang sesuai. Dalam contoh ini, kami menyimpan dokumen sebagai "WorkingWithSdt.ComboBoxContentControl.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

### Contoh kode sumber untuk Kontrol Konten Kotak Kombo menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.ComboBox, MarkupLevel.Block);
	sdt.ListItems.Add(new SdtListItem("Choose an item", "-1"));
	sdt.ListItems.Add(new SdtListItem("Item 1", "1"));
	sdt.ListItems.Add(new SdtListItem("Item 2", "2"));
	doc.FirstSection.Body.AppendChild(sdt);
	doc.Save(dataDir + "WorkingWithSdt.ComboBoxContentControl.docx");
```

Itu dia! Anda telah berhasil membuat Kontrol Konten Kotak Kombo di dokumen Word Anda menggunakan Aspose.Words untuk .NET.