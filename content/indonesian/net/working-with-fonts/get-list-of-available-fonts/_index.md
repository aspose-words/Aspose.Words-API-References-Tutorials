---
title: Dapatkan Daftar Font yang Tersedia
linktitle: Dapatkan Daftar Font yang Tersedia
second_title: API Pemrosesan Dokumen Aspose.Words
description: Temukan cara mendapatkan daftar font yang tersedia menggunakan Aspose.Words untuk .NET dalam tutorial langkah demi langkah yang mendetail ini. Tingkatkan keterampilan manajemen font Anda.
type: docs
weight: 10
url: /id/net/working-with-fonts/get-list-of-available-fonts/
---
## Perkenalan

Pernahkah Anda kesulitan mengelola font di dokumen Word Anda? Jika Anda seorang pengembang .NET, Aspose.Words for .NET hadir untuk menyelamatkan Anda! Pustaka canggih ini tidak hanya membantu Anda membuat dan memanipulasi dokumen Word secara terprogram tetapi juga menawarkan kemampuan manajemen font yang ekstensif. Dalam panduan ini, kami akan memandu Anda melalui tutorial langkah demi langkah tentang cara mendapatkan daftar font yang tersedia menggunakan Aspose.Words untuk .NET. Kami akan membaginya menjadi langkah-langkah yang mudah dipahami untuk memastikan Anda dapat mengikutinya dengan mudah. Jadi, mari selami dan jadikan pengelolaan font menjadi mudah!

## Prasyarat

Sebelum kita mulai, ada beberapa hal yang Anda perlukan:

-  Aspose.Words for .NET: Pastikan Anda telah menginstal perpustakaan Aspose.Words for .NET. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/words/net/).
- Visual Studio: Contoh ini menggunakan Visual Studio sebagai lingkungan pengembangan.
- .NET Framework: Pastikan Anda telah menginstal .NET Framework di mesin Anda.
- Direktori Dokumen: Jalur direktori tempat dokumen Anda disimpan.

## Impor Namespace

Pertama, impor namespace yang diperlukan ke dalam proyek Anda:

```csharp
using System;
using System.Collections.Generic;
using Aspose.Words;
using Aspose.Words.Fonts;
```

## Langkah 1: Inisialisasi Pengaturan Font

Langkah pertama adalah menginisialisasi pengaturan font. Ini akan memungkinkan Anda mengelola sumber font untuk dokumen Anda.

```csharp
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
```

- FontSettings: Kelas ini digunakan untuk menentukan pengaturan substitusi font dan sumber font.
- fontSources: Kami membuat daftar sumber font yang ada dari pengaturan font saat ini.

## Langkah 2: Tentukan Direktori Dokumen

Selanjutnya, tentukan jalur ke direktori dokumen Anda. Di sinilah Aspose.Words akan mencari font.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

-  dataDir: Variabel string ini menyimpan jalur ke direktori tempat font Anda berada. Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya.

## Langkah 3: Tambahkan Folder Font Kustom

Sekarang, tambahkan folder baru sumber untuk menginstruksikan Aspose.Words mencari font di folder ini.

```csharp
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
```

- FolderFontSource: Kelas ini mewakili sumber font folder. Parameter kedua (`true`) menunjukkan apakah akan mencari font secara rekursif di subfolder.

## Langkah 4: Perbarui Sumber Font

Tambahkan folder font khusus ke daftar sumber font yang ada dan perbarui pengaturan font.

```csharp
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
```

- fontSources.Add(folderFontSource): Menambahkan folder font khusus ke sumber font yang ada.
- updateFontSources: Mengonversi daftar sumber font menjadi array.

## Langkah 5: Ambil dan Tampilkan Font

Terakhir, ambil font yang tersedia dan tampilkan detailnya.

```csharp
foreach (PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
    Console.WriteLine("FontFamilyName : " + fontInfo.FontFamilyName);
    Console.WriteLine("FullFontName  : " + fontInfo.FullFontName);
    Console.WriteLine("Version  : " + fontInfo.Version);
    Console.WriteLine("FilePath : " + fontInfo.FilePath);
}
```

- GetAvailableFonts(): Mengambil daftar font yang tersedia dari sumber font pertama dalam daftar yang diperbarui.
-  fontInfo: Sebuah contoh dari`PhysicalFontInfo` berisi detail tentang setiap font.

## Kesimpulan

Selamat! Anda telah berhasil mengambil daftar font yang tersedia menggunakan Aspose.Words untuk .NET. Tutorial ini telah memandu Anda melalui setiap langkah, mulai dari menginisialisasi pengaturan font hingga menampilkan detail font. Dengan pengetahuan ini, kini Anda dapat mengelola font di dokumen Word Anda dengan mudah. Ingat, Aspose.Words for .NET adalah alat canggih yang dapat meningkatkan kemampuan pemrosesan dokumen Anda secara signifikan. Jadi, lanjutkan dan jelajahi lebih banyak fitur untuk membuat proses pengembangan Anda lebih efisien.

## FAQ

### Bisakah saya menggunakan Aspose.Words untuk .NET dengan kerangka .NET lainnya?
Ya, Aspose.Words untuk .NET kompatibel dengan berbagai kerangka .NET termasuk .NET Core dan .NET 5+.

### Bagaimana cara menginstal Aspose.Words untuk .NET?
Anda dapat menginstalnya melalui NuGet Package Manager di Visual Studio dengan mencari "Aspose.Words".

### Apakah mungkin untuk menambahkan beberapa folder font khusus?
 Ya, Anda dapat menambahkan beberapa folder font khusus dengan membuat beberapa folder`FolderFontSource` contoh dan menambahkannya ke daftar sumber font.

### Bisakah saya mengambil detail font dari sumber font tertentu?
 Ya, Anda dapat mengambil detail font dari sumber font mana pun dengan menentukan indeks sumber font di`updatedFontSources` susunan.

### Apakah Aspose.Words untuk .NET mendukung substitusi font?
Ya, ini mendukung substitusi font untuk memastikan bahwa teks ditampilkan dengan benar meskipun font asli tidak tersedia.