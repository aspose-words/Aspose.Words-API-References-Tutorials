---
title: Status Kotak Centang Saat Ini
linktitle: Status Kotak Centang Saat Ini
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengelola kotak centang di dokumen Word dengan Aspose.Words untuk .NET. Panduan ini mencakup pengaturan, pembaruan, dan penyimpanan kotak centang secara terprogram.
type: docs
weight: 10
url: /id/net/programming-with-sdt/current-state-of-check-box/
---
## Perkenalan

Dalam tutorial ini, kita akan memandu proses bekerja dengan kotak centang di dokumen Word. Kami akan membahas cara mengakses kotak centang, menentukan statusnya, dan memperbaruinya. Baik Anda sedang mengembangkan formulir yang memerlukan opsi yang dapat diperiksa atau mengotomatiskan modifikasi dokumen, panduan ini akan memberi Anda dasar yang kuat.

## Prasyarat

Sebelum kita masuk ke tutorialnya, pastikan Anda memiliki prasyarat berikut:

1.  Aspose.Words untuk .NET Library: Pastikan Anda telah menginstal perpustakaan Aspose.Words. Jika Anda belum melakukannya, Anda dapat mengunduhnya dari[Asumsikan situs web](https://releases.aspose.com/words/net/).

2. Visual Studio: Lingkungan pengembangan .NET seperti Visual Studio akan diperlukan untuk mengkompilasi dan menjalankan kode Anda.

3. Pengetahuan Dasar C#: Keakraban dengan pemrograman C# akan membantu Anda memahami dan mengikuti contoh yang diberikan.

4. Dokumen Word dengan Kotak Centang: Untuk tutorial ini, Anda memerlukan dokumen Word yang berisi kolom formulir kotak centang. Kami akan menggunakan dokumen ini untuk mendemonstrasikan cara memanipulasi kotak centang secara terprogram.

## Impor Namespace

Untuk memulai Aspose.Words untuk .NET, Anda perlu mengimpor namespace yang diperlukan. Di awal file C# Anda, sertakan arahan penggunaan berikut:

```csharp
using Aspose.Words;
using Aspose.Words.Markup;
```

Namespace ini akan memungkinkan Anda mengakses dan bekerja dengan Aspose.Words API dan menangani tag dokumen terstruktur, termasuk kotak centang.

## Langkah 1: Menyiapkan Jalur Dokumen

 Pertama, Anda perlu menentukan jalur ke dokumen Word Anda. Di sinilah Aspose.Words akan mencari file untuk melakukan operasi. Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya tempat dokumen Anda disimpan.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Memuat Dokumen

 Selanjutnya, muat dokumen Word ke dalam instance`Document` kelas. Kelas ini mewakili dokumen Word Anda dalam kode dan menyediakan berbagai metode untuk memanipulasinya.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
```

 Di Sini,`"Structured document tags.docx"` harus diganti dengan nama file Word Anda.

## Langkah 3: Mengakses Bidang Formulir Kotak Centang

Untuk mengakses kotak centang tertentu, Anda perlu mengambilnya dari dokumen. Aspose.Words memperlakukan kotak centang sebagai tag dokumen terstruktur. Kode berikut mengambil tag dokumen terstruktur pertama dalam dokumen dan memeriksa apakah itu adalah kotak centang.

```csharp
//Dapatkan kontrol konten pertama dari dokumen.
StructuredDocumentTag sdtCheckBox =
    (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Langkah 4: Memeriksa dan Memperbarui Status Kotak Centang

 Setelah Anda memilikinya`StructuredDocumentTag` Misalnya, Anda dapat memeriksa jenisnya dan memperbarui statusnya. Contoh ini menyetel kotak centang menjadi dicentang jika memang itu adalah kotak centang.

```csharp
if (sdtCheckBox.SdtType == SdtType.Checkbox)
    sdtCheckBox.Checked = true;
```

## Langkah 5: Menyimpan Dokumen

Terakhir, simpan dokumen yang dimodifikasi ke file baru. Ini memungkinkan Anda menyimpan dokumen asli dan bekerja dengan versi yang diperbarui.

```csharp
doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

 Dalam contoh ini,`"WorkingWithSdt.CurrentStateOfCheckBox.docx"` adalah nama file tempat dokumen yang dimodifikasi akan disimpan.

## Kesimpulan

Dalam tutorial ini, kami telah membahas cara memanipulasi bidang formulir kotak centang di dokumen Word menggunakan Aspose.Words untuk .NET. Kami mempelajari cara menyiapkan jalur dokumen, memuat dokumen, mengakses kotak centang, memperbarui statusnya, dan menyimpan perubahan. Dengan keterampilan ini, kini Anda dapat membuat dokumen Word yang lebih interaktif dan dinamis secara terprogram.

## FAQ

### Jenis elemen dokumen apa yang dapat saya manipulasi dengan Aspose.Words untuk .NET?
Aspose.Words untuk .NET memungkinkan Anda memanipulasi berbagai elemen dokumen termasuk paragraf, tabel, gambar, header, footer, dan tag dokumen terstruktur seperti kotak centang.

### Bagaimana saya bisa menangani banyak kotak centang dalam satu dokumen?
Untuk menangani beberapa kotak centang, Anda perlu menelusuri kumpulan tag dokumen terstruktur dan memeriksa masing-masing kotak untuk menentukan apakah itu kotak centang.

### Bisakah saya menggunakan Aspose.Words untuk .NET untuk membuat kotak centang baru di dokumen Word?
 Ya, Anda dapat membuat kotak centang baru dengan menambahkan tipe tag dokumen terstruktur`SdtType.Checkbox` ke dokumen Anda.

### Apakah mungkin membaca status kotak centang dari suatu dokumen?
 Sangat. Anda dapat membaca status kotak centang dengan mengakses`Checked` properti dari`StructuredDocumentTag` jika itu bertipe`SdtType.Checkbox`.

### Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Words untuk .NET?
 Anda dapat memperoleh lisensi sementara dari[Asumsikan halaman pembelian](https://purchase.aspose.com/temporary-license/), yang memungkinkan Anda mengevaluasi fungsionalitas penuh perpustakaan.