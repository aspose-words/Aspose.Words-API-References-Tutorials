---
title: Gunakan Karakter Spasi Per Level Untuk Indentasi Daftar
linktitle: Gunakan Karakter Spasi Per Level Untuk Indentasi Daftar
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk menggunakan karakter spasi per level untuk indentasi daftar di Aspose.Words untuk .NET. Buat dokumen Word yang terstruktur dengan baik dengan mudah.
type: docs
weight: 10
url: /id/net/programming-with-txtsaveoptions/use-space-character-per-level-for-list-indentation/
---
Aspose.Words untuk .NET adalah perpustakaan yang kuat untuk membuat, mengedit, dan memanipulasi dokumen Word dalam aplikasi C#. Di antara fitur yang ditawarkan oleh Aspose.Words adalah kemungkinan menggunakan satu karakter spasi per level untuk lekukan daftar. Dalam panduan ini, kami akan menunjukkan kepada Anda cara menggunakan kode sumber C# Aspose.Words untuk .NET untuk mengimplementasikan fungsi ini.

## Memahami perpustakaan Aspose.Words

Sebelum mendalami kodenya, penting untuk memahami perpustakaan Aspose.Words untuk .NET. Aspose.Words adalah perpustakaan populer yang membuat Pemrosesan Kata dengan dokumen Word menjadi mudah dan efisien. Ia menawarkan berbagai fungsi untuk membuat, memodifikasi dan memanipulasi dokumen Word, termasuk pengelolaan daftar dan indentasi.

## Membuat dokumen dan menambahkan konten

Langkah pertama adalah membuat dokumen baru dan menambahkan konten ke dalamnya. Gunakan kelas Dokumen untuk membuat instance dokumen baru. Kemudian gunakan kelas DocumentBuilder untuk menambahkan teks dan membuat daftar dengan beberapa tingkat indentasi. Berikut ini contohnya:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Buat daftar dengan tiga tingkat lekukan
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder.ListFormat.ListIndent();
builder. Writen("Element 2");
builder.ListFormat.ListIndent();
builder.Write("Element 3");
```

Dalam contoh ini, kita membuat dokumen baru dan menggunakan DocumentBuilder untuk menambahkan teks dan membuat daftar dengan tiga tingkat indentasi. Kami telah menambahkan tiga item ke daftar, dengan setiap item menunjukkan level tambahan.

## Menggunakan satu karakter spasi per level untuk lekukan daftar

Setelah konten ditambahkan, sekarang kita dapat mengonfigurasi indentasi daftar menggunakan satu karakter spasi per level. Untuk ini kita menggunakan kelas TxtSaveOptions dan kita mengatur properti ListIndentation.Count ke jumlah tingkat indentasi dan properti ListIndentation.Character ke karakter spasi yang akan digunakan. Begini caranya:

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 3;
saveOptions.ListIndentation.Character = ' ';

doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
```

Dalam contoh ini, kita membuat instance TxtSaveOptions dan menyetel properti ListIndentation.Count ke 3 untuk menunjukkan bahwa ada tiga tingkat indentasi dalam daftar. Kita juga mengatur properti ListIndentation.Character ke karakter spasi (' ') yang ingin kita gunakan untuk indentasi.

### Contoh kode sumber untuk fitur "Gunakan satu karakter spasi per level untuk indentasi daftar" dengan Aspose.Words untuk .NET

Berikut ini contoh kode sumber lengkap untuk fitur "Gunakan satu karakter spasi per level untuk indentasi daftar" dengan Aspose.Words untuk .NET:

```csharp

using Aspose.Words;
using Aspose.Words.Saving;

namespace Example
{
     class Program
     {
         static void Main(string[] args)
         {
             // Jalur ke direktori dokumen Anda
             string dataDir = "YOUR DOCUMENTS DIRECTORY";

             // Buat dokumen dan tambahkan konten
             Document doc = new Document();
             DocumentBuilder builder = new DocumentBuilder(doc);

             // Buat daftar dengan tiga tingkat lekukan
             builder.ListFormat.ApplyNumberDefault();
             builder. Writen("Element 1");
             builder.ListFormat.ListIndent();
             builder. Writen("Element 2");
             builder.ListFormat.ListIndent();
             builder.Write("Element 3");

             // Gunakan satu karakter spasi per level untuk lekukan daftar
             TxtSaveOptions saveOptions = new TxtSaveOptions();
             saveOptions.ListIndentation.Count = 3;
             saveOptions.ListIndentation.Character = ' ';

             // Simpan dokumen dengan opsi yang ditentukan
             doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
         }
     }
}

```

## Kesimpulan

Dalam panduan ini, kami menjelaskan cara menggunakan Aspose.Words untuk .NET untuk menerapkan fungsionalitas "Gunakan satu karakter spasi per level untuk indentasi daftar". Dengan mengikuti langkah-langkah yang disediakan dan menggunakan kode sumber C# yang disediakan, Anda dapat dengan mudah mengonfigurasi indentasi daftar di dokumen Word Anda menggunakan satu karakter spasi per level. Aspose.Words menawarkan fleksibilitas dan kekuatan luar biasa untuk Pemrosesan Kata dengan pemformatan teks dan manajemen daftar, memungkinkan Anda membuat dokumen terstruktur dengan baik dalam aplikasi C# Anda.

### Pertanyaan yang Sering Diajukan

#### T: Apa itu Aspose.Words untuk .NET?
Aspose.Words for .NET adalah perpustakaan yang kuat untuk membuat, mengedit, dan memanipulasi dokumen Word dalam aplikasi C#. Ia menawarkan banyak fitur untuk Pemrosesan Kata dengan dokumen Word, termasuk kemampuan untuk menggunakan satu spasi per level untuk membuat indentasi daftar.

#### T: Bagaimana cara menggunakan satu spasi per level untuk indentasi daftar dengan Aspose.Words untuk .NET?
Anda dapat menggunakan satu spasi per tingkat untuk indentasi daftar dengan mengikuti langkah-langkah berikut:

 Buat dokumen baru menggunakan`Document` kelas.

 Menggunakan`DocumentBuilder`kelas untuk menambahkan konten ke dokumen dan membuat daftar dengan berbagai tingkat lekukan.

 Setelah Anda menambahkan konten dan mengonfigurasi lekukan daftar, gunakan`TxtSaveOptions` kelas dan atur`ListIndentation.Count` properti dengan jumlah tingkat lekukan dan`ListIndentation.Character` properti di ruang (`' '`) menggunakan.

 Simpan dokumen dengan opsi yang ditentukan menggunakan`Save` metode`Document` kelas.

#### T: Apakah Aspose.Words mendukung karakter lain untuk indentasi daftar?
Ya, Aspose.Words mendukung karakter lain untuk membuat indentasi daftar. Anda dapat menggunakan karakter selain spasi, misalnya tab (`'\t'` ) atau karakter khusus lainnya, dengan mengatur`ListIndentation.Character` properti ke karakter yang diinginkan.

#### T: Apakah mungkin untuk menyesuaikan jumlah spasi per level untuk indentasi daftar?
 Ya, Anda dapat menyesuaikan jumlah spasi per tingkat untuk indentasi daftar dengan mengubah nilai`ListIndentation.Count` properti di`TxtSaveOptions` kelas. Anda dapat menentukan jumlah spasi yang Anda inginkan untuk setiap tingkat indentasi.

#### T: Fitur lain apa yang ditawarkan Aspose.Words untuk manajemen daftar?
Aspose.Words menawarkan banyak fitur untuk mengelola daftar di dokumen Word. Anda dapat membuat daftar bernomor atau berpoin, mengatur tingkat indentasi, mengkustomisasi gaya daftar, menambahkan item daftar, dan banyak lagi.