---
title: Akses Dan Verifikasi Tanda Tangan Di Dokumen Word
linktitle: Akses Dan Verifikasi Tanda Tangan Di Dokumen Word
second_title: API Pemrosesan Dokumen Aspose.Words
description: Akses dan verifikasi tanda tangan digital di dokumen Word menggunakan Aspose.Words for .NET dengan panduan langkah demi langkah yang komprehensif ini. Pastikan keaslian dokumen dengan mudah.
type: docs
weight: 10
url: /id/net/programming-with-digital-signatures/access-and-verify-signature/
---
## Perkenalan

Hai, rekan-rekan penggemar teknologi! Pernahkah Anda berada dalam situasi di mana Anda perlu mengakses dan memverifikasi tanda tangan digital di dokumen Word tetapi tidak tahu harus mulai dari mana? Nah, Anda beruntung! Hari ini, kita menyelami dunia Aspose.Words for .NET yang menakjubkan, perpustakaan canggih yang memudahkan penanganan dokumen Word. Kami akan memandu Anda melalui proses ini selangkah demi selangkah, sehingga di akhir panduan ini, Anda akan ahli dalam memverifikasi tanda tangan digital di dokumen Word. Mari kita mulai!

## Prasyarat

Sebelum kita mendalami seluk beluknya, ada beberapa hal yang perlu Anda siapkan:

1. Visual Studio: Pastikan Anda telah menginstal Visual Studio di mesin Anda. Di sinilah Anda akan menulis dan menjalankan kode Anda.
2.  Aspose.Words untuk .NET: Anda harus menginstal Aspose.Words untuk .NET. Anda dapat mengunduhnya[Di Sini](https://releases.aspose.com/words/net/) . Jangan lupa untuk mendapatkan uji coba gratis Anda[Di Sini](https://releases.aspose.com/) jika Anda belum melakukannya!
3. Dokumen Word yang Ditandatangani Secara Digital: Miliki dokumen Word yang sudah ditandatangani secara digital. Ini adalah file yang akan Anda gunakan untuk memverifikasi tanda tangan.

## Impor Namespace

Hal pertama yang pertama, mari impor namespace yang diperlukan. Namespace ini memungkinkan Anda menggunakan fitur Aspose.Words di proyek Anda.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.DigitalSignatures;
```

Baiklah, mari kita bagi menjadi langkah-langkah yang dapat dikelola. Setiap langkah akan memandu Anda melalui bagian proses tertentu. Siap? Ayo pergi!

## Langkah 1: Siapkan Proyek Anda

Sebelum Anda dapat memverifikasi tanda tangan digital, Anda perlu menyiapkan proyek Anda di Visual Studio. Begini caranya:

### Buat Proyek Baru

1. Buka Visual Studio.
2. Klik Buat proyek baru.
3. Pilih Aplikasi Konsol (.NET Core) atau Aplikasi Konsol (.NET Framework), bergantung pada preferensi Anda.
4. Klik Berikutnya, beri nama proyek Anda, dan klik Buat.

### Instal Aspose.Words untuk .NET

1. Di Solution Explorer, klik kanan pada nama proyek Anda dan pilih Kelola Paket NuGet.
2. Di Manajer Paket NuGet, cari Aspose.Words.
3. Klik Instal untuk menambahkannya ke proyek Anda.

## Langkah 2: Muat Dokumen Word yang Ditandatangani Secara Digital

Sekarang proyek Anda sudah siap, mari muat dokumen Word yang ditandatangani secara digital.

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Digitally signed.docx");
```

 Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke direktori dokumen Anda. Cuplikan kode ini menginisialisasi yang baru`Document` objek dan memuat dokumen Word yang Anda tandatangani.

## Langkah 3: Akses Tanda Tangan Digital

Dengan dokumen Anda dimuat, saatnya mengakses tanda tangan digital.

```csharp
foreach (DigitalSignature signature in doc.DigitalSignatures)
{
    Console.WriteLine("* Signature Found *");
    Console.WriteLine("Is valid: " + signature.IsValid);
    Console.WriteLine("Reason for signing: " + signature.Comments); 
    Console.WriteLine("Time of signing: " + signature.SignTime);
    Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
    Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
    Console.WriteLine();
}
```

Kode ini menelusuri setiap tanda tangan digital dalam dokumen dan mencetak berbagai detail tentang tanda tangan tersebut. Mari kita uraikan fungsi masing-masing bagian:

1. Tanda Tangan Ditemukan: Menunjukkan bahwa tanda tangan telah ditemukan.
2. Valid: Memeriksa apakah tanda tangan valid.
3. Alasan penandatanganan: Menampilkan alasan penandatanganan, jika tersedia.
4. Waktu penandatanganan: Menampilkan stempel waktu saat dokumen ditandatangani.
5. Nama subjek: Mengambil nama subjek dari sertifikat.
6. Nama penerbit: Mengambil nama penerbit dari sertifikat.

## Langkah 4: Jalankan Kode Anda

Setelah semuanya siap, saatnya menjalankan kode Anda dan melihat hasilnya.


1. Tekan F5 atau klik tombol Start di Visual Studio untuk menjalankan program Anda.
2. Jika dokumen Anda ditandatangani secara digital, Anda akan melihat detail tanda tangan tercetak di konsol.

## Langkah 5: Tangani Potensi Kesalahan

Itu selalu merupakan ide bagus untuk menangani potensi kesalahan yang mungkin terjadi. Mari tambahkan beberapa penanganan kesalahan dasar pada kode kita.

```csharp
try
{
    // Jalur ke direktori dokumen.
    string dataDir = "YOUR DOCUMENT DIRECTORY";
    Document doc = new Document(dataDir + "Digitally signed.docx");

    foreach (DigitalSignature signature in doc.DigitalSignatures)
    {
        Console.WriteLine("* Signature Found *");
        Console.WriteLine("Is valid: " + signature.IsValid);
        Console.WriteLine("Reason for signing: " + signature.Comments); 
        Console.WriteLine("Time of signing: " + signature.SignTime);
        Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
        Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
        Console.WriteLine();
    }
}
catch (Exception ex)
{
    Console.WriteLine("An error occurred: " + ex.Message);
}
```

Ini akan menangkap setiap pengecualian yang mungkin terjadi dan mencetak pesan kesalahan.

## Kesimpulan

Dan itu dia! Anda telah berhasil mengakses dan memverifikasi tanda tangan digital di dokumen Word menggunakan Aspose.Words untuk .NET. Ini tidak sesulit kelihatannya, bukan? Dengan langkah-langkah ini, Anda dapat dengan percaya diri menangani tanda tangan digital di dokumen Word Anda, memastikan keaslian dan integritasnya. Selamat membuat kode!

## FAQ

### Bisakah saya menggunakan Aspose.Words untuk .NET untuk menambahkan tanda tangan digital ke dokumen Word?

Ya, Anda dapat menggunakan Aspose.Words untuk .NET untuk menambahkan tanda tangan digital ke dokumen Word. Perpustakaan menyediakan fitur lengkap untuk menambah dan memverifikasi tanda tangan digital.

### Jenis tanda tangan digital apa yang dapat diverifikasi Aspose.Words for .NET?

Aspose.Words untuk .NET dapat memverifikasi tanda tangan digital dalam file DOCX yang menggunakan sertifikat X.509.

### Apakah Aspose.Words for .NET kompatibel dengan semua versi Microsoft Word?

Aspose.Words untuk .NET mendukung semua versi dokumen Microsoft Word, termasuk DOC, DOCX, RTF, dan banyak lagi.

### Bagaimana cara mendapatkan lisensi sementara untuk Aspose.Words untuk .NET?

 Anda bisa mendapatkan lisensi sementara untuk Aspose.Words untuk .NET dari[Di Sini](https://purchase.aspose.com/temporary-license/). Ini memungkinkan Anda untuk mencoba fitur lengkap perpustakaan tanpa batasan apa pun.

### Di mana saya dapat menemukan dokumentasi lebih lanjut tentang Aspose.Words untuk .NET?

 Anda dapat menemukan dokumentasi terperinci untuk Aspose.Words untuk .NET[Di Sini](https://reference.aspose.com/words/net/).