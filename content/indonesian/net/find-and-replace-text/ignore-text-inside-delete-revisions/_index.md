---
title: Abaikan Teks di Dalam Hapus Revisi
linktitle: Abaikan Teks di Dalam Hapus Revisi
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menggunakan fitur "Abaikan Teks di Dalam Hapus Revisi" Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/find-and-replace-text/ignore-text-inside-delete-revisions/
---

Pada artikel ini, kita akan menjelajahi kode sumber C# di atas untuk memahami cara menggunakan fitur "Abaikan Teks di Dalam Hapus Revisi" di pustaka Aspose.Words untuk .NET. Fitur ini berguna ketika kita ingin mengabaikan teks di dalam revisi penghapusan saat Words Processing dengan dokumen.

## Ikhtisar perpustakaan Aspose.Words untuk .NET

Sebelum mendalami detail kode, izinkan saya memperkenalkan secara singkat perpustakaan Aspose.Words untuk .NET. Ini adalah perpustakaan canggih yang memungkinkan pembuatan, modifikasi, dan konversi dokumen Word dalam aplikasi .NET. Ini menawarkan banyak fitur lanjutan untuk Pemrosesan Kata dengan dokumen, termasuk manajemen revisi.

## Memahami fitur "Abaikan Teks di Dalam Hapus Revisi".

Fitur "Abaikan Teks di Dalam Hapus Revisi" di Aspose.Words untuk .NET memungkinkan Anda menentukan apakah teks di dalam revisi penghapusan harus diabaikan selama operasi tertentu, seperti menemukan dan mengganti teks. Jika fitur ini diaktifkan, teks yang dihapus di dalam revisi tidak dipertimbangkan selama pengoperasian.

## Langkah 1: Membuat dokumen baru menggunakan Aspose.Words untuk .NET

 Sebelum kita mulai memanipulasi teks dalam dokumen, kita perlu membuat dokumen baru menggunakan Aspose.Words untuk .NET. Hal ini dapat dilakukan dengan membuat contoh a`Document` obyek:

```csharp
Document doc = new Document();
```

## Langkah 2: Memasukkan teks yang tidak direvisi ke dalam dokumen

 Setelah kita memiliki dokumen, kita dapat menyisipkan teks yang belum ditinjau menggunakan a`DocumentBuilder` obyek. Misalnya untuk menyisipkan teks "Teks yang Dihapus", kita dapat menggunakan`Writeln` Dan`Write` metode:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. Writen("Deleted");
builder. Write("Text");
```

## Langkah 3: Menghapus paragraf dengan pelacakan revisi

Untuk mengilustrasikan penggunaan fitur "Abaikan Teks di Dalam Hapus Revisi", kami akan menghapus satu paragraf dari dokumen menggunakan pelacakan revisi. Ini akan memungkinkan kita melihat bagaimana fitur ini memengaruhi operasi selanjutnya.

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

## Langkah 4: Menerapkan fitur "Abaikan Teks di Dalam Hapus Revisi".

 Sekarang kita telah mempersiapkan dokumen kita dengan menghapus sebuah paragraf, kita dapat mengaktifkan fitur "Abaikan Teks di Dalam Hapus Revisi" menggunakan`FindReplaceOptions` obyek. Kami akan mengaturnya`IgnoreDeleted`properti ke`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

## Langkah 5: Menggunakan ekspresi reguler untuk menemukan dan mengganti

Untuk melakukan operasi pencarian dan penggantian pada teks dokumen, kita akan menggunakan ekspresi reguler. Dalam contoh kita, kita akan mencari semua kemunculan huruf "e" dan menggantinya dengan tanda bintang "* ". .NET`Regex` kelas digunakan untuk ini:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## Langkah 6: Menampilkan keluaran dokumen yang dimodifikasi

 Setelah menerapkan pencarian dan penggantian, kita dapat menampilkan konten dokumen yang diubah menggunakan`GetText` metode:

```csharp
Console.WriteLine(doc.GetText());
```

## Langkah 7: Memodifikasi opsi untuk memasukkan teks yang dihapus

 Jika kita ingin memasukkan teks yang dihapus ke dalam hasil keluaran, kita dapat mengubah opsi untuk tidak mengabaikan teks yang dihapus. Untuk ini kami akan mengaturnya`IgnoreDeleted`properti ke`false`:

```csharp
options. IgnoreDeleted = false;
```

## Langkah 8: Mengeluarkan dokumen yang dimodifikasi dengan teks yang dihapus

Setelah mengubah pilihan, kita dapat melakukan pencarian dan penggantian lagi untuk mendapatkan hasil dengan teks yang dihapus termasuk:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```

### Contoh kode sumber untuk Abaikan Teks di Dalam Hapus Revisi menggunakan Aspose.Words untuk .NET

Berikut ini contoh kode sumber lengkap untuk mendemonstrasikan penggunaan fitur "Abaikan Teks di Dalam Hapus Revisi" dengan Aspose.Words untuk .NET:

```csharp
        
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Sisipkan teks yang tidak direvisi.
	builder.Writeln("Deleted");
	builder.Write("Text");

	// Hapus paragraf pertama dengan pelacakan revisi.
	doc.StartTrackRevisions("author", DateTime.Now);
	doc.FirstSection.Body.FirstParagraph.Remove();
	doc.StopTrackRevisions();

	FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };

	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);

	Console.WriteLine(doc.GetText());

	options.IgnoreDeleted = false;
	doc.Range.Replace(regex, "*", options);

	Console.WriteLine(doc.GetText());
    
```

## Kesimpulan

Dalam artikel ini, kami menjelajahi kode sumber C# untuk memahami cara menggunakan fitur "Abaikan Teks di Dalam Hapus Revisi" di Aspose.Words untuk .NET. Fitur ini berguna untuk mengabaikan teks di dalam revisi penghapusan saat memanipulasi dokumen. Kami mengikuti panduan langkah demi langkah untuk membuat dokumen, menyisipkan teks, menghapus paragraf dengan pelacakan revisi, menerapkan fitur "Abaikan Teks di Dalam Hapus Revisi", dan melakukan operasi pencarian dan penggantian.

### FAQ

#### T: Apa yang dimaksud dengan fungsi "Abaikan Teks di Dalam Hapus Revisi" di Aspose.Words untuk .NET?

J: Fungsi "Abaikan Teks di Dalam Hapus Revisi" di Aspose.Words untuk .NET memungkinkan Anda menentukan apakah teks di dalam revisi penghapusan harus diabaikan selama operasi tertentu, seperti menemukan dan mengganti teks. Jika fitur ini diaktifkan, teks yang dihapus di dalam revisi tidak dipertimbangkan selama pengoperasian.

#### T: Apa itu Aspose.Words untuk .NET?

J: Aspose.Words for .NET adalah perpustakaan yang kuat untuk membuat, mengedit, dan mengonversi dokumen Word menjadi aplikasi .NET. Ini menawarkan banyak fitur lanjutan untuk Pemrosesan Kata dengan dokumen, termasuk manajemen revisi.

#### T: Bagaimana cara membuat dokumen baru di Aspose.Words untuk .NET?

 J: Sebelum Anda mulai memanipulasi teks dalam dokumen, Anda perlu membuat dokumen baru menggunakan Aspose.Words untuk .NET. Hal ini dapat dilakukan dengan membuat contoh a`Document` obyek. Berikut ini contoh kode untuk membuat dokumen baru:

```csharp
Document doc = new Document();
```

#### T: Bagaimana cara menyisipkan teks yang belum diedit ke dalam dokumen menggunakan Aspose.Words untuk .NET?

 J: Setelah Anda memiliki dokumen, Anda dapat menyisipkan teks yang belum ditinjau menggunakan a`DocumentBuilder` obyek. Misalnya, untuk menyisipkan teks "Teks yang Dihapus", Anda dapat menggunakan`Writeln` Dan`Write` metode:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writen("Deleted");
builder.Write("Text");
```

#### T: Bagaimana cara menghapus paragraf dengan pelacakan revisi di Aspose.Words untuk .NET?

J: Untuk mengilustrasikan penggunaan fungsi "Abaikan Teks di Dalam Hapus Revisi", kami akan menghapus satu paragraf dari dokumen menggunakan pelacakan revisi. Ini akan memungkinkan kita melihat bagaimana fungsi ini mempengaruhi operasi selanjutnya.

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

#### T: Bagaimana cara mengaktifkan fitur "Abaikan Teks di Dalam Hapus Revisi" di Aspose.Words untuk .NET?

 A: Sekarang kita telah mempersiapkan dokumen kita dengan menghapus sebuah paragraf, kita dapat mengaktifkan fitur "Abaikan Teks di Dalam Hapus Revisi" menggunakan`FindReplaceOptions` obyek. Kami akan mengaturnya`IgnoreDeleted`properti ke`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

#### T: Bagaimana cara mencari dan mengganti menggunakan ekspresi reguler di Aspose.Words untuk .NET?

A: Untuk melakukan operasi pencarian dan penggantian pada teks dokumen, kita akan menggunakan ekspresi reguler. Dalam contoh kita, kita akan mencari semua kemunculan huruf "e" dan menggantinya dengan tanda bintang "* ". Kami akan menggunakan .NET`Regex` kelas untuk ini:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### T: Bagaimana cara melihat konten dokumen yang diubah di Aspose.Words untuk .NET?

A: Setelah menerapkan pencarian dan penggantian, kami dapat menampilkan konten dokumen yang diubah menggunakan`GetText` metode:

```csharp
Console.WriteLine(doc.GetText());
```

#### T: Bagaimana cara memasukkan teks yang dihapus dalam hasil keluaran di Aspose.Words untuk .NET?

 A: Jika kita ingin memasukkan teks yang dihapus ke dalam hasil keluaran, kita dapat mengubah opsi untuk tidak mengabaikan teks yang dihapus. Untuk ini, kami akan mengaturnya`IgnoreDeleted`properti ke`false`:

```csharp
options. IgnoreDeleted = false;
```

#### T: Bagaimana cara menampilkan dokumen yang diedit dengan teks yang dihapus di Aspose.Words untuk .NET?

A: Setelah mengubah opsi, kita dapat melakukan pencarian dan penggantian baru untuk mendapatkan hasil dengan teks yang dihapus termasuk:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```
