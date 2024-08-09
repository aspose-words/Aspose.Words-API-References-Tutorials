---
title: Atur Folder Font
linktitle: Atur Folder Font
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengatur folder font khusus di Aspose.Words untuk .NET dengan panduan langkah demi langkah yang komprehensif ini. Sempurna untuk pengembang yang ingin menyempurnakan font dokumen.
type: docs
weight: 10
url: /id/net/working-with-fonts/set-fonts-folders/
---
## Perkenalan

Hai! Siap terjun ke dunia font khusus di Aspose.Words untuk .NET? Mari kita mulai. Tutorial ini akan memandu Anda melalui proses pengaturan folder font khusus, memastikan dokumen Anda terlihat sesuai keinginan Anda. Baik Anda seorang pengembang berpengalaman atau baru memulai, panduan ini akan memandu Anda melalui setiap langkah. Jadi, mari kita buat font-font itu tampak luar biasa!

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki semua yang Anda butuhkan:

-  Aspose.Words untuk .NET: Anda bisa[unduh](https://releases.aspose.com/words/net/) itu jika Anda belum melakukannya.
- Visual Studio: Versi apa pun bisa digunakan, tetapi versi terbaru selalu yang terbaik.
- Dokumen: Kami akan menggunakan dokumen Word untuk tutorial ini. Anda dapat membuatnya sendiri atau menggunakan yang sudah ada.
- Font Khusus: Siapkan beberapa font khusus. Kami akan menggunakan ini untuk mendemonstrasikan cara mengatur folder font.

## Impor Namespace

Hal pertama yang pertama, mari impor namespace yang diperlukan. Ini penting untuk mengakses kelas dan metode yang kita perlukan dari Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
```

Dengan namespace ini diimpor, kami siap untuk mulai menyiapkan folder font khusus kami.

## Langkah 1: Tentukan Direktori Dokumen Anda

 Mari kita mulai dengan menentukan jalur ke direktori dokumen Anda. Di sinilah dokumen Word Anda disimpan. Kami akan menggunakan variabel yang disebut`dataDir` untuk menyimpan jalur ini.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori Anda. Ini penting karena Aspose.Words perlu mengetahui di mana menemukan dokumen Anda.

## Langkah 2: Tetapkan Sumber Font

 Selanjutnya, kita perlu menyiapkan sumber font. Di sinilah kami memberi tahu Aspose.Words di mana menemukan font khusus kami. Kami akan menggunakan`FontSettings.DefaultInstance.SetFontsSources` metode untuk mencapai hal ini.

```csharp
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true)
});
```

Inilah yang kami lakukan:

- SystemFontSource: Ini memberitahu Aspose.Words untuk menggunakan font default sistem.
-  FolderFontSource: Di sinilah kita menentukan folder yang berisi font khusus kita. Mengganti`"C:\\MyFonts\\"` dengan jalur ke direktori font khusus Anda. Itu`true` parameter menunjukkan bahwa subdirektori juga harus disertakan.

## Langkah 3: Muat Dokumen Anda

Sekarang kita telah menyiapkan sumber font, saatnya memuat dokumen yang ingin kita kerjakan. Kami akan menggunakan`Document` kelas dari Aspose. Kata-kata untuk ini.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

 Pastikan itu`"Rendering.docx"` adalah nama dokumen Word Anda. Jika dokumen Anda memiliki nama yang berbeda, pastikan untuk memperbaruinya.

## Langkah 4: Simpan Dokumen Anda sebagai PDF

 Terakhir, mari simpan dokumen kita sebagai PDF untuk melihat font kustom beraksi. Kami akan menggunakan`Save` metode`Document` kelas.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

Ini akan menyimpan dokumen Anda sebagai PDF di direktori yang ditentukan, menggunakan font khusus yang kami siapkan sebelumnya.

## Kesimpulan

Dan itu dia! Anda telah berhasil menyiapkan folder font khusus di Aspose.Words untuk .NET dan menyimpan dokumen Anda sebagai PDF dengan font khusus tersebut. Cukup keren, bukan? Menyesuaikan font dapat membuat perbedaan besar pada tampilan dokumen Anda, dan sekarang Anda tahu persis bagaimana melakukannya. Selamat membuat kode!

## FAQ

### Bagaimana cara menginstal Aspose.Words untuk .NET?

 Anda bisa[unduh](https://releases.aspose.com/words/net/) versi terbaru Aspose.Words untuk .NET dari situs web.

### Bisakah saya menggunakan beberapa folder font khusus?

 Ya, Anda dapat menambahkan lebih dari satu`FolderFontSource` contoh ke`SetFontsSources`metode untuk menggunakan font dari direktori berbeda.

### Apakah perlu menyertakan font sistem?

Menyertakan font sistem bersifat opsional tetapi disarankan untuk memastikan semua font standar tersedia.

### Jenis file apa yang didukung oleh Aspose.Words?

Aspose.Words mendukung berbagai format file, termasuk DOCX, DOC, PDF, TXT, HTML, dan banyak lagi.

### Bagaimana saya bisa mendapatkan lisensi sementara untuk Aspose.Words?

 Anda dapat memperoleh a[izin sementara](https://purchase.aspose.com/temporary-license/) dari situs Aspose untuk mencoba fitur lengkap Aspose.Words.