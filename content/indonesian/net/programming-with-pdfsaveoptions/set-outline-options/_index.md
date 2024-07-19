---
title: Tetapkan Opsi Garis Besar dalam Dokumen PDF
linktitle: Tetapkan Opsi Garis Besar dalam Dokumen PDF
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk mengatur opsi kerangka dalam dokumen PDF dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-pdfsaveoptions/set-outline-options/
---

Artikel ini memberikan panduan langkah demi langkah tentang cara menggunakan opsi kerangka set untuk fitur ukuran metafile dengan Aspose.Words untuk .NET. Kami akan menjelaskan setiap bagian kode secara detail. Di akhir tutorial ini, Anda akan dapat memahami cara mengatur opsi kerangka dalam dokumen dan menghasilkan PDF dengan opsi kerangka yang sesuai.

Sebelum memulai, pastikan Anda telah menginstal dan mengonfigurasi pustaka Aspose.Words untuk .NET di proyek Anda. Anda dapat menemukan perpustakaan dan petunjuk instalasi di situs web Aspose.

## Langkah 1: Tentukan direktori dokumen

 Untuk memulai, Anda perlu menentukan jalur ke direktori tempat dokumen Anda berada. Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Unggah dokumen

Selanjutnya, kita perlu memuat dokumen yang ingin kita proses. Dalam contoh ini, kami berasumsi bahwa dokumen tersebut bernama "Rendering.docx" dan terletak di direktori dokumen yang ditentukan.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Langkah 3: Konfigurasikan opsi simpan sebagai PDF dengan opsi paket

Untuk mengatur opsi kerangka dalam PDF yang dihasilkan, kita perlu mengkonfigurasi`PdfSaveOptions` obyek. Kita dapat mengatur jumlah level outline heading (`HeadingsOutlineLevels`) dan jumlah tingkat garis besar yang diperluas (`ExpandedOutlineLevels`).

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;
```

## Langkah 4: Simpan dokumen sebagai PDF dengan opsi garis besar

Terakhir, kita dapat menyimpan dokumen dalam format PDF menggunakan opsi penyimpanan yang dikonfigurasi sebelumnya.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
```

Itu saja ! Anda telah berhasil mengatur opsi kerangka dalam dokumen dan menghasilkan PDF dengan opsi kerangka yang sesuai menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber untuk mengatur opsi paket ke ukuran metafile dengan Aspose.Words untuk .NET


```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
	saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
   
```

## Kesimpulan

Dalam tutorial ini, kami menjelaskan cara mengatur opsi kerangka dalam dokumen PDF menggunakan Aspose.Words untuk .NET. Dengan menggunakan langkah-langkah yang dijelaskan, Anda dapat dengan mudah menentukan tingkat judul dan garis besar dalam dokumen Anda dan menghasilkan file PDF dengan opsi garis besar yang sesuai. Nikmati manfaat opsi kerangka untuk meningkatkan struktur dan navigasi dalam dokumen PDF Anda menggunakan Aspose.Words untuk .NET.

### Pertanyaan yang Sering Diajukan

#### T: Apa yang dimaksud dengan opsi kerangka dalam dokumen PDF?
J: Opsi garis besar dalam dokumen PDF mengacu pada struktur hierarki konten dokumen. Ini memungkinkan Anda membuat daftar isi interaktif dan memfasilitasi navigasi dalam dokumen. Opsi kerangka menentukan tingkat judul dan subjudul untuk disertakan dalam kerangka dan tingkat detail untuk ditampilkan dalam kerangka yang dihasilkan.

#### T: Bagaimana cara mengatur opsi kerangka dalam dokumen PDF menggunakan Aspose.Words untuk .NET?
J: Untuk mengatur opsi kerangka dalam dokumen PDF menggunakan Aspose.Words untuk .NET, ikuti langkah-langkah berikut:

 Atur jalur direktori tempat dokumen Anda berada dengan mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya dari direktori dokumen Anda.

 Muat dokumen yang ingin Anda konversi ke PDF menggunakan`Document` kelas dan tentukan jalur ke dokumen di direktori dokumen yang ditentukan.

 Konfigurasikan opsi simpan sebagai PDF dengan membuat instance dari`PdfSaveOptions` kelas dan menggunakan`OutlineOptions` properti untuk mengatur opsi garis besar. Anda dapat menentukan jumlah tingkat judul yang akan disertakan dalam kerangka menggunakan`HeadingsOutlineLevels` properti dan jumlah tingkat garis yang diperluas menggunakan`ExpandedOutlineLevels` Properti.

 Simpan dokumen dalam format PDF menggunakan`Save` metode`Document` kelas yang menentukan jalur dan opsi penyimpanan.

#### T: Apa saja pilihan paket dalam dokumen PDF?
J: Opsi kerangka dalam dokumen PDF memungkinkan Anda membuat struktur hierarki konten, yang memudahkan navigasi dokumen dan mengakses berbagai bagian. Hal ini memungkinkan pengguna untuk dengan cepat melompat ke bagian tertentu dari dokumen dengan mengklik entri di daftar isi atau kerangka. Opsi garis besar juga meningkatkan pengalaman membaca dengan memberikan gambaran umum tentang struktur dokumen secara keseluruhan.
