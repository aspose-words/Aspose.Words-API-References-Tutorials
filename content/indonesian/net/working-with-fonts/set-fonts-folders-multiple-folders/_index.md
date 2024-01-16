---
title: Atur Folder Font Beberapa Folder
linktitle: Atur Folder Font Beberapa Folder
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk mengatur beberapa folder font saat merender dokumen menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-fonts/set-fonts-folders-multiple-folders/
---

Dalam tutorial ini, kami akan memandu Anda melalui proses langkah demi langkah untuk mengatur beberapa folder font saat merender dokumen menggunakan Aspose.Words untuk .NET. Kami akan menjelaskan paket kode sumber C# dan memberi Anda panduan komprehensif untuk membantu Anda memahami dan menerapkan fitur ini dalam proyek Anda sendiri. Di akhir tutorial ini, Anda akan mengetahui cara menentukan beberapa folder font untuk digunakan saat merender dokumen Anda menggunakan Aspose.Words untuk .NET.

## Langkah 1: Tentukan direktori dokumen
Pertama, Anda perlu menyetel jalur ke direktori dokumen Anda. Ini adalah lokasi di mana Anda ingin menyimpan dokumen hasil editan Anda. Ganti "DIREKTORI DOKUMEN ANDA" dengan jalur yang sesuai.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Muat dokumen yang akan dirender
 Kemudian Anda dapat memuat dokumen untuk dirender menggunakan`Document` kelas. Pastikan untuk menentukan jalur dokumen yang benar.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Langkah 3: Atur Folder Font
 Sekarang Anda dapat mengatur beberapa folder font menggunakan`FontSettings` kelas dan`SetFontsFolders()` metode. Anda dapat menentukan jalur ke folder font yang ingin Anda gunakan dalam array. Dalam contoh ini, kami telah menentukan dua folder font: "C:\MyFonts\" dan "D:\Lain-lain\Font\".

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
```

## Langkah 4: Terapkan Pengaturan Font
 Selanjutnya, Anda perlu menerapkan pengaturan font ke dokumen Anda menggunakan`FontSettings` properti dari`Document` kelas.

```csharp
doc.FontSettings = fontSettings;
```

## Langkah 5: Simpan dokumen yang dirender
 Terakhir, Anda dapat menyimpan dokumen yang dirender ke file menggunakan`Save()` metode`Document` kelas. Pastikan untuk menentukan jalur dan nama file yang benar.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

### Contoh kode sumber untuk Mengatur Folder Font Beberapa Folder menggunakan Aspose.Words untuk .NET 

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Perhatikan bahwa pengaturan ini akan mengesampingkan sumber font default apa pun yang sedang dicari secara default. Sekarang hanya folder-folder ini yang akan dicari
// font saat merender atau menyematkan font. Untuk menambahkan sumber font tambahan sambil mempertahankan sumber font sistem, gunakan FontSettings.GetFontSources dan
// FontSettings.SetFontSources sebagai gantinya.
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara mengatur beberapa folder font saat merender dokumen menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah ini, Anda dapat dengan mudah menentukan beberapa folder font untuk digunakan saat merender dokumen Anda. Aspose.Words menawarkan API yang kuat dan fleksibel untuk Pemrosesan Kata dengan font di dokumen Anda. Dengan pengetahuan ini, Anda dapat mengontrol dan menyesuaikan sumber font yang digunakan saat merender dokumen sesuai kebutuhan spesifik Anda.

### FAQ

#### T: Bagaimana cara mengatur beberapa folder font di Aspose.Words?

 A: Untuk mengatur beberapa folder font di Aspose.Words, Anda dapat menggunakan`SetFontsFolders` metode`Fonts` kelas menyediakan daftar lokasi folder font khusus.

#### T: Apakah pengaturan beberapa folder font mempengaruhi semua dokumen yang diproses dengan Aspose.Words?

A: Ya, pengaturan beberapa folder font mempengaruhi semua dokumen yang diproses dengan Aspose.Words. Setelah Anda menentukan folder font, Aspose.Words akan menggunakan lokasi ini untuk mencari font di semua dokumen.

#### T: Berapa banyak folder font yang dapat saya tentukan di Aspose.Words?

A: Anda dapat menentukan folder font sebanyak yang diperlukan di Aspose.Words. Tidak ada batasan khusus mengenai jumlah folder font yang dapat Anda tentukan.

#### T: Bagaimana cara memeriksa folder font yang ditentukan di Aspose.Words?

 A: Untuk memeriksa folder font yang ditentukan di Aspose.Words, Anda dapat menggunakan`GetFolders` metode`Fonts` kelas untuk mendapatkan lokasi folder font yang dikonfigurasi.

#### T: Apakah folder font harus berisi font tertentu?

J: Ya, folder font harus berisi font yang ingin Anda gunakan di dokumen Word Anda. Aspose.Words akan mencari font di folder yang ditentukan saat memproses dokumen.