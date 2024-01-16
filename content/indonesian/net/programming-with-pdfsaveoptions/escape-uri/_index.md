---
title: Escape URI dalam Dokumen PDF
linktitle: Escape URI dalam Dokumen PDF
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah Cara Escape URI dalam Dokumen PDF dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-pdfsaveoptions/escape-uri/
---

Artikel ini memberikan panduan langkah demi langkah tentang cara Escape URI dalam Dokumen PDF dengan Aspose.Words untuk .NET. Kami akan menjelaskan setiap bagian kode secara detail. Di akhir tutorial ini, Anda akan dapat memahami cara menyisipkan hyperlink dengan escape Uri ke dalam dokumen.

Sebelum memulai, pastikan Anda telah menginstal dan mengonfigurasi pustaka Aspose.Words untuk .NET di proyek Anda. Anda dapat menemukan perpustakaan dan petunjuk instalasi di situs web Aspose.

## Langkah 1: Tentukan direktori dokumen

 Untuk memulai, Anda perlu menentukan jalur ke direktori tempat dokumen Anda berada. Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Buat dokumen dan DocumentBuilder

 Selanjutnya, kita perlu membuat yang baru`Document` objek dan a`DocumentBuilder` objek untuk membuat dokumen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 3: Sisipkan hyperlink dengan escape Uri

 Menggunakan`InsertHyperlink` metode`DocumentBuilder` objek untuk menyisipkan hyperlink ke dalam dokumen. Uri harus di-escape menggunakan`Uri.EscapeUriString` berfungsi untuk menghindari kesalahan format.

```csharp
builder.InsertHyperlink("Testlink",
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), salah);
builder. Writen();
builder.InsertHyperlink(Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"),
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), salah);
```

## Langkah 4: Simpan dokumen sebagai PDF

 Terakhir, kita dapat menyimpan dokumen sebagai PDF menggunakan`Save` metode`Document` obyek. Tentukan nama file keluaran.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");
```

Itu saja ! Anda telah berhasil menyisipkan hyperlink dengan escape Uri dalam dokumen menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber untuk pelolosan Uri dengan Aspose.Words untuk .NET


```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.InsertHyperlink("Testlink", 
		"https://www.google.com/search?q=%2Fthe%20test", salah);
	builder.Writeln();
	builder.InsertHyperlink("https:// www.google.com/search?q=%2Fthe%20test",
		"https://www.google.com/search?q=%2Fthe%20test", salah);

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");    
  
```

## Kesimpulan

Dalam tutorial ini, kita membahas cara keluar dari URI dalam dokumen PDF menggunakan Aspose.Words untuk .NET. Dengan keluar dari URI, Anda dapat menghindari kesalahan pemformatan dan memastikan bahwa hyperlink diinterpretasikan dan ditampilkan dengan benar dalam dokumen PDF. Ikuti langkah-langkah yang dijelaskan untuk menyisipkan hyperlink dengan escape URI ke dalam dokumen PDF Anda. Pastikan untuk melarikan diri.

### Pertanyaan yang Sering Diajukan

#### T: Apa yang dimaksud dengan escape URI dalam dokumen PDF dan mengapa ini penting?
J: Escape URI dalam dokumen PDF mengacu pada metode mengubah karakter khusus dalam URL menjadi urutan escape untuk menghindari kesalahan format. Hal ini penting karena karakter khusus dalam URL dapat mengganggu struktur URL dan menyebabkan salah tafsir atau rendering yang salah. Dengan menghilangkan karakter khusus, kami menjamin bahwa URL diinterpretasikan dan ditampilkan dengan benar dalam dokumen PDF.

#### T: Bagaimana cara menggunakan Aspose.Words untuk .NET untuk keluar dari URI dalam dokumen PDF?
J: Untuk keluar dari URI dalam dokumen PDF menggunakan Aspose.Words untuk .NET, ikuti langkah-langkah berikut:

 Atur jalur direktori tempat dokumen Anda berada dengan mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya dari direktori dokumen Anda.

 Buat instance baru dari`Document` kelas dan a`DocumentBuilder` objek untuk membuat dokumen.

 Menggunakan`InsertHyperlink` metode`DocumentBuilder` objek untuk menyisipkan hyperlink ke dalam dokumen. Pastikan untuk keluar dari URI menggunakan`Uri.EscapeUriString` berfungsi untuk menghindari kesalahan format.

 Menggunakan`Save` metode`Document` objek untuk menyimpan dokumen dalam format PDF dengan menentukan nama file keluaran.

#### T: Apa keuntungan melakukan pelolosan URI dalam dokumen PDF?
J: Manfaat pelolosan URI dalam dokumen PDF adalah:

Pencegahan kesalahan format: Pelarian URI membantu mencegah kesalahan format yang disebabkan oleh karakter khusus dalam URL, memastikan bahwa URL diinterpretasikan dengan benar dan ditampilkan dalam dokumen PDF.

Kompatibilitas dengan pembaca PDF: URI yang lolos umumnya didukung dengan baik oleh pembaca PDF, memastikan kompatibilitas yang lebih baik dan pengalaman pengguna yang konsisten.

#### T: Karakter khusus apa yang harus di-escape dalam URI?
 A: Karakter khusus yang harus di-escape dalam URI adalah: spasi, <, >, ", #, %, {, },|, \, ^, ~, [, ], `, ;, /, ?, :, @, =, &, $, +, ,, [, ], and !.