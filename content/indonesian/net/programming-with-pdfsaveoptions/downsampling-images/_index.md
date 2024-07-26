---
title: Kurangi Ukuran Dokumen PDF dengan Downsampling Gambar
linktitle: Kurangi Ukuran Dokumen PDF dengan Downsampling Gambar
second_title: API Pemrosesan Dokumen Aspose.Words
description: Kurangi ukuran dokumen PDF dengan melakukan downsampling gambar menggunakan Aspose.Words untuk .NET. Optimalkan PDF Anda untuk waktu unggah dan unduh yang lebih cepat.
type: docs
weight: 10
url: /id/net/programming-with-pdfsaveoptions/downsampling-images/
---
## Perkenalan

PDF adalah kebutuhan pokok di dunia digital, digunakan untuk segala hal mulai dari berbagi dokumen hingga membuat eBuku. Namun, ukurannya terkadang menjadi kendala, terutama ketika berhadapan dengan konten yang kaya gambar. Di sinilah downsampling gambar berperan. Dengan mengurangi resolusi gambar dalam PDF, Anda dapat mengurangi ukuran file secara signifikan tanpa terlalu mengurangi kualitasnya. Dalam tutorial ini, kita akan memandu langkah-langkah untuk mencapai hal ini menggunakan Aspose.Words untuk .NET.

## Prasyarat

Sebelum kita beralih ke kode, pastikan Anda memiliki semua yang Anda butuhkan:

1.  Aspose.Words untuk .NET: Pastikan Anda telah menginstal perpustakaan Aspose.Words. Jika belum, Anda dapat mendownloadnya[Di Sini](https://releases.aspose.com/words/net/).
2. Lingkungan Pengembangan: Lingkungan pengembangan .NET apa pun seperti Visual Studio.
3. Pengetahuan Dasar C#: Memahami dasar-dasar pemrograman C# akan sangat membantu.
4.  Contoh Dokumen: Dokumen Word (misalnya,`Rendering.docx`) dengan gambar untuk dikonversi ke PDF.

## Impor Namespace

Hal pertama yang pertama, Anda perlu mengimpor namespace yang diperlukan. Tambahkan ini di bagian atas file kode Anda:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Sekarang, mari kita bagi prosesnya menjadi langkah-langkah yang dapat dikelola.

## Langkah 1: Muat Dokumen

Langkah pertama adalah memuat dokumen Word Anda. Di sinilah Anda menentukan jalur ke direktori dokumen Anda.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Pada langkah ini, kami memuat dokumen Word dari direktori yang ditentukan. Pastikan untuk mengganti`"YOUR DOCUMENT DIRECTORY"`dengan jalur sebenarnya di mana dokumen Anda berada.

## Langkah 2: Konfigurasikan Opsi Downsampling

Selanjutnya, kita perlu mengkonfigurasi opsi downsampling. Ini melibatkan pengaturan resolusi dan ambang resolusi untuk gambar.

```csharp
// Kita dapat menetapkan ambang batas minimum untuk downsampling.
// Nilai ini akan mencegah gambar kedua dalam dokumen masukan didownsampling.
PdfSaveOptions saveOptions = new PdfSaveOptions
{
    DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
};
```

 Di sini, kami membuat contoh baru`PdfSaveOptions` dan mengatur`Resolution` hingga 36 DPI dan`ResolutionThreshold` hingga 128DPI. Artinya, gambar apa pun dengan resolusi lebih tinggi dari 128 DPI akan diturunkan sampelnya menjadi 36 DPI.

## Langkah 3: Simpan Dokumen sebagai PDF

Terakhir, kami menyimpan dokumen sebagai PDF dengan opsi yang dikonfigurasi.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);
```

Pada langkah terakhir ini, kami menyimpan dokumen sebagai PDF di direktori yang sama dengan opsi downsampling yang ditentukan.

## Kesimpulan

Dan itu dia! Anda telah berhasil mengurangi ukuran PDF Anda dengan menurunkan sampel gambar menggunakan Aspose.Words untuk .NET. Ini tidak hanya membuat PDF Anda lebih mudah dikelola tetapi juga membantu pengunggahan, pengunduhan, dan pengalaman menonton yang lebih cepat.

## FAQ

### Apa itu downsampling?
Downsampling adalah proses pengurangan resolusi gambar, yang membantu memperkecil ukuran file dokumen yang berisi gambar tersebut.

### Apakah downsampling akan mempengaruhi kualitas gambar?
Ya, downsampling akan menurunkan kualitas gambar. Namun, dampaknya bergantung pada tingkat pengurangan resolusi. Ini adalah trade-off antara ukuran file dan kualitas gambar.

### Bisakah saya memilih gambar mana yang akan didownsample?
 Ya, dengan mengatur`ResolutionThreshold`, Anda dapat mengontrol gambar mana yang diambil sampelnya berdasarkan resolusi aslinya.

### Apa resolusi ideal untuk downsampling?
Resolusi ideal bergantung pada kebutuhan spesifik Anda. Umumnya, 72 DPI digunakan untuk gambar web, sedangkan resolusi yang lebih tinggi digunakan untuk kualitas cetak.

### Apakah Aspose.Words untuk .NET gratis?
 Aspose.Words untuk .NET adalah produk komersial, tetapi Anda dapat mengunduh uji coba gratis[Di Sini](https://releases.aspose.com/) atau melamar a[izin sementara](https://purchase.aspose.com/temporary-license/).