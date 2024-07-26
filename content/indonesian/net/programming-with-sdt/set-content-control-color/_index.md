---
title: Atur Warna Kontrol Konten
linktitle: Atur Warna Kontrol Konten
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengatur warna kontrol konten di dokumen Word menggunakan Aspose.Words untuk .NET, dan menyesuaikan tampilannya.
type: docs
weight: 10
url: /id/net/programming-with-sdt/set-content-control-color/
---

Tutorial ini menjelaskan cara mengatur warna kontrol konten di dokumen Word menggunakan Aspose.Words untuk .NET. Anda dapat menyesuaikan tampilan kontrol konten dengan mengubah warnanya.

## Prasyarat
Untuk mengikuti tutorial ini, Anda perlu memiliki yang berikut ini:

- Aspose.Words untuk perpustakaan .NET diinstal.
- Pengetahuan dasar tentang C# dan Pemrosesan Kata dengan dokumen Word.

## Langkah 1: Siapkan Direktori Dokumen
 Mulailah dengan menyiapkan jalur ke direktori dokumen Anda. Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori tempat dokumen Anda berada.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Muat Dokumen dan Ambil Kontrol Konten
 Muat dokumen Word menggunakan`Document`konstruktor, meneruskan jalur ke dokumen sebagai parameter. Ambil kontrol konten yang diinginkan dari dokumen. Dalam contoh ini, kami berasumsi bahwa kontrol konten adalah tag dokumen terstruktur pertama dalam dokumen.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Langkah 3: Atur Warna Kontrol Konten
 Atur warna kontrol konten dengan menetapkan a`Color` nilai ke`Color` properti tag dokumen terstruktur. Dalam contoh ini, kita mengatur warnanya menjadi merah.

```csharp
sdt.Color = Color.Red;
```

## Langkah 4: Simpan Dokumen
 Simpan dokumen yang dimodifikasi ke direktori yang ditentukan menggunakan`Save` metode. Berikan nama file yang diinginkan dengan ekstensi file yang sesuai. Dalam contoh ini, kami menyimpan dokumen sebagai "WorkingWithSdt.SetContentControlColor.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

### Contoh kode sumber untuk Mengatur Warna Kontrol Konten menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Color = Color.Red;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

Itu dia! Anda telah berhasil mengatur warna kontrol konten di dokumen Word Anda menggunakan Aspose.Words untuk .NET.