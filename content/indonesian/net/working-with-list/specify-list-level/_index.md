---
title: Tentukan Tingkat Daftar
linktitle: Tentukan Tingkat Daftar
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menentukan tingkat daftar dalam dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-list/specify-list-level/
---

Dalam tutorial langkah demi langkah ini, kami akan menunjukkan kepada Anda cara menentukan tingkat daftar dalam dokumen Word menggunakan Aspose.Words untuk .NET. Kami akan menjelaskan kode sumber C# yang disediakan dan menunjukkan cara mengimplementasikannya di proyek Anda sendiri.

 Untuk memulai, pastikan Anda telah menginstal dan mengkonfigurasi Aspose.Words for .NET di lingkungan pengembangan Anda. Jika Anda belum melakukannya, unduh dan instal perpustakaan dari[Aspose.Rilis]https://releases.aspose.com/words/net/.

## Langkah 1: Membuat Dokumen dan Pembuat Dokumen

Pertama, buat dokumen baru dan pembuat dokumen terkait:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 2: Membuat dan Menerapkan Daftar Bernomor

Selanjutnya, buat daftar bernomor berdasarkan salah satu templat daftar Microsoft Word dan terapkan ke paragraf saat ini di pembuat dokumen:

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);
```

## Langkah 3: Daftar Spesifikasi Tingkat

 Gunakan pembuat dokumen`ListLevelNumber` properti untuk menentukan tingkat daftar dan menambahkan teks ke paragraf:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

Ulangi langkah-langkah ini untuk menentukan tingkat daftar dan menambahkan teks di setiap tingkat.

## Langkah 4: Membuat dan Menerapkan Daftar Berpoin

Anda juga dapat membuat dan menerapkan daftar berpoin menggunakan salah satu templat daftar Microsoft Word:

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);
```

## Langkah 5: Menambahkan Teks ke Tingkat Daftar Berpoin

 Menggunakan`ListLevelNumber` properti lagi untuk menentukan tingkat daftar berpoin dan menambahkan teks:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

## Langkah 6: Hentikan Pemformatan Daftar

 Untuk menghentikan pemformatan daftar, atur`null` ke`List`properti pembuat dokumen:

```csharp
builder. ListFormat. List = null;
```

## Langkah 7: Menyimpan dokumen yang dimodifikasi

Simpan dokumen yang diubah:

```csharp
builder.Document.Save(dataDir + "SpecifyListLevel.docx");
```

Jadi ! Anda telah berhasil menentukan tingkat daftar dalam dokumen Word menggunakan Aspose.Words untuk .NET.

### Contoh kode sumber untuk menentukan tingkat daftar

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Buat daftar bernomor berdasarkan salah satu templat daftar Microsoft Word.
//dan menerapkannya pada paragraf pembuat dokumen saat ini.
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);

// Ada sembilan level dalam daftar ini, mari kita coba semuanya.
for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// Buat daftar berpoin berdasarkan salah satu templat daftar Microsoft Word.
//dan menerapkannya pada paragraf pembuat dokumen saat ini.
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);

for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// Ini adalah cara untuk menghentikan pemformatan daftar.
builder.ListFormat.List = null;

builder.Document.Save(dataDir + "WorkingWithList.SpecifyListLevel.docx");
            
```

### FAQ

#### T: Bagaimana cara menentukan level daftar di Aspose.Words?

 J: Untuk menentukan level daftar di Aspose.Words, Anda perlu membuat instance dari`List` kelas dan berikan daftar bernomor. Kemudian Anda dapat menggunakan`Paragraph.ListFormat.ListLevelNumber` properti untuk menentukan level setiap item daftar. Anda dapat mengaitkan daftar ini dengan bagian dokumen Anda sehingga item daftar memiliki tingkat yang diinginkan.

#### T: Apakah mungkin mengubah format penomoran item daftar di Aspose.Words?

 A: Ya, Anda dapat mengubah format penomoran item daftar di Aspose.Words. Itu`ListLevel` class menawarkan beberapa properti untuk ini, seperti`ListLevel.NumberFormat`, `ListLevel.NumberStyle`, `ListLevel.NumberPosition`, dll. Anda dapat menggunakan properti ini untuk mengatur format penomoran item daftar, seperti angka Arab, angka Romawi, huruf, dll.

#### T: Bisakah saya menambahkan level tambahan ke daftar bernomor di Aspose.Words?

 J: Ya, dimungkinkan untuk menambahkan level tambahan ke daftar bernomor di Aspose.Words. Itu`ListLevel`kelas memungkinkan Anda mengatur properti pemformatan untuk setiap level daftar. Anda dapat mengatur opsi seperti awalan, akhiran, perataan, indentasi, dll. Ini memungkinkan Anda membuat daftar dengan berbagai tingkat hierarki.


