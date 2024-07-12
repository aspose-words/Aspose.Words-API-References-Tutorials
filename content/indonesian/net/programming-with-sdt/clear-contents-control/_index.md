---
title: Hapus Kontrol Isi
linktitle: Hapus Kontrol Isi
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menghapus konten kontrol di dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-sdt/clear-contents-control/
---

Tutorial ini menunjukkan cara menghapus konten SDT dalam dokumen Word menggunakan Aspose.Words untuk .NET. Menghapus konten SDT akan menghapus teks atau simpul anak apa pun dalam kontrol konten.

## Prasyarat
Untuk mengikuti tutorial ini, Anda harus memiliki yang berikut ini:

- Aspose.Words untuk perpustakaan .NET diinstal.
- Pengetahuan dasar tentang C# dan Pemrosesan Kata dengan dokumen Word.

## Langkah 1: Siapkan Direktori Dokumen
 Mulailah dengan menyiapkan jalur ke direktori dokumen Anda. Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori tempat dokumen Anda berada.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Muat Dokumen dan Dapatkan StructuredDocumentTag
 Muat dokumen Word menggunakan`Document` konstruktor, meneruskan jalur ke dokumen sebagai parameter. Kemudian, ambil yang diinginkan`StructuredDocumentTag`dari dokumen. Dalam contoh ini, kami berasumsi bahwa SDT adalah node anak pertama dalam dokumen.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Langkah 3: Hapus Isi StructuredDocumentTag
 Hapus isi SDT menggunakan`Clear` metode. Ini menghapus teks atau simpul anak apa pun dalam kontrol konten.

```csharp
sdt.Clear();
```

## Langkah 4: Simpan Dokumen
 Simpan dokumen yang dimodifikasi menggunakan`Save` metode. Berikan nama file yang diinginkan dengan ekstensi file yang sesuai. Dalam contoh ini, kami menyimpan dokumen sebagai "WorkingWithSdt.ClearContentsControl.doc".

```csharp
doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

### Contoh kode sumber untuk Clear Contents Control menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Clear();
	doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

Itu dia! Anda telah berhasil menghapus konten StructuredDocumentTag di dokumen Word Anda menggunakan Aspose.Words untuk .NET.