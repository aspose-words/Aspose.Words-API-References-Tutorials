---
title: Rasio Aspek Terkunci
linktitle: Rasio Aspek Terkunci
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengunci rasio aspek bentuk di dokumen Word menggunakan Aspose.Words untuk .NET. Ikuti panduan langkah demi langkah ini untuk menjaga gambar dan bentuk Anda tetap proporsional.
type: docs
weight: 10
url: /id/net/programming-with-shapes/aspect-ratio-locked/
---
## Perkenalan

Pernahkah Anda bertanya-tanya bagaimana cara mempertahankan proporsi gambar dan bentuk yang sempurna di dokumen Word Anda? Terkadang, Anda perlu memastikan bahwa gambar dan bentuk Anda tidak terdistorsi saat diubah ukurannya. Di sinilah mengunci rasio aspek berguna. Dalam tutorial ini, kita akan mempelajari cara mengatur rasio aspek untuk bentuk di dokumen Word menggunakan Aspose.Words untuk .NET. Kami akan membaginya menjadi langkah-langkah yang mudah diikuti, memastikan Anda dapat menerapkan keterampilan ini pada proyek Anda dengan percaya diri.

## Prasyarat

Sebelum kita mendalami kodenya, mari kita bahas apa yang Anda perlukan untuk memulai:

- Aspose.Words untuk .NET Library: Anda harus menginstal Aspose.Words untuk .NET. Jika Anda belum melakukannya, Anda bisa[unduh di sini](https://releases.aspose.com/words/net/).
- Lingkungan Pengembangan: Pastikan Anda telah menyiapkan lingkungan pengembangan .NET. Visual Studio adalah pilihan yang populer.
- Pengetahuan Dasar C#: Keakraban dengan pemrograman C# akan sangat membantu.

## Impor Namespace

Hal pertama yang pertama, mari impor namespace yang diperlukan. Namespace ini akan memberi kita akses ke kelas dan metode yang kita perlukan untuk bekerja dengan dokumen dan bentuk Word.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Langkah 1: Siapkan Direktori Dokumen Anda

 Sebelum kita mulai memanipulasi bentuk, kita perlu menyiapkan direktori tempat dokumen kita akan disimpan. Demi kesederhanaan, kami akan menggunakan placeholder`YOUR DOCUMENT DIRECTORY`. Ganti ini dengan jalur sebenarnya ke direktori dokumen Anda.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Buat Dokumen Baru

Selanjutnya, kita akan membuat dokumen Word baru menggunakan Aspose.Words. Dokumen ini akan berfungsi sebagai kanvas kita untuk menambahkan bentuk dan gambar.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Di sini, kita membuat sebuah instance dari`Document` kelas dan gunakan a`DocumentBuilder` untuk membantu kami membangun konten dokumen.

## Langkah 3: Sisipkan Gambar

 Sekarang, mari masukkan gambar ke dalam dokumen kita. Kami akan menggunakan`InsertImage` metode`DocumentBuilder`kelas. Pastikan Anda memiliki gambar di direktori yang Anda tentukan.

```csharp
Shape shape = builder.InsertImage(dataDir + "Transparent background logo.png");
```

 Mengganti`dataDir + "Transparent background logo.png"` dengan jalur ke file gambar Anda.

## Langkah 4: Kunci Rasio Aspek

Setelah gambar dimasukkan, kita dapat mengunci rasio aspeknya. Mengunci rasio aspek memastikan proporsi gambar tetap konstan saat mengubah ukuran.

```csharp
shape.AspectRatioLocked = true;
```

 Pengaturan`AspectRatioLocked` ke`true` memastikan bahwa gambar mempertahankan rasio aspek aslinya.

## Langkah 5: Simpan Dokumen

Terakhir, kami akan menyimpan dokumen ke direktori yang ditentukan. Langkah ini menulis semua perubahan yang kita buat pada file dokumen.

```csharp
doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

## Kesimpulan

Selamat! Anda telah berhasil mempelajari cara mengatur rasio aspek untuk bentuk di dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti langkah-langkah ini, Anda dapat memastikan bahwa gambar dan bentuk Anda mempertahankan proporsinya, membuat dokumen Anda terlihat profesional dan halus. Jangan ragu untuk bereksperimen dengan berbagai gambar dan bentuk untuk melihat cara kerja fitur penguncian rasio aspek dalam berbagai skenario.

## FAQ

### Bisakah saya membuka kunci rasio aspek setelah menguncinya?
Ya, Anda dapat membuka kunci rasio aspek dengan mengaturnya`shape.AspectRatioLocked = false`.

### Apa yang terjadi jika saya mengubah ukuran gambar dengan rasio aspek terkunci?
Gambar akan diubah ukurannya secara proporsional, mempertahankan rasio lebar dan tinggi aslinya.

### Bisakah saya menerapkan ini pada bentuk lain selain gambar?
Sangat! Fitur penguncian rasio aspek dapat diterapkan pada bentuk apa pun, termasuk persegi panjang, lingkaran, dan lainnya.

### Apakah Aspose.Words untuk .NET kompatibel dengan .NET Core?
Ya, Aspose.Words untuk .NET mendukung .NET Framework dan .NET Core.

### Di mana saya dapat menemukan dokumentasi lebih lanjut tentang Aspose.Words untuk .NET?
 Anda dapat menemukan dokumentasi yang komprehensif[Di Sini](https://reference.aspose.com/words/net/).