---
title: Ekspor Ke Penurunan Harga Dengan Penyelarasan Isi Tabel
linktitle: Ekspor Ke Penurunan Harga Dengan Penyelarasan Isi Tabel
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengekspor dokumen Word ke Markdown dengan tabel yang disejajarkan menggunakan Aspose.Words untuk .NET. Ikuti panduan langkah demi langkah kami untuk tabel penurunan harga yang sempurna.
type: docs
weight: 10
url: /id/net/programming-with-markdownsaveoptions/export-into-markdown-with-table-content-alignment/
---
## Perkenalan

Hai! Pernah bertanya-tanya bagaimana cara mengekspor dokumen Word Anda ke format Markdown dengan tabel yang selaras sempurna? Baik Anda seorang pengembang yang mengerjakan dokumentasi atau hanya seseorang yang menyukai Markdown, panduan ini cocok untuk Anda. Kami akan mendalami seluk beluk penggunaan Aspose.Words untuk .NET untuk mencapai hal ini. Siap mengubah tabel Word Anda menjadi tabel Markdown yang tersusun rapi? Mari kita mulai!

## Prasyarat

Sebelum kita mendalami kodenya, ada beberapa hal yang perlu Anda siapkan:

1.  Perpustakaan Aspose.Words untuk .NET: Pastikan Anda memiliki perpustakaan Aspose.Words untuk .NET. Anda dapat mengunduhnya dari[Halaman Rilis Aspose](https://releases.aspose.com/words/net/).
2. Lingkungan Pengembangan: Siapkan lingkungan pengembangan Anda. Visual Studio adalah pilihan populer untuk pengembangan .NET.
3. Pengetahuan Dasar C#: Memahami C# sangat penting karena kita akan menulis kode dalam bahasa ini.
4. Contoh Dokumen Word: Miliki dokumen Word yang dapat Anda gunakan untuk pengujian.

## Impor Namespace

Sebelum kita mulai coding, mari impor namespace yang diperlukan. Ini akan memberi kita akses ke kelas dan metode Aspose.Words yang akan kita gunakan.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Langkah 1: Inisialisasi Dokumen dan DocumentBuilder

Hal pertama yang pertama, kita perlu membuat dokumen Word baru dan menginisialisasi a`DocumentBuilder` keberatan untuk mulai membuat dokumen kita.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buat dokumen baru.
Document doc = new Document();

// Inisialisasi DocumentBuilder.
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 2: Sisipkan Sel dan Sejajarkan Konten

Selanjutnya, kita akan memasukkan beberapa sel ke dalam dokumen kita dan mengatur perataannya. Hal ini penting untuk memastikan bahwa ekspor penurunan harga tetap berada pada jalur yang benar.

```csharp
// Sisipkan sel dan atur perataan ke kanan.
builder.InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Cell1");

// Masukkan sel lain dan atur perataan ke tengah.
builder.InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Write("Cell2");
```

## Langkah 3: Tetapkan Penyelarasan Isi Tabel untuk Ekspor Penurunan Harga

 Sekarang saatnya untuk mengkonfigurasi`MarkdownSaveOptions` untuk mengontrol perataan konten tabel dalam file Markdown yang diekspor. Kami akan menyimpan dokumen dengan pengaturan perataan berbeda untuk melihat cara kerjanya.

```csharp
// Buat objek MarkdownSaveOptions.
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
{
    TableContentAlignment = TableContentAlignment.Left
};

// Simpan dokumen dengan rata kiri.
doc.Save(dataDir + "LeftTableContentAlignment.md", saveOptions);

// Ubah perataan ke kanan dan simpan.
saveOptions.TableContentAlignment = TableContentAlignment.Right;
doc.Save(dataDir + "RightTableContentAlignment.md", saveOptions);

// Ubah perataan ke tengah dan simpan.
saveOptions.TableContentAlignment = TableContentAlignment.Center;
doc.Save(dataDir + "CenterTableContentAlignment.md", saveOptions);
```

## Langkah 4: Gunakan Penyelarasan Konten Tabel Otomatis

 Itu`Auto`opsi perataan mengambil perataan dari paragraf pertama di kolom tabel terkait. Ini bisa berguna ketika Anda memiliki perataan campuran dalam satu tabel.

```csharp
// Atur perataan ke Otomatis.
saveOptions.TableContentAlignment = TableContentAlignment.Auto;

// Simpan dokumen dengan penyelarasan otomatis.
doc.Save(dataDir + "AutoTableContentAlignment.md", saveOptions);
```

## Kesimpulan

Dan itu dia! Mengekspor dokumen Word ke Markdown dengan tabel yang disejajarkan menggunakan Aspose.Words untuk .NET sangatlah mudah setelah Anda mengetahui cara melakukannya. Pustaka canggih ini memudahkan Anda mengontrol pemformatan dan perataan tabel, memastikan dokumen Markdown Anda terlihat sesuai keinginan Anda. Selamat membuat kode!

## FAQ

### Apa itu Aspose.Words untuk .NET?
Aspose.Words untuk .NET adalah perpustakaan canggih yang memungkinkan pengembang membuat, memodifikasi, mengonversi, dan mengekspor dokumen Word secara terprogram.

### Bisakah saya mengatur perataan berbeda untuk kolom berbeda dalam tabel yang sama?
 Ya, dengan menggunakan`Auto` opsi perataan, Anda dapat memiliki perataan berbeda berdasarkan paragraf pertama di setiap kolom.

### Apakah saya memerlukan lisensi untuk menggunakan Aspose.Words untuk .NET?
 Ya, Aspose.Words untuk .NET memerlukan lisensi untuk fungsionalitas penuh. Anda bisa mendapatkan[izin sementara](https://purchase.aspose.com/temporary-license/) untuk evaluasi.

### Apakah mungkin mengekspor elemen dokumen lain ke Markdown menggunakan Aspose.Words?
Ya, Aspose.Words mendukung ekspor berbagai elemen seperti judul, daftar, dan gambar ke format penurunan harga.

### Di mana saya bisa mendapatkan dukungan jika saya mengalami masalah?
 Anda bisa mendapatkan dukungan dari[Forum Dukungan Aspose.Words](https://forum.aspose.com/c/words/8).
