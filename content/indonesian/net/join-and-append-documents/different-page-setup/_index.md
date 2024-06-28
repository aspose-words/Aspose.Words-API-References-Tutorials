---
title: Pengaturan Halaman Berbeda
linktitle: Pengaturan Halaman Berbeda
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menambahkan dokumen dengan pengaturan pengaturan halaman berbeda menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/join-and-append-documents/different-page-setup/
---

Tutorial ini menjelaskan cara menggunakan Aspose.Words untuk .NET untuk menambahkan dokumen dengan pengaturan pengaturan halaman berbeda ke dokumen lain. Kode sumber yang disediakan menunjukkan cara menyiapkan pengaturan halaman berbeda untuk dokumen sumber dan tujuan serta memastikan kelanjutan dan penomoran yang tepat.

## Langkah 1: Siapkan proyek

Pastikan Anda memiliki prasyarat berikut:

-  Aspose.Words untuk perpustakaan .NET diinstal. Anda dapat mengunduhnya dari[Aspose.Releases]https://releases.aspose.com/words/net/ atau gunakan manajer paket NuGet untuk menginstalnya.
- Jalur direktori dokumen tempat dokumen sumber dan tujuan berada.

## Langkah 2: Buka dokumen sumber dan tujuan

 Buka dokumen sumber dan tujuan menggunakan`Document` konstruktor kelas. Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Langkah 3: Siapkan pengaturan halaman untuk dokumen sumber

 Sesuaikan pengaturan pengaturan halaman dokumen sumber untuk memastikan kelanjutan dan penomoran yang tepat. Dalam contoh ini, kami menyetel bagian mulai ke`SectionStart.Continuous`dan mulai ulang penomoran halaman. Kami juga memastikan bahwa lebar, tinggi, dan orientasi halaman sesuai dengan bagian terakhir dokumen tujuan.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
```

## Langkah 4: Ubah format paragraf

 Untuk mempertahankan pemformatan yang benar, ulangi seluruh paragraf dalam dokumen sumber dan atur`KeepWithNext`properti ke`true`. Hal ini memastikan bahwa paragraf tetap menyatu selama proses penambahan.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Langkah 5: Tambahkan dokumen sumber ke dokumen tujuan

 Menggunakan`AppendDocument` metode dokumen tujuan untuk menambahkan dokumen sumber yang dimodifikasi ke dokumen tujuan, mempertahankan format sumber.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Langkah 6: Simpan dokumen tujuan

Terakhir, simpan dokumen tujuan yang telah dimodifikasi menggunakan`Save` metode`Document` obyek.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```

Ini menyelesaikan implementasi penambahan dokumen dengan pengaturan pengaturan halaman berbeda menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber untuk Pengaturan Halaman Berbeda menggunakan Aspose.Words untuk .NET 

```csharp
	// Jalur ke direktori dokumen Anda
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Atur dokumen sumber agar dilanjutkan tepat setelah akhir dokumen tujuan.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Mulai ulang penomoran halaman di awal dokumen sumber.
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
	//Untuk memastikan hal ini tidak terjadi ketika dokumen sumber memiliki pengaturan pengaturan halaman yang berbeda, pastikan
	// pengaturannya identik antara bagian terakhir dokumen tujuan.
	// Jika ada bagian lanjutan yang mengikuti dokumen sumber,
	// ini perlu diulangi untuk bagian tersebut.
	srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
	srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
	srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
	// Ulangi semua bagian dalam dokumen sumber.
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```