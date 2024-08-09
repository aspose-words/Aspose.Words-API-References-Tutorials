---
title: Konversi Antar Satuan Pengukuran
linktitle: Konversi Antar Satuan Pengukuran
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengonversi satuan pengukuran di Aspose.Words untuk .NET. Ikuti panduan langkah demi langkah kami untuk mengatur margin, header, dan footer dokumen dalam inci dan titik.
type: docs
weight: 10
url: /id/net/programming-with-document-properties/convert-between-measurement-units/
---
## Perkenalan

Hai! Apakah Anda seorang pengembang yang bekerja dengan dokumen Word menggunakan Aspose.Words untuk .NET? Jika demikian, Anda mungkin sering merasa perlu mengatur margin, header, atau footer dalam satuan pengukuran yang berbeda. Mengonversi satuan seperti inci dan titik bisa jadi rumit jika Anda tidak terbiasa dengan fungsi perpustakaan. Dalam tutorial komprehensif ini, kami akan memandu Anda melalui proses konversi antar unit pengukuran menggunakan Aspose.Words untuk .NET. Mari selami dan sederhanakan konversi tersebut!

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki hal berikut:

1.  Aspose.Words untuk .NET Library: Jika Anda belum melakukannya, unduhlah[Di Sini](https://releases.aspose.com/words/net/).
2. Lingkungan Pengembangan: Visual Studio atau IDE lain yang kompatibel dengan .NET.
3. Pengetahuan Dasar C#: Memahami dasar-dasar C# akan membantu Anda mengikutinya dengan mudah.
4.  Lisensi Aspose: Opsional tetapi direkomendasikan untuk fungsionalitas penuh. Anda bisa mendapatkan lisensi sementara[Di Sini](https://purchase.aspose.com/temporary-license/).

## Impor Namespace

Pertama, Anda perlu mengimpor namespace yang diperlukan. Ini penting untuk mengakses kelas dan metode yang disediakan oleh Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Layout;
```

Mari kita uraikan proses konversi satuan pengukuran di Aspose.Words untuk .NET. Ikuti langkah-langkah mendetail berikut untuk menyiapkan dan menyesuaikan margin dan jarak dokumen Anda.

## Langkah 1: Buat Dokumen Baru

Pertama, Anda perlu membuat dokumen baru menggunakan Aspose.Words.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Ini menginisialisasi dokumen Word baru dan a`DocumentBuilder` untuk memfasilitasi pembuatan dan pemformatan konten.

## Langkah 2: Akses Pengaturan Halaman

 Untuk mengatur margin, header, dan footer, Anda perlu mengakses`PageSetup` obyek.

```csharp
PageSetup pageSetup = builder.PageSetup;
```

Ini memberi Anda akses ke berbagai properti pengaturan halaman seperti margin, jarak header, dan jarak footer.

## Langkah 3: Ubah Inci menjadi Poin

 Aspose.Words menggunakan titik sebagai satuan pengukuran secara default. Untuk mengatur margin dalam inci, Anda perlu mengonversi inci menjadi poin menggunakan`ConvertUtil.InchToPoint` metode.

```csharp
pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
```

Berikut rincian fungsi setiap baris:
- Atur margin atas dan bawah menjadi 1 inci (dikonversi menjadi poin).
- Mengatur margin kiri dan kanan menjadi 1,5 inci (dikonversi menjadi poin).
- Mengatur jarak header dan footer menjadi 0,2 inci (dikonversi menjadi poin).

## Langkah 4: Simpan Dokumen

Terakhir, simpan dokumen Anda untuk memastikan semua perubahan diterapkan.

```csharp
doc.Save("ConvertedDocument.docx");
```

Ini menyimpan dokumen Anda dengan margin dan jarak yang ditentukan dalam poin.

## Kesimpulan

Dan itu dia! Anda telah berhasil mengonversi dan mengatur margin dan jarak dalam dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah menangani berbagai konversi unit, sehingga memudahkan proses penyesuaian dokumen Anda. Teruslah bereksperimen dengan pengaturan yang berbeda dan jelajahi berbagai fungsi yang ditawarkan Aspose.Words. Selamat membuat kode!

## FAQ

### Bisakah saya mengonversi satuan lain seperti sentimeter menjadi titik menggunakan Aspose.Words?
 Ya, Aspose.Words menyediakan metode seperti`ConvertUtil.CmToPoint` untuk mengubah sentimeter menjadi titik.

### Apakah lisensi diperlukan untuk menggunakan Aspose.Words untuk .NET?
Meskipun Anda dapat menggunakan Aspose.Words tanpa lisensi, beberapa fitur lanjutan mungkin dibatasi. Memperoleh lisensi memastikan fungsionalitas penuh.

### Bagaimana cara menginstal Aspose.Words untuk .NET?
 Anda dapat mengunduhnya dari[situs web](https://releases.aspose.com/words/net/) dan ikuti petunjuk instalasi.

### Bisakah saya menetapkan unit yang berbeda untuk bagian dokumen yang berbeda?
 Ya, Anda dapat menyesuaikan margin dan pengaturan lainnya untuk bagian yang berbeda menggunakan`Section` kelas.

### Fitur lain apa yang ditawarkan Aspose.Words?
 Aspose.Words mendukung berbagai fitur termasuk konversi dokumen, penggabungan surat, dan opsi pemformatan ekstensif. Periksa[dokumentasi](https://reference.aspose.com/words/net/) untuk lebih jelasnya.