---
title: Pertahankan Karakter Kontrol Lama
linktitle: Pertahankan Karakter Kontrol Lama
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mempertahankan karakter kontrol lama di dokumen Word menggunakan Aspose.Words untuk .NET dengan panduan langkah demi langkah ini.
type: docs
weight: 10
url: /id/net/programming-with-ooxmlsaveoptions/keep-legacy-control-chars/
---
## Perkenalan

Pernah dibuat bingung dengan karakter kontrol yang aneh dan tidak terlihat di dokumen Word Anda? Mereka seperti gremlin kecil dan tersembunyi yang dapat mengacaukan format dan fungsionalitas. Untungnya, Aspose.Words untuk .NET menyediakan fitur praktis untuk menjaga karakter kontrol lama ini tetap utuh saat menyimpan dokumen. Dalam tutorial ini, kita akan mendalami cara mengelola karakter kontrol ini menggunakan Aspose.Words untuk .NET. Kami akan menguraikannya langkah demi langkah, memastikan Anda memahami setiap detailnya. Siap untuk memulai? Ayo selami!

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki yang berikut ini:

1.  Aspose.Words untuk .NET: Unduh dan instal dari[Di Sini](https://releases.aspose.com/words/net/).
2.  Lisensi Aspose yang valid: Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).
3. Lingkungan Pengembangan: Visual Studio atau IDE lain yang mendukung .NET.
4. Pengetahuan Dasar C#: Keakraban dengan bahasa pemrograman C# akan sangat membantu.

## Impor Namespace

Sebelum menulis kode, Anda perlu mengimpor namespace yang diperlukan. Tambahkan baris berikut ke bagian atas file C# Anda:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Langkah 1: Menyiapkan Proyek Anda

Pertama, Anda harus menyiapkan proyek Anda di Visual Studio (atau IDE pilihan Anda). 

1. Buat proyek C# baru: Buka Visual Studio dan buat proyek Aplikasi Konsol C# baru.
2. Instal Aspose.Words untuk .NET: Gunakan NuGet Package Manager untuk menginstal Aspose.Words untuk .NET. Klik kanan proyek Anda di Solution Explorer, pilih "Kelola Paket NuGet", cari "Aspose.Words", dan instal.

## Langkah 2: Muat Dokumen Anda

Selanjutnya, Anda akan memuat dokumen Word yang berisi karakter kontrol lama.

1. Tentukan jalur dokumen: Tetapkan jalur ke direktori dokumen Anda.
   
   ```csharp
   string dataDir = "YOUR DOCUMENT DIRECTORY";
   ```

2.  Memuat dokumen: Gunakan`Document` kelas untuk memuat dokumen Anda.

   ```csharp
   Document doc = new Document(dataDir + "Legacy control character.doc");
   ```

## Langkah 3: Konfigurasikan Opsi Penyimpanan

Sekarang, mari konfigurasikan opsi penyimpanan agar karakter kontrol lama tetap utuh.

1.  Buat Opsi Simpan: Inisialisasi sebuah instance dari`OoxmlSaveOptions` dan atur`KeepLegacyControlChars`properti ke`true`.

   ```csharp
   OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc)
   {
       KeepLegacyControlChars = true
   };
   ```

## Langkah 4: Simpan Dokumen

Terakhir, simpan dokumen dengan opsi penyimpanan yang dikonfigurasi.

1.  Menyimpan dokumen: Gunakan`Save` metode`Document` kelas untuk menyimpan dokumen dengan opsi penyimpanan yang ditentukan.

   ```csharp
   doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
   ```

## Kesimpulan

Dan itu dia! Dengan mengikuti langkah-langkah ini, Anda dapat memastikan bahwa karakter kontrol lama Anda dipertahankan saat bekerja dengan dokumen Word di Aspose.Words untuk .NET. Fitur ini dapat menjadi penyelamat, terutama ketika berhadapan dengan dokumen kompleks yang mana karakter kontrol memainkan peran penting. 

## FAQ

### Apa yang dimaksud dengan karakter kontrol warisan?

Karakter kontrol lama adalah karakter non-cetak yang digunakan dalam dokumen lama untuk mengontrol pemformatan dan tata letak.

### Bisakah saya menghapus karakter kontrol ini dan tidak menyimpannya?

Ya, Anda dapat menggunakan Aspose.Words untuk .NET untuk menghapus atau mengganti karakter ini jika diperlukan.

### Apakah fitur ini tersedia di semua versi Aspose.Words untuk .NET?

Fitur ini tersedia dalam versi terbaru. Pastikan untuk menggunakan versi terbaru untuk mengakses semua fungsi.

### Apakah saya memerlukan lisensi untuk menggunakan Aspose.Words untuk .NET?

 Ya, Anda memerlukan lisensi yang valid. Anda bisa mendapatkan lisensi sementara untuk tujuan evaluasi[Di Sini](https://purchase.aspose.com/temporary-license/).

### Di mana saya dapat menemukan dokumentasi lebih lanjut tentang Aspose.Words untuk .NET?

 Anda dapat menemukan dokumentasi terperinci[Di Sini](https://reference.aspose.com/words/net/).
 