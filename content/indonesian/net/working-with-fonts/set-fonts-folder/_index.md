---
title: Atur Folder Font
linktitle: Atur Folder Font
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengatur direktori font di Aspose.Words untuk .NET dan memastikan ketersediaan font yang digunakan dalam dokumen Anda.
type: docs
weight: 10
url: /id/net/working-with-fonts/set-fonts-folder/
---
Dalam tutorial ini, kami akan menunjukkan cara mengatur direktori font di Aspose.Words untuk .NET. Anda akan mempelajari cara menentukan direktori yang berisi font yang digunakan dalam dokumen Word Anda.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki item berikut:
- Pengetahuan tentang bahasa pemrograman C#
- Pustaka Aspose.Words untuk .NET diinstal di proyek Anda

## Langkah 1: Tentukan direktori dokumen
Mulailah dengan mengatur jalur direktori ke lokasi dokumen Word Anda. Mengganti`"YOUR DOCUMENT DIRECTORY"` dalam kode dengan jalur yang sesuai.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Atur direktori font
 Buat sebuah instance dari`FontSettings` kelas dan gunakan`SetFontsFolder` metode untuk menentukan direktori yang berisi font. Mengganti`"Fonts"` dengan nama direktori font sebenarnya.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
```

## Langkah 3: Muat dokumen dengan pengaturan font
 Menggunakan`LoadOptions` kelas untuk menentukan pengaturan font di`FontSettings` pilihan. Kemudian gunakan`Document` kelas untuk memuat dokumen menggunakan opsi ini.

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

### Contoh kode sumber untuk Mengatur Folder Font menggunakan Aspose.Words untuk .NET 

```csharp

// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## Kesimpulan
Selamat! Anda sekarang tahu cara mengatur direktori font di Aspose.Words untuk .NET. Anda dapat menggunakan fitur ini untuk memastikan ketersediaan font yang digunakan dalam dokumen Anda dan untuk memastikan konsistensi dalam tampilan font.

### FAQ

#### T: Bagaimana cara mengatur folder font khusus di Aspose.Words?

 A: Untuk mengatur folder font khusus di Aspose.Words, Anda dapat menggunakan`FontsFolder` kelas dan`SetFontsFolders` metode yang menentukan jalur ke folder yang berisi font Anda.

#### T: Bisakah saya mengatur beberapa folder font di Aspose.Words?

 A: Ya, Anda dapat mengatur beberapa folder font di Aspose.Words dengan memanggil`SetFontsFolders` metode beberapa kali dengan jalur folder font berbeda yang ingin Anda gunakan.

#### T: Apa yang terjadi jika font yang digunakan dalam dokumen tidak ada dalam folder font yang ditentukan?

J: Jika font yang digunakan dalam dokumen tidak ada dalam folder font yang ditentukan di Aspose.Words, font pengganti akan digunakan. Hal ini memastikan bahwa teks dalam dokumen akan selalu ditampilkan dengan benar, meskipun font aslinya tidak tersedia.

#### T: Apakah folder font yang ditentukan di Aspose.Words memiliki prioritas dibandingkan font yang diinstal pada sistem?

J: Ya, folder font yang ditentukan di Aspose.Words lebih diutamakan daripada font yang diinstal pada sistem. Artinya, jika font dengan nama yang sama ada di folder font yang ditentukan dan di font sistem, versi di folder font tersebut akan digunakan saat memproses dokumen Word.