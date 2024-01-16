---
title: Atur Gaya Kontrol Konten
linktitle: Atur Gaya Kontrol Konten
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengatur gaya kontrol konten dalam dokumen Word menggunakan Aspose.Words untuk .NET, dengan menerapkan pemformatan yang konsisten.
type: docs
weight: 10
url: /id/net/programming-with-sdt/set-content-control-style/
---

Tutorial ini menjelaskan cara mengatur gaya kontrol konten dalam dokumen Word menggunakan Aspose.Words untuk .NET. Anda dapat menerapkan gaya yang telah ditentukan sebelumnya atau gaya khusus ke kontrol konten untuk pemformatan yang konsisten.

## Prasyarat
Untuk mengikuti tutorial ini, Anda harus memiliki yang berikut ini:

- Aspose.Words untuk perpustakaan .NET diinstal.
- Pengetahuan dasar tentang C# dan Pemrosesan Kata dengan dokumen Word.

## Langkah 1: Siapkan Direktori Dokumen
 Mulailah dengan menyiapkan jalur ke direktori dokumen Anda. Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori tempat dokumen Anda berada.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Muat Dokumen dan Ambil Kontrol Konten
 Muat dokumen Word menggunakan`Document` konstruktor, meneruskan jalur ke dokumen sebagai parameter. Ambil kontrol konten yang diinginkan dari dokumen. Dalam contoh ini, kami berasumsi bahwa kontrol konten adalah tag dokumen terstruktur pertama dalam dokumen.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Langkah 3: Ambil Gaya dan Terapkan ke Kontrol Konten
 Ambil gaya yang diinginkan dari koleksi gaya dokumen. Dalam contoh ini, kita mengambil gaya "Kutipan" dengan menggunakan`StyleIdentifier.Quote` . Kemudian, tetapkan gaya yang diambil ke`Style` properti tag dokumen terstruktur.

```csharp
Style style = doc.Styles[StyleIdentifier.Quote];
sdt.Style = style;
```

## Langkah 4: Simpan Dokumen
 Simpan dokumen yang dimodifikasi ke direktori yang ditentukan menggunakan`Save` metode. Berikan nama file yang diinginkan dengan ekstensi file yang sesuai. Dalam contoh ini, kami menyimpan dokumen sebagai "WorkingWithSdt.SetContentControlStyle.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

### Contoh kode sumber untuk Mengatur Gaya Kontrol Konten menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	Style style = doc.Styles[StyleIdentifier.Quote];
	sdt.Style = style;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

Itu dia! Anda telah berhasil mengatur gaya kontrol konten di dokumen Word Anda menggunakan Aspose.Words untuk .NET.