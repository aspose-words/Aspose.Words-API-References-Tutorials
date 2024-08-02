---
title: Ubah Sumber Budaya Pembaruan Bidang
linktitle: Ubah Sumber Budaya Pembaruan Bidang
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengubah sumber budaya pembaruan bidang di Aspose.Words untuk .NET dengan panduan ini. Kontrol pemformatan tanggal berdasarkan budaya yang berbeda dengan mudah.
type: docs
weight: 10
url: /id/net/working-with-fields/change-field-update-culture-source/
---
## Perkenalan

Dalam tutorial ini, kita akan mendalami dunia Aspose.Words untuk .NET dan menjelajahi cara mengubah sumber budaya pembaruan lapangan. Jika Anda berurusan dengan dokumen Word yang menyertakan bidang tanggal dan Anda perlu mengontrol bagaimana tanggal tersebut diformat berdasarkan budaya yang berbeda, panduan ini cocok untuk Anda. Mari kita telusuri prosesnya langkah demi langkah, memastikan Anda memahami setiap konsep dan dapat menerapkannya secara efektif dalam proyek Anda.

## Prasyarat

Sebelum kita beralih ke kode, pastikan Anda memiliki yang berikut:

-  Aspose.Words untuk .NET: Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/words/net/).
- Lingkungan Pengembangan: Semua IDE yang kompatibel dengan .NET (misalnya, Visual Studio).
- Pengetahuan Dasar C#: Tutorial ini mengasumsikan Anda memiliki pemahaman mendasar tentang pemrograman C#.

## Impor Namespace

Pertama, mari impor namespace yang diperlukan untuk proyek kita. Ini akan memastikan bahwa kita memiliki akses ke semua kelas dan metode wajib yang disediakan oleh Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

Sekarang, mari kita bagi contoh ini menjadi beberapa langkah untuk membantu Anda memahami cara mengubah sumber budaya pembaruan bidang di Aspose.Words untuk .NET.

## Langkah 1: Inisialisasi Dokumen

 Langkah pertama adalah membuat instance baru dari`Document` kelas dan a`DocumentBuilder`. Ini menetapkan dasar untuk membangun dan memanipulasi dokumen Word kami.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 2: Sisipkan Bidang dengan Lokal Tertentu

Selanjutnya, kita perlu memasukkan field ke dalam dokumen. Untuk contoh ini, kami akan menyisipkan dua kolom tanggal. Kami akan mengatur lokal font ke Jerman (LocaleId = 1031) untuk menunjukkan bagaimana budaya mempengaruhi format tanggal.

```csharp
builder.Font.LocaleId = 1031; // Jerman
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");
```

## Langkah 3: Tetapkan Sumber Budaya Pembaruan Bidang

 Untuk mengontrol budaya yang digunakan saat memperbarui bidang, kami mengatur`FieldUpdateCultureSource` properti dari`FieldOptions`kelas. Properti ini menentukan apakah budaya diambil dari kode lapangan atau dokumen.

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
```

## Langkah 4: Jalankan Penggabungan Surat

Kita sekarang perlu menjalankan gabungan surat untuk mengisi kolom dengan data aktual. Dalam contoh ini, kita akan menyetel kolom tanggal kedua (`Date2`) sampai dengan 1 Januari 2011.

```csharp
doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });
```

## Langkah 5: Simpan Dokumen

Terakhir, kami menyimpan dokumen ke direktori yang ditentukan. Langkah ini menyelesaikan proses mengubah sumber budaya pembaruan lapangan.

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

## Kesimpulan

Dan itu dia! Anda telah berhasil mengubah sumber budaya pembaruan bidang di Aspose.Words untuk .NET. Dengan mengikuti langkah-langkah ini, Anda bisa memastikan bahwa dokumen Word Anda menampilkan tanggal dan nilai bidang lainnya sesuai dengan pengaturan budaya yang ditentukan. Hal ini khususnya berguna ketika menghasilkan dokumen untuk audiens internasional.

## FAQ

###  Apa tujuan dari pengaturan tersebut`LocaleId`?
 Itu`LocaleId` menentukan pengaturan budaya untuk teks, yang memengaruhi cara format tanggal dan data sensitif lokal lainnya.

### Bisakah saya menggunakan bahasa lain selain bahasa Jerman?
 Ya, Anda dapat mengaturnya`LocaleId`ke pengenal lokal apa pun yang valid. Misalnya 1033 untuk Bahasa Inggris (Amerika Serikat).

###  Apa yang terjadi jika saya tidak mengaturnya`FieldUpdateCultureSource` property?
Jika properti ini tidak disetel, pengaturan budaya default dokumen akan digunakan saat memperbarui kolom.

### Apakah mungkin memperbarui bidang berdasarkan budaya dokumen, bukan kode bidang?
 Ya, Anda dapat mengaturnya`FieldUpdateCultureSource` ke`FieldUpdateCultureSource.Document` untuk menggunakan pengaturan budaya dokumen.

### Bagaimana cara memformat tanggal dalam pola yang berbeda?
 Anda dapat mengubah pola format tanggal di`InsertField` metode dengan memodifikasi`\\@` beralih nilai.