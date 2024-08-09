---
title: Dapatkan Substitusi Tanpa Sufiks
linktitle: Dapatkan Substitusi Tanpa Sufiks
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengelola substitusi font tanpa sufiks di Aspose.Words untuk .NET. Ikuti panduan langkah demi langkah kami untuk memastikan dokumen Anda terlihat sempurna setiap saat.
type: docs
weight: 10
url: /id/net/working-with-fonts/get-substitution-without-suffixes/
---
## Perkenalan

Selamat datang di panduan komprehensif tentang mengelola substitusi font menggunakan Aspose.Words untuk .NET. Jika Anda pernah mengalami masalah dengan font yang tidak muncul dengan benar di dokumen Anda, Anda telah datang ke tempat yang tepat. Tutorial ini akan membawa Anda melalui proses langkah demi langkah untuk menangani substitusi font tanpa sufiks secara efisien.

## Prasyarat

Sebelum mendalami tutorial, pastikan Anda memiliki hal berikut:

- Pengetahuan Dasar C#: Memahami pemrograman C# akan memudahkan untuk mengikuti dan mengimplementasikan langkah-langkahnya.
-  Aspose.Words untuk .NET Library: Unduh dan instal perpustakaan dari[tautan unduhan](https://releases.aspose.com/words/net/).
- Lingkungan Pengembangan: Siapkan lingkungan pengembangan seperti Visual Studio untuk menulis dan menjalankan kode Anda.
-  Contoh Dokumen: Contoh dokumen (misalnya,`Rendering.docx`) untuk digunakan selama tutorial ini.

## Impor Namespace

Pertama, kita perlu mengimpor namespace yang diperlukan untuk mengakses kelas dan metode yang disediakan oleh Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
using System.Collections.Generic;
```

## Langkah 1: Tentukan Direktori Dokumen

Untuk memulai, tentukan direktori tempat dokumen Anda berada. Ini membantu dalam menemukan dokumen yang ingin Anda kerjakan.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Langkah 2: Siapkan Pengendali Peringatan Pergantian

Selanjutnya, kita perlu menyiapkan penangan peringatan yang akan memberi tahu kita setiap kali terjadi penggantian font selama pemrosesan dokumen. Ini penting untuk menangkap dan menangani masalah font apa pun.

```csharp
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
Document doc = new Document(dataDir + "Rendering.docx");
doc.WarningCallback = substitutionWarningHandler;
```

## Langkah 3: Tambahkan Sumber Font Khusus

Pada langkah ini, kami akan menambahkan sumber font khusus untuk memastikan Aspose.Words dapat menemukan dan menggunakan font yang benar. Ini sangat berguna jika Anda memiliki font tertentu yang disimpan di direktori khusus.

```csharp
List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());

FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);

FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
```

Dalam kode ini:
-  Kami mengambil sumber font saat ini dan menambahkan yang baru`FolderFontSource` menunjuk ke direktori font khusus kami (`C:\\MyFonts\\`).
- Kami kemudian memperbarui sumber font dengan daftar baru ini.

## Langkah 4: Simpan Dokumen

Terakhir, simpan dokumen setelah menerapkan pengaturan substitusi font. Untuk tutorial ini, kami akan menyimpannya sebagai PDF.

```csharp
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");
```

## Langkah 5: Buat Kelas Penangan Peringatan

 Untuk menangani peringatan secara efektif, buat kelas khusus yang mengimplementasikan`IWarningCallback` antarmuka. Kelas ini akan menangkap dan mencatat peringatan penggantian font apa pun.

```csharp
public class DocumentSubstitutionWarnings : IWarningCallback
{
    public void Warning(WarningInfo info)
    {
        if (info.WarningType == WarningType.FontSubstitution)
            FontWarnings.Warning(info);
    }

    public WarningInfoCollection FontWarnings = new WarningInfoCollection();
}
```

Di kelas ini:
-  Itu`Warning`metode menangkap peringatan terkait penggantian font.
-  Itu`FontWarnings` koleksi menyimpan peringatan ini untuk pemeriksaan atau pencatatan lebih lanjut.

## Kesimpulan

Anda sekarang telah menguasai proses penanganan substitusi font tanpa sufiks menggunakan Aspose.Words untuk .NET. Pengetahuan ini akan memastikan bahwa dokumen Anda mempertahankan tampilan yang diinginkan, apa pun font yang tersedia di sistem. Teruslah bereksperimen dengan pengaturan dan sumber yang berbeda untuk sepenuhnya memanfaatkan kekuatan Aspose.Words.

## FAQ

### Bagaimana cara menggunakan font dari beberapa direktori khusus?

 Anda dapat menambahkan banyak`FolderFontSource` contoh ke`fontSources` daftar dan perbarui sumber font yang sesuai.

### Di mana saya dapat mengunduh uji coba gratis Aspose.Words untuk .NET?

 Anda dapat mengunduh uji coba gratis dari[Asumsikan halaman uji coba gratis](https://releases.aspose.com/).

###  Bisakah saya menangani berbagai jenis peringatan menggunakan`IWarningCallback`?

 Ya, itu`IWarningCallback` antarmuka memungkinkan Anda menangani berbagai jenis peringatan, bukan hanya penggantian font.

### Di mana saya bisa mendapatkan dukungan untuk Aspose.Words?

 Untuk dukungan, kunjungi[Forum dukungan Aspose.Words](https://forum.aspose.com/c/words/8).

### Apakah mungkin untuk membeli lisensi sementara?

 Ya, Anda bisa mendapatkan lisensi sementara dari[halaman lisensi sementara](https://purchase.aspose.com/temporary-license/).