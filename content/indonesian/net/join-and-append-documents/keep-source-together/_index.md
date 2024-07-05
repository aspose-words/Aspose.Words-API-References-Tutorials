---
title: Pertahankan Sumber Bersama
linktitle: Pertahankan Sumber Bersama
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menggunakan Aspose.Words untuk .NET untuk menggabungkan dan menambahkan dokumen Word sekaligus menjaga konten sumber tetap bersama dengan dokumen tujuan.
type: docs
weight: 10
url: /id/net/join-and-append-documents/keep-source-together/
---

Tutorial ini akan memandu Anda melalui proses penggunaan fitur Keep Source Together di Aspose.Words untuk .NET. Fitur ini memungkinkan Anda untuk menggabungkan dan menambahkan beberapa dokumen Word sekaligus menjaga konten dokumen sumber tetap bersama dengan konten dokumen tujuan. 

## Prasyarat

Sebelum memulai, pastikan Anda memiliki hal berikut:

1. Aspose.Words untuk .NET diinstal. Anda dapat mendownloadnya dari situs Aspose atau menginstalnya melalui NuGet.
2. Visual Studio atau lingkungan pengembangan C# lainnya.

## Langkah 1: Inisialisasi Direktori Dokumen

 Pertama, Anda perlu menyetel jalur ke direktori dokumen Anda. Ubah nilai`dataDir` variabel ke jalur di mana dokumen Anda berada.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Muat Dokumen Sumber dan Tujuan

Selanjutnya, Anda perlu memuat dokumen sumber dan tujuan menggunakan Aspose.Words`Document` kelas. Perbarui nama file di`Document` konstruktor sesuai dengan nama dokumen Anda.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Langkah 3: Atur Dokumen Sumber agar Muncul Setelah Konten Dokumen Tujuan

 Untuk memastikan bahwa dokumen sumber muncul tepat setelah konten dokumen tujuan, Anda perlu mengaturnya`SectionStart` properti bagian pertama dalam dokumen sumber ke`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Langkah 4: Atur Pemformatan Paragraf "Simpan dengan Berikutnya" untuk Dokumen Sumber

 Untuk menyatukan paragraf-paragraf dalam dokumen sumber, Anda dapat mengulangi setiap paragraf dalam dokumen dan mengaturnya`KeepWithNext`properti ke`true`.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Langkah 5: Tambahkan Dokumen Sumber ke Dokumen Tujuan

 Sekarang, Anda dapat menambahkan dokumen sumber ke dokumen tujuan menggunakan`AppendDocument` metode`Document` kelas. Itu`ImportFormatMode.KeepSourceFormatting` parameter memastikan bahwa pemformatan sumber dipertahankan selama operasi penambahan.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Langkah 6: Simpan Dokumen Akhir

 Terakhir, simpan dokumen gabungan dengan fitur "Simpan Sumber Bersama" yang diaktifkan menggunakan`Save` metode`Document` kelas.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

### Contoh kode sumber untuk Keep Source Together menggunakan Aspose.Words untuk .NET 

Berikut kode sumber lengkap untuk fitur "Keep Source Together" di C# menggunakan Aspose.Words untuk .NET:


```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Atur dokumen sumber agar muncul tepat setelah konten dokumen tujuan.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

Itu dia! Anda telah berhasil mengimplementasikan fitur Keep Source Together menggunakan Aspose.Words untuk .NET. Dokumen akhir akan berisi konten yang digabungkan dengan paragraf dalam dokumen sumber yang disatukan.