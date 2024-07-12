---
title: Sisipkan Bagan Area ke dalam Dokumen Word
linktitle: Sisipkan Bagan Area ke dalam Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyisipkan bagan area ke dalam dokumen menggunakan Aspose.Words untuk .NET. Tambahkan data seri dan simpan dokumen dengan bagan.
type: docs
weight: 10
url: /id/net/programming-with-charts/insert-area-chart/
---
## Perkenalan

Selamat datang di panduan langkah demi langkah tentang cara menyisipkan bagan area ke dalam dokumen Word menggunakan Aspose.Words untuk .NET. Baik Anda seorang pengembang berpengalaman atau baru memulai, tutorial ini akan memandu Anda melalui semua yang perlu Anda ketahui untuk membuat bagan area yang menakjubkan dan informatif di dokumen Word Anda. Kami akan membahas prasyaratnya, menunjukkan cara mengimpor namespace yang diperlukan, dan memandu Anda melalui setiap langkah proses dengan instruksi yang jelas dan mudah diikuti.

## Prasyarat

Sebelum kita mendalaminya, pastikan Anda memiliki semua yang dibutuhkan untuk memulai:

1.  Aspose.Words for .NET: Pastikan Anda telah menginstal Aspose.Words for .NET. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/words/net/).
2. .NET Framework: Pastikan Anda telah menginstal .NET Framework di mesin Anda.
3. IDE: Lingkungan Pengembangan Terpadu (IDE) seperti Visual Studio untuk menulis dan mengeksekusi kode Anda.
4. Pengetahuan C# Dasar: Pemahaman dasar tentang pemrograman C# akan sangat membantu.

Setelah Anda memiliki prasyarat ini, Anda siap untuk mulai membuat bagan area yang indah di dokumen Word Anda.

## Impor Namespace

Hal pertama yang pertama, mari impor namespace yang diperlukan. Namespace ini menyediakan kelas dan metode yang diperlukan untuk bekerja dengan dokumen dan bagan Word di Aspose.Words untuk .NET.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System;
```

Sekarang kita telah mengimpor namespace penting, mari beralih ke pembuatan dokumen dan menyisipkan diagram area langkah demi langkah.

## Langkah 1: Buat Dokumen Word Baru

Mari kita mulai dengan membuat dokumen Word baru. Ini akan menjadi dasar dimana kita akan memasukkan grafik area kita.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
```

 Pada langkah ini, kami menginisialisasi yang baru`Document` objek yang mewakili dokumen Word kita.

## Langkah 2: Gunakan DocumentBuilder untuk Menyisipkan Bagan

 Selanjutnya, kita akan menggunakan`DocumentBuilder` kelas untuk memasukkan bagan area ke dalam dokumen kita.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
```

 Di sini, kami membuat a`DocumentBuilder` objek dan menggunakannya untuk memasukkan bagan area dengan dimensi tertentu (432x252) ke dalam dokumen kita.

## Langkah 3: Akses Objek Bagan

 Setelah memasukkan grafik, kita perlu mengakses`Chart` objek untuk menyesuaikan bagan area kami.

```csharp
Chart chart = shape.Chart;
```

 Baris kode ini mengambil`Chart` objek dari bentuk yang baru saja kita sisipkan.

## Langkah 4: Tambahkan Data Seri ke Bagan

Sekarang, saatnya menambahkan beberapa data ke grafik kita. Kami akan menambahkan rangkaian dengan tanggal dan nilai yang sesuai.

```csharp
chart.Series.Add("Aspose Series 1", new []
{
    new DateTime(2002, 05, 01),
    new DateTime(2002, 06, 01),
    new DateTime(2002, 07, 01),
    new DateTime(2002, 08, 01),
    new DateTime(2002, 09, 01)
}, 
new double[] { 32, 32, 28, 12, 15 });
```

Pada langkah ini, kita menambahkan rangkaian bernama "Aspose Seri 1" dengan serangkaian tanggal dan nilai yang sesuai.

## Langkah 5: Simpan Dokumen

Terakhir, kita akan menyimpan dokumen kita dengan bagan area yang disisipkan.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

Baris kode ini menyimpan dokumen ke direktori tertentu dengan nama file tertentu.

## Kesimpulan

Selamat! Anda telah berhasil menyisipkan bagan area ke dalam dokumen Word menggunakan Aspose.Words untuk .NET. Panduan ini telah memandu Anda melalui setiap langkah, mulai dari menyiapkan lingkungan hingga menyimpan dokumen akhir. Dengan Aspose.Words untuk .NET, Anda dapat membuat berbagai macam bagan dan elemen kompleks lainnya di dokumen Word Anda, menjadikan laporan dan presentasi Anda lebih dinamis dan informatif.

## FAQ

### Bisakah saya menggunakan Aspose.Words untuk .NET dengan bahasa .NET lainnya?
Ya, Aspose.Words untuk .NET mendukung bahasa .NET lainnya seperti VB.NET.

### Apakah mungkin untuk menyesuaikan tampilan grafik?
Sangat! Aspose.Words for .NET menyediakan opsi ekstensif untuk menyesuaikan tampilan bagan Anda.

### Bisakah saya menambahkan beberapa bagan ke satu dokumen Word?
Ya, Anda bisa menyisipkan bagan sebanyak yang Anda perlukan ke dalam satu dokumen Word.

### Apakah Aspose.Words untuk .NET mendukung tipe bagan lainnya?
Ya, Aspose.Words untuk .NET mendukung berbagai jenis bagan termasuk batang, garis, pai, dan banyak lagi.

### Di mana saya bisa mendapatkan lisensi sementara untuk Aspose.Words untuk .NET?
 Anda dapat memperoleh lisensi sementara dari[Di Sini](https://purchase.aspose.com/temporary-license/).