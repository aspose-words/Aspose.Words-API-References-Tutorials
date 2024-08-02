---
title: Gunakan Karakter Spasi Per Level Untuk Indentasi Daftar
linktitle: Gunakan Karakter Spasi Per Level Untuk Indentasi Daftar
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara membuat daftar bertingkat dengan lekukan karakter spasi di Aspose.Words untuk .NET. Panduan langkah demi langkah untuk pemformatan dokumen yang tepat.
type: docs
weight: 10
url: /id/net/programming-with-txtsaveoptions/use-space-character-per-level-for-list-indentation/
---
## Perkenalan

Dalam hal pemformatan dokumen, terutama saat bekerja dengan daftar, presisi adalah kuncinya. Dalam skenario di mana Anda perlu membuat dokumen dengan berbagai tingkat indentasi, Aspose.Words for .NET menawarkan alat canggih untuk menangani tugas ini. Salah satu fitur khusus yang berguna adalah mengonfigurasi indentasi daftar dalam file teks. Panduan ini akan memandu Anda tentang cara menggunakan karakter spasi untuk indentasi daftar, memastikan dokumen Anda mempertahankan struktur dan keterbacaan yang diinginkan.

## Prasyarat

Sebelum masuk ke tutorial, inilah yang Anda perlukan:

-  Aspose.Words untuk .NET: Pastikan Anda telah menginstal perpustakaan Aspose.Words. Jika Anda belum memilikinya, Anda dapat mengunduhnya dari[Asumsikan situs web](https://releases.aspose.com/words/net/).
- Visual Studio: Lingkungan pengembangan untuk menulis dan menguji kode Anda.
- Pemahaman Dasar C#: Keakraban dengan C# dan .NET framework akan membantu Anda mengikutinya dengan lancar.

## Impor Namespace

Untuk mulai bekerja dengan Aspose.Words, Anda harus mengimpor namespace yang diperlukan. Inilah cara Anda dapat memasukkannya ke dalam proyek Anda:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Mari kita uraikan proses pembuatan dokumen dengan daftar bertingkat dan menentukan karakter spasi untuk lekukan. 

## Langkah 1: Siapkan Dokumen Anda

 Pertama, Anda harus membuat dokumen baru dan menginisialisasi`DocumentBuilder` obyek. Objek ini akan memudahkan Anda menambahkan konten dan memformatnya sesuai kebutuhan.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Buat dokumen dan tambahkan konten
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Dalam cuplikan ini, ganti`"YOUR DOCUMENTS DIRECTORY"` dengan jalur sebenarnya tempat Anda ingin menyimpan dokumen Anda.

## Langkah 2: Buat Daftar dengan Berbagai Tingkat Indentasi

 Dengan`DocumentBuilder` Misalnya, Anda kini dapat membuat daftar dengan tingkat lekukan berbeda. Menggunakan`ListFormat` properti untuk menerapkan penomoran dan membuat indentasi item daftar sesuai kebutuhan.

```csharp
// Buat daftar dengan tiga tingkat lekukan
builder.ListFormat.ApplyNumberDefault();
builder.Write("Element 1");
builder.ListFormat.ListIndent();
builder.Write("Element 2");
builder.ListFormat.ListIndent();
builder.Write("Element 3");
```

 Pada langkah ini,`ApplyNumberDefault` mengatur format daftar, dan`ListIndent` digunakan untuk meningkatkan tingkat indentasi untuk setiap item daftar berikutnya.

## Langkah 3: Konfigurasikan Karakter Spasi untuk Indentasi

Sekarang setelah daftar Anda disiapkan, langkah selanjutnya adalah mengonfigurasi cara penanganan indentasi daftar saat menyimpan dokumen ke file teks. Anda akan menggunakan`TxtSaveOptions` untuk menentukan bahwa karakter spasi harus digunakan untuk indentasi.

```csharp
// Gunakan satu karakter spasi per level untuk lekukan daftar
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 3;
saveOptions.ListIndentation.Character = ' ';
```

 Di Sini,`ListIndentation.Count` menentukan jumlah karakter spasi per tingkat lekukan, dan`ListIndentation.Character` mengatur karakter sebenarnya yang digunakan untuk indentasi.

## Langkah 4: Simpan Dokumen dengan Opsi Tertentu

Terakhir, simpan dokumen Anda menggunakan opsi yang dikonfigurasi. Ini akan menerapkan pengaturan indentasi dan menyimpan file Anda dalam format yang diinginkan.

```csharp
// Simpan dokumen dengan opsi yang ditentukan
doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
```

 Cuplikan kode ini menyimpan dokumen ke jalur yang ditentukan`dataDir` dengan nama file`"WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt"`. File yang disimpan akan memiliki daftar yang diformat sesuai dengan pengaturan indentasi Anda.

## Kesimpulan

Dengan mengikuti langkah-langkah ini, Anda telah berhasil membuat dokumen dengan lekukan daftar bertingkat menggunakan karakter spasi untuk pemformatan. Pendekatan ini memastikan daftar Anda terstruktur dengan baik dan mudah dibaca, bahkan ketika disimpan sebagai file teks. Aspose.Words untuk .NET menyediakan alat canggih untuk manipulasi dokumen, dan menguasai fitur-fitur ini dapat meningkatkan alur kerja pemrosesan dokumen Anda secara signifikan.

## FAQ

### Bisakah saya menggunakan karakter berbeda untuk indentasi daftar selain spasi?
 Ya, Anda dapat menentukan karakter berbeda untuk indentasi daftar dengan mengatur`Character` properti di`TxtSaveOptions`.

### Bagaimana cara menerapkan poin-poin alih-alih angka dalam daftar?
 Menggunakan`ListFormat.ApplyBulletDefault()` alih-alih`ApplyNumberDefault()` untuk membuat daftar berpoin.

### Bisakah saya menyesuaikan jumlah ruang untuk lekukan secara dinamis?
 Ya, Anda dapat menyesuaikannya`ListIndentation.Count` properti untuk mengatur jumlah ruang berdasarkan kebutuhan Anda.

### Apakah mungkin mengubah indentasi daftar setelah dokumen dibuat?
Ya, Anda dapat mengubah format daftar dan pengaturan indentasi kapan saja sebelum menyimpan dokumen.

### Format dokumen lain apa yang mendukung pengaturan indentasi daftar?
Selain file teks, pengaturan indentasi daftar dapat diterapkan ke format lain seperti DOCX, PDF, dan HTML saat menggunakan Aspose.Words.