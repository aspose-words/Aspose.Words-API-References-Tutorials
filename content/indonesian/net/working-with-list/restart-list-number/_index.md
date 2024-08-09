---
title: Mulai Ulang Nomor Daftar
linktitle: Mulai Ulang Nomor Daftar
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara memulai ulang nomor daftar di dokumen Word menggunakan Aspose.Words untuk .NET. Panduan terperinci sepanjang 2000 kata ini mencakup semua yang perlu Anda ketahui, mulai dari penyiapan hingga penyesuaian tingkat lanjut.
type: docs
weight: 10
url: /id/net/working-with-list/restart-list-number/
---
## Perkenalan

Apakah Anda ingin menguasai seni manipulasi daftar di dokumen Word Anda menggunakan Aspose.Words untuk .NET? Nah, Anda berada di tempat yang tepat! Dalam tutorial ini, kita akan mendalami cara memulai ulang nomor daftar, sebuah fitur bagus yang akan membawa keterampilan otomatisasi dokumen Anda ke tingkat berikutnya. Kencangkan sabuk pengaman, dan mari kita mulai!

## Prasyarat

Sebelum kita beralih ke kode, pastikan Anda memiliki semua yang Anda butuhkan:

1.  Aspose.Words untuk .NET: Anda harus menginstal Aspose.Words untuk .NET. Jika Anda belum menginstalnya, Anda bisa[unduh di sini](https://releases.aspose.com/words/net/).
2. Lingkungan Pengembangan: Pastikan Anda memiliki lingkungan pengembangan yang sesuai seperti Visual Studio.
3. Pengetahuan Dasar C#: Pemahaman dasar C# akan membantu Anda mengikuti tutorial.

## Impor Namespace

Hal pertama yang pertama, mari impor namespace yang diperlukan. Ini sangat penting untuk mengakses fitur Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Lists;
using System.Drawing;
```

Sekarang, mari kita bagi prosesnya menjadi langkah-langkah yang mudah diikuti. Kami akan membahas semuanya mulai dari membuat daftar hingga memulai kembali penomorannya.

## Langkah 1: Siapkan Dokumen dan Pembuat Anda

Sebelum Anda dapat mulai memanipulasi daftar, Anda memerlukan dokumen dan DocumentBuilder. DocumentBuilder adalah alat bantu Anda untuk menambahkan konten ke dokumen Anda.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 2: Buat dan Sesuaikan Daftar Pertama Anda

Selanjutnya, kita akan membuat daftar berdasarkan template dan menyesuaikan tampilannya. Dalam contoh ini, kami menggunakan format angka Arab dengan tanda kurung.

```csharp
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;
```

Di sini, kami telah mengatur warna font menjadi merah dan menyelaraskan teks ke kanan.

## Langkah 3: Tambahkan Item ke Daftar Pertama Anda

 Setelah daftar Anda siap, saatnya menambahkan beberapa item. Pembuat Dokumen`ListFormat.List` properti membantu dalam menerapkan format daftar ke teks.

```csharp
builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();
```

## Langkah 4: Mulai Ulang Penomoran Daftar

Untuk menggunakan kembali daftar dan memulai kembali penomorannya, Anda perlu membuat salinan daftar asli. Ini memungkinkan Anda untuk mengubah daftar baru secara mandiri.

```csharp
List list2 = doc.Lists.AddCopy(list1);
list2.ListLevels[0].StartAt = 10;
```

Dalam contoh ini, daftar baru dimulai dari nomor 10.

## Langkah 5: Tambahkan Item ke Daftar Baru

Sama seperti sebelumnya, tambahkan item ke daftar baru Anda. Ini menunjukkan daftar dimulai ulang pada nomor yang ditentukan.

```csharp
builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();
```

## Langkah 6: Simpan Dokumen Anda

Terakhir, simpan dokumen Anda ke direktori yang Anda tentukan.

```csharp
builder.Document.Save(dataDir + "WorkingWithList.RestartListNumber.docx");
```

## Kesimpulan

Memulai ulang nomor daftar di dokumen Word menggunakan Aspose.Words untuk .NET sangatlah mudah dan sangat berguna. Baik Anda membuat laporan, membuat dokumen terstruktur, atau hanya memerlukan kontrol yang lebih baik atas daftar Anda, teknik ini siap membantu Anda.

## FAQ

### Bisakah saya menggunakan templat daftar lain selain NumberArabicParenthesis?

Sangat! Aspose.Words menawarkan berbagai templat daftar seperti poin, huruf, angka Romawi, dan banyak lagi. Anda dapat memilih salah satu yang paling sesuai dengan kebutuhan Anda.

### Bagaimana cara mengubah level daftar?

 Anda dapat mengubah tingkat daftar dengan memodifikasi`ListLevels` milik. Misalnya,`list1.ListLevels[1]` akan mengacu pada tingkat kedua dari daftar.

### Bisakah saya memulai kembali penomoran di nomor mana pun?

 Ya, Anda dapat mengatur angka awal ke nilai integer apa pun menggunakan`StartAt` properti tingkat daftar.

### Apakah mungkin untuk memiliki format yang berbeda untuk tingkat daftar yang berbeda?

Memang! Setiap tingkat daftar dapat memiliki pengaturan pemformatannya sendiri, seperti font, perataan, dan gaya penomoran.

### Bagaimana jika saya ingin melanjutkan penomoran dari daftar sebelumnya dan bukan memulai ulang?

Jika Anda ingin melanjutkan penomoran, Anda tidak perlu membuat salinan daftarnya. Cukup lanjutkan menambahkan item ke daftar asli.


