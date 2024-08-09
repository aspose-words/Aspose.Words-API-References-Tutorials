---
title: Bagian Tidak Terbatas Dalam Dokumen Word
linktitle: Bagian Tidak Terbatas Dalam Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Buka kunci bagian tertentu di dokumen Word Anda menggunakan Aspose.Words untuk .NET dengan panduan langkah demi langkah ini. Sempurna untuk melindungi konten sensitif.
type: docs
weight: 10
url: /id/net/document-protection/unrestricted-section/
---
## Perkenalan

Hai! Siap terjun ke dunia Aspose.Words untuk .NET? Hari ini, kami membahas sesuatu yang sangat praktis: cara membuka kunci bagian tertentu di dokumen Word sambil menjaga bagian lain tetap terlindungi. Jika Anda pernah perlu melindungi beberapa bagian dokumen Anda namun membiarkan bagian lainnya terbuka untuk diedit, tutorial ini cocok untuk Anda. Mari kita mulai!

## Prasyarat

Sebelum kita masuk ke seluk beluknya, pastikan Anda memiliki semua yang Anda butuhkan:

-  Aspose.Words for .NET: Jika Anda belum melakukannya, Anda bisa[unduh di sini](https://releases.aspose.com/words/net/).
- Visual Studio: Atau IDE lain yang kompatibel dengan .NET.
- Pemahaman Dasar C#: Sedikit pemahaman tentang C# akan membantu Anda memahami tutorial ini.
-  Lisensi Aspose: Ambil a[uji coba gratis](https://releases.aspose.com/) atau dapatkan a[izin sementara](https://purchase.aspose.com/temporary-license/) Jika Anda membutuhkannya untuk pengujian.

## Impor Namespace

Sebelum memulai pengkodean, pastikan Anda telah mengimpor namespace yang diperlukan dalam proyek C# Anda:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Tables;
```

Sekarang, mari kita uraikan langkah demi langkah!

## Langkah 1: Siapkan Proyek Anda

### Inisialisasi Direktori Dokumen Anda

Hal pertama yang pertama, Anda perlu mengatur jalur ke direktori dokumen Anda. Di sinilah file Word Anda akan disimpan.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya tempat Anda ingin menyimpan dokumen Anda. Ini penting karena memastikan file Anda disimpan di lokasi yang benar.

### Buat Dokumen Baru

Selanjutnya, kita akan membuat dokumen baru menggunakan Aspose.Words. Dokumen ini akan menjadi kanvas di mana kita akan menerapkan keajaiban kita.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Itu`Document` kelas menginisialisasi dokumen baru, dan`DocumentBuilder` membantu kami dengan mudah menambahkan konten ke dokumen kami.

## Langkah 2: Sisipkan Bagian

### Tambahkan Bagian yang Tidak Dilindungi

Mari kita mulai dengan menambahkan bagian pertama, yang tetap tidak terlindungi.

```csharp
builder.Writeln("Section 1. Unprotected.");
```

Baris kode ini menambahkan teks "Bagian 1. Tidak dilindungi." ke dokumen. Sederhana, bukan?

### Tambahkan Bagian yang Dilindungi

Sekarang, mari tambahkan bagian kedua dan masukkan pemisah bagian untuk memisahkannya dari bagian pertama.

```csharp
builder.InsertBreak(BreakType.SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");
```

 Itu`InsertBreak` metode menyisipkan hentian bagian secara terus-menerus, memungkinkan kita memiliki pengaturan berbeda untuk setiap bagian.

## Langkah 3: Lindungi Dokumen

### Aktifkan Perlindungan Dokumen

 Untuk melindungi dokumen, kami akan menggunakan`Protect` metode. Metode ini memastikan bahwa hanya kolom formulir yang dapat diedit kecuali ditentukan lain.

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

 Di sini, dokumen dilindungi dengan kata sandi, dan hanya kolom formulir yang dapat diedit. Ingatlah untuk mengganti`"password"` dengan kata sandi yang Anda inginkan.

### Buka Proteksi Bagian Tertentu

Secara default, semua bagian dilindungi. Kita perlu mematikan perlindungan secara selektif untuk bagian pertama.

```csharp
doc.Sections[0].ProtectedForForms = false;
```

Baris ini memastikan bahwa bagian pertama tetap tidak terlindungi sementara bagian dokumen lainnya diamankan.

## Langkah 4: Simpan dan Muat Dokumen

### Simpan Dokumen

Sekarang, saatnya menyimpan dokumen Anda dengan pengaturan proteksi yang diterapkan.

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");
```

 Ini menyimpan dokumen di direktori tertentu dengan nama`DocumentProtection.UnrestrictedSection.docx`.

### Muat Dokumen

Terakhir, kami memuat dokumen untuk memverifikasi bahwa semuanya telah diatur dengan benar.

```csharp
doc = new Document(dataDir + "DocumentProtection.UnrestrictedSection.docx");
```

Langkah ini memastikan bahwa dokumen disimpan dengan benar dan dapat dimuat ulang tanpa kehilangan pengaturan proteksi.

## Kesimpulan

Dan itu dia! Dengan mengikuti langkah-langkah ini, Anda telah berhasil membuat dokumen Word dengan campuran bagian yang dilindungi dan tidak dilindungi menggunakan Aspose.Words untuk .NET. Metode ini sangat berguna ketika Anda perlu mengunci bagian tertentu dari dokumen dan membiarkan bagian lain dapat diedit.

## FAQ

### Bisakah saya melindungi lebih dari satu bagian?
Ya, Anda dapat memproteksi dan membuka proteksi beberapa bagian secara selektif sesuai kebutuhan.

### Apakah mungkin mengubah jenis proteksi setelah menyimpan dokumen?
Ya, Anda dapat membuka kembali dokumen dan mengubah pengaturan proteksi sesuai kebutuhan.

### Jenis perlindungan apa lagi yang tersedia di Aspose.Words?
 Aspose.Words mendukung beberapa jenis perlindungan termasuk`ReadOnly`, `Comments` , Dan`TrackedChanges`.

### Bisakah saya melindungi dokumen tanpa kata sandi?
Ya, Anda dapat melindungi dokumen tanpa menentukan kata sandi.

### Bagaimana cara memeriksa apakah suatu bagian dilindungi?
 Anda dapat memeriksa`ProtectedForForms` properti suatu bagian untuk menentukan apakah bagian tersebut dilindungi.