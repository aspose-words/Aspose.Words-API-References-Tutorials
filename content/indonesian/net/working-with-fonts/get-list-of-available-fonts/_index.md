---
title: Dapatkan Daftar Font yang Tersedia
linktitle: Dapatkan Daftar Font yang Tersedia
second_title: API Pemrosesan Dokumen Aspose.Words
description: Dalam tutorial ini, pelajari cara mendapatkan daftar font yang tersedia di Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-fonts/get-list-of-available-fonts/
---
Dalam tutorial ini, kami akan menjelaskan cara mendapatkan daftar font yang tersedia di Aspose.Words untuk .NET. Daftar font yang tersedia memungkinkan Anda mengetahui font mana yang dapat Anda gunakan dalam dokumen Anda. Kami akan memandu Anda langkah demi langkah untuk membantu Anda memahami dan menerapkan kode dalam proyek .NET Anda.

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

## Langkah 2: Konfigurasikan sumber font
 Selanjutnya, kita akan membuat sebuah instance dari`FontSettings` dan dapatkan sumber font yang ada menggunakan`GetFontsSources()` metode. Kami juga akan menambahkan sumber font baru dengan menentukan folder yang berisi font.

```csharp
// Konfigurasikan sumber font
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());

// Tambahkan sumber font baru
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
fontSources.Add(folderFontSource);

FontSourceBase[] updatedFontSources = fontSources.ToArray();
```

## Langkah 3: Dapatkan daftar font yang tersedia
 Sekarang kita akan menelusuri font yang tersedia menggunakan`GetAvailableFonts()` metode pada sumber font pertama yang diperbarui.

```csharp
// Dapatkan daftar font yang tersedia
foreach(PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
Console.WriteLine("Font Family Name: " + fontInfo.FontFamilyName);
Console.WriteLine("Full font name: " + fontInfo.FullFontName);
Console.WriteLine("Version: " + fontInfo.Version);
Console.WriteLine("Path: " + fontInfo.FilePath);
}
```


### Contoh kode sumber untuk Dapatkan Daftar Font yang Tersedia menggunakan Aspose.Words untuk .NET 

```csharp

// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
// Tambahkan folder baru sumber yang akan menginstruksikan Aspose.Words untuk mencari font di folder berikut.
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
//Tambahkan folder khusus yang berisi font kami ke daftar sumber font yang ada.
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
foreach (PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
	Console.WriteLine("FontFamilyName : " + fontInfo.FontFamilyName);
	Console.WriteLine("FullFontName  : " + fontInfo.FullFontName);
	Console.WriteLine("Version  : " + fontInfo.Version);
	Console.WriteLine("FilePath : " + fontInfo.FilePath);
}

```

## Kesimpulan
Dalam tutorial ini, kita melihat cara mendapatkan daftar font yang tersedia di Aspose.Words untuk .NET. Ini memungkinkan Anda mengetahui font mana yang dapat Anda gunakan dalam dokumen Anda. Jangan ragu untuk menggunakan fitur ini untuk memilih font yang sesuai dengan kebutuhan Anda.

### FAQ

#### T: Bagaimana cara mengambil daftar font yang tersedia di Aspose.Words?

 A: Untuk mengambil daftar font yang tersedia di Aspose.Words, Anda dapat menggunakan`FontsProvider` kelas dan`GetAvailableFonts` metode. Metode ini akan mengembalikan daftar semua font yang diinstal pada sistem Anda.

#### T: Bisakah saya memfilter daftar font yang tersedia berdasarkan kriteria tertentu di Aspose.Words?

A: Ya, Anda dapat memfilter daftar font yang tersedia di Aspose.Words menggunakan kriteria tertentu. Misalnya, Anda dapat memfilter font berdasarkan jenis, gaya, atau bahasa.

#### T: Bagaimana cara menggunakan daftar font yang tersedia di dokumen Word saya?

J: Untuk menggunakan daftar font yang tersedia di dokumen Word Anda, Anda dapat menelusuri daftar dan memilih font yang sesuai menggunakan metode dan properti dari`FontSettings` kelas di Aspose.Words.