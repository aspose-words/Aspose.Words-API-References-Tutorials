---
title: Atur Folder Font Dengan Prioritas
linktitle: Atur Folder Font Dengan Prioritas
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk mengatur folder font dengan prioritas saat merender dokumen menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-fonts/set-fonts-folders-with-priority/
---

Dalam tutorial ini, kami akan memandu Anda melalui proses langkah demi langkah untuk mengatur folder font dengan prioritas saat merender dokumen menggunakan Aspose.Words untuk .NET. Kami akan menjelaskan paket kode sumber C# dan memberi Anda panduan komprehensif untuk membantu Anda memahami dan menerapkan fitur ini dalam proyek Anda sendiri. Di akhir tutorial ini, Anda akan mengetahui cara menentukan beberapa folder font dengan prioritas pencarian khusus saat merender dokumen Anda menggunakan Aspose.Words untuk .NET.

## Langkah 1: Tentukan direktori dokumen
Pertama, Anda perlu menyetel jalur ke direktori dokumen Anda. Ini adalah lokasi di mana Anda ingin menyimpan dokumen hasil editan Anda. Ganti "DIREKTORI DOKUMEN ANDA" dengan jalur yang sesuai.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Tetapkan folder font dengan prioritas
 Kemudian Anda dapat mengatur folder font dengan prioritas menggunakan`FontSettings` kelas dan`SetFontsSources()`metode. Anda dapat menentukan beberapa sumber font menggunakan contoh`SystemFontSource`Dan`FolderFontSource`. Dalam contoh ini, kami telah menetapkan dua sumber font: sumber font sistem default dan folder font khusus dengan prioritas 1.

```csharp
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true, 1)
});
```

## Langkah 3: Muat dokumen yang akan dirender
 Sekarang Anda dapat memuat dokumen untuk dirender menggunakan`Document` kelas. Pastikan untuk menentukan jalur dokumen yang benar.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Langkah 4: Simpan dokumen yang dirender
 Terakhir, Anda dapat menyimpan dokumen yang dirender ke file menggunakan`Save()` metode`Document` kelas. Pastikan untuk menentukan jalur dan nama file yang benar.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

### Contoh kode sumber untuk Mengatur Folder Font Dengan Prioritas menggunakan Aspose.Words untuk .NET 
```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true,1)
});
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara mengatur folder font dengan prioritas saat merender dokumen menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah ini, Anda dapat dengan mudah menentukan beberapa folder font dengan prioritas pencarian khusus saat merender dokumen Anda. Aspose.Words menawarkan API yang kuat dan fleksibel untuk Pemrosesan Kata dengan font di dokumen Anda. Dengan pengetahuan ini, Anda dapat mengontrol dan menyesuaikan sumber font yang digunakan saat merender dokumen sesuai kebutuhan spesifik Anda.

### FAQ

#### T: Bagaimana cara mengatur folder font dengan prioritas di Aspose.Words?

 A: Untuk mengatur folder font dengan prioritas di Aspose.Words, Anda dapat menggunakan`SetFontsFoldersWithPriority` metode`Fonts` kelas dengan menentukan lokasi folder font dan urutan prioritasnya.

#### Q: Apa yang terjadi jika font ada di beberapa folder dengan prioritas berbeda?

J: Jika font ada di beberapa folder dengan prioritas berbeda, Aspose.Words akan menggunakan versi dari folder dengan prioritas tertinggi saat memproses dokumen.

#### T: Bisakah saya menentukan beberapa folder font dengan prioritas yang sama di Aspose.Words?

A: Ya, Anda dapat menentukan beberapa folder font dengan prioritas yang sama di Aspose.Words. Aspose.Words akan mempertimbangkan semuanya dengan prioritas yang sama saat mencari font di dokumen Anda.

#### T: Bagaimana cara memeriksa folder font yang ditentukan dengan prioritas di Aspose.Words?

 A: Untuk memeriksa folder font yang ditentukan dengan prioritas di Aspose.Words, Anda dapat menggunakan`GetFolders` metode`Fonts` kelas untuk mendapatkan daftar folder font yang dikonfigurasi termasuk urutan prioritasnya.

#### Q: Apa gunanya mengatur folder font dengan prioritas di Aspose.Words?

J: Mengatur folder font dengan prioritas di Aspose.Words memungkinkan Anda mengontrol urutan pencarian font di dokumen Word Anda. Ini membantu Anda memastikan bahwa font yang Anda inginkan digunakan dan menghindari masalah penggantian font yang tidak diinginkan.