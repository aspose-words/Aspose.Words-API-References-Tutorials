---
title: Masukkan Tabel Secara Langsung
linktitle: Masukkan Tabel Secara Langsung
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyisipkan tabel langsung ke dokumen Word menggunakan Aspose.Words untuk .NET. Ikuti panduan langkah demi langkah kami yang terperinci untuk menyederhanakan pembuatan dokumen Anda.
type: docs
weight: 10
url: /id/net/programming-with-tables/insert-table-directly/
---
## Perkenalan
Membuat tabel secara terprogram bisa menjadi sebuah tantangan, terutama ketika berhadapan dengan struktur dokumen yang kompleks. Tapi jangan khawatir, kami di sini untuk menguraikannya untuk Anda! Dalam panduan ini, kita akan memandu langkah-langkah menyisipkan tabel langsung ke dokumen Word menggunakan Aspose.Words untuk .NET. Baik Anda seorang pengembang berpengalaman atau baru memulai, tutorial ini akan membantu Anda menguasai prosesnya dengan mudah.

## Prasyarat

Sebelum mendalami kodenya, pastikan Anda memiliki semua yang Anda perlukan untuk memulai. Berikut daftar periksa singkatnya:

1.  Perpustakaan Aspose.Words untuk .NET: Pastikan Anda telah mengunduh dan menginstal perpustakaan Aspose.Words untuk .NET. Anda bisa mendapatkannya dari[Unduh Halaman](https://releases.aspose.com/words/net/).
2. Lingkungan Pengembangan: Lingkungan pengembangan seperti Visual Studio.
3. Pengetahuan Dasar C#: Memahami dasar-dasar pemrograman C#.
4. Direktori Dokumen: Jalur direktori tempat Anda menyimpan dokumen.

Dengan prasyarat ini, Anda siap untuk mulai membuat kode!

## Impor Namespace

Pertama, mari impor namespace yang diperlukan. Namespace ini akan memberi kita kelas dan metode yang diperlukan untuk bekerja dengan dokumen Word.

```csharp
using System;
using System.Drawing;
using Aspose.Words;
using Aspose.Words.Tables;
```

Sekarang kita sudah memiliki namespace, mari beralih ke bagian yang menarik—membuat dan menyisipkan tabel langsung ke dalam dokumen Word.

## Langkah 1: Menyiapkan Dokumen

Mari kita mulai dengan menyiapkan dokumen Word baru. Di sinilah tabel kita akan disisipkan.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
```

 Kode ini menginisialisasi dokumen Word baru. Anda harus menggantinya`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda.

## Langkah 2: Membuat Objek Tabel

Selanjutnya, kita membuat objek tabel. Di sinilah kita akan menentukan struktur tabel kita.

```csharp
// Kita mulai dengan membuat objek tabel. Perhatikan bahwa kita harus meneruskan objek dokumen
// ke konstruktor setiap node. Hal ini karena setiap node yang kita buat harus dimiliki
// ke beberapa dokumen.
Table table = new Table(doc);
doc.FirstSection.Body.AppendChild(table);
```

Di sini, kita membuat tabel baru dan menambahkannya ke badan bagian pertama dokumen kita.

## Langkah 3: Menambahkan Baris dan Sel

Sebuah tabel terdiri dari baris dan sel. Mari tambahkan elemen ini langkah demi langkah.

### Menambahkan Baris

```csharp
// Di sini kita dapat memanggil PastikanMinimum untuk membuat baris dan sel untuk kita. Metode ini digunakan
// untuk memastikan bahwa node yang ditentukan valid. Dalam hal ini, tabel yang valid harus memiliki setidaknya satu Baris dan satu sel.
// Sebagai gantinya, kita akan menangani sendiri pembuatan baris dan tabelnya.
// Ini akan menjadi cara terbaik untuk melakukan ini jika kita membuat tabel di dalam suatu algoritma.
Row row = new Row(doc);
row.RowFormat.AllowBreakAcrossPages = true;
table.AppendChild(row);
```

Kode ini membuat baris baru dan menambahkannya ke tabel kita.

### Menambahkan Sel ke Baris

Sekarang, mari tambahkan beberapa sel ke baris kita. 

```csharp
Cell cell = new Cell(doc);
cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
cell.CellFormat.Width = 80;
cell.AppendChild(new Paragraph(doc));
cell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 1 Text"));
row.AppendChild(cell);
```

Dalam cuplikan ini, kita membuat sel, mengatur warna latar belakangnya menjadi biru muda, dan menentukan lebarnya. Lalu, kita menambahkan sebuah paragraf dan tanda run ke sel untuk menampung teks kita.

## Langkah 4: Mengkloning Sel

Untuk mempercepat proses penambahan sel, kita bisa mengkloning sel yang sudah ada.

```csharp
// Kami kemudian akan mengulangi proses untuk sel dan baris lain dalam tabel.
// Kita juga dapat mempercepatnya dengan mengkloning sel dan baris yang ada.
row.AppendChild(cell.Clone(false));
row.LastCell.AppendChild(new Paragraph(doc));
row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 2 Text"));
```

Kode ini mengkloning sel yang ada dan menambahkannya ke baris. Kami kemudian menambahkan paragraf dan menjalankan ke sel baru.

## Langkah 5: Menerapkan Pengaturan Pas Otomatis

Terakhir, mari terapkan pengaturan penyesuaian otomatis ke tabel kita untuk memastikan kolom memiliki lebar tetap.

```csharp
// Kami sekarang dapat menerapkan pengaturan penyesuaian otomatis apa pun.
table.AutoFit(AutoFitBehavior.FixedColumnWidths);
```

## Langkah 6: Menyimpan Dokumen

Dengan tabel kita yang sudah diatur sepenuhnya, saatnya menyimpan dokumen.

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

Kode ini menyimpan dokumen dengan tabel yang disisipkan.

## Kesimpulan

Selamat! Anda telah berhasil menyisipkan tabel langsung ke dokumen Word menggunakan Aspose.Words untuk .NET. Proses ini dapat digunakan untuk membuat tabel kompleks secara terprogram, membuat tugas otomatisasi dokumen Anda menjadi lebih mudah. Baik Anda membuat laporan, faktur, atau jenis dokumen lainnya, memahami cara memanipulasi tabel adalah keterampilan yang penting.

## FAQ

### Bagaimana cara mengunduh Aspose.Words untuk .NET?
 Anda dapat mengunduh Aspose.Words untuk .NET dari[Unduh Halaman](https://releases.aspose.com/words/net/).

### Bisakah saya mencoba Aspose.Words untuk .NET sebelum membeli?
 Ya, Anda dapat meminta a[uji coba gratis](https://releases.aspose.com/) untuk mengevaluasi perpustakaan sebelum membeli.

### Bagaimana cara membeli Aspose.Words untuk .NET?
 Anda dapat membeli Aspose.Words untuk .NET dari[halaman pembelian](https://purchase.aspose.com/buy).

### Di mana saya dapat menemukan dokumentasi Aspose.Words untuk .NET?
 Dokumentasi tersedia[Di Sini](https://reference.aspose.com/words/net/).

### Bagaimana jika saya memerlukan dukungan saat menggunakan Aspose.Words untuk .NET?
 Untuk dukungan, Anda dapat mengunjungi[Aspose.Forum kata-kata](https://forum.aspose.com/c/words/8).