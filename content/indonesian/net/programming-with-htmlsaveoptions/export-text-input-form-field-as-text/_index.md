---
title: Ekspor Bidang Formulir Input Teks Sebagai Teks
linktitle: Ekspor Bidang Formulir Input Teks Sebagai Teks
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengekspor bidang formulir masukan teks sebagai teks biasa menggunakan Aspose.Words untuk .NET dengan panduan langkah demi langkah yang komprehensif ini.
type: docs
weight: 10
url: /id/net/programming-with-htmlsaveoptions/export-text-input-form-field-as-text/
---
## Perkenalan

Jadi, Anda terjun ke dunia Aspose.Words untuk .NET? Pilihan yang luar biasa! Jika Anda ingin mempelajari cara mengekspor bidang formulir masukan teks sebagai teks, Anda berada di tempat yang tepat. Baik Anda baru memulai atau mengasah keterampilan Anda, panduan ini akan memandu Anda melalui semua yang perlu Anda ketahui. Mari kita mulai, oke?

## Prasyarat

Sebelum kita mendalami seluk beluknya, pastikan Anda memiliki semua yang perlu Anda ikuti dengan lancar:

-  Aspose.Words untuk .NET: Unduh dan instal versi terbaru dari[Di Sini](https://releases.aspose.com/words/net/).
- IDE: Visual Studio atau lingkungan pengembangan C# apa pun.
- Pengetahuan Dasar C#: Pemahaman tentang sintaks dasar C# dan konsep pemrograman berorientasi objek.
- Dokumen: Contoh dokumen Word (`Rendering.docx`) dengan kolom formulir masukan teks.

## Impor Namespace

Hal pertama yang pertama, Anda perlu mengimpor namespace yang diperlukan. Ini seperti elemen dasar yang membuat segalanya berjalan lancar.

```csharp
using System;
using System.IO;
using Aspose.Words;
using Aspose.Words.Saving;
```

Baiklah, sekarang namespace kita sudah siap, mari kita mulai beraksi!

## Langkah 1: Siapkan Proyek

Sebelum kita masuk ke kodenya, pastikan proyek kita sudah diatur dengan benar.

## Membuat Proyek

1. Buka Visual Studio: Mulailah dengan membuka Visual Studio atau lingkungan pengembangan C# pilihan Anda.
2.  Buat Proyek Baru: Navigasikan ke`File > New > Project` . Pilih`Console App (.NET Core)` atau jenis proyek lain yang relevan.
3.  Beri Nama Proyek Anda: Berikan nama yang bermakna pada proyek Anda, kira-kira`AsposeWordsExportExample`.

## Menambahkan Aspose.Kata-kata

1.  Kelola Paket NuGet: Klik kanan proyek Anda di Solution Explorer dan pilih`Manage NuGet Packages`.
2.  Cari Aspose.Words: Di Manajer Paket NuGet, cari`Aspose.Words`.
3.  Instal Aspose.Words: Klik`Install` untuk menambahkan perpustakaan Aspose.Words ke proyek Anda.

## Langkah 2: Muat Dokumen Word

Sekarang proyek kita sudah siap, mari muat dokumen Word yang berisi kolom formulir input teks.

1. Tentukan Direktori Dokumen: Tentukan jalur ke direktori tempat dokumen Anda disimpan.
2.  Memuat Dokumen: Gunakan`Document` kelas untuk memuat dokumen Word Anda.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

## Langkah 3: Siapkan Direktori Ekspor

Sebelum kita mengekspor, pastikan direktori ekspor kita sudah siap. Di sinilah file HTML dan gambar kita akan disimpan.

1. Tentukan Direktori Ekspor: Tentukan jalur penyimpanan file yang diekspor.
2. Periksa dan Bersihkan Direktori: Pastikan direktori tersebut ada dan kosong.

```csharp
string imagesDir = Path.Combine(dataDir, "Images");

if (Directory.Exists(imagesDir))
    Directory.Delete(imagesDir, true);

Directory.CreateDirectory(imagesDir);
```

## Langkah 4: Konfigurasikan Opsi Penyimpanan

Di sinilah keajaiban terjadi. Kita perlu mengatur opsi penyimpanan untuk mengekspor bidang formulir input teks sebagai teks biasa.

1.  Buat Opsi Simpan: Inisialisasi yang baru`HtmlSaveOptions` obyek.
2.  Atur Opsi Ekspor Teks: Konfigurasikan`ExportTextInputFormFieldAsText`properti ke`true`.
3. Atur Folder Gambar: Menentukan folder tempat gambar akan disimpan.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
    ExportTextInputFormFieldAsText = true,
    ImagesFolder = imagesDir
};
```

## Langkah 5: Simpan Dokumen sebagai HTML

Terakhir, mari simpan dokumen Word sebagai file HTML menggunakan opsi penyimpanan yang dikonfigurasi.

1. Tentukan Jalur Keluaran: Tentukan jalur di mana file HTML akan disimpan.
2.  Simpan Dokumen: Gunakan`Save` metode`Document`kelas untuk mengekspor dokumen.

```csharp
doc.Save(dataDir + "ExportedDocument.html", saveOptions);
```

## Kesimpulan

Dan itu dia! Anda telah berhasil mengekspor bidang formulir input teks sebagai teks biasa menggunakan Aspose.Words untuk .NET. Panduan ini seharusnya memberi Anda pendekatan langkah demi langkah yang jelas untuk mencapai tugas ini. Ingat, latihan membuat sempurna, jadi teruslah bereksperimen dengan berbagai opsi dan pengaturan untuk melihat apa lagi yang dapat Anda lakukan dengan Aspose.Words.

## FAQ

### Bisakah saya mengekspor jenis kolom formulir lainnya menggunakan metode yang sama?

 Ya, Anda dapat mengekspor tipe bidang formulir lainnya dengan mengonfigurasi properti yang berbeda`HtmlSaveOptions` kelas.

### Bagaimana jika dokumen saya memiliki gambar?

 Gambar akan disimpan di folder gambar yang ditentukan. Pastikan untuk mengatur`ImagesFolder` properti di`HtmlSaveOptions`.

### Apakah saya memerlukan lisensi untuk Aspose.Words?

 Ya, Anda bisa mendapatkan uji coba gratis[Di Sini](https://releases.aspose.com/) atau membeli lisensi[Di Sini](https://purchase.aspose.com/buy).

### Bisakah saya menyesuaikan HTML yang diekspor?

 Sangat! Aspose.Words menyediakan berbagai opsi untuk menyesuaikan keluaran HTML. Mengacu kepada[dokumentasi](https://reference.aspose.com/words/net/) untuk lebih jelasnya.

### Apakah Aspose.Words kompatibel dengan .NET Core?

Ya, Aspose.Words kompatibel dengan .NET Core, .NET Framework, dan platform .NET lainnya.
