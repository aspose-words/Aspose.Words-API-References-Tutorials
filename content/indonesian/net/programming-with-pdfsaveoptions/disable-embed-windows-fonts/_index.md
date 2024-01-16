---
title: Kurangi Ukuran PDF dengan Menonaktifkan Font Tersemat
linktitle: Kurangi Ukuran PDF dengan Menonaktifkan Font Tersemat
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara memperkecil ukuran PDF dengan menonaktifkan penyematan font Windows saat mengonversi dokumen ke PDF dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-pdfsaveoptions/disable-embed-windows-fonts/
---

Dalam tutorial ini, kami akan memandu Anda melalui langkah-langkah untuk mengurangi ukuran PDF dengan menonaktifkan penyematan font Windows dalam dokumen PDF dengan Aspose.Words untuk .NET. Dengan menonaktifkan penyematan font, Anda dapat mengurangi ukuran file PDF yang dihasilkan. Ikuti langkah-langkah di bawah ini:

## Langkah 1: Memuat dokumen

Mulailah dengan mengunggah dokumen yang ingin Anda konversi ke PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Pastikan untuk menentukan jalur yang benar ke dokumen Anda.

## Langkah 2: Tetapkan opsi penyimpanan PDF

Buat instance kelas PdfSaveOptions dan tentukan cara menyematkan font:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
```

Opsi ini memungkinkan Anda untuk menonaktifkan integrasi font Windows dalam file PDF yang dihasilkan.

## Langkah 3: Konversi Dokumen ke PDF

 Menggunakan`Save` metode untuk mengonversi dokumen ke PDF dengan menentukan opsi konversi:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);
```

Pastikan untuk menentukan jalur yang benar untuk menyimpan PDF yang dikonversi.

### Contoh kode sumber untuk Nonaktifkan Sematan Font Windows menggunakan Aspose.Words untuk .NET

Berikut adalah kode sumber lengkap untuk menonaktifkan penyematan font Windows dalam dokumen PDF dengan Aspose.Words untuk .NET:

```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// PDF keluaran akan disimpan tanpa menyematkan font windows standar.
	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);

```
Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah menonaktifkan penyematan font Windows dalam dokumen PDF dengan Aspose.Words untuk .NET.


## Kesimpulan

Dalam tutorial ini, kita mempelajari cara memperkecil ukuran file PDF dengan menonaktifkan penyematan font Windows menggunakan Aspose.Words untuk .NET. Dengan menonaktifkan penyematan font, Anda dapat mengurangi ukuran file PDF yang dihasilkan, sehingga lebih mudah untuk menyimpan, berbagi, dan mentransfer file. Namun, penting untuk dicatat bahwa menonaktifkan penyematan font Windows dapat menyebabkan perubahan tampilan dan format pada dokumen PDF akhir. Pastikan untuk mempertimbangkan konsekuensi ini saat menggunakan fitur ini. Jangan ragu untuk menjelajahi lebih banyak fitur Aspose.Words untuk .NET untuk mengoptimalkan pembuatan file PDF Anda.

### Pertanyaan yang Sering Diajukan

#### T: Apa yang dimaksud dengan menonaktifkan penyematan font Windows di dokumen PDF dan mengapa ini penting?
J: Menonaktifkan penyematan font Windows dalam dokumen PDF adalah proses mencegah font Windows disertakan dalam file PDF yang dihasilkan. Ini mengurangi ukuran file PDF dengan menghapus data font Windows yang tertanam. Hal ini penting untuk mengurangi ukuran file PDF, sehingga lebih mudah disimpan, dibagikan, dan ditransfer lebih cepat.

#### T: Bagaimana cara menonaktifkan penyematan font Windows dalam dokumen PDF menggunakan Aspose.Words untuk .NET?
J: Untuk menonaktifkan penyematan font Windows dalam dokumen PDF menggunakan Aspose.Words untuk .NET, ikuti langkah-langkah berikut:

 Muat dokumen yang ingin Anda konversi ke PDF menggunakan`Document` kelas dan jalur dokumen.

 Buat sebuah instance dari`PdfSaveOptions` kelas dan atur`FontEmbeddingMode`properti ke`PdfFontEmbeddingMode.EmbedNone`. Ini menonaktifkan penyematan font Windows di file PDF yang dihasilkan.

 Menggunakan`Save` metode`Document` objek untuk mengonversi dokumen ke PDF dengan menentukan opsi konversi yang dikonfigurasi sebelumnya.

#### T: Apa manfaat menonaktifkan penyematan font Windows di dokumen PDF?
J: Manfaat menonaktifkan penyematan font Windows di dokumen PDF adalah:

Mengurangi ukuran file PDF: Dengan menonaktifkan penyematan font Windows, data font Windows yang tertanam akan dihapus, sehingga mengurangi ukuran file PDF yang dihasilkan.

Penyimpanan lebih mudah: File PDF yang lebih kecil lebih mudah disimpan, disimpan, dan ditransfer.

Berbagi dan mentransfer lebih cepat: File PDF yang lebih kecil dapat dibagikan dan ditransfer lebih cepat, sehingga menghemat waktu dan sumber daya.

#### T: Apa konsekuensi dari menonaktifkan penyematan font Windows di dokumen PDF?
J: Menonaktifkan penyematan font Windows dalam dokumen PDF dapat menimbulkan konsekuensi seperti:

Hilangnya tampilan dan pemformatan: Jika font Windows yang ditentukan dalam dokumen tidak tersedia di sistem tempat PDF dibuka, font pengganti akan digunakan, yang dapat mengakibatkan tampilan dan pemformatan salah. bentuknya berbeda dari yang diharapkan.

Masalah keterbacaan: Jika font pengganti yang digunakan tidak dapat dibaca seperti font aslinya, hal ini dapat mempengaruhi keterbacaan teks dalam dokumen PDF.