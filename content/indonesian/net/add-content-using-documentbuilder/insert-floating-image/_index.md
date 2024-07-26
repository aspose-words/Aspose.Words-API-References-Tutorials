---
title: Sisipkan Gambar Mengambang di Dokumen Word
linktitle: Sisipkan Gambar Mengambang di Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyisipkan gambar mengambang di dokumen Word menggunakan Aspose.Words untuk .NET dengan panduan langkah demi langkah yang mendetail ini. Sempurna untuk menyempurnakan dokumen Anda.
type: docs
weight: 10
url: /id/net/add-content-using-documentbuilder/insert-floating-image/
---
## Perkenalan

Bayangkan membuat laporan atau proposal menakjubkan dengan gambar diposisikan secara sempurna untuk melengkapi teks Anda. Dengan Aspose.Words untuk .NET, Anda dapat mencapainya dengan mudah. Pustaka ini menyediakan fitur canggih untuk manipulasi dokumen, menjadikannya solusi tepat bagi pengembang. Dalam tutorial ini, kita akan fokus menyisipkan gambar mengambang menggunakan kelas DocumentBuilder. Baik Anda seorang pengembang berpengalaman atau baru memulai, panduan ini akan memandu Anda melalui setiap langkah.

## Prasyarat

Sebelum kita mendalaminya, pastikan Anda memiliki semua yang dibutuhkan untuk memulai:

1.  Aspose.Words untuk .NET: Anda dapat mengunduh perpustakaan dari[Halaman rilis Aspose](https://releases.aspose.com/words/net/).
2. Visual Studio: Versi apa pun yang mendukung pengembangan .NET.
3. Pengetahuan Dasar C#: Memahami dasar-dasar pemrograman C# akan sangat membantu.
4. File Gambar: File gambar yang ingin Anda sisipkan, seperti logo atau gambar.

## Impor Namespace

Untuk menggunakan Aspose.Words dalam proyek Anda, Anda perlu mengimpor namespace yang diperlukan. Ini dilakukan dengan menambahkan baris berikut di bagian atas file C# Anda:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

Dengan prasyarat dan namespace ini, kami siap memulai tutorial kami.

Mari kita uraikan proses memasukkan gambar mengambang ke dalam dokumen Word menjadi langkah-langkah yang dapat dikelola. Setiap langkah akan dijelaskan secara rinci untuk memastikan Anda dapat mengikutinya tanpa hambatan.

## Langkah 1: Siapkan Proyek Anda

Pertama, buat proyek C# baru di Visual Studio. Anda dapat memilih Aplikasi Konsol untuk kesederhanaan.

1. Buka Visual Studio dan buat proyek baru.
2. Pilih "Aplikasi Konsol (.NET Core)" dan klik "Berikutnya".
3. Beri nama proyek Anda dan pilih lokasi untuk menyimpannya. Klik "Buat."
4. Instal Aspose.Words untuk .NET melalui NuGet Package Manager. Klik kanan proyek Anda di Solution Explorer, pilih "Kelola Paket NuGet," dan cari "Aspose.Words." Instal versi terbaru.

## Langkah 2: Inisialisasi Dokumen dan DocumentBuilder

Sekarang proyek Anda sudah siap, mari kita inisialisasi objek Document dan DocumentBuilder.

1.  Buat instance baru dari`Document` kelas:

```csharp
Document doc = new Document();
```

2. Inisialisasi objek DocumentBuilder:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Itu`Document` objek mewakili dokumen Word, dan`DocumentBuilder` membantu dalam menambahkan konten ke dalamnya.

## Langkah 3: Tentukan Jalur Gambar

Selanjutnya, tentukan jalur ke file gambar Anda. Pastikan gambar Anda dapat diakses dari direktori proyek Anda.

Tentukan direktori gambar dan nama file gambar:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string imagePath = dataDir + "Transparent background logo.png";
```

 Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya tempat gambar Anda disimpan.

## Langkah 4: Masukkan Gambar Mengambang

Setelah semuanya siap, mari masukkan gambar mengambang ke dalam dokumen.

 Menggunakan`InsertImage` metode`DocumentBuilder` kelas untuk menyisipkan gambar:

```csharp
builder.InsertImage(imagePath,
   RelativeHorizontalPosition.Margin,
   100,
   RelativeVerticalPosition.Margin,
   100,
   200,
   100,
   WrapType.Square);
```

Berikut arti setiap parameter:
- `imagePath`Jalur ke file gambar Anda.
- `RelativeHorizontalPosition.Margin`: Posisi horizontal relatif terhadap margin.
- `100`: Offset horizontal dari margin (dalam poin).
- `RelativeVerticalPosition.Margin`: Posisi vertikal relatif terhadap margin.
- `100`: Offset vertikal dari margin (dalam poin).
- `200`: Lebar gambar (dalam poin).
- `100`: Ketinggian gambar (dalam poin).
- `WrapType.Square`: Gaya pembungkusan teks di sekitar gambar.

## Langkah 5: Simpan Dokumen

Terakhir, simpan dokumen ke lokasi yang Anda inginkan.

1. Tentukan jalur file keluaran:

```csharp
string outputPath = dataDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx";
```

2. Simpan dokumen:

```csharp
doc.Save(outputPath);
```

Dokumen Word Anda dengan gambar mengambang sekarang siap!

## Kesimpulan

Memasukkan gambar mengambang ke dalam dokumen Word menggunakan Aspose.Words untuk .NET adalah proses yang mudah jika dipecah menjadi beberapa langkah yang dapat dikelola. Dengan mengikuti panduan ini, Anda dapat menambahkan gambar yang terlihat profesional ke dokumen Anda, sehingga meningkatkan daya tarik visualnya. Aspose.Words menyediakan API tangguh yang memudahkan manipulasi dokumen, baik Anda mengerjakan laporan, proposal, atau jenis dokumen lainnya.

## FAQ

### Bisakah saya menyisipkan banyak gambar menggunakan Aspose.Words untuk .NET?

 Ya, Anda dapat menyisipkan banyak gambar dengan mengulanginya`InsertImage` metode untuk setiap gambar dengan parameter yang diinginkan.

### Bagaimana cara mengubah posisi gambar?

 Anda dapat menyesuaikannya`RelativeHorizontalPosition`, `RelativeVerticalPosition`, dan parameter offset untuk memposisikan gambar sesuai kebutuhan.

### Jenis bungkus apa lagi yang tersedia untuk gambar?

 Aspose.Words mendukung berbagai jenis bungkus seperti`Inline`, `TopBottom`, `Tight`, `Through`, dan banyak lagi. Anda dapat memilih salah satu yang paling sesuai dengan tata letak dokumen Anda.

### Bisakah saya menggunakan format gambar yang berbeda?

Ya, Aspose.Words mendukung berbagai format gambar termasuk JPEG, PNG, BMP, dan GIF.

### Bagaimana cara mendapatkan uji coba gratis Aspose.Words untuk .NET?

 Anda bisa mendapatkan uji coba gratis dari[Asumsikan halaman uji coba gratis](https://releases.aspose.com/).