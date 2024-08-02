---
title: Masukkan ASKField Tanpa Pembuat Dokumen
linktitle: Masukkan ASKField Tanpa Pembuat Dokumen
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyisipkan bidang ASK tanpa menggunakan Pembuat Dokumen di Aspose.Words untuk .NET. Ikuti panduan ini untuk menyempurnakan dokumen Word Anda secara dinamis.
type: docs
weight: 10
url: /id/net/working-with-fields/insert-askfield-with-out-document-builder/
---
## Perkenalan

Apakah Anda ingin menguasai otomatisasi dokumen dengan Aspose.Words untuk .NET? Anda datang ke tempat yang tepat! Hari ini, kami akan memandu Anda tentang cara menyisipkan bidang ASK tanpa menggunakan Pembuat Dokumen. Ini adalah fitur bagus ketika Anda ingin dokumen Anda meminta masukan spesifik kepada pengguna, menjadikan dokumen Word Anda lebih interaktif dan dinamis. Jadi, mari selami dan jadikan dokumen Anda lebih cerdas!

## Prasyarat

Sebelum kita mengotori beberapa kode, pastikan kita sudah menyiapkan semuanya:

1.  Aspose.Words untuk .NET: Pastikan Anda telah menginstal perpustakaan ini. Jika tidak, Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/words/net/).
2. Lingkungan Pengembangan: IDE yang cocok seperti Visual Studio.
3. .NET Framework: Pastikan Anda telah menginstal .NET Framework.

Besar! Sekarang kita sudah siap, mari mulai dengan mengimpor namespace yang diperlukan.

## Impor Namespace

Hal pertama yang pertama, kita perlu mengimpor namespace Aspose.Words untuk mengakses semua fitur Aspose.Words untuk .NET. Inilah cara Anda melakukannya:

```csharp
using Aspose.Words;
using Aspose.Words.Fields;
```

## Langkah 1: Buat Dokumen Baru

Sebelum kita dapat menyisipkan kolom ASK, kita memerlukan dokumen untuk digunakan. Berikut cara membuat dokumen baru:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Pembuatan dokumen.
Document doc = new Document();
```

Cuplikan kode ini menyiapkan dokumen Word baru tempat kita akan menambahkan kolom ASK.

## Langkah 2: Akses Node Paragraf

Dalam dokumen Word, konten disusun menjadi node. Kita perlu mengakses node paragraf pertama di mana kita akan memasukkan kolom ASK kita:

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

Baris kode ini mengambil paragraf pertama dalam dokumen, siap untuk dimasukkan ke kolom ASK.

## Langkah 3: Masukkan Bidang ASK

Sekarang, mari kita ke acara utama – memasukkan kolom ASK. Bidang ini akan meminta pengguna untuk memasukkan ketika dokumen dibuka.

```csharp
// Masukkan bidang ASK.
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);
```

Di sini, kami menambahkan bidang ASK ke paragraf. Sederhana, bukan?

## Langkah 4: Konfigurasikan Bidang ASK

Kita perlu mengatur beberapa properti untuk menentukan bagaimana perilaku bidang ASK. Mari konfigurasikan nama bookmark, teks perintah, respons default, dan perilaku gabungan surat:

```csharp
field.BookmarkName = "Test1";
field.PromptText = "Please enter your response:";
field.DefaultResponse = "Default response";
field.PromptOnceOnMailMerge = true;
```

- BookmarkName: Pengidentifikasi unik untuk bidang ASK.
- PromptText: Teks yang meminta pengguna untuk memasukkan.
- DefaultResponse: Respons yang telah diisi sebelumnya dan dapat diubah oleh pengguna.
- PromptOnceOnMailMerge: Menentukan apakah perintah hanya muncul sekali selama penggabungan surat.

## Langkah 5: Perbarui Bidang

Setelah mengonfigurasi kolom ASK, kita perlu memperbaruinya untuk memastikan semua pengaturan diterapkan dengan benar:

```csharp
field.Update();
```

Perintah ini memastikan kolom ASK kita sudah siap dan diatur dengan benar di dokumen.

## Langkah 6: Simpan Dokumen

Terakhir, mari simpan dokumen ke direktori yang kita tentukan:

```csharp
doc.Save(dataDir + "InsertionChampASKSansDocumentBuilder.docx");
```

Baris ini menyimpan dokumen dengan kolom ASK yang disisipkan. Dan begitulah – dokumen Anda kini dilengkapi dengan kolom ASK dinamis!

## Kesimpulan

Selamat! Anda baru saja menambahkan bidang ASK ke dokumen Word menggunakan Aspose.Words untuk .NET tanpa Pembuat Dokumen. Fitur ini dapat meningkatkan interaksi pengguna dengan dokumen Anda secara signifikan, menjadikannya lebih fleksibel dan ramah pengguna. Teruslah bereksperimen dengan berbagai bidang dan properti untuk membuka potensi penuh Aspose.Words. Selamat membuat kode!

## FAQ

### Apa itu bidang ASK di Aspose.Words?
Bidang ASK di Aspose.Words adalah bidang yang meminta pengguna untuk memasukkan input tertentu saat dokumen dibuka, sehingga memungkinkan entri data dinamis.

### Bisakah saya menggunakan beberapa kolom ASK dalam satu dokumen?
Ya, Anda bisa menyisipkan beberapa bidang ASK dalam dokumen, masing-masing dengan perintah dan respons unik.

###  Apa tujuan dari`PromptOnceOnMailMerge` property?
 Itu`PromptOnceOnMailMerge` properti menentukan apakah prompt ASK muncul hanya sekali selama operasi penggabungan surat atau setiap saat.

### Apakah saya perlu memperbarui kolom ASK setelah mengatur propertinya?
Ya, memperbarui bidang ASK memastikan bahwa semua properti diterapkan dengan benar dan bidang berfungsi seperti yang diharapkan.

### Bisakah saya menyesuaikan teks prompt dan respons default?
Sangat! Anda dapat mengatur teks perintah khusus dan respons default untuk menyesuaikan bidang ASK dengan kebutuhan spesifik Anda.