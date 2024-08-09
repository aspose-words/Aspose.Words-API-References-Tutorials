---
title: Atur Folder Gambar
linktitle: Atur Folder Gambar
second_title: API Pemrosesan Dokumen Aspose.Words
description: Konversikan dokumen Word ke Markdown dengan perataan tabel yang tepat menggunakan Aspose.Words untuk .NET. Ikuti panduan terperinci kami untuk hasil sempurna.
type: docs
weight: 10
url: /id/net/programming-with-markdownsaveoptions/set-images-folder/
---
## Perkenalan

Pernahkah Anda ingin mengekspor dokumen Word Anda ke format Markdown sambil memastikan tabel dan konten selaras dengan sempurna? Aspose.Words for .NET adalah solusi tepat Anda untuk tugas ini. Dalam artikel ini, kami akan memandu Anda melalui proses penyiapan Aspose.Words, menyiapkan dokumen Anda, dan mengekspornya ke Markdown dengan penyelarasan konten tabel yang tepat. Kami akan menguraikan setiap langkah agar mudah diikuti dan dipahami. Jadi, mari selami dan ubah dokumen Word Anda menjadi file Markdown yang selaras dengan indah!

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal berikut:

-  Aspose.Words untuk .NET: Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/words/net/).
-  Lisensi yang valid: Dapatkan uji coba gratis[Di Sini](https://releases.aspose.com/) atau izin sementara[Di Sini](https://purchase.aspose.com/temporary-license/).
- Visual Studio: Atau IDE lain yang mendukung pengembangan .NET.
- Pengetahuan dasar C#: Pemahaman bahasa pemrograman C#.

## Impor Namespace

Untuk memulai, Anda harus mengimpor namespace yang diperlukan dalam proyek C# Anda. Namespace ini akan memungkinkan Anda mengakses fungsionalitas Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
using System.IO;
```

## Langkah 1: Siapkan Proyek Anda

Hal pertama yang pertama, siapkan proyek .NET Anda di IDE Anda. Buat aplikasi konsol baru dan tambahkan referensi ke Aspose.Words untuk .NET.

### 1.1 Buat Proyek Baru

Buka Visual Studio dan buat proyek Aplikasi Konsol baru. Beri nama "MarkdownExporter" atau yang serupa.

### 1.2 Tambahkan Referensi Aspose.Words

 Untuk menambahkan Aspose.Words ke proyek Anda, Anda dapat mengunduh DLL dari[Asumsikan situs web](https://releases.aspose.com/words/net/) dan menambahkannya secara manual, atau gunakan NuGet Package Manager:

```bash
Install-Package Aspose.Words
```

## Langkah 2: Tulis Kode untuk Diekspor sebagai Penurunan Harga

Sekarang, mari tulis kode untuk membaca dokumen Word dan menyimpannya sebagai file Markdown dengan perataan tabel yang tepat.

### 2.1 Tentukan Jalur ke Dokumen Anda

Tetapkan jalur ke dokumen Word Anda dan folder tempat Anda ingin menyimpan gambar.

```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY";
```

### 2.2 Memuat Dokumen

Muat dokumen Word Anda menggunakan Aspose.Words.

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

### 2.3 Konfigurasikan Opsi Penyimpanan Penurunan Harga

 Konfigurasikan`MarkdownSaveOptions` untuk menentukan di mana gambar harus disimpan.

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
{
    ImagesFolder = dataDir + "Images"
};
```

### 2.4 Simpan Dokumen sebagai Penurunan Harga

 Gunakan a`MemoryStream` untuk menyimpan dokumen dalam format penurunan harga.

```csharp
using (MemoryStream stream = new MemoryStream())
{
    doc.Save(stream, saveOptions);
}
```

## Kesimpulan

Mengekspor dokumen Word ke Markdown dengan penyelarasan konten tabel menggunakan Aspose.Words untuk .NET sangatlah mudah jika Anda mengikuti langkah-langkah berikut. Dengan beberapa baris kode, Anda dapat mengotomatiskan proses konversi dan memastikan konten Anda diformat dengan baik. Sekarang, Anda dapat dengan mudah membagikan dokumen Anda dalam format Markdown, mengetahui bahwa dokumen tersebut akan terlihat bagus dan mempertahankan strukturnya.

## FAQ

### Bisakah saya menggunakan Aspose.Words untuk .NET dengan bahasa pemrograman lain?

Ya, Aspose.Words untuk .NET dapat digunakan dengan bahasa apa pun yang kompatibel dengan .NET seperti VB.NET, F#, dan lainnya.

### Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Words?

 Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).

### Jenis dokumen apa yang dapat saya konversi ke Markdown?

Anda dapat mengonversi berbagai dokumen Word termasuk .doc, .docx, .rtf, dan lainnya.

### Apakah ada batasan dalam versi uji coba Aspose.Words?

Versi uji coba memiliki beberapa keterbatasan seperti tanda air pada file keluaran. Anda bisa mendapatkan uji coba gratis[Di Sini](https://releases.aspose.com/).

### Di mana saya dapat menemukan lebih banyak contoh dan dokumentasi untuk Aspose.Words?

 Anda dapat menemukan dokumentasi rinci dan contoh di[Asumsikan situs web](https://reference.aspose.com/words/net/).
