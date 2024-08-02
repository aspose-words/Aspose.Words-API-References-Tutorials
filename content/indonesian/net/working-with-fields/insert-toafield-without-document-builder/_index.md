---
title: Sisipkan Bidang TOA Tanpa Pembuat Dokumen
linktitle: Sisipkan Bidang TOA Tanpa Pembuat Dokumen
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyisipkan bidang TOA tanpa menggunakan pembuat dokumen di Aspose.Words untuk .NET. Ikuti panduan langkah demi langkah kami untuk mengelola kutipan resmi secara efisien.
type: docs
weight: 10
url: /id/net/working-with-fields/insert-toafield-without-document-builder/
---
## Perkenalan

Membuat bidang Tabel Otoritas (TOA) di dokumen Word bisa terasa seperti menyusun teka-teki yang rumit. Namun, dengan bantuan Aspose.Words untuk .NET, prosesnya menjadi lancar dan mudah. Dalam artikel ini, kami akan memandu Anda melalui langkah-langkah untuk menyisipkan bidang TOA tanpa menggunakan pembuat dokumen, sehingga memudahkan Anda mengelola kutipan dan referensi hukum dalam dokumen Word Anda.

## Prasyarat

Sebelum masuk ke tutorial, mari kita bahas hal-hal penting yang Anda perlukan:

-  Aspose.Words untuk .NET: Pastikan Anda menginstal versi terbaru. Anda dapat mengunduhnya dari[Asumsikan situs web](https://releases.aspose.com/words/net/).
- Lingkungan Pengembangan: IDE yang kompatibel dengan .NET seperti Visual Studio.
- Pengetahuan Dasar C#: Memahami sintaksis dan konsep dasar C# akan sangat membantu.
- Contoh Dokumen Word: Buat atau siapkan contoh dokumen di mana Anda ingin menyisipkan bidang TOA.

## Impor Namespace

Untuk memulai, Anda harus mengimpor namespace yang diperlukan dari perpustakaan Aspose.Words. Pengaturan ini memastikan bahwa Anda memiliki akses ke semua kelas dan metode yang diperlukan untuk manipulasi dokumen.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

Mari kita bagi prosesnya menjadi langkah-langkah sederhana dan mudah diikuti. Kami akan memandu Anda melalui setiap tahap, menjelaskan fungsi setiap bagian kode dan bagaimana kontribusinya dalam pembuatan bidang TOA.

## Langkah 1: Inisialisasi Dokumen

 Pertama, Anda perlu membuat sebuah instance dari`Document` kelas. Objek ini mewakili dokumen Word yang sedang Anda kerjakan.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
```

Kode ini menginisialisasi dokumen Word baru. Anda dapat menganggapnya seperti membuat kanvas kosong tempat Anda akan menambahkan konten.

## Langkah 2: Buat dan Konfigurasikan Bidang TA

Selanjutnya, kita akan menambahkan kolom TA (Table of Authorities). Bidang ini menandai entri yang akan muncul di TOA.

```csharp
Paragraph para = new Paragraph(doc);

// Kami ingin memasukkan bidang TA dan TOA seperti ini:
// { TA \c 1 \l "Nilai 0" }
FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";

doc.FirstSection.Body.AppendChild(para);
```

Berikut rinciannya:
- Paragraph para = new Paragraph(doc);: Membuat paragraf baru di dalam dokumen.
-  FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false);: Menambahkan bidang TA ke paragraf. Itu`FieldType.FieldTOAEntry` menentukan bahwa ini adalah bidang entri TOA.
- fieldTA.EntryCategory = "1";: Mengatur kategori entri. Ini berguna untuk mengkategorikan berbagai jenis entri.
- fieldTA.LongCitation = "Nilai 0";: Menentukan teks kutipan yang panjang. Ini adalah teks yang akan muncul di TOA.
- doc.FirstSection.Body.AppendChild(para);: Menambahkan paragraf dengan bidang TA ke badan dokumen.

## Langkah 3: Tambahkan Bidang TOA

Sekarang, kita akan memasukkan bidang TOA sebenarnya yang mengkompilasi semua entri TA ke dalam tabel.

```csharp
para = new Paragraph(doc);

FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
doc.FirstSection.Body.AppendChild(para);
```

Pada langkah ini:
- FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);: Menambahkan bidang TOA ke paragraf.
- fieldToa.EntryCategory = "1";: Memfilter entri untuk hanya menyertakan entri yang ditandai dengan kategori "1".

## Langkah 4: Perbarui Bidang TOA

Setelah memasukkan kolom TOA, Anda perlu memperbaruinya untuk memastikan kolom tersebut mencerminkan entri terbaru.

```csharp
fieldToa.Update();
```

Perintah ini menyegarkan bidang TOA, memastikan bahwa semua entri yang ditandai ditampilkan dengan benar di tabel.

## Langkah 5: Simpan Dokumen

Terakhir, simpan dokumen Anda dengan kolom TOA yang baru ditambahkan.

```csharp
doc.Save(dataDir + "WorkingWithFields.InsertTOAFieldWithoutDocumentBuilder.docx");
```

 Baris kode ini menyimpan dokumen ke direktori yang ditentukan. Pastikan untuk mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya tempat Anda ingin menyimpan file Anda.

## Kesimpulan

Dan itu dia! Anda telah berhasil menambahkan bidang TOA ke dokumen Word tanpa menggunakan pembuat dokumen. Dengan mengikuti langkah-langkah ini, Anda dapat mengelola kutipan secara efisien dan membuat tabel otoritas yang komprehensif dalam dokumen hukum Anda. Aspose.Words untuk .NET menjadikan proses ini lancar dan efisien, memberi Anda alat untuk menangani tugas dokumen kompleks dengan mudah.

## FAQ

### Bisakah saya menambahkan beberapa kolom TA dengan kategori berbeda?
 Ya, Anda dapat menambahkan beberapa kolom TA dengan kategori berbeda dengan mengaturnya`EntryCategory`properti yang sesuai.

### Bagaimana cara menyesuaikan tampilan TOA?
Anda dapat menyesuaikan tampilan TOA dengan memodifikasi properti bidang TOA, seperti format entri dan label kategori.

### Apakah mungkin untuk memperbarui kolom TOA secara otomatis?
 Meskipun Anda dapat memperbarui bidang TOA secara manual menggunakan`Update` metode, Aspose.Words saat ini tidak mendukung pembaruan otomatis pada perubahan dokumen.

### Bisakah saya menambahkan bidang TA secara terprogram di bagian tertentu dokumen?
Ya, Anda dapat menambahkan kolom TA di lokasi tertentu dengan memasukkannya ke dalam paragraf atau bagian yang diinginkan.

### Bagaimana cara menangani beberapa bidang TOA dalam satu dokumen?
 Anda dapat mengelola beberapa bidang TOA dengan menetapkan bidang yang berbeda`EntryCategory` nilai-nilai dan memastikan setiap bidang TOA memfilter entri berdasarkan kategorinya.