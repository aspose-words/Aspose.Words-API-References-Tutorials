---
title: Atur Pengaturan Penggantian Font
linktitle: Atur Pengaturan Penggantian Font
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengatur pengaturan substitusi font di Aspose.Words untuk .NET dan mengkustomisasi substitusi font di dokumen Word Anda.
type: docs
weight: 10
url: /id/net/working-with-fonts/set-font-fallback-settings/
---
Dalam tutorial ini, kami akan menunjukkan cara mengatur pengaturan substitusi font di dokumen Word menggunakan Aspose.Words untuk .NET. Pengaturan substitusi font memungkinkan Anda menentukan font pengganti yang akan digunakan ketika font tertentu tidak tersedia.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki item berikut:
- Pengetahuan tentang bahasa pemrograman C#
- Pustaka Aspose.Words untuk .NET diinstal di proyek Anda

## Langkah 1: Tentukan direktori dokumen
 Mulailah dengan mengatur jalur direktori ke lokasi dokumen Word Anda. Mengganti`"YOUR DOCUMENT DIRECTORY"` dalam kode dengan jalur yang sesuai.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Muat pengaturan substitusi font
 Buat sebuah instance dari`FontSettings` kelas dan gunakan`Load` metode untuk memuat pengaturan penggantian font dari file XML. File XML yang ditentukan harus berisi aturan substitusi font yang akan digunakan.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.Load(dataDir + "Font Fallback Rules.xml");
```

## Langkah 3: Terapkan pengaturan substitusi font
 Kaitkan pengaturan substitusi font dengan dokumen dengan menugaskannya ke dokumen`FontSettings` Properti.

```csharp
doc.FontSettings = fontSettings;
```

## Langkah 4: Simpan dokumen
 Simpan dokumen menggunakan`Save` metode`Document` dengan jalur dan nama file yang sesuai.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontFallbackSettings.pdf");
```

### Contoh kode sumber untuk Mengatur Pengaturan Penggantian Font menggunakan Aspose.Words untuk .NET 
```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.Load(dataDir + "Font fallback rules.xml");
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontFallbackSettings.pdf");
```

## Kesimpulan
Dalam tutorial ini, Anda mempelajari cara mengatur pengaturan substitusi font di dokumen Word menggunakan Aspose.Words untuk .NET. Bereksperimenlah dengan aturan substitusi font yang berbeda untuk memastikan dokumen Anda terlihat konsisten, meskipun font yang ditentukan tidak tersedia.

### FAQ

#### T: Bagaimana cara mengatur pengaturan substitusi font di dokumen Word dengan Aspose.Words?

J: Untuk mengatur pengaturan substitusi font di dokumen Word dengan Aspose.Words, Anda dapat menggunakan API untuk menentukan font cadangan yang akan digunakan ketika font yang diperlukan tidak tersedia. Hal ini memastikan visualisasi teks konsisten, bahkan tanpa font aslinya.

#### T: Apakah mungkin untuk menangani font cadangan saat mengganti dokumen Word dengan Aspose.Words?

J: Ya, dengan Aspose.Words Anda dapat mengelola font cadangan saat menggantinya di dokumen Word. API ini memungkinkan Anda mendeteksi font yang hilang dan menentukan font cadangan yang sesuai untuk mempertahankan tampilan teks yang konsisten bahkan ketika font diganti.

#### T: Mengapa penting untuk mengonfigurasi pengaturan substitusi font dengan benar di dokumen Word?

J: Penting untuk mengonfigurasi pengaturan substitusi font dengan benar di dokumen Word untuk menjaga integritas visual teks. Dengan mengatur font fallback yang sesuai dengan Aspose.Words, Anda memastikan bahwa teks akan ditampilkan secara konsisten, meskipun font yang diperlukan tidak tersedia.

#### T: Bagaimana cara mendeteksi font yang hilang saat mengganti dokumen Word dengan Aspose.Words?

J: Aspose.Words memungkinkan Anda mendeteksi font yang hilang selama substitusi dalam dokumen Word menggunakan API. Anda dapat menggunakan metode yang disediakan oleh Aspose.Words untuk memeriksa ketersediaan font yang diperlukan dan mengambil tindakan yang sesuai jika ada font yang hilang.

#### T: Apakah penggantian font memengaruhi tata letak dokumen Word saya?

J: Penggantian font dapat mempengaruhi tata letak dokumen Word Anda jika font cadangan memiliki dimensi yang berbeda dari font aslinya. Namun, dengan memilih font cadangan secara bijak dan mengonfigurasi pengaturan substitusi font dengan Aspose.Words, Anda dapat meminimalkan dampak tata letak.