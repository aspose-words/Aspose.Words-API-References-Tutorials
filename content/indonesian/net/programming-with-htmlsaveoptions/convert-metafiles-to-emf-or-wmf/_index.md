---
title: Konversi Metafile Ke Emf Atau Wmf
linktitle: Konversi Metafile Ke Emf Atau Wmf
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk mengonversi metafile ke format EMF atau WMF saat mengonversi dokumen ke HTML dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-htmlsaveoptions/convert-metafiles-to-emf-or-wmf/
---
## Perkenalan

Selamat datang di penyelaman mendalam lainnya ke dunia Aspose.Words untuk .NET. Hari ini, kami menangani trik yang bagus: mengonversi gambar SVG ke format EMF atau WMF di dokumen Word Anda. Ini mungkin terdengar agak teknis, tapi jangan khawatir. Di akhir tutorial ini, Anda akan menjadi ahli dalam hal itu. Baik Anda seorang pengembang berpengalaman atau baru memulai Aspose.Words untuk .NET, panduan ini akan memandu Anda melalui semua yang perlu Anda ketahui, langkah demi langkah.

## Prasyarat

Sebelum kita mendalami kodenya, pastikan semuanya sudah siap. Inilah yang Anda butuhkan:

1.  Aspose.Words untuk .NET Library: Pastikan Anda memiliki versi terbaru. Jika Anda tidak memilikinya, Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/words/net/).
2. .NET Framework: Pastikan Anda telah menginstal .NET Framework di mesin Anda.
3. Lingkungan Pengembangan: IDE seperti Visual Studio akan membuat hidup Anda lebih mudah.
4. Pengetahuan Dasar C#: Anda tidak perlu menjadi ahli, tetapi pemahaman dasar akan membantu.

Punya segalanya? Besar! Mari kita mulai.

## Impor Namespace

Hal pertama yang pertama, kita perlu mengimpor namespace yang diperlukan. Ini penting karena memberitahu program kita di mana menemukan kelas dan metode yang akan kita gunakan.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Namespace ini mencakup semuanya mulai dari fungsi sistem dasar hingga fungsionalitas Aspose.Words spesifik yang kita perlukan untuk tutorial ini.

## Langkah 1: Siapkan Direktori Dokumen Anda

Mari kita mulai dengan menentukan jalur ke direktori dokumen Anda. Di sinilah dokumen Word Anda akan disimpan setelah kami mengonversi metafile.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya tempat Anda ingin menyimpan dokumen Anda.

## Langkah 2: Buat String HTML dengan SVG

Selanjutnya, kita memerlukan string HTML yang berisi gambar SVG yang ingin kita konversi. Berikut ini contoh sederhananya:

```csharp
string html = 
    @"<html>
        <svg xmlns='http://www.w3.org/2000/svg' width='500' height='40' viewBox='0 0 500 40'>
            <text x='0' y='35' font-family='Verdana' font-size='35'>Hello world!</text>
        </svg>
    </html>";
```

Cuplikan HTML ini menyertakan SVG dasar yang bertuliskan "Halo dunia!".

## Langkah 3: Muat HTML dengan Opsi ConvertSvgToEmf

 Sekarang, kami menggunakan`HtmlLoadOptions` untuk menentukan bagaimana kita ingin menangani gambar SVG dalam HTML. Pengaturan`ConvertSvgToEmf` ke`true` memastikan bahwa gambar SVG dikonversi ke format EMF.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { ConvertSvgToEmf = true };
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);
```

 Cuplikan kode ini membuat yang baru`Document` objek dengan memuat string HTML ke dalamnya dengan opsi pemuatan yang ditentukan.

## Langkah 4: Tetapkan HtmlSaveOptions untuk Format Metafile

 Untuk menyimpan dokumen dengan format metafile yang benar, kami menggunakan`HtmlSaveOptions` . Di sini, kami menetapkan`MetafileFormat` ke`HtmlMetafileFormat.Png` , namun Anda dapat mengubahnya menjadi`Emf` atau`Wmf` tergantung pada kebutuhan Anda.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Png };
```

## Langkah 5: Simpan Dokumen

Terakhir, kami menyimpan dokumen menggunakan opsi penyimpanan yang ditentukan.

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToPng.html", saveOptions);
```

Ini menyimpan dokumen di direktori yang ditentukan dengan format metafile yang dikonversi seperti yang ditentukan.

## Kesimpulan

Dan itu dia! Dengan mengikuti langkah-langkah ini, Anda telah berhasil mengonversi gambar SVG ke format EMF atau WMF di dokumen Word Anda menggunakan Aspose.Words untuk .NET. Metode ini berguna untuk memastikan kompatibilitas dan menjaga integritas visual dokumen Anda di berbagai platform. Selamat membuat kode!

## FAQ

### Bisakah saya mengonversi format gambar lain menggunakan metode ini?
Ya, Anda dapat mengonversi berbagai format gambar dengan menyesuaikan opsi muat dan simpan.

### Apakah perlu menggunakan versi .NET Framework tertentu?
Aspose.Words untuk .NET mendukung beberapa versi .NET Framework, namun selalu merupakan ide bagus untuk menggunakan versi terbaru untuk kompatibilitas dan fitur terbaik.

### Apa keuntungan mengubah SVG ke EMF atau WMF?
Mengonversi SVG ke EMF atau WMF memastikan grafik vektor dipertahankan dan ditampilkan dengan benar di lingkungan yang mungkin tidak sepenuhnya mendukung SVG.

### Bisakah saya mengotomatiskan proses ini untuk banyak dokumen?
Sangat! Anda dapat mengulang beberapa file HTML, menerapkan proses yang sama untuk mengotomatiskan konversi untuk pemrosesan batch.

### Di mana saya dapat menemukan lebih banyak sumber daya dan dukungan untuk Aspose.Words untuk .NET?
 Anda dapat menemukan dokumentasi yang komprehensif[Di Sini](https://reference.aspose.com/words/net/) dan dapatkan dukungan dari komunitas Aspose[Di Sini](https://forum.aspose.com/c/words/8).