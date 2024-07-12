---
title: Wilayah yang Dapat Diedit Tidak Terbatas di Dokumen Word
linktitle: Wilayah yang Dapat Diedit Tidak Terbatas di Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara membuat wilayah yang dapat diedit tanpa batas dalam dokumen Word menggunakan Aspose.Words untuk .NET dengan panduan langkah demi langkah yang komprehensif ini.
type: docs
weight: 10
url: /id/net/document-protection/unrestricted-editable-regions/
---
## Perkenalan

Jika Anda pernah ingin melindungi dokumen Word namun tetap mengizinkan bagian tertentu dapat diedit, Anda berada di tempat yang tepat! Panduan ini akan memandu Anda melalui proses pengaturan wilayah yang dapat diedit tanpa batas dalam dokumen Word menggunakan Aspose.Words untuk .NET. Kami akan membahas semuanya mulai dari prasyarat hingga langkah-langkah mendetail, memastikan Anda mendapatkan pengalaman yang lancar. Siap? Ayo selami!

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki yang berikut ini:

1.  Aspose.Words untuk .NET: Jika Anda belum melakukannya, unduhlah[Di Sini](https://releases.aspose.com/words/net/).
2.  Lisensi Aspose yang valid: Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).
3. Visual Studio: Versi terbaru apa pun akan berfungsi dengan baik.
4. Pengetahuan dasar tentang C# dan .NET: Ini akan membantu Anda mengikuti kodenya.

Sekarang Anda sudah siap, mari beralih ke bagian yang menyenangkan!

## Impor Namespace

Untuk mulai menggunakan Aspose.Words untuk .NET, Anda harus mengimpor namespace yang diperlukan. Inilah cara Anda melakukannya:

```csharp
using Aspose.Words;
using Aspose.Words.Editing;
```

## Langkah 1: Menyiapkan Proyek Anda

Hal pertama yang pertama, mari buat proyek C# baru di Visual Studio.

1. Buka Visual Studio: Mulailah dengan membuka Visual Studio dan membuat proyek Aplikasi Konsol baru.
2. Instal Aspose.Words: Gunakan Manajer Paket NuGet untuk menginstal Aspose.Words. Anda dapat melakukannya dengan menjalankan perintah berikut di Konsol Manajer Paket:
   ```sh
   Install-Package Aspose.Words
   ```

## Langkah 2: Memuat Dokumen

Sekarang, mari muat dokumen yang ingin Anda lindungi. Pastikan Anda telah menyiapkan dokumen Word di direktori Anda.

1. Atur Direktori Dokumen: Tentukan jalur ke direktori dokumen Anda.
   ```csharp
   string dataDir = "YOUR DOCUMENT DIRECTORY";
   ```
2.  Memuat Dokumen: Gunakan`Document` kelas untuk memuat dokumen Word Anda.
   ```csharp
   Document doc = new Document(dataDir + "Document.docx");
   ```

## Langkah 3: Melindungi Dokumen

Selanjutnya, kita akan mengatur dokumen menjadi read-only. Ini akan memastikan bahwa tidak ada perubahan yang dapat dilakukan tanpa kata sandi.

1.  Inisialisasi DocumentBuilder: Buat sebuah instance dari`DocumentBuilder` untuk membuat perubahan pada dokumen.
   ```csharp
   DocumentBuilder builder = new DocumentBuilder(doc);
   ```
2. Tetapkan Tingkat Perlindungan: Lindungi dokumen menggunakan kata sandi.
   ```csharp
   doc.Protect(ProtectionType.ReadOnly, "MyPassword");
   ```
3. Tambahkan Teks Hanya-Baca: Menyisipkan teks yang akan menjadi hanya-baca.
   ```csharp
   builder.Writeln("Hello world! Since we have set the document's protection level to read-only, we cannot edit this paragraph without the password.");
   ```

## Langkah 4: Membuat Rentang yang Dapat Diedit

Di sinilah keajaiban terjadi. Kami akan membuat bagian dalam dokumen yang dapat diedit meskipun ada perlindungan read-only secara keseluruhan.

1. Mulai Rentang yang Dapat Diedit: Tentukan awal rentang yang dapat diedit.
   ```csharp
   EditableRangeStart edRangeStart = builder.StartEditableRange();
   ```
2.  Buat Objek Rentang yang Dapat Diedit: An`EditableRange` objek akan dibuat secara otomatis.
   ```csharp
   EditableRange editableRange = edRangeStart.EditableRange;
   ```
3. Sisipkan Teks yang Dapat Diedit: Tambahkan teks di dalam rentang yang dapat diedit.
   ```csharp
   builder.Writeln("Paragraph inside first editable range");
   ```

## Langkah 5: Menutup Rentang yang Dapat Diedit

Rentang yang dapat diedit tidak lengkap tanpa akhir. Mari kita tambahkan itu selanjutnya.

1. Akhir Rentang yang Dapat Diedit: Tentukan akhir rentang yang dapat diedit.
   ```csharp
   EditableRangeEnd edRangeEnd = builder.EndEditableRange();
   ```
2. Tambahkan Teks Hanya-Baca di Luar Rentang: Sisipkan teks di luar rentang yang dapat diedit untuk menunjukkan perlindungan.
   ```csharp
   builder.Writeln("This paragraph is outside any editable ranges, and cannot be edited.");
   ```

## Langkah 6: Menyimpan Dokumen

Terakhir, mari simpan dokumen dengan perlindungan yang diterapkan dan wilayah yang dapat diedit.

1.  Simpan Dokumen: Gunakan`Save` metode untuk menyimpan dokumen Anda yang dimodifikasi.
   ```csharp
   doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");
   ```

## Kesimpulan

Dan itu dia! Anda telah berhasil membuat wilayah yang dapat diedit tanpa batas dalam dokumen Word menggunakan Aspose.Words untuk .NET. Fitur ini sangat berguna untuk lingkungan kolaboratif di mana bagian tertentu dari dokumen tidak boleh diubah sementara bagian lain dapat diedit. 

 Bereksperimenlah dengan skenario yang lebih kompleks dan tingkat perlindungan yang berbeda untuk mendapatkan hasil maksimal dari Aspose.Words. Jika Anda memiliki pertanyaan atau mengalami masalah, jangan ragu untuk memeriksanya[dokumentasi](https://reference.aspose.com/words/net/) atau menjangkau[mendukung](https://forum.aspose.com/c/words/8).

## FAQ

### Bisakah saya memiliki beberapa wilayah yang dapat diedit dalam satu dokumen?
Ya, Anda dapat membuat beberapa wilayah yang dapat diedit dengan memulai dan mengakhiri rentang yang dapat diedit di berbagai bagian dokumen.

### Jenis perlindungan apa lagi yang tersedia di Aspose.Words?
Aspose.Words mendukung berbagai jenis perlindungan seperti AllowOnlyComments, AllowOnlyFormFields, dan NoProtection.

### Apakah mungkin untuk menghapus perlindungan dari suatu dokumen?
 Ya, Anda dapat menghapus perlindungan menggunakan`Unprotect` metode dan memberikan kata sandi yang benar.

### Bisakah saya menentukan kata sandi berbeda untuk bagian berbeda?
Tidak, perlindungan tingkat dokumen menerapkan satu kata sandi untuk seluruh dokumen.

### Bagaimana cara saya mengajukan lisensi untuk Aspose.Words?
Anda dapat menerapkan lisensi dengan memuatnya dari file atau aliran. Periksa dokumentasi untuk langkah-langkah detailnya.
