---
title: Kurangi Ukuran File PDF dengan Tidak Menyematkan Font Inti
linktitle: Kurangi Ukuran File PDF dengan Tidak Menyematkan Font Inti
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara Mengurangi Ukuran File PDF dengan Tidak Menyematkan Font Inti saat mengonversi dokumen Word ke PDF dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-pdfsaveoptions/avoid-embedding-core-fonts/
---

Dalam tutorial ini, kami akan memandu Anda melalui langkah-langkah cara mengurangi ukuran file PDF dengan tidak menyematkan font inti dengan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda mengontrol apakah font dasar seperti Arial, Times New Roman, dll. harus disematkan dalam PDF saat mengonversi dokumen Word. Ikuti langkah-langkah di bawah ini:

## Langkah 1: Memuat dokumen

Mulailah dengan mengunggah dokumen Word yang ingin Anda konversi ke PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Pastikan untuk menentukan jalur yang benar ke dokumen Word Anda.

## Langkah 2: Tetapkan Opsi Konversi PDF

Buat instance kelas PdfSaveOptions dan aktifkan penghindaran penyematan font dasar:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
```

Opsi ini mengontrol apakah font dasar harus disematkan dalam PDF atau tidak.

## Langkah 3: Konversi Dokumen ke PDF

 Menggunakan`Save` metode untuk mengonversi dokumen Word ke PDF dengan menentukan opsi konversi:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);
```

Pastikan untuk menentukan jalur yang benar untuk menyimpan PDF yang dikonversi.

### Contoh kode sumber untuk Hindari Menyematkan Font Inti menggunakan Aspose.Words untuk .NET

Berikut adalah kode sumber lengkap untuk menggunakan fitur tersebut guna menghindari penyematan font inti dengan Aspose.Words untuk .NET:

```csharp

	// Jalur ke direktori dokumen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// PDF keluaran tidak akan disematkan dengan font inti seperti Arial, Times New Roman, dll.
	PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);

```

Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah mengontrol apakah font dasar harus disematkan dalam PDF saat mengonversi dokumen Word dengan Aspose.Words untuk .NET.


## Kesimpulan

Dalam tutorial ini, kami menjelaskan cara memperkecil ukuran file PDF dengan tidak menyematkan font dasar dengan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda mengontrol apakah font dasar harus disematkan dalam PDF saat mengonversi dokumen Word. Dengan mengikuti langkah-langkah yang diuraikan, Anda dapat dengan mudah mengontrol penyematan atau non-penyematan font dasar, yang dapat membantu mengurangi ukuran file PDF dan memastikan kompatibilitas yang lebih baik serta tampilan dokumen yang konsisten di berbagai perangkat dan platform. Jangan lupa untuk mempertimbangkan konsekuensi dari tidak menyematkan font dasar dan bereksperimen untuk memastikan bahwa dokumen ditampilkan seperti yang diharapkan.

### Pertanyaan yang Sering Diajukan

#### T: Apa yang dimaksud dengan opsi untuk tidak menyematkan font dasar dalam file PDF dan mengapa ini penting?
J: Opsi untuk tidak menyematkan font dasar dalam file PDF mengontrol apakah font dasar seperti Arial, Times New Roman, dll. harus disematkan dalam PDF saat mengonversi dokumen Word. Hal ini penting untuk mengurangi ukuran file PDF dengan menghindari penyertaan font yang umum tersedia pada sistem pembaca PDF. Ini juga dapat membantu memastikan kompatibilitas yang lebih baik dan tampilan dokumen PDF yang konsisten di berbagai perangkat dan platform.

#### T: Bagaimana cara mengonfigurasi Aspose.Words untuk .NET agar tidak menyematkan font dasar dalam file PDF?
J: Untuk mengonfigurasi Aspose.Words untuk .NET agar tidak menyematkan font inti dalam file PDF, ikuti langkah-langkah berikut:

 Atur jalur direktori tempat dokumen Anda berada dengan mengganti`"YOUR DOCUMENTS DIRECTORY"` dengan jalur sebenarnya dari direktori dokumen Anda.

 Muat dokumen Word yang ingin Anda konversi ke PDF menggunakan`Document` kelas dan jalur dokumen yang ditentukan.

 Buat sebuah instance dari`PdfSaveOptions` kelas dan atur`UseCoreFonts`properti ke`true`. Ini akan menghindari penyematan font dasar dalam file PDF yang dihasilkan.

 Menggunakan`Save` metode`Document` keberatan untuk menyimpan dokumen dalam format PDF dengan menentukan opsi konversi yang dikonfigurasi sebelumnya.

#### T: Apa keuntungan jika tidak menyematkan font dasar dalam file PDF?
J: Keuntungan tidak menyematkan font dasar dalam file PDF adalah:

Pengurangan ukuran file PDF: Dengan menghindari penyematan font yang umum tersedia seperti Arial, Times New Roman, dll., ukuran file PDF dapat diperkecil, sehingga lebih mudah untuk menyimpan, berbagi, dan mentransfer file.

Kompatibilitas yang lebih baik: Dengan menggunakan font dasar yang umum tersedia pada sistem pembaca PDF, Anda memastikan kompatibilitas dan tampilan dokumen yang lebih baik di berbagai perangkat dan platform.

#### T: Apa konsekuensi jika tidak menyematkan font dasar dalam file PDF?
A: Akibat tidak menyematkan font dasar pada file PDF adalah sebagai berikut:

Tampilan berbeda: Jika font dasar tidak tersedia di sistem tempat PDF dibuka, font pengganti akan digunakan, yang mungkin menghasilkan tampilan berbeda dari yang diharapkan.

Masalah keterbacaan: Font pengganti yang digunakan mungkin tidak terbaca seperti font asli, sehingga dapat mempengaruhi keterbacaan dokumen.