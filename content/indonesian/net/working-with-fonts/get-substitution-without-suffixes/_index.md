---
title: Dapatkan Substitusi Tanpa Sufiks
linktitle: Dapatkan Substitusi Tanpa Sufiks
second_title: API Pemrosesan Dokumen Aspose.Words
description: Dalam tutorial ini, pelajari cara mendapatkan penggantian tanpa sufiks di dokumen Word dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/working-with-fonts/get-substitution-without-suffixes/
---

Dalam tutorial ini, kami akan menunjukkan kepada Anda cara mendapatkan penggantian tanpa sufiks di dokumen Word menggunakan pustaka Aspose.Words untuk .NET. Substitusi tanpa sufiks digunakan untuk mengatasi masalah substitusi font saat menampilkan atau mencetak dokumen. Kami akan memandu Anda langkah demi langkah untuk membantu Anda memahami dan menerapkan kode dalam proyek .NET Anda.

## Prasyarat
Sebelum memulai, pastikan Anda memiliki item berikut:
- Pengetahuan tentang bahasa pemrograman C#
- Pustaka Aspose.Words untuk .NET diinstal di proyek Anda

## Langkah 1: Tentukan direktori dokumen
 Pertama, Anda perlu mengatur jalur direktori ke lokasi dokumen Word Anda. Mengganti`"YOUR DOCUMENT DIRECTORY"` dalam kode dengan jalur yang sesuai.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Muat dokumen dan konfigurasikan substitusi tanpa sufiks
 Selanjutnya, kita akan memuat dokumen menggunakan`Document` kelas dan konfigurasikan substitusi tanpa akhiran menggunakan`DocumentSubstitutionWarnings` kelas. Kami juga akan menambahkan sumber font dengan menentukan folder yang berisi font.

```csharp
// Muat dokumen dan konfigurasikan substitusi tanpa sufiks
Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;

List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
```

## Langkah 3: Simpan dokumen
Terakhir, kita akan menyimpan dokumen dengan penerapan no-suffix override.

```csharp
// Simpan dokumennya
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");
```

### Contoh kode sumber untuk Dapatkan Substitusi Tanpa Sufiks menggunakan Aspose.Words untuk .NET 
```csharp

// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;
List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");

```

## Kesimpulan
Dalam tutorial ini, kita melihat cara mendapatkan override tanpa sufiks di dokumen Word dengan Aspose.Words untuk .NET. Substitusi tanpa sufiks berguna untuk menyelesaikan masalah substitusi font. Jangan ragu untuk menggunakan fitur ini untuk meningkatkan tampilan dan pencetakan dokumen Anda.

### FAQ

#### T: Mengapa Aspose.Words menambahkan sufiks pada substitusi font?

J: Aspose.Words menambahkan sufiks pada substitusi font untuk menghindari konflik antara font asli dan font pengganti. Ini membantu memastikan kompatibilitas maksimum saat mengonversi dan memanipulasi dokumen.

#### T: Bagaimana cara mengambil substitusi font tanpa sufiks di Aspose.Words?

 A: Untuk mengambil substitusi font tanpa sufiks di Aspose.Words, Anda dapat menggunakan`FontSubstitutionSettings` kelas dan`RemoveSuffixes` Properti. Menyetel properti ini ke`true` akan mendapatkan penggantian font tanpa sufiks tambahan.

#### T: Apakah mungkin untuk menonaktifkan penambahan sufiks ke substitusi font di Aspose.Words?

J: Tidak, tidak mungkin untuk menonaktifkan penambahan sufiks ke substitusi font di Aspose.Words. Sufiks ditambahkan secara default untuk memastikan kompatibilitas dan konsistensi dokumen.

#### T: Bagaimana cara memfilter sufiks yang tidak diinginkan dalam penggantian font di Aspose.Words?

 A: Untuk memfilter sufiks yang tidak diinginkan pada substitusi font di Aspose.Words, Anda dapat menggunakan teknik pemrosesan string, seperti menggunakan`Replace` atau`Substring` metode untuk menghapus sufiks tertentu yang tidak ingin Anda sertakan.