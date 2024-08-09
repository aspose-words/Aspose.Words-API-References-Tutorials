---
title: Kode Sebaris
linktitle: Kode Sebaris
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menerapkan gaya kode sebaris di dokumen Word menggunakan Aspose.Words untuk .NET. Tutorial ini mencakup backtick tunggal dan ganda untuk pemformatan kode.
type: docs
weight: 10
url: /id/net/working-with-markdown/inline-code/
---
## Perkenalan

Jika Anda berupaya membuat atau memanipulasi dokumen Word secara terprogram, Anda mungkin perlu memformat teks agar menyerupai kode. Baik untuk dokumentasi atau cuplikan kode dalam laporan, Aspose.Words untuk .NET menyediakan cara yang tangguh untuk menangani penataan gaya teks. Dalam tutorial ini, kita akan fokus pada cara menerapkan gaya kode sebaris ke teks menggunakan Aspose.Words. Kita akan mempelajari cara menentukan dan menggunakan gaya kustom untuk backtick tunggal dan ganda, sehingga membuat segmen kode Anda menonjol dengan jelas di dokumen Anda.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal berikut:

1.  Aspose.Words untuk .NET Library: Pastikan Anda telah menginstal Aspose.Words di lingkungan .NET Anda. Anda dapat mengunduhnya dari[Halaman rilis Aspose.Words untuk .NET](https://releases.aspose.com/words/net/).

2. Pengetahuan Dasar Pemrograman .NET: Panduan ini mengasumsikan Anda memiliki pemahaman mendasar tentang pemrograman C# dan .NET.

3. Lingkungan Pengembangan: Anda harus menyiapkan lingkungan pengembangan .NET, seperti Visual Studio, tempat Anda dapat menulis dan mengeksekusi kode C#.

## Impor Namespace

Untuk mulai menggunakan Aspose.Words di proyek Anda, Anda harus mengimpor namespace yang diperlukan. Inilah cara Anda melakukannya:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

Mari kita bagi prosesnya menjadi langkah-langkah yang jelas:

## Langkah 1: Inisialisasi Dokumen dan DocumentBuilder

 Pertama, Anda perlu membuat dokumen baru dan a`DocumentBuilder` contoh. Itu`DocumentBuilder`kelas membantu Anda menambahkan konten dan memformatnya dalam dokumen Word.

```csharp
// Inisialisasi DocumentBuilder dengan Dokumen baru.
DocumentBuilder builder = new DocumentBuilder();
```

## Langkah 2: Tambahkan Gaya Kode Inline dengan Satu Backtick

Pada langkah ini, kita akan menentukan gaya untuk kode sebaris dengan satu backtick. Gaya ini akan memformat teks agar terlihat seperti kode sebaris.

### Tentukan Gayanya

```csharp
// Tentukan gaya karakter baru untuk kode sebaris dengan satu backtick.
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
inlineCode1BackTicks.Font.Name = "Courier New"; // Font khas untuk kode.
inlineCode1BackTicks.Font.Size = 10.5; // Ukuran font untuk kode sebaris.
inlineCode1BackTicks.Font.Color = System.Drawing.Color.Blue; // Warna teks kode.
inlineCode1BackTicks.Font.Bold = true; // Buat teks kode menjadi tebal.
```

### Terapkan Gaya

Sekarang, Anda dapat menerapkan gaya ini pada teks di dokumen Anda.

```csharp
// Gunakan DocumentBuilder untuk menyisipkan teks dengan gaya kode sebaris.
builder.Font.Style = inlineCode1BackTicks;
builder.Writeln("Text with InlineCode style with 1 backtick");
```

## Langkah 3: Tambahkan Gaya Kode Inline dengan Tiga Backticks

Selanjutnya, kita akan mendefinisikan gaya untuk kode sebaris dengan tiga tanda tik terbalik, yang biasanya digunakan untuk blok kode multi-baris.

### Tentukan Gayanya

```csharp
// Tentukan gaya karakter baru untuk kode sebaris dengan tiga tanda centang terbalik.
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
inlineCode3BackTicks.Font.Name = "Courier New"; // Font yang konsisten untuk kode.
inlineCode3BackTicks.Font.Size = 10.5; // Ukuran font untuk blok kode.
inlineCode3BackTicks.Font.Color = System.Drawing.Color.Green; //Warna berbeda untuk visibilitas.
inlineCode3BackTicks.Font.Bold = true; // Tetap berani untuk menekankan.
```

### Terapkan Gaya

Terapkan gaya ini ke teks untuk memformatnya sebagai blok kode multi-baris.

```csharp
// Terapkan gaya untuk blok kode.
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backticks");
```

## Kesimpulan

Memformat teks sebagai kode sebaris di dokumen Word menggunakan Aspose.Words untuk .NET sangatlah mudah setelah Anda mengetahui langkah-langkahnya. Dengan menentukan dan menerapkan gaya khusus dengan satu atau beberapa backtick, Anda dapat membuat cuplikan kode Anda menonjol dengan jelas. Metode ini sangat berguna untuk dokumentasi teknis atau dokumen apa pun yang mengutamakan keterbacaan kode.

Jangan ragu untuk bereksperimen dengan berbagai gaya dan opsi pemformatan yang paling sesuai dengan kebutuhan Anda. Aspose.Words menawarkan fleksibilitas yang luas, memungkinkan Anda untuk menyesuaikan tampilan dokumen Anda secara maksimal.

## FAQ

### Bisakah saya menggunakan font berbeda untuk gaya kode sebaris?
Ya, Anda dapat menggunakan font apa pun yang sesuai dengan kebutuhan Anda. Font seperti "Courier New" biasanya digunakan untuk kode karena sifatnya yang monospace.

### Bagaimana cara mengubah warna teks kode sebaris?
 Anda dapat mengubah warnanya dengan mengatur`Font.Color` properti gaya untuk apa pun`System.Drawing.Color`.

### Bisakah saya menerapkan beberapa gaya pada teks yang sama?
Di Aspose.Words, Anda hanya dapat menerapkan satu gaya dalam satu waktu. Jika Anda perlu menggabungkan gaya, pertimbangkan untuk membuat gaya baru yang menggabungkan semua pemformatan yang diinginkan.

### Bagaimana cara menerapkan gaya pada teks yang ada di dokumen?
 Untuk menerapkan gaya pada teks yang ada, Anda harus memilih teks terlebih dahulu lalu menerapkan gaya yang diinginkan menggunakan`Font.Style` milik.

### Bisakah saya menggunakan Aspose.Words untuk format dokumen lain?
Aspose.Words dirancang khusus untuk dokumen Word. Untuk format lain, Anda mungkin perlu menggunakan perpustakaan berbeda atau mengonversi dokumen ke format yang kompatibel.