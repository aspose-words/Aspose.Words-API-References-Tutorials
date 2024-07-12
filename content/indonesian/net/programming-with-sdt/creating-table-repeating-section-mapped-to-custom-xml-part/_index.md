---
title: Membuat Tabel Bagian Berulang yang Dipetakan ke Bagian Xml Kustom
linktitle: Membuat Tabel Bagian Berulang yang Dipetakan ke Bagian Xml Kustom
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara membuat tabel dengan bagian berulang yang dipetakan ke CustomXmlPart di dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-sdt/creating-table-repeating-section-mapped-to-custom-xml-part/
---

Tutorial ini menunjukkan cara membuat tabel dengan bagian berulang yang dipetakan ke Bagian Xml Kustom dalam dokumen Word menggunakan Aspose.Words untuk .NET. Bagian berulang memungkinkan Anda menambahkan baris secara dinamis berdasarkan data XML yang disimpan di Bagian Xml Kustom.

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

## Langkah 3: Tambahkan Data XML Khusus ke CustomXmlPart
 Membuat`CustomXmlPart` dan tambahkan data XML khusus ke dalamnya. Dalam contoh ini, kami membuat string XML yang mewakili kumpulan buku beserta judul dan penulisnya.

```csharp
CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
	"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
	"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
	"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
```

## Langkah 4: Buat Tabel dan Struktur Tabel
 Mulailah membuat tabel menggunakan`StartTable` metode`DocumentBuilder` . Tambahkan sel tabel dan konten menggunakan`InsertCell`Dan`Write` metode.

```csharp
Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Title");
builder.InsertCell();
builder.Write("Author");
builder.EndRow();
builder.EndTable();
```

## Langkah 5: Buat Bagian Berulang yang Dipetakan ke XML Khusus
 Membuat`StructuredDocumentTag` dengan`SdtType.RepeatingSection` untuk mewakili bagian yang berulang. Atur pemetaan XML untuk bagian berulang menggunakan`SetMapping` metode`XmlMapping` Properti. Dalam contoh ini, kami memetakan bagian berulang ke`/books[1]/book`.

```csharp
StructuredDocumentTag repeatingSectionSdt =
	new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
table.AppendChild(repeatingSectionSdt);
```

## Langkah 6: Buat Item Bagian Berulang dan Tambahkan Sel
 Membuat`StructuredDocumentTag` dengan`SdtType.RepeatingSectionItem` untuk mewakili item bagian berulang. Tambahkan sebagai anak-anak ke bagian berulang.

```csharp
StructuredDocumentTag repeatingSectionItemSdt = 
	new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
```

 Membuat`Row` untuk mewakili setiap item di bagian berulang dan menambahkannya ke item bagian berulang.

```csharp
Row row = new Row(doc);
repeatingSectionItemSdt.AppendChild(row);
```

## Langkah 7: Tambahkan Kontrol Konten di Bagian Berulang
 Membuat`StructuredDocumentTag` objek dengan`SdtType.PlainText`

  untuk mewakili judul dan kontrol konten penulis. Atur pemetaan XML untuk setiap kontrol konten menggunakan`SetMapping` metode`XmlMapping` Properti. Dalam contoh ini, kami memetakan kontrol judul ke`/books[1]/book[1]/title[1]` dan penulis mengontrol untuk`/books[1]/book[1]/author[1]`.

```csharp
StructuredDocumentTag titleSdt =
	new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
row.AppendChild(titleSdt);

StructuredDocumentTag authorSdt =
	new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
row.AppendChild(authorSdt);
```

## Langkah 8: Simpan Dokumen
 Simpan dokumen yang dimodifikasi ke direktori yang ditentukan menggunakan`Save` metode. Berikan nama file yang diinginkan dengan ekstensi file yang sesuai. Dalam contoh ini, kami menyimpan dokumen sebagai "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");
```

### Contoh kode sumber untuk Membuat Tabel Bagian Berulang yang Dipetakan ke Bagian Xml Kustom menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
		"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
		"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
		"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
	Table table = builder.StartTable();
	builder.InsertCell();
	builder.Write("Title");
	builder.InsertCell();
	builder.Write("Author");
	builder.EndRow();
	builder.EndTable();
	StructuredDocumentTag repeatingSectionSdt =
		new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
	repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
	table.AppendChild(repeatingSectionSdt);
	StructuredDocumentTag repeatingSectionItemSdt = 
		new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
	repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
	Row row = new Row(doc);
	repeatingSectionItemSdt.AppendChild(row);
	StructuredDocumentTag titleSdt =
		new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
	titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
	row.AppendChild(titleSdt);
	StructuredDocumentTag authorSdt =
		new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
	authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
	row.AppendChild(authorSdt);
	doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");

```

Itu dia! Anda telah berhasil membuat tabel dengan bagian berulang yang dipetakan ke CustomXmlPart di dokumen Word Anda menggunakan Aspose.Words untuk .NET.