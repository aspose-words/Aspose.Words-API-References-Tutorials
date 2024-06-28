---
title: Mulai Ulang Nomor Daftar
linktitle: Mulai Ulang Nomor Daftar
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengatur ulang nomor daftar di dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-list/restart-list-number/
---
Dalam tutorial langkah demi langkah ini, kami akan menunjukkan kepada Anda cara mengatur ulang nomor daftar di dokumen Word menggunakan Aspose.Words untuk .NET. Kami akan menjelaskan kode sumber C# yang disediakan dan menunjukkan cara mengimplementasikannya di proyek Anda sendiri.

 Untuk memulai, pastikan Anda telah menginstal dan mengkonfigurasi Aspose.Words for .NET di lingkungan pengembangan Anda. Jika Anda belum melakukannya, unduh dan instal perpustakaan dari[Aspose.Rilis]https://releases.aspose.com/words/net/.

## Langkah 1: Membuat Dokumen dan Pembuat Dokumen

Pertama, buat dokumen baru dan pembuat dokumen terkait:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 2: Membuat dan Menyesuaikan Daftar Pertama

Selanjutnya, buat daftar berdasarkan templat yang sudah ada, lalu sesuaikan levelnya:

```csharp
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;
```

## Langkah 3: Menambahkan item ke daftar pertama

Gunakan pembuat dokumen untuk menambahkan item ke daftar pertama dan menghapus nomor daftar:

```csharp
builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## Langkah 4: Membuat dan Menyesuaikan Daftar Kedua

Untuk menggunakan kembali daftar pertama dengan mengatur ulang nomornya, buat salinan tata letak daftar asli:

```csharp
List list2 = doc.Lists.AddCopy(list1);
list2.ListLevels[0].StartAt = 10;
```

Anda juga dapat membuat perubahan tambahan pada daftar kedua jika diperlukan.

## Langkah 5: Menambahkan item ke daftar kedua

Gunakan lagi pembuat dokumen untuk menambahkan item ke daftar kedua dan menghapus nomor daftar:

```csharp
builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## Langkah 6: Simpan dokumen yang dimodifikasi

Terakhir, simpan dokumen yang dimodifikasi:

```csharp
builder.Document.Save(dataDir + "ResetListNumber.docx");
```

Jadi ! Anda telah berhasil mereset nomor daftar di dokumen Word menggunakan Aspose.Words untuk .NET.

### Contoh Kode Sumber untuk Reset Nomor Daftar

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Buat daftar berdasarkan templat.
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;

builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

// Untuk menggunakan kembali daftar pertama, kita perlu memulai ulang penomoran dengan membuat salinan format daftar asli.
List list2 = doc.Lists.AddCopy(list1);

// Kami dapat mengubah daftar baru dengan cara apa pun, termasuk menetapkan nomor awal yang baru.
list2.ListLevels[0].StartAt = 10;

builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

builder.Document.Save(dataDir + "WorkingWithList.RestartListNumber.docx");
            
```

### FAQ

#### T: Bagaimana cara memulai ulang penomoran daftar di Aspose.Words?

 A: Untuk memulai kembali penomoran daftar di Aspose.Words, Anda dapat menggunakan`ListRestartAtNumber` metode`List` kelas. Metode ini memungkinkan Anda untuk menetapkan nilai panggilan baru dari mana daftar harus dimulai ulang. Misalnya, Anda bisa menggunakan`list.ListRestartAtNumber(1)` untuk memulai kembali penomoran dari 1.

#### T: Apakah mungkin untuk menyesuaikan awalan dan akhiran penomoran daftar yang dimulai ulang di Aspose.Words?

 A: Ya, Anda dapat menyesuaikan awalan dan akhiran penomoran daftar yang dimulai ulang di Aspose.Words. Itu`ListLevel` kelas menawarkan properti seperti`ListLevel.NumberPrefix` Dan`ListLevel.NumberSuffix`yang memungkinkan Anda menentukan awalan dan akhiran untuk setiap level dalam daftar. Anda dapat menggunakan properti ini untuk menyesuaikan awalan dan akhiran sesuai kebutuhan.

#### T: Bagaimana cara menentukan nilai penomoran tertentu untuk memulai ulang daftar?

 J: Untuk menentukan nilai angka tertentu yang akan digunakan untuk memulai ulang daftar, Anda dapat menggunakan`ListRestartAtNumber` metode meneruskan nilai yang diinginkan sebagai argumen. Misalnya untuk me-restart penomoran dari 5, Anda dapat menggunakan`list.ListRestartAtNumber(5)`.

#### T: Apakah mungkin untuk memulai ulang penomoran daftar multi-level di Aspose.Words?

 J: Ya, Aspose.Words mendukung penomoran ulang beberapa tingkat daftar. Anda dapat menerapkan`ListRestartAtNumber` metode di setiap tingkat daftar untuk memulai kembali penomoran satu per satu. Misalnya, Anda bisa menggunakan`list.Levels[0].ListRestartAtNumber(1)` untuk memulai kembali level daftar pertama dari 1, dan`list.Levels[1].ListRestartAtNumber(1)` untuk memulai kembali daftar level kedua mulai dari 1, dan seterusnya.



