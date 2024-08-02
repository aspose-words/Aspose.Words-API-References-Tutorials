---
title: Tambahkan Sudut Terpotong
linktitle: Tambahkan Sudut Terpotong
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menambahkan bentuk potongan sudut ke dokumen Word Anda menggunakan Aspose.Words untuk .NET. Panduan langkah demi langkah ini memastikan Anda dapat menyempurnakan dokumen Anda dengan mudah.
type: docs
weight: 10
url: /id/net/programming-with-shapes/add-corners-snipped/
---
## Perkenalan

Menambahkan bentuk khusus ke dokumen Word Anda bisa menjadi cara yang menyenangkan dan menarik secara visual untuk menyorot informasi penting atau menambahkan sedikit gaya pada konten Anda. Dalam tutorial ini, kita akan mendalami bagaimana Anda dapat menyisipkan bentuk "Corners Snipped" ke dalam dokumen Word Anda menggunakan Aspose.Words untuk .NET. Panduan ini akan memandu Anda melalui setiap langkah, memastikan Anda dapat dengan mudah menambahkan bentuk-bentuk ini dan menyesuaikan dokumen Anda seperti seorang profesional.

## Prasyarat

Sebelum kita beralih ke kode, pastikan Anda memiliki semua yang Anda perlukan untuk memulai:

1.  Aspose.Words untuk .NET: Jika Anda belum melakukannya, unduh versi terbaru dari .NET[Halaman rilis Aspose](https://releases.aspose.com/words/net/).
2. Lingkungan Pengembangan: Siapkan lingkungan pengembangan Anda. Visual Studio adalah pilihan yang populer, tetapi Anda dapat menggunakan IDE apa pun yang mendukung .NET.
3.  Lisensi: Jika Anda hanya bereksperimen, Anda dapat menggunakan a[uji coba gratis](https://releases.aspose.com/) atau dapatkan a[izin sementara](https://purchase.aspose.com/temporary-license/) untuk membuka kunci fungsionalitas penuh.
4. Pemahaman Dasar C#: Keakraban dengan pemrograman C# akan membantu Anda mengikuti contoh-contohnya.

## Impor Namespace

Sebelum kita dapat mulai bekerja dengan Aspose.Words untuk .NET, kita perlu mengimpor namespace yang diperlukan. Tambahkan ini di bagian atas file C# Anda:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

Sekarang, mari kita uraikan proses penambahan bentuk "Sudut Terpotong" menjadi beberapa langkah. Ikuti langkah-langkah ini dengan cermat untuk memastikan semuanya berjalan lancar.

## Langkah 1: Inisialisasi Dokumen dan DocumentBuilder

 Hal pertama yang perlu kita lakukan adalah membuat dokumen baru dan menginisialisasi a`DocumentBuilder` obyek. Pembuat ini akan membantu kami menambahkan konten ke dokumen kami.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Pada langkah ini, kami telah menyiapkan dokumen dan pembuat kami. Pikirkan tentang`DocumentBuilder` sebagai pena digital Anda, siap untuk menulis dan menggambar di dokumen Word Anda.

## Langkah 2: Masukkan Bentuk Potongan Sudut

 Selanjutnya, kita akan menggunakan`DocumentBuilder` untuk menyisipkan bentuk "Pojok Terpotong". Tipe bentuk ini telah ditentukan sebelumnya di Aspose.Words dan dapat dengan mudah disisipkan dengan satu baris kode.

```csharp
builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
```

Di sini, kami menentukan tipe bentuk dan dimensinya (50x50). Bayangkan Anda menempatkan stiker sudut kecil yang terpotong sempurna pada dokumen Anda. 

## Langkah 3: Tentukan Opsi Penyimpanan dengan Kepatuhan

Sebelum menyimpan dokumen, kita perlu menentukan opsi penyimpanan untuk memastikan dokumen kita mematuhi standar tertentu. Kami akan menggunakan`OoxmlSaveOptions` kelas untuk ini.

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
```

Opsi penyimpanan ini memastikan bahwa dokumen kami mematuhi standar ISO/IEC 29500:2008, yang sangat penting untuk kompatibilitas dan umur panjang dokumen.

## Langkah 4: Simpan Dokumen

Terakhir, kami menyimpan dokumen kami ke direktori yang ditentukan menggunakan opsi penyimpanan yang kami tentukan sebelumnya.

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);
```

Dan begitu saja, dokumen Anda sekarang berisi bentuk khusus "Sudut Terpotong", disimpan dengan opsi kepatuhan yang diperlukan.

## Kesimpulan

Itu dia! Menambahkan bentuk khusus ke dokumen Word Anda menggunakan Aspose.Words untuk .NET sangatlah mudah dan dapat meningkatkan daya tarik visual dokumen Anda secara signifikan. Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah menyisipkan bentuk "Sudut Terpotong" dan memastikan dokumen Anda memenuhi standar yang disyaratkan. Selamat membuat kode!

## FAQ

### Bisakah saya menyesuaikan ukuran bentuk "Sudut Terpotong"?
Ya, Anda dapat menyesuaikan ukurannya dengan mengubah dimensi di dalamnya`InsertShape` metode.

### Apakah mungkin untuk menambahkan jenis bentuk lainnya?
 Sangat! Aspose.Words mendukung berbagai bentuk. Ubah saja`ShapeType` ke bentuk yang Anda inginkan.

### Apakah saya memerlukan lisensi untuk menggunakan Aspose.Words?
Meskipun Anda dapat menggunakan uji coba gratis atau lisensi sementara, lisensi penuh diperlukan untuk penggunaan tidak terbatas.

### Bagaimana cara menata bentuknya lebih jauh?
Anda dapat menggunakan properti dan metode tambahan yang disediakan oleh Aspose.Words untuk menyesuaikan tampilan dan perilaku bentuk.

### Apakah Aspose.Words kompatibel dengan format lain?
Ya, Aspose.Words mendukung berbagai format dokumen termasuk DOCX, PDF, HTML, dan lainnya.