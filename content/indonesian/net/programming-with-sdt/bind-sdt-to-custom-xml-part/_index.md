---
title: Ikat SDT ke Bagian Xml Khusus
linktitle: Ikat SDT ke Bagian Xml Khusus
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengikat SDT ke Bagian Xml Kustom menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-sdt/bind-sdt-to-custom-xml-part/
---

Tutorial ini menunjukkan cara mengikat Tag Dokumen Terstruktur (SDT) ke Bagian Xml Kustom menggunakan Aspose.Words untuk .NET. SDT memungkinkan Anda menambahkan kontrol konten terstruktur ke dokumen Word, dan CustomXmlParts menyediakan cara untuk menyimpan data XML khusus yang terkait dengan dokumen tersebut.

## Prasyarat
Untuk mengikuti tutorial ini, Anda harus memiliki yang berikut ini:

- Aspose.Words untuk perpustakaan .NET diinstal.
- Pengetahuan dasar tentang C# dan XML.

## Langkah 1: Siapkan Direktori Dokumen
 Mulailah dengan menyiapkan jalur ke direktori dokumen Anda. Mengganti`"YOUR DOCUMENT DIRECTORY"`dengan jalur sebenarnya ke direktori tempat Anda ingin menyimpan dokumen.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Buat Dokumen dan CustomXmlPart
 Buat instance baru dari`Document` kelas dan a`CustomXmlPart` untuk menyimpan data XML khusus. XML khusus harus dalam format XML yang valid. Dalam contoh ini, kami menggunakan string XML sederhana`<root><text>Hello, World!</text></root>`.

```csharp
Document doc = new Document();
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
```

## Langkah 3: Tambahkan StructuredDocumentTag (SDT) ke Dokumen
 Tambah sebuah`StructuredDocumentTag` ke dokumen untuk berfungsi sebagai kontrol konten. Tentukan`SdtType` sebagai`PlainText` dan itu`MarkupLevel` sebagai`Block` untuk membuat SDT tingkat blok.

```csharp
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
doc.FirstSection.Body.AppendChild(sdt);
```

## Langkah 4: Atur Pemetaan XML untuk SDT
 Petakan SDT ke`CustomXmlPart` dengan menggunakan`SetMapping` metode`XmlMapping` Properti. Tentukan`CustomXmlPart` , ekspresi XPath untuk menemukan node XML yang diinginkan, dan awalan namespace jika diperlukan. Dalam contoh ini, kami memetakan SDT ke`/root[1]/text[1]`.

```csharp
sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
```

## Langkah 5: Simpan Dokumen
 Simpan dokumen yang dimodifikasi ke direktori yang ditentukan menggunakan`Save` metode. Berikan nama file yang diinginkan dengan ekstensi file yang sesuai. Dalam contoh ini, kami menyimpan dokumen sebagai "WorkingWithSdt.BindSDTtoCustomXmlPart.doc".

```csharp
doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

### Contoh kode sumber untuk Bind Sd Tto Custom Xml Part menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	CustomXmlPart xmlPart =
		doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
	doc.FirstSection.Body.AppendChild(sdt);
	sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
	doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

Itu dia! Anda telah berhasil mengikat SDT ke CustomXmlPart di dokumen Word Anda menggunakan Aspose.Words untuk .NET.