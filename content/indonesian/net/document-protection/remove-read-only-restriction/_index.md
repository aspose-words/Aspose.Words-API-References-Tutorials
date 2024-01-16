---
title: Hapus Pembatasan Hanya Baca
linktitle: Hapus Pembatasan Hanya Baca
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menghapus pembatasan baca-saja dari dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/document-protection/remove-read-only-restriction/
---
Dalam tutorial ini, kami akan memandu Anda melalui langkah-langkah untuk menggunakan fitur penghapusan pembatasan hanya-baca Aspose.Words untuk .NET. Fitur ini memungkinkan Anda untuk menghapus batasan read-only dari dokumen Word agar dapat diedit. Ikuti langkah-langkah di bawah ini:

## Langkah 1: Membuat Dokumen dan Mengatur Perlindungan

Mulailah dengan membuat instance kelas Dokumen:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
doc.WriteProtection.SetPassword("MyPassword");
```

Tetapkan kata sandi untuk dokumen menggunakan properti SetPassword() dari objek WriteProtection:

Pastikan untuk mengganti "Kata Sandi Saya" dengan kata sandi sebenarnya yang Anda gunakan untuk melindungi dokumen.

## Langkah 2: Hapus batasan hanya-baca

Untuk menghapus pembatasan baca-saja, setel properti ReadOnlyRecommended ke false:

```csharp
doc.WriteProtection.ReadOnlyRecommended = false;
```

## Langkah 3: Terapkan Perlindungan Tidak Terbatas

Terakhir, terapkan perlindungan tak terbatas menggunakan metode Protect() pada objek Dokumen:

```csharp
doc.Protect(ProtectionType.NoProtection);
doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");
```

Pastikan untuk menentukan jalur dan nama file yang benar untuk menyimpan dokumen tanpa batasan hanya-baca.

### Contoh kode sumber untuk Menghapus Pembatasan Hanya Baca menggunakan Aspose.Words untuk .NET

Berikut kode sumber lengkap untuk menghilangkan batasan read-only menggunakan Aspose.Words untuk .NET:

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

// Masukkan kata sandi yang panjangnya maksimal 15 karakter.
doc.WriteProtection.SetPassword("MyPassword");

//Hapus opsi baca-saja.
doc.WriteProtection.ReadOnlyRecommended = false;

// Terapkan perlindungan tulis tanpa perlindungan apa pun.
doc.Protect(ProtectionType.NoProtection);
doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");
```

Dengan mengikuti langkah-langkah ini, Anda dapat dengan mudah menghapus pembatasan baca-saja dari dokumen Word dengan Aspose.Words untuk .NET.


## Kesimpulan

Dalam tutorial ini, kita mempelajari cara menghapus pembatasan read-only dari dokumen Word menggunakan Aspose.Words untuk .NET. Dengan mengikuti langkah-langkah yang disediakan, Anda dapat dengan mudah menghapus batasan dan membuat dokumen dapat diedit kembali. Aspose.Words untuk .NET menawarkan serangkaian fitur komprehensif untuk mengelola perlindungan dan pembatasan dokumen, memberi Anda fleksibilitas dan kontrol atas keamanan dan kemampuan pengeditan dokumen Word Anda.

### FAQ

#### T: Apa yang dimaksud dengan pembatasan baca-saja di Aspose.Words untuk .NET?

J: Pembatasan baca-saja di Aspose.Words untuk .NET mengacu pada fitur yang memungkinkan Anda mengatur dokumen Word sebagai hanya-baca, mencegah pengguna melakukan modifikasi apa pun pada konten atau pemformatan. Pembatasan ini membantu melindungi integritas dokumen dan memastikan bahwa dokumen tersebut tidak dimodifikasi secara tidak sengaja atau jahat.

#### T: Bagaimana cara menghapus pembatasan baca-saja menggunakan Aspose.Words untuk .NET?

J: Untuk menghapus pembatasan baca-saja dari dokumen Word menggunakan Aspose.Words untuk .NET, Anda dapat mengikuti langkah-langkah berikut:
1.  Buat sebuah instance dari`Document` kelas dan atur kata sandi untuk dokumen menggunakan`SetPassword` metode`WriteProtection` obyek.
2.  Mengatur`ReadOnlyRecommended` properti dari`WriteProtection` objek untuk`false` untuk menghapus rekomendasi baca-saja.
3.  Terapkan perlindungan tak terbatas pada dokumen menggunakan`Protect` metode`Document` keberatan dengan`NoProtection` jenis perlindungan.
4.  Simpan dokumen tanpa batasan read-only menggunakan`Save` metode`Document` obyek.

#### T: Dapatkah saya menghapus pembatasan baca-saja dari dokumen Word tanpa kata sandi?

J: Tidak, Anda tidak dapat menghapus pembatasan baca-saja dari dokumen Word tanpa memberikan kata sandi yang benar. Pembatasan read-only diatur untuk tujuan keamanan, dan menghapusnya tanpa kata sandi akan merusak tujuan melindungi integritas dokumen.

#### T: Dapatkah saya menghapus pembatasan baca-saja dari dokumen Word dengan kata sandi yang salah?

J: Tidak, Anda tidak dapat menghapus pembatasan baca-saja dari dokumen Word dengan kata sandi yang salah. Kata sandi yang benar harus diberikan untuk menghapus pembatasan hanya-baca dan membuat dokumen dapat diedit kembali. Hal ini memastikan bahwa hanya pengguna yang berwenang dengan kata sandi yang benar yang dapat mengubah dokumen.

#### T: Apakah mungkin untuk menghapus jenis perlindungan dokumen lainnya menggunakan Aspose.Words untuk .NET?

J: Ya, Aspose.Words untuk .NET menyediakan berbagai metode untuk menghapus jenis perlindungan dokumen lainnya, seperti perlindungan kata sandi, perlindungan formulir, atau pembatasan pengeditan dokumen. Bergantung pada jenis perlindungan yang diterapkan pada dokumen, Anda dapat menggunakan metode dan properti terkait yang disediakan oleh Aspose.Words untuk menghapus perlindungan khusus dan membuat dokumen dapat diedit.
