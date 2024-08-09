---
title: Penggabungan Horisontal
linktitle: Penggabungan Horisontal
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menggabungkan sel secara horizontal dalam dokumen Word menggunakan Aspose.Words untuk .NET dengan tutorial langkah demi langkah yang mendetail ini.
type: docs
weight: 10
url: /id/net/programming-with-tables/horizontal-merge/
---
## Perkenalan

Hai! Siap terjun ke dunia Aspose.Words untuk .NET? Hari ini, kita akan membahas fitur yang sangat berguna: penggabungan horizontal dalam tabel. Ini mungkin terdengar agak teknis, tapi jangan khawatir, saya mendukung Anda. Di akhir tutorial ini, Anda akan mahir dalam menggabungkan sel di dokumen Word Anda secara terprogram. Jadi, mari menyingsingkan lengan baju dan mulai!

## Prasyarat

Sebelum kita masuk ke seluk beluknya, ada beberapa hal yang perlu Anda siapkan:

1. Perpustakaan Aspose.Words for .NET: Jika Anda belum melakukannya, unduh perpustakaan Aspose.Words for .NET. Anda bisa mengambilnya[Di Sini](https://releases.aspose.com/words/net/).
2. Lingkungan Pengembangan: Pastikan Anda memiliki lingkungan pengembangan yang sesuai, seperti Visual Studio.
3. Pengetahuan Dasar C#: Pemahaman dasar tentang pemrograman C# akan bermanfaat.

Setelah Anda menyelesaikannya, Anda siap berangkat!

## Impor Namespace

Sebelum mendalami kodenya, pastikan kita telah mengimpor namespace yang diperlukan. Dalam proyek C# Anda, pastikan untuk menyertakan:

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

Baiklah, mari kita uraikan proses penggabungan sel tabel secara horizontal dalam dokumen Word menggunakan Aspose.Words untuk .NET.

## Langkah 1: Menyiapkan Dokumen Anda

 Hal pertama yang pertama, kita perlu membuat dokumen Word baru dan menginisialisasinya`DocumentBuilder`:

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Cuplikan kode ini menyiapkan dokumen baru dan menyiapkan`DocumentBuilder` untuk tindakan.

## Langkah 2: Memasukkan Sel Pertama

Selanjutnya, kita mulai dengan menyisipkan sel pertama dan menandainya untuk penggabungan horizontal:

```csharp
builder.InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.First;
builder.Write("Text in merged cells.");
```

 Di sini, kami memasukkan sel baru dan mengaturnya`HorizontalMerge`properti ke`CellMerge.First`, menunjukkan bahwa sel ini adalah awal dari rangkaian sel yang digabungkan.

## Langkah 3: Memasukkan Sel yang Digabung

Sekarang, kita masukkan sel yang akan digabungkan dengan yang sebelumnya:

```csharp
builder.InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.Previous;
builder.EndRow();
```

 Sel ini diatur untuk digabungkan dengan sel sebelumnya dengan menggunakan`CellMerge.Previous` . Perhatikan bagaimana kita mengakhiri barisnya dengan`builder.EndRow()`.

## Langkah 4: Memasukkan Sel yang Tidak Digabung

Untuk mengilustrasikan perbedaannya, mari masukkan beberapa sel yang tidak digabungkan:

```csharp
builder.InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.None;
builder.Write("Text in one cell.");
builder.InsertCell();
builder.Write("Text in another cell.");
builder.EndRow();
```

Di sini, kami menyisipkan dua sel tanpa penggabungan horizontal. Ini menunjukkan bagaimana sel berperilaku ketika mereka bukan bagian dari urutan yang digabungkan.

## Langkah 5: Menyelesaikan Tabel

Terakhir, kami mengakhiri tabel dan menyimpan dokumen:

```csharp
builder.EndTable();
doc.Save(dataDir + "WorkingWithTables.HorizontalMerge.docx");
```

Cuplikan kode ini melengkapi tabel dan menyimpan dokumen ke direktori yang ditentukan.

## Kesimpulan

Dan itu dia! Anda baru saja menguasai seni menggabungkan sel secara horizontal dalam dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti langkah-langkah ini, Anda dapat membuat struktur tabel yang kompleks dengan mudah. Teruslah bereksperimen dan jelajahi kemampuan Aspose.Words untuk menjadikan dokumen Anda dinamis dan fleksibel sesuai kebutuhan. Selamat membuat kode!

## FAQ

### Apa itu Aspose.Words untuk .NET?
Aspose.Words untuk .NET adalah perpustakaan canggih yang memungkinkan pengembang membuat, mengedit, dan memanipulasi dokumen Word secara terprogram dalam aplikasi .NET.

### Bisakah saya menggabungkan sel secara vertikal dengan Aspose.Words untuk .NET?
 Ya, Anda juga dapat menggabungkan sel secara vertikal dengan menggunakan`CellFormat.VerticalMerge` milik.

### Apakah Aspose.Words untuk .NET gratis untuk digunakan?
 Aspose.Words untuk .NET menawarkan uji coba gratis, tetapi untuk fungsionalitas penuh, Anda perlu membeli lisensi. Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).

### Bagaimana saya bisa mempelajari lebih lanjut tentang Aspose.Words untuk .NET?
 Anda dapat menjelajahi dokumentasi terperinci[Di Sini](https://reference.aspose.com/words/net/).

### Di mana saya bisa mendapatkan dukungan untuk Aspose.Words untuk .NET?
 Untuk pertanyaan atau masalah apa pun, Anda dapat mengunjungi forum dukungan Aspose[Di Sini](https://forum.aspose.com/c/words/8).