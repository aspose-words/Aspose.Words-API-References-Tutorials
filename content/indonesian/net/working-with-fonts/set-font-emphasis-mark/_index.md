---
title: Atur Tanda Penekanan Font
linktitle: Atur Tanda Penekanan Font
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengatur gaya penekanan font di dokumen Word menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-fonts/set-font-emphasis-mark/
---

Dalam tutorial ini, kami akan menunjukkan cara mengatur gaya penekanan font di dokumen Word menggunakan Aspose.Words untuk .NET. Penekanan font digunakan untuk menyorot kata atau frasa tertentu dalam teks.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki item berikut:
- Pengetahuan tentang bahasa pemrograman C#
- Pustaka Aspose.Words untuk .NET diinstal di proyek Anda

## Langkah 1: Tentukan direktori dokumen
Mulailah dengan mengatur jalur direktori ke lokasi dokumen Word Anda. Mengganti`"YOUR DOCUMENT DIRECTORY"` dalam kode dengan jalur yang sesuai.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Buat dan sesuaikan dokumen
 Buat sebuah instance dari`Document` kelas dan yang terkait`DocumentBuilder` untuk membangun konten dokumen. Menggunakan`Font.EmphasisMark` properti untuk mengatur gaya penekanan font`EmphasisMark.UnderSolidCircle` . Kemudian gunakan`Write` Dan`Writeln` metode dari`DocumentBuilder` untuk menambahkan teks dengan penekanan font yang ditentukan.

```csharp
Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasized text");
builder. Writen();
builder.Font.ClearFormatting();
builder.Write("Simple text");
```

## Langkah 3: Simpan dokumen
 Simpan dokumen menggunakan`Save` metode`Document` dengan jalur dan nama file yang sesuai.

```csharp
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

### Contoh kode sumber untuk Mengatur Tanda Penekanan Font menggunakan Aspose.Words untuk .NET 

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasis text");
builder.Writeln();
builder.Font.ClearFormatting();
builder.Write("Simple text");
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

## Kesimpulan
Dalam tutorial ini, Anda mempelajari cara mengatur gaya penekanan font di dokumen Word menggunakan Aspose.Words untuk .NET. Bereksperimenlah dengan berbagai gaya penekanan dan gunakan fitur ini untuk menyorot kata atau frasa dalam dokumen Anda.

### FAQ

#### T: Bagaimana cara menambahkan tanda aksen ke font tertentu di dokumen Word menggunakan Aspose.Words?

J: Untuk menambahkan tanda aksen ke font tertentu di dokumen Word menggunakan Aspose.Words, Anda dapat menggunakan API untuk menavigasi ke font yang diinginkan dan menerapkan tanda aksen yang sesuai. Ini akan menambahkan tanda aksen pada teks dengan font yang dipilih.

#### T: Apakah mungkin mengubah gaya tanda aksen di dokumen Word dengan Aspose.Words?

J: Ya, dengan Aspose.Words Anda dapat mengubah gaya tanda aksen di dokumen Word. API memungkinkan Anda menyesuaikan properti gaya seperti warna, ukuran, tipe garis, dll., untuk menyesuaikan tampilan tanda aksen.

#### T: Bagaimana cara menghapus semua tanda aksen dari dokumen Word menggunakan Aspose.Words?

J: Untuk menghapus semua tanda aksen dari dokumen Word menggunakan Aspose.Words, Anda dapat menggunakan API untuk menelusuri dokumen, mendeteksi tanda aksen yang ada, dan menghapusnya menggunakan metode yang sesuai. Ini akan menghapus semua tanda penekanan dari dokumen.

#### T: Bisakah saya menambahkan tanda aksen ke bagian teks tertentu di dokumen Word?

J: Ya, Anda dapat menambahkan tanda aksen ke bagian teks tertentu di dokumen Word menggunakan Aspose.Words. Anda dapat memilih rentang teks yang diinginkan menggunakan API dan menambahkan tanda penekanan yang sesuai ke bagian teks tersebut.

#### Q: Apakah tanda aksen dapat disesuaikan dengan kebutuhan saya?

A: Ya, tanda aksen dapat disesuaikan dengan kebutuhan Anda menggunakan Aspose.Words. Anda dapat menyesuaikan properti gaya tanda aksen, seperti warna, ukuran, tipe garis, dan lainnya, agar sesuai dengan preferensi pemformatan Anda.