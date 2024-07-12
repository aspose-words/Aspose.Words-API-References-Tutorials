---
title: Status Kotak Centang Saat Ini
linktitle: Status Kotak Centang Saat Ini
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengambil dan mengatur status kontrol konten kotak centang saat ini di dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-sdt/current-state-of-check-box/
---

Tutorial ini menjelaskan cara mengambil dan mengatur status kontrol konten kotak centang saat ini di dokumen Word menggunakan Aspose.Words untuk .NET. Anda dapat mencentang atau menghapus centang pada kotak berdasarkan statusnya saat ini.

## Prasyarat
Untuk mengikuti tutorial ini, Anda harus memiliki yang berikut ini:

- Aspose.Words untuk perpustakaan .NET diinstal.
- Pengetahuan dasar tentang C# dan Pemrosesan Kata dengan dokumen Word.

## Langkah 1: Siapkan Direktori Dokumen
 Mulailah dengan menyiapkan jalur ke direktori dokumen Anda. Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori tempat dokumen Anda berada.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Muat Dokumen dan Ambil Kontrol Konten Kotak Centang
 Muat dokumen Word menggunakan`Document` konstruktor, meneruskan jalur ke dokumen sebagai parameter. Kemudian, ambil kontrol konten kotak centang yang diinginkan dari dokumen. Dalam contoh ini, kami berasumsi bahwa kotak centang adalah tag dokumen terstruktur pertama dalam dokumen.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdtCheckBox =
	(StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Langkah 3: Centang atau Hapus Centang Kotak Berdasarkan Statusnya Saat Ini
 Periksa apakah tag dokumen terstruktur yang diambil bertipe`SdtType.Checkbox` . Jika ya, atur`Checked` properti kontrol konten ke`true` untuk mencentang kotak. Jika tidak, Anda dapat membiarkannya tidak dicentang.

```csharp
if (sdtCheckBox.SdtType == SdtType.Checkbox)
	sdtCheckBox.Checked = true;
```

## Langkah 4: Simpan Dokumen
 Simpan dokumen yang dimodifikasi ke direktori yang ditentukan menggunakan`Save` metode. Berikan nama file yang diinginkan dengan ekstensi file yang sesuai. Dalam contoh ini, kami menyimpan dokumen sebagai "WorkingWithSdt.CurrentStateOfCheckBox.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

### Contoh kode sumber untuk Status Kotak Centang Saat Ini menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	// Dapatkan kontrol konten pertama dari dokumen.
	StructuredDocumentTag sdtCheckBox =
		(StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	if (sdtCheckBox.SdtType == SdtType.Checkbox)
		sdtCheckBox.Checked = true;
	doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

Itu dia! Anda telah berhasil mengambil dan mengatur status kontrol konten kotak centang saat ini di dokumen Word Anda menggunakan Aspose.Words untuk .NET.