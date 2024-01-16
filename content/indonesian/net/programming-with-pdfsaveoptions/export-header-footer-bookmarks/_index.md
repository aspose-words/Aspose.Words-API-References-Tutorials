---
title: Ekspor Bookmark Header Footer Dokumen Word ke Dokumen PDF
linktitle: Ekspor Bookmark Header Footer Dokumen Word ke Dokumen PDF
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk mengekspor bookmark header footer dokumen kata ke bookmark dokumen pdf dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-pdfsaveoptions/export-header-footer-bookmarks/
---

Artikel ini memberikan panduan langkah demi langkah tentang cara mengekspor bookmark header footer dokumen Word ke fitur dokumen pdf dengan Aspose.Words untuk .NET. Kami akan menjelaskan setiap bagian kode secara detail. Di akhir tutorial ini, Anda akan dapat memahami cara mengekspor bookmark dari header dan footer dokumen dan menghasilkan PDF dengan bookmark yang sesuai.

Sebelum memulai, pastikan Anda telah menginstal dan mengonfigurasi pustaka Aspose.Words untuk .NET di proyek Anda. Anda dapat menemukan perpustakaan dan petunjuk instalasi di situs web Aspose.

## Langkah 1: Tentukan direktori dokumen

 Untuk memulai, Anda perlu menentukan jalur ke direktori tempat dokumen Anda berada. Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Unggah dokumen

Selanjutnya, kita perlu memuat dokumen yang ingin kita proses. Dalam contoh ini, kami berasumsi bahwa dokumen tersebut bernama "Bookmark di header dan footer.docx" dan terletak di direktori dokumen yang ditentukan.

```csharp
Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");
```

## Langkah 3: Konfigurasikan opsi simpan sebagai PDF

 Untuk mengekspor bookmark header dan footer, kita perlu mengkonfigurasi`PdfSaveOptions` obyek. Dalam contoh ini, kami menetapkan tingkat kerangka bookmark default ke 1 dan mode ekspor bookmark header dan footer ke "Pertama".

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;
```

## Langkah 4: Simpan dokumen sebagai PDF dengan penanda header dan footer

Terakhir, kita dapat menyimpan dokumen dalam format PDF menggunakan opsi penyimpanan yang dikonfigurasi sebelumnya.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);
```

Itu saja ! Anda telah berhasil mengekspor penanda header dan footer dari dokumen dan menghasilkan PDF dengan penanda yang sesuai menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber untuk mengekspor bookmark header dan footer dengan Aspose.Words untuk .NET

```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
	saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);

```

## Kesimpulan

Dalam tutorial ini, kami menjelaskan cara mengekspor bookmark header dan footer dari dokumen Word ke dokumen PDF menggunakan Aspose.Words untuk .NET. Bookmark yang diekspor memungkinkan navigasi yang mudah dan referensi cepat ke header dan footer terkait dalam dokumen PDF yang dihasilkan. Ikuti langkah-langkah yang dijelaskan untuk mengekspor bookmark header dan footer dari dokumen dan menghasilkan PDF dengan bookmark yang sesuai menggunakan Aspose.Words untuk .NET. Pastikan untuk menentukan jalur yang benar ke dokumen Anda dan konfigurasikan opsi penyimpanan sesuai kebutuhan.

### Pertanyaan yang Sering Diajukan

### T: Apa yang dimaksud dengan mengekspor penanda header dan footer dari dokumen Word ke dokumen PDF?
A: Mengekspor bookmark header dan footer dari dokumen Word ke dokumen PDF adalah fitur untuk menyimpan dan menghasilkan bookmark dalam dokumen PDF dari header dan footer. footer dokumen Word asli. Hal ini memungkinkan pengguna dengan cepat dan mudah menavigasi dokumen PDF dengan menggunakan bookmark yang sesuai dengan header dan footer.

### T: Bagaimana cara menggunakan Aspose.Words untuk .NET untuk mengekspor penanda header dan footer dari dokumen Word ke dokumen PDF?
J: Untuk mengekspor penanda header dan footer dari dokumen Word ke dokumen PDF menggunakan Aspose.Words untuk .NET, ikuti langkah-langkah berikut:

 Atur jalur direktori tempat dokumen Anda berada dengan mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya dari direktori dokumen Anda.

 Muat dokumen yang ingin Anda proses menggunakan`Document` kelas dan tentukan jalur ke dokumen Word di direktori dokumen yang ditentukan.

 Konfigurasikan opsi simpan sebagai PDF dengan membuat instance dari`PdfSaveOptions` kelas dan mengatur opsi penanda header dan footer yang sesuai.

 Simpan dokumen dalam format PDF menggunakan`Save` metode`Document` kelas yang menentukan jalur dan opsi penyimpanan.

### T: Apa manfaat mengekspor penanda header dan footer ke dokumen PDF?
J: Keuntungan mengekspor bookmark header dan footer ke dalam dokumen PDF adalah:

Navigasi Mudah: Bookmark memungkinkan pengguna menavigasi dokumen PDF dengan mudah dengan merujuk ke header dan footer tertentu.

Referensi Cepat: Bookmark memungkinkan pengguna dengan cepat menemukan bagian yang relevan dari dokumen PDF berdasarkan header dan footer.