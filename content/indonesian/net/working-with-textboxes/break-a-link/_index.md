---
title: Putuskan Tautan Maju Dalam Dokumen Word
linktitle: Putuskan Tautan Maju Dalam Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara memutus tautan maju dalam dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-textboxes/break-a-link/
---

Aspose.Words for .NET adalah perpustakaan canggih yang menawarkan berbagai fitur untuk Pemrosesan Kata dengan dokumen Microsoft Word secara terprogram. Salah satu fitur yang berguna adalah kemampuan untuk memutus tautan dalam dokumen Word. Dalam tutorial ini, kita akan menjelajahi kode sumber dalam C# yang menunjukkan cara memutus tautan maju di dokumen Word menggunakan Aspose.Words untuk .NET.

## Langkah 1: Pratinjau Kode Sumber C#

Kode sumber C# yang disediakan berfokus pada fitur "Break A Link" dari Aspose.Words untuk .NET. Ini menunjukkan cara memutus tautan dalam bentuk Kotak Teks di dalam dokumen. Kode ini menyajikan skenario berbeda untuk memutus tautan dan memberikan instruksi jelas tentang cara mencapai hasil yang diinginkan.

## Langkah 2: Menyiapkan dokumen dan membuat bentuk TextBox

 Untuk memulai, kita perlu menyiapkan dokumen dan membuat bentuk TextBox. Kode berikut menginisialisasi instance baru dari`Document` kelas dan membuat bentuk kotak teks:

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;
```

## Langkah 3: Putuskan tautan di TextBox

 Untuk memutus tautan maju di TextBox, kita dapat menggunakan`BreakForwardLink()` metode. Metode ini memutus tautan ke bentuk berikutnya dalam urutan. Kode berikut menunjukkan cara memutus tautan maju:

```csharp
textBox.BreakForwardLink();
```

## Langkah 4: Putuskan tautan maju dengan menetapkan nilai nol

 Alternatifnya, kita dapat memutus tautan maju dengan mengatur TextBox's`Next`properti ke`null`. Ini secara efektif menghilangkan koneksi ke bentuk berikutnya. Kode berikut menunjukkan pendekatan ini:

```csharp
textBox. Next = null;
```

## Langkah 5: Putuskan tautan yang mengarah ke TextBox

 Dalam beberapa kasus, kita perlu memutus tautan yang mengarah ke bentuk TextBox. Kita dapat mencapai hal ini dengan menelepon`BreakForwardLink()` metode pada`Previous` formulir, yang memutus tautan ke TextBox. Berikut ini contoh cara memutus tautan tersebut:

```csharp
textBox.Previous?.BreakForwardLink();
```

### Contoh kode sumber untuk memutus tautan dengan Aspose.Words untuk .NET

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;

// Putuskan tautan ke depan.
textBox.BreakForwardLink();

// Putuskan tautan maju dengan menetapkan nilai nol.
textBox. Next = null;

// Putuskan tautan yang mengarah ke kotak teks ini.
textBox.Previous?.BreakForwardLink();
```

## Kesimpulan

Selamat! Anda sekarang telah mempelajari cara memutus tautan pengalihan di dokumen Word menggunakan pustaka Aspose.Words untuk .NET. Dengan mengikuti langkah-langkah dalam panduan ini, Anda dapat menyiapkan dokumen, membuat bentuk TextBox, dan memutus tautan pengalihan menggunakan metode yang berbeda.

### FAQ untuk tautan maju dalam dokumen Word

#### T: Pustaka apa yang digunakan untuk memutus tautan pengalihan dalam dokumen Word menggunakan Aspose.Words untuk .NET?

A: Untuk memutus link pengalihan pada dokumen Word menggunakan Aspose.Words for .NET, pustaka yang digunakan adalah Aspose.Words for .NET.

#### T: Bagaimana cara memutus tautan pengalihan di Kotak Teks?

 A: Untuk memutus tautan maju di TextBox, Anda dapat menggunakan`BreakForwardLink()` metode. Metode ini memutus tautan ke bentuk berikutnya dalam urutan.

#### T: Bagaimana cara memutus tautan pengalihan dengan menetapkan nilai nol?

J: Alternatifnya, Anda dapat memutus tautan pengalihan dengan menyetel`Next` milik TextBox ke`null`. Ini secara efektif menghilangkan koneksi ke bentuk berikutnya.

#### Q: Bagaimana cara memutus link yang mengarah ke TextBox?

 J: Dalam beberapa kasus, Anda perlu memutus tautan yang mengarah ke Kotak Teks. Anda dapat mencapai hal ini dengan menelepon`BreakForwardLink()` metode pada`Previous` formulir, yang memutus tautan ke TextBox.

#### T: Bisakah kita memutus tautan pengalihan pada elemen selain Kotak Teks?

J: Ya, dengan Aspose.Words untuk .NET dimungkinkan untuk memutus tautan pengalihan pada elemen berbeda seperti paragraf, tabel, gambar, dll. Prosesnya mungkin bervariasi tergantung pada item spesifik yang ingin Anda putuskan tautannya.