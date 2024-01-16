---
title: Pindah Ke Dokumen Mulai Akhir Di Dokumen Word
linktitle: Pindah Ke Dokumen Mulai Akhir Di Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menggunakan Aspose.Words untuk .NET untuk berpindah ke awal dan akhir dokumen di dokumen Word dengan panduan langkah demi langkah ini.
type: docs
weight: 10
url: /id/net/add-content-using-documentbuilder/move-to-document-start-end/
---
Dalam contoh ini, kita akan menjelajahi fitur Pindah Ke Dokumen Mulai/Akhir dari Aspose.Words untuk .NET. Aspose.Words adalah pustaka manipulasi dokumen canggih yang memungkinkan pengembang membuat, memodifikasi, dan mengonversi dokumen Word secara terprogram. Fitur Pindah Ke Dokumen Mulai/Akhir memungkinkan kita menavigasi ke awal atau akhir dokumen menggunakan kelas DocumentBuilder.

## Menjelaskan kode sumber langkah demi langkah

Mari kita telusuri kode sumber langkah demi langkah untuk memahami cara menggunakan fitur Pindahkan Ke Dokumen Mulai/Akhir menggunakan Aspose.Words untuk .NET.


## Langkah 1: Menginisialisasi dokumen dan pembuat dokumen

Selanjutnya, inisialisasi objek Document dan DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Langkah 2: Pindah ke awal dokumen

Untuk memindahkan posisi kursor ke awal dokumen, gunakan metode MoveToDocumentStart dari kelas DocumentBuilder:

```csharp
builder.MoveToDocumentStart();
```

## Langkah 3: Pindah ke akhir dokumen

Untuk memindahkan posisi kursor ke akhir dokumen, gunakan metode MoveToDocumentEnd dari kelas DocumentBuilder:

```csharp
builder.MoveToDocumentEnd();
```

## Langkah 4: Mengeluarkan posisi kursor

Anda dapat menampilkan posisi kursor menggunakan Console.WriteLine atau metode lain yang diinginkan. Misalnya:

```csharp
Console.WriteLine("\nThis is the beginning of the document.");
Console.WriteLine("\nThis is the end of the document.");
```

### Contoh kode sumber untuk Pindah Ke Dokumen Awal/Akhir menggunakan Aspose.Words untuk .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Pindahkan posisi kursor ke awal dokumen Anda.
builder.MoveToDocumentStart();
Console.WriteLine("\nThis is the beginning of the document.");

// Pindahkan posisi kursor ke akhir dokumen Anda.
builder.MoveToDocumentEnd();
Console.WriteLine("\nThis is the end of the document.");
```

## Kesimpulan

Dalam contoh ini, kita telah menjelajahi fitur Pindah Ke Dokumen Mulai/Akhir dari Aspose.Words untuk .NET. Kita mempelajari cara menavigasi ke awal dan akhir dokumen menggunakan kelas DocumentBuilder. Fitur ini berguna ketika Pemrosesan Kata secara terprogram dengan dokumen Word dan perlu memanipulasi atau menyisipkan konten pada posisi tertentu dalam dokumen.

### FAQ

#### T: Apa tujuan fitur Pindah Ke Dokumen Mulai/Akhir di Aspose.Words untuk .NET?

J: Fitur Pindah Ke Dokumen Mulai/Akhir di Aspose.Words untuk .NET memungkinkan pengembang menavigasi ke awal atau akhir dokumen Word menggunakan kelas DocumentBuilder. Ini berguna untuk memanipulasi atau menyisipkan konten secara terprogram pada posisi tertentu dalam dokumen.

#### T: Dapatkah saya menggunakan fitur ini dengan dokumen Word yang sudah ada?

J: Ya, Anda dapat menggunakan fitur Pindah Ke Dokumen Awal/Akhir dengan dokumen Word baru dan yang sudah ada. Cukup inisialisasi DocumentBuilder dengan objek Dokumen yang sesuai, lalu gunakan metode MoveToDocumentStart dan MoveToDocumentEnd seperti yang ditunjukkan dalam contoh kode sumber.

#### T: Bagaimana metode DocumentBuilder.MoveToDocumentStart/MoveToDocumentEnd memengaruhi konten dokumen?

J: Metode DocumentBuilder.MoveToDocumentStart memindahkan kursor ke awal dokumen tanpa mengubah konten yang ada. Demikian pula, metode DocumentBuilder.MoveToDocumentEnd memindahkan kursor ke akhir dokumen tanpa mengubah konten.

#### T: Dapatkah saya melakukan operasi lain setelah memindahkan kursor ke akhir dokumen?

J: Ya, setelah memindahkan kursor ke ujung dokumen, Anda dapat terus menggunakan DocumentBuilder untuk menambah atau mengubah konten pada posisi tersebut. Posisi kursor tetap berada di akhir dokumen hingga dipindahkan secara eksplisit.

#### T: Bagaimana cara menampilkan posisi kursor menggunakan Aspose.Words untuk .NET?

J: Anda dapat menampilkan posisi kursor menggunakan metode seperti Console.WriteLine, logging, atau mekanisme keluaran lain yang diinginkan. Dalam contoh kode sumber yang diberikan, Console.WriteLine digunakan untuk menampilkan pesan di awal dan akhir dokumen.