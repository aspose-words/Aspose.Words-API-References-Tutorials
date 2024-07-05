---
title: Terapkan Batas Dan Bayangan Pada Paragraf Dalam Dokumen Word
linktitle: Terapkan Batas Dan Bayangan Pada Paragraf Dalam Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Terapkan batas dan bayangan pada paragraf di dokumen Word menggunakan Aspose.Words untuk .NET. Ikuti panduan langkah demi langkah kami untuk menyempurnakan format dokumen Anda.
type: docs
weight: 10
url: /id/net/document-formatting/apply-borders-and-shading-to-paragraph/
---
## Perkenalan

Hai, pernah bertanya-tanya bagaimana cara membuat dokumen Word Anda menonjol dengan batas dan bayangan yang indah? Nah, Anda berada di tempat yang tepat! Hari ini, kita menyelami dunia Aspose.Words untuk .NET untuk meramaikan paragraf kita. Bayangkan dokumen Anda tampak ramping seperti karya desainer profesional hanya dengan beberapa baris kode. Siap untuk memulai? Ayo pergi!

## Prasyarat

Sebelum kita menyingsingkan lengan baju dan menyelami coding, pastikan kita memiliki semua yang kita butuhkan. Inilah daftar periksa singkat Anda:

-  Aspose.Words untuk .NET: Anda harus menginstal perpustakaan ini. Anda dapat mengunduhnya dari[Asumsikan situs web](https://releases.aspose.com/words/net/).
- Lingkungan Pengembangan: Visual Studio atau IDE lain yang mendukung .NET.
- Pengetahuan Dasar C#: Cukup untuk memahami dan mengubah cuplikan kode.
- Lisensi yang Sah: Salah satu a[izin sementara](https://purchase.aspose.com/temporary-license/) atau yang dibeli dari[Berasumsi](https://purchase.aspose.com/buy).

## Impor Namespace

Sebelum beralih ke kode, kita perlu memastikan bahwa kita telah mengimpor namespace yang diperlukan ke dalam proyek kita. Ini membuat semua fitur keren Aspose.Words dapat kami akses.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
using Aspose.Words.Drawing;
using System.Drawing;
```

Sekarang, mari kita bagi prosesnya menjadi langkah-langkah kecil. Setiap langkah akan memiliki judul dan penjelasan rinci. Siap? Ayo pergi!

## Langkah 1: Siapkan Direktori Dokumen Anda

Hal pertama yang pertama, kita memerlukan tempat untuk menyimpan dokumen kita yang diformat dengan indah. Mari atur jalur ke direktori dokumen Anda.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Direktori ini adalah tempat dokumen akhir Anda akan disimpan. Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya di mesin Anda.

## Langkah 2: Buat Dokumen Baru dan DocumentBuilder

 Selanjutnya, kita perlu membuat dokumen baru dan a`DocumentBuilder` obyek. Itu`DocumentBuilder` adalah tongkat ajaib yang memungkinkan kita memanipulasi dokumen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Itu`Document` objek mewakili seluruh dokumen Word kita, dan`DocumentBuilder` membantu kami menambah dan memformat konten.

## Langkah 3: Tentukan Batas Paragraf

Sekarang, mari tambahkan beberapa batas gaya pada paragraf kita. Kami akan menentukan jarak dari teks dan mengatur gaya batas yang berbeda.

```csharp
BorderCollection borders = builder.ParagraphFormat.Borders;
borders.DistanceFromText = 20;
borders[BorderType.Left].LineStyle = LineStyle.Double;
borders[BorderType.Right].LineStyle = LineStyle.Double;
borders[BorderType.Top].LineStyle = LineStyle.Double;
borders[BorderType.Bottom].LineStyle = LineStyle.Double;
```

Di sini, kami menetapkan jarak 20 poin antara teks dan batas. Batas pada semua sisi (kiri, kanan, atas, bawah) dibuat garis ganda. Mewah, bukan?

## Langkah 4: Terapkan Shading pada Paragraf

Perbatasan memang bagus, tapi mari kita tingkatkan dengan beberapa bayangan. Kita akan menggunakan pola silang diagonal dengan perpaduan warna untuk membuat paragraf kita menonjol.

```csharp
Shading shading = builder.ParagraphFormat.Shading;
shading.Texture = TextureIndex.TextureDiagonalCross;
shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;
```

Pada langkah ini, kami menerapkan tekstur silang diagonal dengan karang muda sebagai warna latar belakang dan salmon muda sebagai warna latar depan. Ini seperti mendandani paragraf Anda dengan pakaian desainer!

## Langkah 5: Tambahkan Teks ke Paragraf

Apa jadinya paragraf tanpa teks? Mari tambahkan contoh kalimat untuk melihat pemformatan kita beraksi.

```csharp
builder.Write("I'm a formatted paragraph with double border and nice shading.");
```

Baris ini menyisipkan teks kita ke dalam dokumen. Sederhana, namun kini dibalut dalam bingkai penuh gaya dan latar belakang yang teduh.

## Langkah 6: Simpan Dokumen

Akhirnya, saatnya untuk menyimpan pekerjaan kita. Mari simpan dokumen ke direktori yang ditentukan dengan nama deskriptif.

```csharp
doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");
```

 Ini menyimpan dokumen kita dengan nama`DocumentFormatting.ApplyBordersAndShadingToParagraph.doc` di direktori yang kami tentukan sebelumnya.

## Kesimpulan

Dan itu dia! Hanya dengan beberapa baris kode, kami telah mengubah paragraf biasa menjadi konten yang menarik secara visual. Aspose.Words untuk .NET membuatnya sangat mudah untuk menambahkan pemformatan yang terlihat profesional ke dokumen Anda. Baik Anda sedang menyiapkan laporan, surat, atau dokumen apa pun, trik berikut akan membantu Anda memberikan kesan yang baik. Jadi silakan, cobalah, dan lihat dokumen Anda menjadi nyata!

## FAQ

### Bisakah saya menggunakan gaya garis yang berbeda untuk setiap batas?  
 Sangat! Aspose.Words untuk .NET memungkinkan Anda menyesuaikan setiap batas satu per satu. Atur saja`LineStyle` untuk setiap jenis perbatasan seperti yang ditunjukkan dalam panduan.

### Tekstur bayangan apa lagi yang tersedia?  
 Ada beberapa tekstur yang bisa Anda gunakan, seperti solid, garis horizontal, garis vertikal, dan lainnya. Periksalah[Asumsikan dokumentasi](https://reference.aspose.com/words/net/) untuk daftar lengkap.

### Bagaimana cara mengubah warna tepi?  
 Anda dapat mengatur warna batas menggunakan`Color` properti untuk setiap perbatasan. Misalnya,`borders[BorderType.Left].Color = Color.Red;`.

### Apakah mungkin untuk menerapkan batas dan bayangan pada bagian teks tertentu?  
 Ya, Anda dapat menerapkan batas dan bayangan pada teks tertentu menggunakan`Run` objek di dalam`DocumentBuilder`.

### Bisakah saya mengotomatiskan proses ini untuk beberapa paragraf?  
Tentu saja! Anda dapat mengulang paragraf Anda dan menerapkan pengaturan batas dan bayangan yang sama secara terprogram.
