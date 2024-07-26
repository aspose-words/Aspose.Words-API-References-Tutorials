---
title: Rentang Tag Dokumen Terstruktur Mulai Pemetaan Xml
linktitle: Rentang Tag Dokumen Terstruktur Mulai Pemetaan Xml
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyiapkan pemetaan XML untuk rentang tag dokumen terstruktur yang dimulai di dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-sdt/structured-document-tag-range-start-xml-mapping/
---

Tutorial ini menjelaskan cara menyiapkan pemetaan XML untuk rentang tag dokumen terstruktur yang dimulai dalam dokumen Word menggunakan Aspose.Words untuk .NET. Pemetaan XML memungkinkan Anda menampilkan bagian tertentu dari sumber data XML dalam kontrol konten.

## Prasyarat
Untuk mengikuti tutorial ini, Anda perlu memiliki yang berikut ini:

- Aspose.Words untuk perpustakaan .NET diinstal.
- Pengetahuan dasar tentang C# dan Pemrosesan Kata dengan dokumen Word.

## Langkah 1: Siapkan Direktori Dokumen
 Mulailah dengan menyiapkan jalur ke direktori dokumen Anda. Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori tempat dokumen Anda berada.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Muat Dokumen dan Buat Bagian XML
 Muat dokumen Word menggunakan`Document` konstruktor, meneruskan jalur ke dokumen sebagai parameter. Buat bagian XML yang berisi data yang ingin Anda tampilkan dalam tag dokumen terstruktur.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
```

## Langkah 3: Tetapkan Pemetaan XML untuk Tag Dokumen Terstruktur
Ambil rentang tag dokumen terstruktur mulai dari dokumen. Kemudian, atur pemetaan XML untuk tag dokumen terstruktur untuk menampilkan bagian tertentu dari bagian XML kustom menggunakan ekspresi XPath.

```csharp
StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
```

## Langkah 4: Simpan Dokumen
 Simpan dokumen yang dimodifikasi ke direktori yang ditentukan menggunakan`Save`metode. Berikan nama file yang diinginkan dengan ekstensi file yang sesuai. Dalam contoh ini, kami menyimpan dokumen sebagai "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

### Contoh kode sumber untuk Rentang Tag Dokumen Terstruktur Mulai Pemetaan Xml menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	// Buat bagian XML yang berisi data dan tambahkan ke koleksi CustomXmlPart dokumen.
	string xmlPartId = Guid.NewGuid().ToString("B");
	string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
	Console.WriteLine(Encoding.UTF8.GetString(xmlPart.Data));
	// Buat StructuredDocumentTag yang akan menampilkan konten CustomXmlPart kami di dokumen.
	StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
	// Jika kita menetapkan pemetaan untuk StructuredDocumentTag kita,
	// itu hanya akan menampilkan bagian dari CustomXmlPart yang ditunjuk oleh XPath.
	// XPath ini akan menunjuk ke konten elemen "<text>" kedua dari elemen "<root>" pertama dari CustomXmlPart kita.
	sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
	doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

Itu dia! Anda telah berhasil menyiapkan pemetaan XML untuk rentang tag dokumen terstruktur yang dimulai di dokumen Word Anda menggunakan Aspose.Words untuk .NET.