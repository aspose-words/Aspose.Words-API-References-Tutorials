---
title: Sesuaikan Seri Bagan Tunggal Dalam Bagan
linktitle: Sesuaikan Seri Bagan Tunggal Dalam Bagan
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengkustomisasi rangkaian bagan tunggal dalam dokumen Word menggunakan Aspose.Words untuk .NET. Ikuti panduan langkah demi langkah kami untuk pengalaman yang lancar.
type: docs
weight: 10
url: /id/net/programming-with-charts/single-chart-series/
---
## Perkenalan

Hai! Pernahkah Anda ingin meramaikan dokumen Word Anda dengan beberapa bagan yang menarik? Nah, Anda berada di tempat yang tepat! Hari ini, kita mendalami dunia Aspose.Words untuk .NET guna menyesuaikan rangkaian bagan tunggal dalam bagan. Baik Anda seorang profesional berpengalaman atau baru memulai, panduan ini akan memandu Anda melalui seluruh proses langkah demi langkah. Jadi, kencangkan sabuk pengaman dan mari kita mulai membuat grafik!

## Prasyarat

Sebelum kita mulai, pastikan kita memiliki semua yang kita butuhkan. Berikut daftar periksa singkatnya:

1.  Aspose.Words untuk .NET Library: Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/words/net/).
2. Visual Studio: Versi terbaru apa pun akan berhasil.
3. Pemahaman Dasar tentang C#: Tidak ada yang terlalu mewah, hanya dasar-dasarnya saja yang cukup.

## Impor Namespace

Hal pertama yang pertama, kita perlu mengimpor namespace yang diperlukan. Ini seperti menyiapkan panggung sebelum pertunjukan besar.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Charts;
```

## Langkah 1: Siapkan Dokumen Anda

Mari kita mulai dengan menyiapkan dokumen Word baru. Di sinilah semua keajaiban akan terjadi.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; // Jalur ke direktori dokumen Anda
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 2: Sisipkan Bagan

Selanjutnya, kita akan menyisipkan diagram garis ke dalam dokumen kita. Anggap saja ini seperti menambahkan kanvas tempat kita akan melukis karya agung kita.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## Langkah 3: Akses Seri Bagan

Sekarang, mari kita akses rangkaian grafiknya. Di sinilah kami akan mulai menyesuaikan.

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];
```

## Langkah 4: Ganti Nama Seri Bagan

Mari beri rangkaian bagan kita beberapa nama yang bermakna. Ini seperti memberi label pada kuas Anda sebelum mulai melukis.

```csharp
series0.Name = "Chart Series Name 1";
series1.Name = "Chart Series Name 2";
```

## Langkah 5: Ratakan Garisnya

Ingin garis-garis itu terlihat halus dan ramping? Mari kita lakukan itu menggunakan spline Catmull-Rom.

```csharp
series0.Smooth = true;
series1.Smooth = true;
```

## Langkah 6: Tangani Nilai Negatif

Terkadang, data bisa negatif. Mari kita pastikan bagan kita menangani hal itu dengan baik.

```csharp
series0.InvertIfNegative = true;
```

## Langkah 7: Sesuaikan Penanda

Penanda itu seperti titik-titik kecil di garis kita. Mari kita buat mereka menonjol.

```csharp
series0.Marker.Symbol = MarkerSymbol.Circle;
series0.Marker.Size = 15;
series1.Marker.Symbol = MarkerSymbol.Star;
series1.Marker.Size = 10;
```

## Langkah 8: Simpan Dokumen Anda

Terakhir, mari simpan dokumen kita. Di sinilah kami mengagumi pekerjaan kami.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

## Kesimpulan

Dan itu dia! Anda telah berhasil mengkustomisasi satu rangkaian bagan dalam dokumen Word menggunakan Aspose.Words untuk .NET. Cukup keren, bukan? Ini hanyalah puncak gunung es; masih banyak lagi yang dapat Anda lakukan dengan Aspose.Words. Jadi, teruslah bereksperimen dan buat dokumen keren!

## FAQ

### Apa itu Aspose.Words untuk .NET?
Aspose.Words untuk .NET adalah perpustakaan canggih yang memungkinkan Anda membuat, mengedit, mengonversi, dan memanipulasi dokumen Word secara terprogram.

### Bisakah saya menggunakan Aspose.Words secara gratis?
 Ya, Anda bisa mulai dengan a[uji coba gratis](https://releases.aspose.com/).

### Bagaimana cara mendapatkan dukungan untuk Aspose.Words?
 Anda bisa mendapatkan dukungan dari komunitas Aspose di situs mereka[forum](https://forum.aspose.com/c/words/8).

### Apakah mungkin untuk menyesuaikan jenis bagan lainnya?
Sangat! Aspose.Words mendukung berbagai jenis bagan seperti bagan batang, pai, dan sebar.

### Di mana saya dapat menemukan dokumentasi lainnya?
 Lihat[dokumentasi](https://reference.aspose.com/words/net/) untuk panduan dan contoh yang lebih rinci.