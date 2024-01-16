---
title: Atur Sistem Folder Font Dan Folder Kustom
linktitle: Atur Sistem Folder Font Dan Folder Kustom
second_title: API Pemrosesan Dokumen Aspose.Words
description: Panduan langkah demi langkah untuk mengatur sistem dan folder font khusus saat merender dokumen menggunakan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-fonts/set-fonts-folders-system-and-custom-folder/
---

Dalam tutorial ini, kami akan memandu Anda melalui proses langkah demi langkah untuk mengatur folder font sistem dan folder kustom saat merender dokumen menggunakan Aspose.Words untuk .NET. Kami akan menjelaskan paket kode sumber C# dan memberi Anda panduan komprehensif untuk membantu Anda memahami dan menerapkan fitur ini dalam proyek Anda sendiri. Di akhir tutorial ini, Anda akan mengetahui cara menentukan beberapa folder font, termasuk folder sistem dan folder kustom, untuk digunakan saat merender dokumen Anda menggunakan Aspose.Words untuk .NET.

## Langkah 1: Tentukan direktori dokumen
Pertama, Anda perlu menyetel jalur ke direktori dokumen Anda. Ini adalah lokasi di mana Anda ingin menyimpan dokumen hasil editan Anda. Ganti "DIREKTORI DOKUMEN ANDA" dengan jalur yang sesuai.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Muat dokumen yang akan dirender
 Kemudian Anda dapat memuat dokumen untuk dirender menggunakan`Document` kelas. Pastikan untuk menentukan jalur dokumen yang benar.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Langkah 3: Atur sistem dan folder font khusus
 Sekarang Anda dapat mengatur folder font sistem dan folder khusus menggunakan`FontSettings` kelas dan`SetFontsSources()` metode. Pertama, Anda perlu mengambil daftar sumber font yang bergantung pada lingkungan menggunakan`GetFontsSources()` dan menyimpannya dalam daftar. Kemudian Anda dapat membuat instance baru`FolderFontSource` menentukan jalur ke folder khusus yang berisi font Anda. Tambahkan contoh ini ke daftar sumber font yang ada. Terakhir, gunakan`SetFontsSources()` untuk memperbarui sumber font dengan daftar baru.

```csharp
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
```

## Langkah 4: Terapkan Pengaturan Font
 Selanjutnya, Anda perlu menerapkan pengaturan font ke dokumen Anda menggunakan`FontSettings` properti dari`Document` kelas.

```csharp
doc.FontSettings = fontSettings;
```

## Langkah 5: Simpan dokumen yang dirender
Terakhir, Anda dapat menyimpan dokumen yang dirender ke file dengan

   menggunakan`Save()` metode`Document` kelas. Pastikan untuk menentukan jalur dan nama file yang benar.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

### Contoh kode sumber untuk Mengatur Sistem Folder Font dan Folder Kustom menggunakan Aspose.Words untuk .NET 

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Ambil rangkaian sumber font yang bergantung pada lingkungan yang dicari secara default.
// Misalnya ini akan berisi sumber "Windows\Fonts\" pada mesin Windows.
// Kami menambahkan array ini ke Daftar baru untuk membuat penambahan atau penghapusan entri font menjadi lebih mudah.
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
// Tambahkan folder baru sumber yang akan menginstruksikan Aspose.Words untuk mencari font di folder berikut.
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
// Tambahkan folder khusus yang berisi font kami ke daftar sumber font yang ada.
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

## Kesimpulan
Dalam tutorial ini, kita mempelajari cara mengatur folder font sistem dan folder khusus saat merender dokumen menggunakan Aspose.Words untuk .NET. Dengan mengikuti panduan langkah demi langkah ini, Anda dapat dengan mudah menentukan beberapa folder font, termasuk folder sistem dan folder khusus, untuk digunakan saat merender dokumen Anda. Aspose.Words menawarkan API yang kuat dan fleksibel untuk Pemrosesan Kata dengan font di dokumen Anda. Dengan pengetahuan ini, Anda dapat mengontrol dan menyesuaikan sumber font yang digunakan saat merender dokumen sesuai kebutuhan spesifik Anda.

### FAQ

#### T: Bagaimana cara mengatur folder font sistem di Aspose.Words?

J: Untuk mengatur folder font sistem di Aspose.Words, Anda tidak perlu melakukan apa pun. Aspose.Words secara otomatis menggunakan font sistem yang diinstal pada sistem operasi Anda.

#### T: Bagaimana cara mengatur folder font khusus di Aspose.Words?

 A: Untuk mengatur folder font khusus di Aspose.Words, Anda dapat menggunakan`SetFontsFolders` metode`Fonts` kelas yang menentukan lokasi folder font khusus.

#### T: Dapatkah saya menentukan beberapa folder font khusus di Aspose.Words?

 J: Ya, Anda dapat menentukan beberapa folder font khusus di Aspose.Words menggunakan`SetFontsFolders` metode`Fonts` kelas dengan daftar lokasi folder.

#### T: Bagaimana cara memeriksa folder font yang ditentukan di Aspose.Words?

 Untuk memeriksa folder font yang ditentukan di Aspose.Words, Anda dapat menggunakan`GetFolders` metode`Fonts` kelas untuk mendapatkan daftar folder font yang dikonfigurasi.

#### T: Apakah font folder khusus lebih diprioritaskan daripada font sistem di Aspose.Words?

J: Ya, font folder khusus memiliki prioritas dibandingkan font sistem di Aspose.Words. Jika font ada di folder khusus dan font sistem, Aspose.Words akan menggunakan versi dari folder khusus.