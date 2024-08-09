---
title: Atur Sistem Folder Font Dan Folder Kustom
linktitle: Atur Sistem Folder Font Dan Folder Kustom
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengatur folder sistem dan font kustom di dokumen Word menggunakan Aspose.Words untuk .NET, memastikan dokumen Anda ditampilkan dengan benar di berbagai lingkungan.
type: docs
weight: 10
url: /id/net/working-with-fonts/set-fonts-folders-system-and-custom-folder/
---
## Perkenalan

Bayangkan Anda membuat dokumen dengan gaya font yang unik, hanya untuk mengetahui bahwa font tersebut tidak ditampilkan dengan benar di komputer lain. Membuat frustrasi, bukan? Di sinilah konfigurasi folder font berperan. Dengan Aspose.Words untuk .NET, Anda dapat menentukan sistem dan folder font khusus untuk memastikan dokumen Anda selalu terlihat sebagaimana mestinya. Mari selami bagaimana Anda dapat mencapai hal ini.

## Prasyarat

Sebelum kita mulai, pastikan Anda memiliki yang berikut ini:

-  Aspose.Words untuk .NET Library: Jika Anda belum melakukannya, unduhlah[Di Sini](https://releases.aspose.com/words/net/).
- Lingkungan Pengembangan: IDE seperti Visual Studio.
- Pengetahuan Dasar C#: Keakraban dengan C# akan membantu Anda mengikuti contoh kode.

## Impor Namespace

Pertama, impor namespace yang diperlukan dalam proyek Anda:

```csharp
using System;
using System.Collections.Generic;
using Aspose.Words;
using Aspose.Words.Fonts;
```

Sekarang, mari kita bagi prosesnya menjadi langkah-langkah sederhana.

## Langkah 1: Muat Dokumen

 Untuk memulai, muat dokumen Word Anda ke dalam Aspose.Words`Document` obyek. Dokumen ini akan menjadi dokumen tempat Anda ingin mengatur folder font.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

## Langkah 2: Inisialisasi Pengaturan Font

 Buat instance baru dari`FontSettings`. Objek ini memungkinkan Anda mengelola sumber font.

```csharp
FontSettings fontSettings = new FontSettings();
```

## Langkah 3: Ambil Sumber Font Sistem

Ambil sumber font sistem default. Pada mesin Windows, ini biasanya mencakup file "Windows\Fonts\" direktori.

```csharp
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
```

## Langkah 4: Tambahkan Folder Font Kustom

Tambahkan folder khusus yang berisi font tambahan Anda. Ini berguna jika Anda memiliki font tertentu yang tidak diinstal di direktori font sistem.

```csharp
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);
```

## Langkah 5: Perbarui Sumber Font

 Konversikan daftar sumber font kembali ke array dan atur ke`FontSettings` obyek.

```csharp
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
```

## Langkah 6: Terapkan Pengaturan Font ke Dokumen

 Terakhir, terapkan yang dikonfigurasi`FontSettings` ke dokumen Anda dan simpan dalam format yang Anda inginkan, seperti PDF.

```csharp
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

## Kesimpulan

Dan itu dia! Dengan mengikuti langkah-langkah ini, Anda dapat memastikan bahwa dokumen Word Anda menggunakan font yang benar, baik font sistem atau font kustom yang disimpan di direktori tertentu. Penyiapan ini membantu menjaga integritas tampilan dokumen Anda di berbagai lingkungan.

## FAQ

### Apa yang terjadi jika font hilang di folder sistem dan folder khusus?

Aspose.Words akan menggunakan font default untuk menggantikan font yang hilang, memastikan dokumen tetap dapat dibaca.

### Bisakah saya menambahkan beberapa folder font khusus?

 Ya, Anda dapat menambahkan beberapa folder font khusus dengan mengulangi proses pembuatan`FolderFontSource` objek dan menambahkannya ke daftar sumber font.

### Apakah mungkin menggunakan jalur jaringan untuk folder font khusus?

 Ya, Anda dapat menentukan jalur jaringan di`FolderFontSource` konstruktor.

### Format file apa yang didukung Aspose.Words untuk menyimpan dokumen?

Aspose.Words mendukung berbagai format, termasuk DOCX, PDF, HTML, dan lainnya.

### Bagaimana cara menangani pemberitahuan penggantian font?

 Anda dapat menangani pemberitahuan penggantian font dengan menggunakan`FontSettings` kelas`FontSubstitutionWarning`peristiwa.