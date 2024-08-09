---
title: Membuat Tabel Bagian Berulang yang Dipetakan ke Bagian Xml Kustom
linktitle: Membuat Tabel Bagian Berulang yang Dipetakan ke Bagian Xml Kustom
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara membuat tabel dengan bagian berulang yang dipetakan ke CustomXmlPart di dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-sdt/creating-table-repeating-section-mapped-to-custom-xml-part/
---
## Perkenalan

Dalam tutorial ini, kita akan memandu proses pembuatan tabel dengan bagian berulang yang dipetakan ke bagian XML kustom menggunakan Aspose.Words untuk .NET. Hal ini sangat berguna untuk menghasilkan dokumen secara dinamis berdasarkan data terstruktur.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal berikut:
1.  Aspose.Words untuk perpustakaan .NET diinstal. Anda dapat mengunduhnya dari[Asumsikan situs web](https://releases.aspose.com/words/net/).
2. Pemahaman dasar tentang C# dan XML.

## Impor Namespace

Pastikan untuk menyertakan namespace yang diperlukan dalam proyek Anda:

```csharp
using Aspose.Words;
using Aspose.Words.Markup;
using Aspose.Words.Tables;
```

## Langkah 1: Inisialisasi Dokumen dan DocumentBuilder

 Pertama, buat dokumen baru dan inisialisasi a`DocumentBuilder`:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 2: Tambahkan Bagian XML Khusus

Tambahkan bagian XML khusus ke dokumen. XML ini berisi data yang ingin kita petakan ke tabel kita:

```csharp
CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
    "<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
    "<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
    "<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
```

## Langkah 3: Buat Struktur Tabel

 Selanjutnya, gunakan`DocumentBuilder` untuk membuat header tabel:

```csharp
Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Title");
builder.InsertCell();
builder.Write("Author");
builder.EndRow();
builder.EndTable();
```

## Langkah 4: Buat Bagian Berulang

 Buat sebuah`StructuredDocumentTag` (SDT) untuk bagian berulang dan memetakannya ke data XML:

```csharp
StructuredDocumentTag repeatingSectionSdt = new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
table.AppendChild(repeatingSectionSdt);
```

## Langkah 5: Buat Item Bagian Berulang

Buat SDT untuk item bagian berulang dan tambahkan ke bagian berulang:

```csharp
StructuredDocumentTag repeatingSectionItemSdt = new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
Row row = new Row(doc);
repeatingSectionItemSdt.AppendChild(row);
```

## Langkah 6: Petakan Data XML ke Sel Tabel

Buat SDT untuk judul dan penulis, petakan ke data XML, dan tambahkan ke baris:

```csharp
StructuredDocumentTag titleSdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
row.AppendChild(titleSdt);

StructuredDocumentTag authorSdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
row.AppendChild(authorSdt);
```

## Langkah 7: Simpan Dokumen

Terakhir, simpan dokumen ke direktori yang ditentukan:

```csharp
doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");
```

## Kesimpulan

Dengan mengikuti langkah-langkah ini, Anda telah berhasil membuat tabel dengan bagian berulang yang dipetakan ke bagian XML kustom menggunakan Aspose.Words untuk .NET. Hal ini memungkinkan pembuatan konten dinamis berdasarkan data terstruktur, menjadikan pembuatan dokumen lebih fleksibel dan canggih.

## FAQ

### Apa itu StructuredDocumentTag (SDT)?
SDT, juga dikenal sebagai kontrol konten, adalah wilayah terbatas dalam dokumen yang digunakan untuk memuat data terstruktur.

### Bisakah saya menggunakan tipe data lain di bagian XML khusus?
Ya, Anda dapat menyusun bagian XML khusus Anda dengan tipe data apa pun dan memetakannya sesuai dengan itu.

### Bagaimana cara menambahkan lebih banyak baris ke bagian berulang?
Bagian berulang secara otomatis mereplikasi struktur baris untuk setiap item di jalur XML yang dipetakan.