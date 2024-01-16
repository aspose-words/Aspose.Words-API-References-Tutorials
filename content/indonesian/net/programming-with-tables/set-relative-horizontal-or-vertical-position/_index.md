---
title: Atur Posisi Relatif Horisontal Atau Vertikal
linktitle: Atur Posisi Relatif Horisontal Atau Vertikal
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengatur posisi relatif horizontal atau vertikal tabel dalam dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-tables/set-relative-horizontal-or-vertical-position/
---

Dalam tutorial ini, kita akan mempelajari cara mengatur posisi relatif horizontal atau vertikal tabel dalam dokumen Word menggunakan Aspose.Words untuk .NET. Kami akan mengikuti panduan langkah demi langkah untuk memahami kode dan menerapkan fitur ini. Di akhir tutorial ini, Anda akan dapat mengatur posisi relatif horizontal atau vertikal tabel Anda di dokumen Word Anda.

## Langkah 1: Pengaturan Proyek
1. Luncurkan Visual Studio dan buat proyek C# baru.
2. Tambahkan referensi ke perpustakaan Aspose.Words untuk .NET.

## Langkah 2: Memuat dokumen
Untuk memulai Pemrosesan Kata dengan dokumen, ikuti langkah-langkah berikut:

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Muat dokumen
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

Pastikan untuk mengganti "DIREKTORI DOKUMEN ANDA" dengan jalur sebenarnya ke direktori dokumen Anda dan berikan nama file yang benar.

## Langkah 3: Mengatur posisi relatif tabel
Selanjutnya, kita akan mengatur posisi relatif horizontal atau vertikal tabel. Gunakan kode berikut:

```csharp
// Ambil mejanya
Table table = doc.FirstSection.Body.Tables[0];

//Definisi posisi horizontal relatif tabel
table.HorizontalAnchor = RelativeHorizontalPosition.Column;

// Tentukan posisi vertikal relatif tabel
table.VerticalAnchor = RelativeVerticalPosition.Page;
```

 Di sini kita menggunakan dokumen untuk mengambil tabel pertama dari isi bagian pertama. Selanjutnya, kita atur posisi horizontal relatif tabel dengan`HorizontalAnchor` properti menggunakan`RelativeHorizontalPosition.Column` nilai. Demikian pula, kita mengatur posisi vertikal relatif tabel dengan`VerticalAnchor` properti menggunakan`RelativeVerticalPosition.Page` nilai.

## Langkah 4: Menyimpan dokumen yang dimodifikasi
Terakhir, kita perlu menyimpan dokumen yang dimodifikasi dengan posisi relatif tabel yang ditentukan. Gunakan kode berikut:

```csharp
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

Pastikan untuk menentukan jalur dan nama file yang benar untuk dokumen keluaran.

### Contoh kode sumber untuk Mengatur Posisi Relatif Horisontal Atau Vertikal menggunakan Aspose.Words untuk .NET 

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table wrapped by text.docx");
Table table = doc.FirstSection.Body.Tables[0];
table.HorizontalAnchor = RelativeHorizontalPosition.Column;
table.VerticalAnchor = RelativeVerticalPosition.Page;
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara mengatur posisi relatif horizontal atau vertikal tabel dalam dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah ini dan menerapkan kode C# yang disediakan, Anda bisa menerapkan posisi relatif ini ke tabel Anda di dokumen Word Anda.