---
title: Tulis Semua Aturan Css Dalam Satu File
linktitle: Tulis Semua Aturan Css Dalam Satu File
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengonversi dokumen Word ke HTML menggunakan Aspose.Words untuk .NET dengan semua aturan CSS dalam satu file untuk kode yang lebih bersih dan pemeliharaan yang lebih mudah.
type: docs
weight: 10
url: /id/net/programming-with-htmlfixedsaveoptions/write-all-css-rules-in-single-file/
---
## Perkenalan

Pernahkah Anda menemukan diri Anda terjerat dalam jaringan aturan CSS yang tersebar di mana-mana saat mengonversi dokumen Word ke HTML? Jangan khawatir! Hari ini, kita mendalami fitur menarik dari Aspose.Words untuk .NET yang memungkinkan Anda menulis semua aturan CSS dalam satu file. Ini tidak hanya merapikan kode Anda tetapi juga membuat hidup Anda jauh lebih mudah. Bersiaplah, dan mari kita mulai perjalanan menuju keluaran HTML yang lebih bersih dan efisien!

## Prasyarat

Sebelum kita mendalami seluk beluknya, mari kita urutkan dulu. Inilah yang Anda perlukan untuk memulai:

1.  Aspose.Words untuk .NET: Pastikan Anda memiliki perpustakaan Aspose.Words untuk .NET. Jika Anda belum memilikinya, Anda bisa[unduh di sini](https://releases.aspose.com/words/net/).
2. Lingkungan Pengembangan .NET: Anda memerlukan pengaturan lingkungan pengembangan .NET di mesin Anda. Visual Studio adalah pilihan yang populer.
3. Pengetahuan Dasar C#: Pemahaman dasar tentang pemrograman C# akan sangat membantu.
4. Dokumen Word: Siapkan dokumen Word (.docx) yang ingin Anda konversi.

## Impor Namespace

Hal pertama yang pertama, mari impor namespace yang diperlukan dalam proyek C# Anda. Ini akan memungkinkan kita mengakses fungsi Aspose.Words dengan mudah.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Baiklah, mari kita bagi prosesnya menjadi langkah-langkah yang mudah diikuti. Setiap langkah akan memandu Anda melalui bagian tertentu dari proses untuk memastikan semuanya berjalan lancar.

## Langkah 1: Siapkan Direktori Dokumen Anda

Pertama, kita perlu menentukan jalur ke direktori dokumen Anda. Di sinilah dokumen Word Anda disimpan dan HTML yang dikonversi akan disimpan.

```csharp
// Jalur akses ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Muat Dokumen Word

 Selanjutnya, kita memuat dokumen Word yang ingin Anda ubah menjadi HTML. Ini dilakukan dengan menggunakan`Document` kelas dari perpustakaan Aspose.Words.

```csharp
// Muat dokumen Word
Document doc = new Document(dataDir + "Document.docx");
```

## Langkah 3: Konfigurasikan Opsi Penyimpanan HTML

 Sekarang, kita perlu mengkonfigurasi opsi penyimpanan HTML. Secara khusus, kami ingin mengaktifkan fitur yang menulis semua aturan CSS ke dalam satu file. Hal ini dicapai dengan mengatur`SaveFontFaceCssSeparately`properti ke`false`.

```csharp
// Konfigurasikan opsi pencadangan dengan fitur "Tulis semua aturan CSS dalam satu file".
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions 
{ 
    SaveFontFaceCssSeparately = false 
};
```

## Langkah 4: Konversi Dokumen ke HTML Tetap

Terakhir, kami menyimpan dokumen sebagai file HTML menggunakan opsi penyimpanan yang dikonfigurasi. Langkah ini memastikan bahwa semua aturan CSS ditulis dalam satu file.

```csharp
//Ubah dokumen menjadi HTML tetap
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

## Kesimpulan

Dan itu dia! Hanya dengan beberapa baris kode, Anda telah berhasil mengonversi dokumen Word Anda ke HTML dengan semua aturan CSS tersusun rapi dalam satu file. Metode ini tidak hanya menyederhanakan pengelolaan CSS Anda tetapi juga meningkatkan kemudahan pemeliharaan dokumen HTML Anda. Jadi, lain kali Anda ditugaskan untuk mengonversi dokumen Word, Anda tahu persis bagaimana menjaga semuanya tetap rapi!

## FAQ

### Mengapa saya harus menggunakan satu file CSS untuk keluaran HTML saya?
Menggunakan satu file CSS menyederhanakan pengelolaan dan pemeliharaan gaya Anda. Itu membuat HTML Anda lebih bersih dan efisien.

### Bisakah saya memisahkan aturan CSS tampilan font jika diperlukan?
 Ya, dengan pengaturan`SaveFontFaceCssSeparately` ke`true`, Anda dapat memisahkan aturan CSS tampilan font ke dalam file lain.

### Apakah Aspose.Words untuk .NET gratis untuk digunakan?
 Aspose.Words menawarkan uji coba gratis yang Anda bisa[unduh di sini](https://releases.aspose.com/) . Untuk penggunaan berkelanjutan, pertimbangkan untuk membeli lisensi[Di Sini](https://purchase.aspose.com/buy).

### Format lain apa yang dapat dikonversi ke Aspose.Words untuk .NET?
Aspose.Words untuk .NET mendukung berbagai format termasuk PDF, TXT, dan format gambar seperti JPEG dan PNG.

### Di mana saya dapat menemukan lebih banyak sumber daya tentang Aspose.Words untuk .NET?
 Lihat[dokumentasi](https://reference.aspose.com/words/net/) untuk panduan komprehensif dan referensi API.
