---
title: Setel Instans Default Folder Font
linktitle: Setel Instans Default Folder Font
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengatur folder font untuk instans default di Aspose.Words untuk .NET dengan tutorial langkah demi langkah ini. Sesuaikan dokumen Word Anda dengan mudah.
type: docs
weight: 10
url: /id/net/working-with-fonts/set-fonts-folders-default-instance/
---
## Perkenalan

Hai, rekan pembuat kode! Jika Anda bekerja dengan dokumen Word di .NET, Anda mungkin tahu pentingnya memiliki font yang tepat. Hari ini, kita mempelajari cara mengatur folder font untuk instans default menggunakan Aspose.Words untuk .NET. Bayangkan memiliki semua font khusus di ujung jari Anda, membuat dokumen Anda terlihat persis seperti yang Anda bayangkan. Kedengarannya bagus, bukan? Mari kita mulai!

## Prasyarat

Sebelum kita mendalami detailnya, pastikan Anda memiliki semua yang Anda butuhkan:
-  Aspose.Words untuk .NET: Pastikan Anda telah menginstal perpustakaan. Jika tidak, Anda bisa[unduh di sini](https://releases.aspose.com/words/net/).
- Lingkungan Pengembangan: Visual Studio atau IDE lain yang kompatibel dengan .NET.
- Pengetahuan Dasar C#: Anda harus terbiasa dengan pemrograman C#.
- Folder Font: Direktori yang berisi font khusus Anda.

## Impor Namespace

Hal pertama yang pertama, mari impor namespace yang diperlukan. Ini membantu dalam mengakses kelas dan metode yang diperlukan untuk mengatur folder font.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fonts;
```

Mari kita bagi prosesnya menjadi langkah-langkah sederhana dan mudah dicerna.

## Langkah 1: Tentukan Direktori Data

Setiap perjalanan hebat dimulai dengan satu langkah, dan perjalanan kami dimulai dengan menentukan direktori tempat dokumen Anda disimpan. Di sinilah Aspose.Words akan mencari dokumen Word Anda.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Ini, ganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda. Di sinilah dokumen sumber Anda berada dan di mana hasilnya akan disimpan.

## Langkah 2: Atur Folder Font

 Sekarang, mari beri tahu Aspose.Words di mana menemukan font khusus Anda. Hal ini dilakukan dengan mengatur folder font menggunakan`FontSettings.DefaultInstance.SetFontsFolder` metode.

```csharp
FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
```

 Di baris ini,`"C:\\MyFonts\\"` adalah jalur ke folder font khusus Anda. Parameter kedua,`true`, menunjukkan bahwa font dalam folder ini harus dipindai secara rekursif.

## Langkah 3: Muat Dokumen Anda

 Setelah folder font diatur, langkah selanjutnya adalah memuat dokumen Word Anda ke Aspose.Words. Ini dilakukan dengan menggunakan`Document` kelas.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

 Di Sini,`dataDir + "Rendering.docx"` mengacu pada jalur lengkap dokumen Word Anda. Pastikan dokumen Anda ada di direktori yang ditentukan.

## Langkah 4: Simpan Dokumen

Langkah terakhir adalah menyimpan dokumen Anda setelah mengatur folder font. Ini memastikan bahwa font khusus Anda diterapkan dengan benar di output.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

Baris ini menyimpan dokumen Anda sebagai PDF dengan font khusus yang diterapkan. File keluaran akan ditempatkan di direktori yang sama dengan dokumen sumber Anda.

## Kesimpulan

Dan itu dia! Mengatur folder font untuk instance default di Aspose.Words untuk .NET sangatlah mudah jika Anda memecahnya menjadi beberapa langkah sederhana. Dengan mengikuti panduan ini, Anda dapat memastikan bahwa dokumen Word Anda terlihat persis seperti yang Anda inginkan, dengan semua font khusus Anda tersedia. Jadi silakan mencobanya, dan buat dokumen Anda bersinar!

## FAQ

### Bisakah saya mengatur beberapa folder font?
 Ya, Anda dapat mengatur beberapa folder font dengan menggunakan`SetFontsFolders` metode yang menerima array jalur folder.

### Format file apa yang didukung Aspose.Words untuk menyimpan dokumen?
Aspose.Words mendukung berbagai format termasuk DOCX, PDF, HTML, EPUB, dan banyak lagi.

### Apakah mungkin menggunakan font online di Aspose.Words?
Tidak, Aspose.Words saat ini hanya mendukung file font lokal.

### Bagaimana cara memastikan font khusus saya tertanam dalam PDF yang disimpan?
 Dengan mengatur`FontSettings` dengan benar dan memastikan font tersedia, Aspose.Words akan menyematkannya dalam output PDF.

### Apa yang terjadi jika font tidak ditemukan di folder yang ditentukan?
Aspose.Words akan menggunakan font fallback jika font yang ditentukan tidak ditemukan.