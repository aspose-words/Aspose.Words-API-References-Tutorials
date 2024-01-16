---
title: Bandingkan Opsi Dalam Dokumen Word
linktitle: Bandingkan Opsi Dalam Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk menjelaskan kode sumber C# dari Opsi Bandingkan di fitur dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/compare-documents/compare-options/
---
Dalam tutorial ini, kami akan menjelaskan cara menggunakan fitur Bandingkan Opsi di dokumen Word dengan Aspose.Words untuk .NET. Ikuti langkah-langkah di bawah ini untuk memahami kode sumber dan menerapkan perubahan.

## Langkah 1: Bandingkan dokumen dengan opsi khusus

 Untuk memulai, muat dua dokumen untuk dibandingkan. Dalam contoh ini, kita akan menggunakan`Clone()` metode untuk membuat salinan dokumen asli. Begini caranya:

```csharp
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();
```

## Langkah 2: Mengonfigurasi opsi perbandingan

 Kami sekarang akan mengkonfigurasi opsi perbandingan dengan membuat a`CompareOptions` objek dan mengatur berbagai properti sesuai kebutuhan. Begini caranya:

```csharp
CompareOptions options = new CompareOptions
{
IgnoreFormatting = true,
IgnoreHeadersAndFooters = true,
IgnoreCaseChanges = true,
IgnoreTables = true,
IgnoreFields = true,
IgnoreComments = true,
IgnoreTextboxes=true,
IgnoreFootnotes=true
};
```

## Langkah 3: Bandingkan dokumen dengan opsi khusus

 Kami sekarang akan menggunakan`Compare()` metode meneruskan opsi khusus untuk membandingkan kedua dokumen. Cara ini akan menandai perubahan pada dokumen asli. Begini caranya:

```csharp
// Bandingkan dokumen dengan opsi khusus
docA.Compare(docB, "user", DateTime.Now, options);

// Periksa apakah dokumennya sama
Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal": "Documents are not equal");
```

### Contoh kode sumber untuk Bandingkan Opsi menggunakan Aspose.Words untuk .NET

Berikut source code lengkap fitur Compare Options dengan Aspose.Words for .NET:

```csharp

	Document docA = new Document(MyDir + "Document.docx");
	Document docB = docA.Clone();

	CompareOptions options = new CompareOptions
	{
		IgnoreFormatting = true,
		IgnoreHeadersAndFooters = true,
		IgnoreCaseChanges = true,
		IgnoreTables = true,
		IgnoreFields = true,
		IgnoreComments = true,
		IgnoreTextboxes = true,
		IgnoreFootnotes = true
	};

	docA.Compare(docB, "user", DateTime.Now, options);

	Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal" : "Documents are not equal");

```

Dengan kode ini Anda dapat membandingkan dua dokumen menggunakan opsi khusus untuk mengabaikan elemen tertentu saat membandingkan dengan Aspose.Words untuk .NET.

## Kesimpulan

Dalam tutorial ini, kita mempelajari cara menggunakan Opsi Bandingkan di Aspose.Words untuk .NET untuk menyesuaikan proses perbandingan saat membandingkan dua dokumen. Dengan menentukan opsi berbeda, Anda dapat mengabaikan elemen tertentu dan membuat proses perbandingan lebih fleksibel. Fitur ini memungkinkan Anda memiliki kontrol lebih besar terhadap proses perbandingan, menyesuaikannya dengan kebutuhan spesifik Anda. Aspose.Words untuk .NET memberikan kemampuan perbandingan dokumen yang kuat, sehingga memudahkan untuk mengidentifikasi perbedaan antara dokumen sambil mengabaikan elemen tertentu sesuai kebutuhan.

### FAQ

#### T: Apa tujuan menggunakan Opsi Bandingkan di Aspose.Words untuk .NET?

J: Opsi Bandingkan di Aspose.Words untuk .NET memungkinkan Anda menyesuaikan proses perbandingan saat membandingkan dua dokumen. Dengan opsi ini, Anda bisa menentukan elemen mana yang akan diabaikan selama perbandingan, seperti perubahan format, header dan footer, tabel, bidang, komentar, kotak teks, dan catatan kaki.

#### T: Bagaimana cara menggunakan Opsi Bandingkan di Aspose.Words untuk .NET?

J: Untuk menggunakan Opsi Bandingkan di Aspose.Words untuk .NET, ikuti langkah-langkah berikut:
1. Muat dua dokumen yang ingin Anda bandingkan ke dalam objek Dokumen terpisah.
2.  Menggunakan`Clone()` metode untuk membuat salinan dokumen asli.
3.  Membuat`CompareOptions` objek dan atur propertinya untuk menyesuaikan proses perbandingan. Anda dapat menentukan elemen mana yang diabaikan selama perbandingan.
4.  Menggunakan`Compare()` metode pada salah satu dokumen dan meneruskan dokumen lainnya dan`CompareOptions` objek sebagai parameter. Cara ini akan membandingkan dokumen berdasarkan opsi yang ditentukan dan menandai perubahan pada dokumen asli.
5.  Periksalah`Revisions` milik dokumen asli. Jika hitungannya nol, berarti dokumennya identik, dengan mempertimbangkan opsi yang ditentukan.

#### T: Apa saja opsi umum yang tersedia di CompareOptions?

J: Opsi umum yang tersedia di CompareOptions meliputi:
- `IgnoreFormatting`: Mengabaikan perubahan format.
- `IgnoreHeadersAndFooters`: Mengabaikan perubahan pada header dan footer.
- `IgnoreCaseChanges`: Mengabaikan perubahan huruf besar/kecil.
- `IgnoreTables`: Mengabaikan perubahan dalam tabel.
- `IgnoreFields`: Mengabaikan perubahan pada kolom.
- `IgnoreComments`: Mengabaikan perubahan dalam komentar.
- `IgnoreTextboxes`Mengabaikan perubahan di kotak teks.
- `IgnoreFootnotes`: Mengabaikan perubahan pada catatan kaki.

#### T: Dapatkah saya menggunakan opsi khusus untuk elemen tertentu selama perbandingan dokumen?

 J: Ya, Anda dapat menggunakan opsi khusus untuk elemen tertentu selama perbandingan dokumen. Dengan mengatur properti dari`CompareOptions` objek yang sesuai, Anda dapat memilih elemen mana yang diabaikan dan mana yang dipertimbangkan selama perbandingan.