---
title: Format Aturan Horizontal Dalam Dokumen Word
linktitle: Format Aturan Horizontal Dalam Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyisipkan aturan horizontal yang dapat disesuaikan di dokumen Word menggunakan Aspose.Words untuk .NET. Tingkatkan otomatisasi dokumen Anda.
type: docs
weight: 10
url: /id/net/add-content-using-documentbuilder/horizontal-rule-format/
---
## Perkenalan

Dalam bidang pengembangan .NET, memanipulasi dan memformat dokumen Word secara terprogram bisa menjadi tugas yang menakutkan. Untungnya, Aspose.Words untuk .NET memberikan solusi tangguh, memberdayakan pengembang untuk mengotomatiskan pembuatan, pengeditan, dan pengelolaan dokumen dengan mudah. Artikel ini membahas salah satu fitur penting: memasukkan aturan horizontal ke dalam dokumen Word. Baik Anda seorang pengembang berpengalaman atau baru memulai Aspose.Words, menguasai kemampuan ini akan meningkatkan proses pembuatan dokumen Anda.

## Prasyarat

Sebelum mendalami penerapan aturan horizontal menggunakan Aspose.Words untuk .NET, pastikan Anda memiliki prasyarat berikut:

- Visual Studio: Instal Visual Studio IDE untuk pengembangan .NET.
- Aspose.Words untuk .NET: Unduh dan instal Aspose.Words untuk .NET dari[Di Sini](https://releases.aspose.com/words/net/).
- Pengetahuan Dasar C#: Keakraban dengan dasar-dasar bahasa pemrograman C#.
-  Kelas DocumentBuilder: Pemahaman tentang`DocumentBuilder` kelas di Aspose.Words untuk manipulasi dokumen.

## Impor Namespace

Untuk memulai, impor namespace yang diperlukan dalam proyek C# Anda:

```csharp
using Aspose.Words;
using System.Drawing;
```

Namespace ini menyediakan akses ke kelas Aspose.Words untuk manipulasi dokumen dan kelas .NET standar untuk menangani warna.

Mari kita uraikan proses penambahan aturan horizontal di dokumen Word menggunakan Aspose.Words untuk .NET menjadi langkah-langkah komprehensif:

## Langkah 1: Inisialisasi DocumentBuilder dan Atur Direktori

 Pertama, inisialisasi a`DocumentBuilder` objek dan atur jalur direktori tempat dokumen akan disimpan.

```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY_PATH";
DocumentBuilder builder = new DocumentBuilder();
```

## Langkah 2: Masukkan Aturan Horizontal

 Gunakan`InsertHorizontalRule()` metode`DocumentBuilder` kelas untuk menambahkan aturan horizontal.

```csharp
Shape shape = builder.InsertHorizontalRule();
```

## Langkah 3: Sesuaikan Format Aturan Horizontal

 Akses`HorizontalRuleFormat` properti dari bentuk yang disisipkan untuk menyesuaikan tampilan aturan horizontal.

```csharp
HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;
```

- Alignment: Menentukan perataan aturan horizontal (`HorizontalRuleAlignment.Center` dalam contoh ini).
- LebarPersen: Menetapkan lebar aturan horizontal sebagai persentase lebar halaman (70% dalam contoh ini).
- Tinggi: Mendefinisikan ketinggian aturan horizontal dalam poin (3 poin dalam contoh ini).
- Warna: Mengatur warna aturan horizontal (`Color.Blue` dalam contoh ini).
- NoShade: Menentukan apakah aturan horizontal harus memiliki bayangan (`true` dalam contoh ini).

## Langkah 4: Simpan Dokumen

 Terakhir, simpan dokumen yang dimodifikasi menggunakan`Save` metode`Document` obyek.

```csharp
builder.Document.Save(dataDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

## Kesimpulan

Menguasai penyisipan aturan horizontal dalam dokumen Word menggunakan Aspose.Words untuk .NET meningkatkan kemampuan otomatisasi dokumen Anda. Dengan memanfaatkan fleksibilitas dan kekuatan Aspose.Words, pengembang dapat menyederhanakan proses pembuatan dan pemformatan dokumen secara efisien.

## FAQ

### Apa itu Aspose.Words untuk .NET?
Aspose.Words untuk .NET adalah perpustakaan yang kuat untuk bekerja dengan dokumen Word secara terprogram dalam aplikasi .NET.

### Bagaimana cara mengunduh Aspose.Words untuk .NET?
 Anda dapat mengunduh Aspose.Words untuk .NET dari[Di Sini](https://releases.aspose.com/words/net/).

### Bisakah saya mengkustomisasi tampilan aturan horizontal di Aspose.Words?
Ya, Anda dapat menyesuaikan berbagai aspek seperti perataan, lebar, tinggi, warna, dan bayangan aturan horizontal menggunakan Aspose.Words.

### Apakah Aspose.Words cocok untuk pemrosesan dokumen tingkat perusahaan?
Ya, Aspose.Words banyak digunakan di lingkungan perusahaan karena kemampuan manipulasi dokumennya yang kuat.

### Di mana saya bisa mendapatkan dukungan untuk Aspose.Words untuk .NET?
 Untuk dukungan dan keterlibatan komunitas, kunjungi[Aspose.Forum kata-kata](https://forum.aspose.com/c/words/8).
