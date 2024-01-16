---
title: Setel Folder Font Tipe Benar
linktitle: Setel Folder Font Tipe Benar
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk mengatur folder font tipe sebenarnya saat merender dokumen menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-fonts/set-true-type-fonts-folder/
---

Dalam tutorial ini, kami akan memandu Anda melalui proses langkah demi langkah untuk mengatur folder font tipe sebenarnya saat merender dokumen menggunakan Aspose.Words untuk .NET. Kami akan menjelaskan paket kode sumber C# dan memberi Anda panduan komprehensif untuk membantu Anda memahami dan menerapkan fitur ini dalam proyek Anda sendiri. Di akhir tutorial ini, Anda akan mengetahui cara menentukan folder khusus yang berisi font True Type untuk digunakan saat merender dokumen Anda menggunakan Aspose.Words untuk .NET.

## Langkah 1: Tentukan direktori dokumen
Pertama, Anda perlu menyetel jalur ke direktori dokumen Anda. Ini adalah lokasi di mana Anda ingin menyimpan dokumen hasil editan Anda. Ganti "DIREKTORI DOKUMEN ANDA" dengan jalur yang sesuai.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Muat dokumen yang akan dirender
 Selanjutnya, Anda perlu memuat dokumen untuk dirender menggunakan`Document` kelas. Pastikan untuk menentukan jalur dokumen yang benar.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Langkah 3: Atur Folder Font Tipe Benar
Sekarang Anda dapat menentukan folder font tipe sebenarnya yang akan digunakan saat rendering dengan membuat instance dari`FontSettings` kelas dan menggunakan`SetFontsFolder()` metode untuk mengatur folder font. Anda dapat menentukan folder khusus yang berisi font True Type Anda. Parameter kedua untuk`SetFontsFolder()` menunjukkan apakah Anda ingin mencari subfolder dari folder tertentu juga.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
doc.FontSettings = fontSettings;
```

## Langkah 4: Simpan dokumen yang dirender
 Terakhir, Anda dapat menyimpan dokumen yang dirender ke file menggunakan`Save()` metode`Document` kelas. Pastikan untuk menentukan jalur dan nama file yang benar.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

### Contoh kode sumber untuk Mengatur Folder Font Tipe Benar menggunakan Aspose.Words untuk .NET 

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Perhatikan bahwa pengaturan ini akan mengesampingkan sumber font default apa pun yang sedang dicari secara default. Sekarang hanya folder-folder ini yang akan dicari
// Font saat merender atau menyematkan font. Untuk menambahkan sumber font tambahan sambil mempertahankan sumber font sistem, gunakan FontSettings.GetFontSources dan
// FontSettings.SetFontSources sebagai gantinya
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
// Tetapkan pengaturan font
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara mengatur folder font tipe sebenarnya saat merender dokumen menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah ini, Anda dapat dengan mudah menentukan folder khusus yang berisi font True Type untuk digunakan saat merender dokumen Anda. Aspose.Words menawarkan API yang kuat dan fleksibel untuk Pemrosesan Kata dengan font di dokumen Anda. Dengan pengetahuan ini, Anda dapat mengontrol dan menyesuaikan font yang digunakan saat merender dokumen sesuai kebutuhan spesifik Anda.

### FAQ

#### T: Bagaimana cara mengonfigurasi folder font TrueType di Aspose.Words?

 J: Untuk mengonfigurasi folder font TrueType di Aspose.Words, Anda dapat menggunakan`SetTrueTypeFontsFolder` metode`Fonts` kelas yang menentukan lokasi folder yang berisi font TrueType.

#### T: Jenis font apa yang dianggap sebagai font TrueType?

J: Font TrueType adalah format font yang populer. Mereka sering digunakan dalam dokumen Word dan memiliki ekstensi file .ttf atau .ttc.

#### T: Bisakah saya menentukan beberapa folder font TrueType di Aspose.Words?

J: Ya, Anda dapat menentukan beberapa folder font TrueType di Aspose.Words menggunakan`SetTrueTypeFontsFolder` metode`Fonts` kelas dengan daftar lokasi folder.

#### T: Bagaimana cara memeriksa folder font TrueType yang dikonfigurasi di Aspose.Words?

 J: Untuk memeriksa folder TrueType Fonts yang dikonfigurasi di Aspose.Words, Anda dapat menggunakan`GetTrueTypeFontsFolder` metode`Fonts` kelas untuk mendapatkan lokasi folder TrueType Fonts yang dikonfigurasi.

#### T: Mengapa penting untuk mengonfigurasi folder font TrueType di Aspose.Words?

J: Menyiapkan folder font TrueType di Aspose.Words penting karena membantu Aspose.Words menemukan font yang diperlukan saat memproses dokumen Word. Hal ini memastikan konsistensi dalam format dan tampilan dokumen, bahkan di berbagai sistem.