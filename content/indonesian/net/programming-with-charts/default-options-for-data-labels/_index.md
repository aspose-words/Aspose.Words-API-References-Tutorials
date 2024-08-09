---
title: Tetapkan Opsi Default Untuk Label Data Dalam Bagan
linktitle: Tetapkan Opsi Default Untuk Label Data Dalam Bagan
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengatur opsi default untuk label data dalam bagan menggunakan Aspose.Words untuk .NET. Ikuti panduan langkah demi langkah kami untuk membuat dan menyesuaikan grafik dengan mudah.
type: docs
weight: 10
url: /id/net/programming-with-charts/default-options-for-data-labels/
---
## Perkenalan

Hai! Apakah Anda bersemangat untuk terjun ke dunia otomatisasi dokumen? Hari ini, kita akan mempelajari cara menggunakan Aspose.Words untuk .NET untuk membuat dokumen menakjubkan secara terprogram. Aspose.Words adalah perpustakaan canggih yang memungkinkan Anda memanipulasi dokumen Word dengan mudah, dan dalam tutorial ini, kita akan fokus pada pengaturan opsi default untuk label data dalam bagan. Baik Anda seorang pengembang berpengalaman atau pemula, panduan ini akan memandu Anda melalui setiap langkah agar Anda siap dan berjalan dalam waktu singkat.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki semua yang Anda perlukan untuk mengikuti tutorial ini. Berikut daftar periksa singkatnya:

- Visual Studio atau IDE lain yang kompatibel dengan .NET: Di sinilah Anda akan menulis dan menjalankan kode Anda.
-  Aspose.Words untuk .NET: Anda bisa[unduh versi terbaru](https://releases.aspose.com/words/net/) dan menginstalnya di proyek Anda.
- Pengetahuan dasar pemrograman C#: Meskipun panduan ini ramah bagi pemula, sedikit pemahaman tentang C# akan sangat membantu.
- .NET Framework terinstal: Pastikan Anda telah menyiapkan .NET Framework di mesin Anda.
-  Lisensi sementara untuk Aspose.Words: Dapatkan satu[Di Sini](https://purchase.aspose.com/temporary-license/) untuk membuka kunci fungsionalitas penuh.

Setelah Anda menyelesaikan prasyarat ini, kami siap memulai!

## Impor Namespace

Hal pertama yang pertama, mari siapkan proyek kita dan impor namespace yang diperlukan. Namespace ini sangat penting untuk mengakses fungsionalitas Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.ReportingServices;
```

## Langkah 1: Buat Dokumen Baru


 Perjalanan dimulai dengan membuat dokumen baru dan menginisialisasi a`DocumentBuilder` . Itu`DocumentBuilder` kelas menyediakan serangkaian metode untuk memanipulasi konten dokumen dengan mudah.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Buat dokumen baru
Document doc = new Document();

// Inisialisasi DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);
```

### Penjelasan

 Pada langkah ini, kita telah menyiapkan dokumen dan pembuat yang akan kita gunakan untuk menyisipkan dan memformat konten kita. Itu`dataDir` variabel menyimpan jalur di mana kita akan menyimpan dokumen akhir kita.

## Langkah 2: Sisipkan Bagan

 Selanjutnya, kita akan menambahkan diagram lingkaran ke dokumen kita. Itu`InsertChart` metode`DocumentBuilder` kelas membuat ini sangat mudah.

```csharp
// Sisipkan diagram lingkaran
Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);

// Akses objek bagan
Chart chart = shape.Chart;
```

### Penjelasan

Di sini, kami memasukkan diagram lingkaran ke dalam dokumen kami. Itu`InsertChart` metode memerlukan jenis bagan, lebar, dan tinggi sebagai parameter. Setelah memasukkan grafik, kita mengakses objek grafik untuk memanipulasinya lebih lanjut.

## Langkah 3: Sesuaikan Seri Bagan

Sekarang, kami akan menghapus semua rangkaian yang ada di bagan dan menambahkan rangkaian khusus kami. Seri ini akan mewakili titik data kami.

```csharp
// Hapus rangkaian bagan yang ada
chart.Series.Clear();

// Tambahkan seri baru ke bagan
ChartSeries series = chart.Series.Add("Aspose Series 1",
    new string[] { "Category 1", "Category 2", "Category 3" },
    new double[] { 2.7, 3.2, 0.8 });
```

### Penjelasan

Pada langkah ini, kami memastikan grafik kami kosong dengan menghapus semua rangkaian yang sudah ada sebelumnya. Kemudian, kami menambahkan rangkaian baru dengan kategori dan nilai khusus, yang akan ditampilkan di diagram lingkaran kami.

## Langkah 4: Tetapkan Opsi Default untuk Label Data

Label data sangat penting untuk membuat bagan Anda informatif. Kami akan mengatur opsi untuk menampilkan persentase, nilai, dan menyesuaikan pemisah.

```csharp
// Akses koleksi label data
ChartDataLabelCollection labels = series.DataLabels;

// Tetapkan opsi label data
labels.ShowPercentage = true;
labels.ShowValue = true;
labels.ShowLeaderLines = false;
labels.Separator = " - ";
```

### Penjelasan

 Di sini, kami mengakses`DataLabels`properti seri kami untuk menyesuaikan tampilan dan informasi yang ditampilkan pada setiap label data. Kami telah memilih untuk menampilkan persentase dan nilai, menyembunyikan garis pemimpin, dan menetapkan pemisah khusus.

## Langkah 5: Simpan Dokumen

Terakhir, kami akan menyimpan dokumen kami ke direktori yang ditentukan. Langkah ini memastikan bahwa semua perubahan kami ditulis ke file.

```csharp
// Simpan dokumennya
doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

### Penjelasan

 Pada langkah terakhir ini, kami menyimpan dokumen kami menggunakan`Save` metode. Dokumen akan disimpan di direktori yang ditentukan oleh`dataDir`, dengan nama "WorkingWithCharts.DefaultOptionsForDataLabels.docx".

## Kesimpulan

Dan itu dia! Anda telah berhasil membuat dokumen Word dengan diagram lingkaran yang disesuaikan menggunakan Aspose.Words untuk .NET. Pustaka canggih ini memudahkan pembuatan dan manipulasi dokumen secara otomatis, sehingga menghemat waktu dan tenaga Anda. Baik Anda membuat laporan, faktur, atau jenis dokumen lainnya, Aspose.Words siap membantu Anda.

 Jangan ragu untuk menjelajahinya[Dokumentasi Aspose.Words](https://reference.aspose.com/words/net/) untuk lebih banyak fitur dan contoh. Selamat membuat kode!

## FAQ

### Bisakah saya menggunakan Aspose.Words secara gratis?
Anda dapat menggunakan Aspose.Words secara gratis dengan a[izin sementara](https://purchase.aspose.com/temporary-license/) atau jelajahi fitur-fiturnya menggunakan[uji coba gratis](https://releases.aspose.com/).

### Bagaimana cara mendapatkan dukungan untuk Aspose.Words?
 Anda bisa mendapatkan dukungan melalui[Forum dukungan Aspose.Words](https://forum.aspose.com/c/words/8).

### Bisakah saya menambahkan jenis grafik lainnya?
 Ya, Aspose.Words mendukung berbagai jenis bagan seperti bagan batang, garis, dan kolom. Periksa[dokumentasi](https://reference.aspose.com/words/net/) untuk lebih jelasnya.

### Apakah Aspose.Words kompatibel dengan .NET Core?
 Ya, Aspose.Words kompatibel dengan .NET Core. Anda dapat menemukan informasi lebih lanjut di[dokumentasi](https://reference.aspose.com/words/net/).

### Bagaimana cara membeli lisensi untuk Aspose.Words?
 Anda dapat membeli lisensi dari[Asumsikan toko](https://purchase.aspose.com/buy).

