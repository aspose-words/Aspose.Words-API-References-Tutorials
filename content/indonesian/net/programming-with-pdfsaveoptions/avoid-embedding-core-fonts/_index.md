---
title: Kurangi Ukuran File PDF dengan Tidak Menyematkan Font Inti
linktitle: Kurangi Ukuran File PDF dengan Tidak Menyematkan Font Inti
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengurangi ukuran file PDF dengan tidak menyematkan font inti menggunakan Aspose.Words untuk .NET. Ikuti panduan langkah demi langkah kami untuk mengoptimalkan PDF Anda.
type: docs
weight: 10
url: /id/net/programming-with-pdfsaveoptions/avoid-embedding-core-fonts/
---
## Perkenalan

Pernahkah Anda menggaruk-garuk kepala dan bertanya-tanya mengapa file PDF Anda begitu besar? Ya, kamu tidak sendirian. Salah satu penyebab umum adalah menyematkan font inti seperti Arial dan Times New Roman. Untungnya, Aspose.Words untuk .NET memiliki cara yang bagus untuk mengatasi masalah ini. Dalam tutorial ini, saya akan menunjukkan cara memperkecil ukuran file PDF Anda dengan menghindari penyematan font inti ini. Mari selami!

## Prasyarat

Sebelum kita memulai perjalanan yang mengasyikkan ini, pastikan Anda memiliki semua yang Anda butuhkan. Berikut daftar periksa singkatnya:

-  Aspose.Words for .NET: Pastikan Anda telah menginstal Aspose.Words for .NET. Jika Anda belum memilikinya, Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/words/net/).
- Lingkungan Pengembangan: Anda memerlukan lingkungan pengembangan seperti Visual Studio.
- Dokumen Word: Kami akan menggunakan dokumen Word (misalnya, "Rendering.docx") untuk tutorial ini.
- Pengetahuan Dasar C#: Pemahaman dasar tentang C# akan membantu Anda mengikutinya.

Baiklah, sekarang kita sudah siap, mari masuk ke seluk beluknya!

## Impor Namespace

Hal pertama yang pertama, mari impor namespace yang diperlukan. Langkah ini memastikan kita memiliki akses ke semua fungsi Aspose.Words yang kita perlukan.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

## Langkah 1: Inisialisasi Direktori Dokumen Anda

Sebelum kita mulai memanipulasi dokumen kita, kita perlu menentukan direktori dimana dokumen kita disimpan. Ini penting untuk mengakses file.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya di mana dokumen Word Anda berada.

## Langkah 2: Muat Dokumen Word

Selanjutnya, kita perlu memuat dokumen Word yang ingin kita konversi ke PDF. Dalam contoh ini, kami menggunakan dokumen bernama "Rendering.docx".

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

Baris kode ini memuat dokumen ke dalam memori, siap untuk diproses lebih lanjut.

## Langkah 3: Konfigurasikan Opsi Penyimpanan PDF

Sekarang sampai pada bagian ajaibnya! Kami akan mengonfigurasi opsi penyimpanan PDF untuk menghindari penyematan font inti. Ini adalah langkah kunci yang membantu mengurangi ukuran file PDF.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
    UseCoreFonts = true
};
```

 Pengaturan`UseCoreFonts` ke`true` memastikan bahwa font inti seperti Arial dan Times New Roman tidak tertanam dalam PDF, sehingga mengurangi ukuran file secara signifikan.

## Langkah 4: Simpan Dokumen sebagai PDF

Terakhir, kami menyimpan dokumen Word sebagai PDF menggunakan opsi penyimpanan yang dikonfigurasi. Langkah ini menghasilkan file PDF tanpa menyematkan font inti.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);
```

Dan itu dia! File PDF Anda sekarang disimpan di direktori yang ditentukan tanpa font inti yang besar.

## Kesimpulan

Mengurangi ukuran file PDF sangatlah mudah dengan Aspose.Words untuk .NET. Dengan menghindari penyematan font inti, Anda dapat mengurangi ukuran file secara signifikan, sehingga lebih mudah untuk berbagi dan menyimpan dokumen Anda. Saya harap tutorial ini bermanfaat dan memberi Anda pemahaman yang jelas tentang prosesnya. Ingat, perubahan kecil dapat membuat perbedaan besar!

## FAQ

### Mengapa saya harus menghindari penyematan font inti dalam PDF?
Menghindari penyematan font inti akan mengurangi ukuran file, sehingga lebih mudah untuk dibagikan dan disimpan.

### Apakah saya masih dapat melihat PDF dengan benar tanpa font inti yang disematkan?
Ya, font inti seperti Arial dan Times New Roman umumnya tersedia di sebagian besar sistem.

### Bagaimana jika saya perlu menyematkan font khusus?
 Anda dapat menyesuaikannya`PdfSaveOptions`untuk menyematkan font tertentu sesuai kebutuhan.

### Apakah Aspose.Words untuk .NET gratis untuk digunakan?
 Aspose.Words untuk .NET memerlukan lisensi. Anda bisa mendapatkan uji coba gratis[Di Sini](https://releases.aspose.com/).

### Di mana saya dapat menemukan dokumentasi lebih lanjut tentang Aspose.Words untuk .NET?
 Anda dapat menemukan dokumentasi terperinci[Di Sini](https://reference.aspose.com/words/net/).