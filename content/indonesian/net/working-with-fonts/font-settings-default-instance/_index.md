---
title: Contoh Default Pengaturan Font
linktitle: Contoh Default Pengaturan Font
second_title: API Pemrosesan Dokumen Aspose.Words
description: Dalam tutorial ini, pelajari cara mengonfigurasi pengaturan font default di dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-fonts/font-settings-default-instance/
---

Dalam tutorial ini, kami akan memandu Anda tentang cara mengonfigurasi pengaturan font default di dokumen Word menggunakan pustaka Aspose.Words untuk .NET. Pengaturan font default memungkinkan Anda menentukan sumber font yang digunakan saat memuat dan merender dokumen. Kami akan memandu Anda langkah demi langkah untuk membantu Anda memahami dan menerapkan kode dalam proyek .NET Anda.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki item berikut:
- Pengetahuan tentang bahasa pemrograman C#
- Pustaka Aspose.Words untuk .NET diinstal di proyek Anda

## Langkah 1: Tentukan direktori dokumen
 Pertama, Anda perlu mengatur jalur direktori ke lokasi dokumen Word Anda. Mengganti`"YOUR DOCUMENT DIRECTORY"` dalam kode dengan jalur yang sesuai.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Konfigurasikan Pengaturan Font Default
 Selanjutnya, kita akan membuat sebuah instance dari`FontSettings` menggunakan`FontSettings.DefaultInstance`, lalu kami akan menentukan sumber font yang digunakan saat memuat dan merender dokumen. Dalam contoh ini, kami menggunakan sumber font sistem dan sumber font folder.

```csharp
// Konfigurasikan pengaturan font default
FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(),
new FolderFontSource("C:\\MyFonts\\", true)
});
```

## Langkah 3: Unggah dokumen dengan pengaturan font
 Sekarang kita akan memuat dokumen menggunakan`LoadOptions` dan menentukan pengaturan font yang akan digunakan.

```csharp
// Muat dokumen dengan pengaturan font
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);
```


### Contoh kode sumber untuk Instans Default Pengaturan Font menggunakan Aspose.Words untuk .NET 
```csharp

// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(),
	new FolderFontSource("C:\\MyFonts\\", true)
});
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## Kesimpulan
Dalam tutorial ini, kita melihat cara mengonfigurasi pengaturan font default di dokumen Word dengan Aspose.Words untuk .NET. Dengan menentukan sumber font yang digunakan saat memuat dan merender dokumen, Anda dapat mengontrol tampilan font di dokumen Anda. Jangan ragu untuk menggunakan fitur ini untuk menyesuaikan pengaturan font di proyek Anda.

### FAQ

#### T: Bagaimana cara mengatur font default di Aspose.Words?

 A: Untuk mengatur font default di Aspose.Words, Anda dapat menggunakan`FontSettings` kelas dan`DefaultFontName` properti yang menentukan nama font yang diinginkan.

#### T: Dapatkah saya menentukan ukuran font default di Aspose.Words?

 A: Ya, Anda dapat menentukan ukuran font default di Aspose.Words menggunakan`DefaultFontSize` properti dari`FontSettings` kelas. Anda dapat mengatur ukuran titik yang diinginkan.

#### Q: Apakah mungkin untuk mengatur warna font default di Aspose.Words?

 A: Ya, Anda dapat mengatur warna font default di Aspose.Words menggunakan`DefaultColor` properti dari`FontSettings` kelas. Anda dapat menentukan warna menggunakan nilai RGB atau nama yang telah ditentukan sebelumnya.

#### T: Apakah pengaturan font default berlaku untuk semua dokumen?

J: Ya, pengaturan font default berlaku untuk semua dokumen yang dibuat atau diedit di Aspose.Words, kecuali pengaturan spesifik ditetapkan untuk masing-masing dokumen.