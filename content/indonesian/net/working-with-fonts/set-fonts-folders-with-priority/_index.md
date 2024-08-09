---
title: Atur Folder Font Dengan Prioritas
linktitle: Atur Folder Font Dengan Prioritas
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengatur folder font dengan prioritas di dokumen Word menggunakan Aspose.Words untuk .NET. Panduan kami memastikan dokumen Anda ditampilkan dengan sempurna setiap saat.
type: docs
weight: 10
url: /id/net/working-with-fonts/set-fonts-folders-with-priority/
---
## Perkenalan

Dalam dunia manipulasi dokumen, mengatur folder font khusus dapat membuat perbedaan besar dalam memastikan dokumen Anda ditampilkan dengan sempurna, di mana pun dokumen tersebut dilihat. Hari ini, kita akan mendalami cara mengatur folder font dengan prioritas di dokumen Word Anda menggunakan Aspose.Words untuk .NET. Panduan komprehensif ini akan memandu Anda melalui setiap langkah, membuat prosesnya selancar mungkin.

## Prasyarat

Sebelum kita mulai, pastikan kita memiliki semua yang kita butuhkan. Berikut daftar periksa singkatnya:

-  Aspose.Words untuk .NET: Anda harus menginstal perpustakaan ini. Jika Anda belum memilikinya, Anda bisa[unduh di sini](https://releases.aspose.com/words/net/).
- Lingkungan Pengembangan: Pastikan Anda memiliki lingkungan pengembangan .NET yang berfungsi, seperti Visual Studio.
-  Direktori Dokumen: Pastikan Anda memiliki direktori untuk dokumen Anda. Sebagai contoh, kami akan menggunakan`"YOUR DOCUMENT DIRECTORY"` sebagai pengganti jalur ini.

## Impor Namespace

Hal pertama yang pertama, kita perlu mengimpor namespace yang diperlukan. Namespace ini penting untuk mengakses kelas dan metode yang disediakan oleh Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fonts;
```

Sekarang, mari kita uraikan setiap langkah untuk mengatur folder font dengan prioritas.

## Langkah 1: Siapkan Sumber Font Anda

Untuk memulai, Anda ingin menentukan sumber font. Di sinilah Anda memberi tahu Aspose.Words di mana mencari font. Anda dapat menentukan beberapa folder font dan bahkan mengatur prioritasnya.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
    new SystemFontSource(), 
    new FolderFontSource("C:\\MyFonts\\", true, 1)
});
```

Dalam contoh ini, kami menetapkan dua sumber font:
- SystemFontSource: Ini adalah sumber font default yang mencakup semua font yang diinstal pada sistem Anda.
-  FolderFontSource: Ini adalah folder font khusus yang terletak di`C:\\MyFonts\\` . Itu`true` parameter menentukan bahwa folder ini harus dipindai secara rekursif, dan`1` menetapkan prioritasnya.

## Langkah 2: Muat Dokumen Anda

Selanjutnya, muat dokumen yang ingin Anda kerjakan. Pastikan dokumen tersebut terletak di direktori yang Anda tentukan.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

 Baris kode ini memuat dokumen bernama`Rendering.docx` dari direktori dokumen Anda.

## Langkah 3: Simpan Dokumen Anda dengan Pengaturan Font Baru

Terakhir, simpan dokumen Anda. Saat Anda menyimpan dokumen, Aspose.Words akan menggunakan pengaturan font yang Anda tentukan.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

 Ini menyimpan dokumen sebagai PDF di direktori dokumen Anda dengan nama`WorkingWithFonts.SetFontsFoldersWithPriority.pdf`.

## Kesimpulan

Dan itu dia! Anda telah berhasil menyiapkan folder font dengan prioritas menggunakan Aspose.Words untuk .NET. Dengan menentukan folder dan prioritas font khusus, Anda dapat memastikan dokumen Anda ditampilkan secara konsisten, di mana pun dokumen tersebut dilihat. Ini sangat berguna di lingkungan di mana font tertentu tidak diinstal secara default.

## FAQ

### Mengapa saya perlu mengatur folder font khusus?
Mengatur folder font khusus memastikan dokumen Anda ditampilkan dengan benar, meskipun menggunakan font yang tidak diinstal pada sistem tempat dokumen tersebut dilihat.

### Bisakah saya mengatur beberapa folder font khusus?
Ya, Anda dapat menentukan beberapa folder font. Aspose.Words memungkinkan Anda mengatur prioritas untuk setiap folder, memastikan font terpenting ditemukan terlebih dahulu.

### Apa yang terjadi jika font hilang dari semua sumber yang ditentukan?
Jika font hilang dari semua sumber yang ditentukan, Aspose.Words akan menggunakan font fallback untuk memastikan dokumen masih dapat dibaca.

### Bisakah saya mengubah prioritas font sistem?
Font sistem selalu disertakan secara default, namun Anda dapat mengatur prioritasnya terkait dengan folder font khusus Anda.

### Apakah mungkin menggunakan jalur jaringan untuk folder font khusus?
Ya, Anda dapat menentukan jalur jaringan sebagai folder font khusus, memungkinkan Anda memusatkan sumber daya font di lokasi jaringan.