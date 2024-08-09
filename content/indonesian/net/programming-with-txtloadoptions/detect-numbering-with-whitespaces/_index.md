---
title: Deteksi Penomoran Dengan Spasi Putih
linktitle: Deteksi Penomoran Dengan Spasi Putih
second_title: API Pemrosesan Dokumen Aspose.Words
description: Temukan cara menggunakan Aspose.Words untuk .NET untuk mendeteksi penomoran dengan spasi putih dalam dokumen teks biasa dan memastikan daftar Anda dikenali dengan benar.
type: docs
weight: 10
url: /id/net/programming-with-txtloadoptions/detect-numbering-with-whitespaces/
---
## Perkenalan

Aspose.Words untuk penggemar .NET! Hari ini, kita akan mendalami fitur menarik yang dapat mempermudah penanganan daftar dalam dokumen teks biasa. Pernahkah Anda berurusan dengan file teks yang beberapa barisnya seharusnya berupa daftar, tetapi baris-baris tersebut terlihat kurang tepat saat dimuat ke dalam dokumen Word? Ya, kami punya trik menarik: mendeteksi penomoran dengan spasi. Tutorial ini akan memandu Anda tentang cara menggunakan`DetectNumberingWithWhitespaces` opsi di Aspose.Words untuk .NET untuk memastikan daftar Anda dikenali dengan benar, meskipun ada spasi antara angka dan teks.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal berikut:

-  Aspose.Words untuk .NET: Anda dapat mengunduhnya dari[Asumsikan Rilis](https://releases.aspose.com/words/net/) halaman.
- Lingkungan Pengembangan: Visual Studio atau C# IDE lainnya.
- .NET Framework diinstal pada mesin Anda.
- Pengetahuan Dasar C#: Memahami dasar-dasarnya akan membantu Anda mengikuti contoh.

## Impor Namespace

Sebelum beralih ke kode, pastikan Anda telah mengimpor namespace yang diperlukan ke proyek Anda. Berikut cuplikan singkat untuk membantu Anda memulai:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Loading;
```

Mari kita bagi prosesnya menjadi langkah-langkah sederhana dan mudah dikelola. Setiap langkah akan memandu Anda melalui kode yang diperlukan dan menjelaskan apa yang terjadi.

## Langkah 1: Tentukan Direktori Dokumen Anda

Hal pertama yang pertama, mari siapkan jalur ke direktori dokumen Anda. Di sinilah file input dan output Anda akan disimpan.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Buat Dokumen Plaintext

Selanjutnya, kita akan membuat dokumen plaintext sebagai string. Dokumen ini akan berisi bagian-bagian yang dapat diartikan sebagai daftar.

```csharp
const string textDoc = "Full stop delimiters:\n" +
                       "1. First list item 1\n" +
                       "2. First list item 2\n" +
                       "3. First list item 3\n\n" +
                       "Right bracket delimiters:\n" +
                       "1) Second list item 1\n" +
                       "2) Second list item 2\n" +
                       "3) Second list item 3\n\n" +
                       "Bullet delimiters:\n" +
                       "• Third list item 1\n" +
                       "• Third list item 2\n" +
                       "• Third list item 3\n\n" +
                       "Whitespace delimiters:\n" +
                       "1 Fourth list item 1\n" +
                       "2 Fourth list item 2\n" +
                       "3 Fourth list item 3";
```

## Langkah 3: Konfigurasikan LoadOptions

 Untuk mendeteksi penomoran dengan spasi, kita perlu mengatur`DetectNumberingWithWhitespaces` pilihan untuk`true` di sebuah`TxtLoadOptions` obyek.

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };
```

## Langkah 4: Muat Dokumen

 Sekarang, mari kita memuat dokumen menggunakan`TxtLoadOptions` sebagai parameter. Hal ini memastikan bahwa daftar keempat (dengan spasi) terdeteksi dengan benar.

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);
```

## Langkah 5: Simpan Dokumen

Terakhir, simpan dokumen ke direktori yang Anda tentukan. Ini akan menampilkan dokumen Word dengan daftar yang terdeteksi dengan benar.

```csharp
doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
```

## Kesimpulan

Dan itu dia! Hanya dengan beberapa baris kode, Anda telah menguasai seni mendeteksi penomoran dengan spasi di dokumen teks biasa menggunakan Aspose.Words untuk .NET. Fitur ini bisa sangat berguna saat menangani berbagai format teks dan memastikan daftar Anda terwakili secara akurat dalam dokumen Word Anda. Jadi, lain kali Anda menemukan daftar rumit tersebut, Anda akan tahu persis apa yang harus dilakukan.

## FAQ

###  Apa`DetectNumberingWithWhitespaces` in Aspose.Words for .NET?
`DetectNumberingWithWhitespaces` adalah pilihan di`TxtLoadOptions` yang memungkinkan Aspose.Words mengenali daftar bahkan ketika ada spasi antara penomoran dan teks item daftar.

### Bisakah saya menggunakan fitur ini untuk pembatas lain seperti poin dan tanda kurung?
 Ya, Aspose.Words secara otomatis mendeteksi daftar dengan pembatas umum seperti poin dan tanda kurung. Itu`DetectNumberingWithWhitespaces` secara khusus membantu dengan daftar yang memiliki spasi.

###  Apa yang terjadi jika saya tidak menggunakannya`DetectNumberingWithWhitespaces`?
Tanpa opsi ini, daftar dengan spasi antara penomoran dan teks mungkin tidak dikenali sebagai daftar, dan item dapat muncul sebagai paragraf biasa.

### Apakah fitur ini tersedia di produk Aspose lainnya?
Fitur khusus ini disesuaikan untuk Aspose.Words untuk .NET, dirancang untuk menangani pemrosesan dokumen Word.

### Bagaimana saya bisa mendapatkan lisensi sementara untuk Aspose.Words untuk .NET?
 Anda dapat memperoleh lisensi sementara dari[Ajukan Lisensi Sementara](https://purchase.aspose.com/temporary-license/) halaman.

