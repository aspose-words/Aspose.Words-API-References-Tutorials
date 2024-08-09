---
title: Hitung Properti
linktitle: Hitung Properti
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menghitung properti dalam dokumen Word menggunakan Aspose.Words untuk .NET dengan panduan langkah demi langkah ini. Sempurna untuk pengembang dari semua tingkat keahlian.
type: docs
weight: 10
url: /id/net/programming-with-document-properties/enumerate-properties/
---
## Perkenalan

Ingin bekerja dengan dokumen Word secara terprogram? Aspose.Words for .NET adalah alat canggih yang dapat membantu Anda mencapai hal itu. Hari ini, saya akan memandu Anda tentang cara menghitung properti dokumen Word menggunakan Aspose.Words untuk .NET. Baik Anda seorang pemula atau sudah berpengalaman, panduan ini akan menguraikannya langkah demi langkah dengan cara yang komunikatif dan mudah diikuti.

## Prasyarat

Sebelum kita mendalami tutorialnya, ada beberapa hal yang Anda perlukan untuk memulai:

-  Aspose.Words untuk .NET: Anda bisa[unduh di sini](https://releases.aspose.com/words/net/).
- Lingkungan Pengembangan: Visual Studio direkomendasikan, tetapi Anda dapat menggunakan C# IDE apa pun.
- Pengetahuan Dasar tentang C#: Pemahaman mendasar tentang C# akan membantu Anda mengikutinya.

Sekarang, ayo langsung masuk!

## Langkah 1: Menyiapkan Proyek Anda

Hal pertama yang pertama, Anda perlu menyiapkan proyek Anda di Visual Studio.

1. Buat Proyek Baru: Buka Visual Studio dan buat proyek Aplikasi Konsol baru.
2. Instal Aspose.Words untuk .NET: Gunakan NuGet Package Manager untuk menginstal Aspose.Words untuk .NET. Klik kanan proyek Anda di Solution Explorer, pilih "Kelola Paket NuGet," dan cari "Aspose.Words". Instal paketnya.

## Langkah 2: Impor Namespace

Untuk bekerja dengan Aspose.Words, Anda perlu mengimpor namespace yang diperlukan. Tambahkan yang berikut ini di bagian atas file Program.cs Anda:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Properties;
```

## Langkah 3: Muat Dokumen Anda

Selanjutnya, muat dokumen Word yang ingin Anda kerjakan. Untuk contoh ini, kami akan menggunakan dokumen bernama "Properties.docx" yang terletak di direktori proyek Anda.

1. Tentukan Jalur Dokumen: Tentukan jalur ke dokumen Anda.
2.  Muat Dokumen: Gunakan Aspose.Words`Document` kelas untuk memuat dokumen.

Berikut kodenya:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

## Langkah 4: Tampilkan Nama Dokumen

Setelah dokumen Anda dimuat, Anda mungkin ingin menampilkan namanya. Aspose.Words menyediakan properti untuk ini:

```csharp
Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
```

## Langkah 5: Hitung Properti Bawaan

Properti bawaan adalah properti metadata yang telah ditentukan sebelumnya oleh Microsoft Word. Ini termasuk judul, penulis, dan banyak lagi.

1.  Akses Properti Bawaan: Gunakan`BuiltInDocumentProperties` koleksi.
2. Loop Through Properties: Ulangi properti dan tampilkan nama dan nilainya.

Berikut kodenya:

```csharp
Console.WriteLine("2. Built-in Properties");

foreach (DocumentProperty prop in doc.BuiltInDocumentProperties)
    Console.WriteLine("{0} : {1}", prop.Name, prop.Value);
```

## Langkah 6: Hitung Properti Kustom

Properti khusus adalah properti metadata yang ditentukan pengguna. Ini bisa berupa apa saja yang ingin Anda tambahkan ke dokumen Anda.

1.  Akses Properti Kustom: Gunakan`CustomDocumentProperties` koleksi.
2. Loop Through Properties: Ulangi properti dan tampilkan nama dan nilainya.

Berikut kodenya:

```csharp
Console.WriteLine("3. Custom Properties");

foreach (DocumentProperty prop in doc.CustomDocumentProperties)
    Console.WriteLine("{0} : {1}", prop.Name, prop.Value);
```

## Kesimpulan

Dan itu dia! Anda telah berhasil menghitung properti bawaan dan kustom dokumen Word menggunakan Aspose.Words untuk .NET. Ini hanyalah puncak gunung es dalam hal apa yang dapat Anda lakukan dengan Aspose.Words. Baik Anda mengotomatiskan pembuatan dokumen atau memanipulasi dokumen kompleks, Aspose.Words menyediakan serangkaian fitur yang kaya untuk membuat hidup Anda lebih mudah.

## FAQ

### Bisakah saya menambahkan properti baru ke dokumen?
 Ya, Anda dapat menambahkan properti khusus baru menggunakan`CustomDocumentProperties` koleksi.

### Apakah Aspose.Words gratis untuk digunakan?
 Aspose.Words menawarkan a[uji coba gratis](https://releases.aspose.com/) dan berbeda[opsi pembelian](https://purchase.aspose.com/buy).

### Bagaimana cara mendapatkan dukungan untuk Aspose.Words?
 Anda bisa mendapatkan dukungan dari komunitas Aspose[Di Sini](https://forum.aspose.com/c/words/8).

### Bisakah saya menggunakan Aspose.Words dengan bahasa .NET lainnya?
Ya, Aspose.Words mendukung beberapa bahasa .NET termasuk VB.NET.

### Di mana saya dapat menemukan lebih banyak contoh?
 Lihat[Aspose.Words untuk dokumentasi .NET](https://reference.aspose.com/words/net/) untuk lebih banyak contoh dan informasi rinci.
