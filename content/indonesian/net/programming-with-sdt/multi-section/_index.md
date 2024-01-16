---
title: Multi Bagian
linktitle: Multi Bagian
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengambil dan memproses tag dokumen terstruktur multi-bagian dalam dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-sdt/multi-section/
---

Tutorial ini menjelaskan cara bekerja dengan tag dokumen terstruktur multi-bagian dalam dokumen Word menggunakan Aspose.Words untuk .NET. Anda dapat mengambil dan memproses tag bagian yang ada di dokumen.

## Prasyarat
Untuk mengikuti tutorial ini, Anda harus memiliki yang berikut ini:

- Aspose.Words untuk perpustakaan .NET diinstal.
- Pengetahuan dasar tentang C# dan Pemrosesan Kata dengan dokumen Word.

## Langkah 1: Siapkan Direktori Dokumen
 Mulailah dengan menyiapkan jalur ke direktori dokumen Anda. Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori tempat dokumen Anda berada.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Muat Dokumen dan Ambil Tag Multi-Bagian
 Muat dokumen Word menggunakan`Document` konstruktor, meneruskan jalur ke dokumen sebagai parameter. Ambil semua node awal rentang tag dokumen terstruktur dalam dokumen menggunakan`GetChildNodes` metode.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
```

## Langkah 3: Proses Tag Multi-Bagian
Iterasi melalui kumpulan node awal rentang tag dokumen terstruktur. Dalam contoh ini, kita cukup mencetak judul setiap tag ke konsol. Anda dapat melakukan pemrosesan lebih lanjut berdasarkan kebutuhan Anda.

```csharp
foreach (StructuredDocumentTagRangeStart tag in tags)
    Console.WriteLine(tag.Title);
```

### Contoh kode sumber untuk Multi Bagian menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
	foreach (StructuredDocumentTagRangeStart tag in tags)
		Console.WriteLine(tag.Title);
```

Itu dia! Anda telah berhasil mengambil dan memproses tag dokumen terstruktur multi-bagian di dokumen Word Anda menggunakan Aspose.Words untuk .NET.