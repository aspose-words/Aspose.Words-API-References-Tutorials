---
title: Kurangi Ukuran PDF dengan Skala Font Wmf Ke Ukuran Metafile
linktitle: Kurangi Ukuran PDF dengan Skala Font Wmf Ke Ukuran Metafile
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk memperkecil ukuran pdf dengan skala font wmf ke ukuran metafile saat mengonversi ke PDF dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-pdfsaveoptions/scale-wmf-fonts-to-metafile-size/
---

Artikel ini memberikan panduan langkah demi langkah tentang cara memperkecil ukuran pdf dengan fitur skala font wmf ke ukuran metafile dengan Aspose.Words untuk .NET. Kami akan menjelaskan setiap bagian kode secara detail. Di akhir tutorial ini, Anda akan dapat memahami cara mengaktifkan atau menonaktifkan penskalaan font WMF saat mengonversi ke PDF.

Sebelum memulai, pastikan Anda telah menginstal dan mengonfigurasi pustaka Aspose.Words untuk .NET di proyek Anda. Anda dapat menemukan perpustakaan dan petunjuk instalasi di situs web Aspose.

## Langkah 1: Tentukan direktori dokumen

 Untuk memulai, Anda perlu menentukan jalur ke direktori tempat dokumen Anda berada. Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Unggah dokumen

Selanjutnya, kita perlu memuat dokumen yang ingin kita proses. Dalam contoh ini, kami berasumsi bahwa dokumen tersebut bernama "WMF dengan text.docx" dan terletak di direktori dokumen yang ditentukan.

```csharp
Document doc = new Document(dataDir + "WMF with text.docx");
```

## Langkah 3: Konfigurasikan opsi rendering metafile

 Untuk mengaktifkan atau menonaktifkan penskalaan font WMF ke ukuran metafile, kita perlu mengkonfigurasi`MetafileRenderingOptions` obyek. Dalam contoh ini, kami menonaktifkan penskalaan font dengan mengatur`ScaleWmfFontsToMetafileSize`properti ke`false`.

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     ScaleWmfFontsToMetafileSize=false
};
```

## Langkah 4: Konfigurasikan opsi simpan sebagai PDF dengan opsi rendering metafile

Terakhir, kita dapat mengonfigurasi opsi simpan ke PDF menggunakan opsi rendering metafile yang dikonfigurasi sebelumnya.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };
```

## Langkah 5: Simpan Dokumen sebagai PDF dengan Opsi Rendering Metafile

Simpan dokumen dalam format PDF menggunakan opsi penyimpanan yang dikonfigurasi sebelumnya.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
```

Itu saja ! Anda telah berhasil mengaktifkan atau menonaktifkan penskalaan font WMF ke ukuran metafile saat mengonversi

dokumen PDF menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber untuk menskalakan font WMF ke ukuran metafile dengan Aspose.Words untuk .NET

```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with text.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		ScaleWmfFontsToMetafileSize = false
	};

	//Jika Aspose.Words tidak dapat merender beberapa rekaman metafile ke grafik vektor dengan benar
	// lalu Aspose.Words merender metafile ini menjadi bitmap.
	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
	
        
```

## Kesimpulan

Dalam tutorial ini, kami menjelaskan cara mengaktifkan atau menonaktifkan pengubahan ukuran font WMF ke ukuran metafile dalam dokumen PDF menggunakan Aspose.Words untuk .NET. Dengan mengikuti langkah-langkah yang dijelaskan, Anda dapat dengan mudah mengontrol apakah font WMF harus diubah ukurannya agar sesuai dengan ukuran metafile saat mengonversi ke dokumen PDF. Ini dapat membantu Anda mengurangi ukuran file PDF yang dihasilkan dan meningkatkan kinerja rendering. Pastikan untuk menentukan jalur yang benar ke dokumen Anda dan konfigurasikan opsi rendering metafile sesuai kebutuhan.

### Pertanyaan yang Sering Diajukan

#### T: Apa yang dimaksud dengan mengubah ukuran font WMF menjadi ukuran metafile dalam dokumen PDF?
J: Mengubah ukuran font WMF ke ukuran metafile dalam dokumen PDF adalah fitur yang mengontrol apakah font WMF harus diskalakan agar sesuai dengan ukuran metafile saat mengonversi ke dokumen PDF. Saat fitur ini diaktifkan, font WMF akan diskalakan agar sesuai dengan ukuran metafile, yang dapat mengurangi ukuran dokumen PDF yang dihasilkan.

#### T: Bagaimana cara menggunakan Aspose.Words untuk .NET untuk mengaktifkan atau menonaktifkan pengubahan ukuran font WMF menjadi ukuran metafile dalam dokumen PDF?
J: Untuk mengaktifkan atau menonaktifkan pengubahan ukuran font WMF ke ukuran metafile dalam dokumen PDF menggunakan Aspose.Words untuk .NET, ikuti langkah-langkah berikut:

 Atur jalur direktori tempat dokumen Anda berada dengan mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya dari direktori dokumen Anda.

 Muat dokumen yang ingin Anda proses menggunakan`Document` kelas dan tentukan jalur ke dokumen Word di direktori dokumen yang ditentukan.

 Konfigurasikan opsi rendering metafile dengan membuat instance dari`MetafileRenderingOptions` kelas dan pengaturan`ScaleWmfFontsToMetafileSize`properti ke`true` untuk mengaktifkan penskalaan font WMF ke ukuran metafile, atau ke`false` untuk menonaktifkan fitur ini.

 Konfigurasikan opsi simpan sebagai PDF dengan membuat instance dari`PdfSaveOptions` kelas dan menggunakan opsi rendering metafile yang dikonfigurasi sebelumnya.

 Simpan dokumen dalam format PDF menggunakan`Save` metode`Document` kelas yang menentukan jalur dan opsi penyimpanan.

#### T: Apa manfaat mengubah ukuran font WMF menjadi ukuran metafile dalam dokumen PDF?
A: Keuntungan mengubah ukuran font WMF ke ukuran metafile dalam dokumen PDF adalah:

Pengurangan ukuran file PDF: Mengubah ukuran font WMF ke ukuran metafile dapat mengurangi ukuran dokumen PDF yang dihasilkan dengan menyesuaikan ukuran font dengan kebutuhan metafile.

Peningkatan kinerja: Dengan menyesuaikan ukuran font WMF dengan dimensi metafile, rendering dokumen PDF bisa lebih cepat dan efisien.