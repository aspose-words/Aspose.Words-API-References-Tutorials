---
title: Perlindungan Hanya Baca Dalam Dokumen Word
linktitle: Perlindungan Hanya Baca Dalam Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara melindungi dokumen Word Anda dengan menerapkan perlindungan baca-saja menggunakan Aspose.Words untuk .NET. Ikuti panduan langkah demi langkah kami.
type: docs
weight: 10
url: /id/net/document-protection/read-only-protection/
---
## Perkenalan

Saat mengelola dokumen Word, ada kalanya Anda perlu menjadikannya hanya-baca untuk melindungi kontennya. Baik untuk berbagi informasi penting tanpa risiko pengeditan yang tidak disengaja atau memastikan integritas dokumen hukum, perlindungan hanya baca adalah fitur yang berharga. Dalam tutorial ini, kita akan mempelajari cara menerapkan perlindungan baca-saja di dokumen Word menggunakan Aspose.Words untuk .NET. Kami akan memandu Anda melalui setiap langkah secara mendetail dan menarik, memastikan Anda dapat mengikutinya dengan mudah.

## Prasyarat

Sebelum kita mendalami kodenya, ada beberapa prasyarat yang perlu Anda miliki:

1.  Aspose.Words for .NET: Pastikan Anda telah menginstal perpustakaan Aspose.Words for .NET. Anda dapat mengunduhnya dari[Halaman rilis Aspose](https://releases.aspose.com/words/net/).
2. Lingkungan Pengembangan: Siapkan lingkungan pengembangan dengan .NET terinstal. Visual Studio adalah pilihan yang bagus.
3. Pemahaman Dasar C#: Tutorial ini mengasumsikan Anda memiliki pemahaman dasar tentang pemrograman C#.

## Impor Namespace

Pertama, pastikan kita telah mengimpor namespace yang diperlukan. Ini penting karena memungkinkan kita mengakses kelas dan metode yang kita perlukan dari Aspose.Words untuk .NET.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Langkah 1: Siapkan Dokumen

Pada langkah ini, kita akan membuat dokumen baru dan pembuat dokumen. Ini menjadi landasan bagi operasi kami.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Tulis beberapa teks ke dokumen.
builder.Write("Open document as read-only");
```

Penjelasan:

- Kita mulai dengan menentukan jalur direktori tempat dokumen akan disimpan.
-  Yang baru`Document` objek dibuat, dan a`DocumentBuilder` dikaitkan dengannya.
- Dengan menggunakan pembuatnya, kami menambahkan sebaris teks sederhana ke dokumen.

## Langkah 2: Tetapkan Kata Sandi Perlindungan Tulis

Selanjutnya, kita perlu mengatur kata sandi untuk proteksi penulisan. Kata sandi ini bisa sampai 15 karakter.

```csharp
//Masukkan kata sandi yang panjangnya maksimal 15 karakter.
doc.WriteProtection.SetPassword("MyPassword");
```

Penjelasan:

-  Itu`SetPassword` metode dipanggil di`WriteProtection` milik dokumen.
- Kami memberikan kata sandi ("Kata Sandi Saya" dalam hal ini) yang diperlukan untuk menghapus perlindungan.

## Langkah 3: Aktifkan Rekomendasi Hanya-Baca

Pada langkah ini, kami membuat dokumen direkomendasikan hanya-baca. Artinya ketika dokumen dibuka, pengguna akan diminta untuk membukanya dalam mode read-only.

```csharp
// Jadikan dokumen sebagai read-only direkomendasikan.
doc.WriteProtection.ReadOnlyRecommended = true;
```

Penjelasan:

-  Itu`ReadOnlyRecommended` properti disetel ke`true`.
- Ini akan meminta pengguna untuk membuka dokumen dalam mode baca-saja, meskipun mereka dapat memilih untuk mengabaikan rekomendasi tersebut.

## Langkah 4: Terapkan Perlindungan Hanya-Baca

Terakhir, kami menerapkan perlindungan read-only pada dokumen. Langkah ini menegakkan perlindungan.

```csharp
// Terapkan perlindungan tulis sebagai hanya-baca.
doc.Protect(ProtectionType.ReadOnly);
```

Penjelasan:

-  Itu`Protect` metode dipanggil pada dokumen dengan`ProtectionType.ReadOnly` sebagai argumennya.
- Metode ini menerapkan perlindungan read-only, mencegah modifikasi apa pun pada dokumen tanpa kata sandi.

## Langkah 5: Simpan Dokumen

Langkah terakhir adalah menyimpan dokumen dengan pengaturan proteksi yang diterapkan.

```csharp
// Simpan dokumen yang dilindungi.
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");
```

Penjelasan:

-  Itu`Save` metode dipanggil pada dokumen, menentukan jalur dan nama file.
- Dokumen disimpan dengan perlindungan read-only.

## Kesimpulan

Dan itu dia! Anda telah berhasil membuat dokumen Word yang dilindungi hanya-baca menggunakan Aspose.Words untuk .NET. Fitur ini memastikan konten dokumen Anda tetap utuh dan tidak berubah, sehingga memberikan lapisan keamanan tambahan. Baik Anda berbagi informasi sensitif atau dokumen hukum, perlindungan hanya baca adalah alat yang harus dimiliki dalam gudang manajemen dokumen Anda.

## FAQ

### Apa itu Aspose.Words untuk .NET?
Aspose.Words untuk .NET adalah pustaka canggih yang memungkinkan pengembang membuat, memodifikasi, mengonversi, dan melindungi dokumen Word secara terprogram menggunakan C# atau bahasa .NET lainnya.

### Bisakah saya menghapus perlindungan baca-saja dari suatu dokumen?
 Ya, Anda dapat menghapus perlindungan read-only dengan menggunakan`Unprotect` metode dan memberikan kata sandi yang benar.

### Apakah kata sandi yang ditetapkan dalam dokumen dienkripsi?
Ya, Aspose.Words mengenkripsi kata sandi untuk memastikan keamanan dokumen yang dilindungi.

### Bisakah saya menerapkan jenis perlindungan lain menggunakan Aspose.Words untuk .NET?
Ya, Aspose.Words untuk .NET mendukung berbagai jenis perlindungan, termasuk hanya mengizinkan komentar, mengisi formulir, atau melacak perubahan.

### Apakah ada uji coba gratis yang tersedia untuk Aspose.Words untuk .NET?
 Ya, Anda dapat mengunduh uji coba gratis dari[Halaman rilis Aspose](https://releases.aspose.com/).