---
title: Panggilan Balik Tanda Hubung
linktitle: Panggilan Balik Tanda Hubung
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menerapkan panggilan balik tanda hubung di Aspose.Words untuk .NET guna menyempurnakan pemformatan dokumen dengan panduan langkah demi langkah yang komprehensif ini.
type: docs
weight: 10
url: /id/net/working-with-hyphenation/hyphenation-callback/
---

## Perkenalan

Hai! Pernahkah Anda terjebak dalam kerumitan pemformatan teks, terutama ketika berhadapan dengan bahasa yang memerlukan tanda hubung? Anda tidak sendirian. Tanda hubung, meskipun penting untuk tata letak teks yang tepat, bisa sedikit memusingkan. Tapi coba tebak? Aspose.Words untuk .NET mendukung Anda. Pustaka canggih ini memungkinkan Anda mengelola pemformatan teks dengan lancar, termasuk menangani tanda hubung melalui mekanisme panggilan balik. Penasaran? Mari selami seluk beluk bagaimana Anda dapat mengimplementasikan callback tanda hubung menggunakan Aspose.Words untuk .NET.

## Prasyarat

Sebelum kita mengotak-atik kode, pastikan Anda memiliki semua yang Anda butuhkan:

1. Aspose.Words untuk .NET: Pastikan Anda memiliki perpustakaan. Anda bisa[unduh di sini](https://releases.aspose.com/words/net/).
2. IDE: Lingkungan pengembangan seperti Visual Studio.
3. Pengetahuan Dasar C#: Pemahaman C# dan .NET framework.
4. Kamus Tanda Hubung: Kamus tanda hubung untuk bahasa yang ingin Anda gunakan.
5.  Lisensi Aspose: Lisensi Aspose yang valid. Anda bisa mendapatkan[izin sementara](https://purchase.aspose.com/temporary-license/) jika Anda tidak memilikinya.

## Impor Namespace

Hal pertama yang pertama, mari impor namespace yang diperlukan. Ini memastikan kode kita memiliki akses ke semua kelas dan metode yang kita perlukan dari Aspose.Words.

```csharp
using Aspose.Words;
using System;
using System.IO;
```

## Langkah 1: Daftarkan Panggilan Balik Tanda Hubung

Untuk memulai, kita perlu mendaftarkan panggilan balik tanda hubung kita. Di sinilah kami memberi tahu Aspose.Words untuk menggunakan logika tanda hubung khusus kami.

```csharp
try
{
    // Daftarkan panggilan balik tanda hubung.
    Hyphenation.Callback = new CustomHyphenationCallback();
}
catch (Exception e)
{
    Console.WriteLine($"Error registering hyphenation callback: {e.Message}");
}
```

 Di sini, kami membuat instance panggilan balik khusus kami dan menugaskannya ke dalamnya`Hyphenation.Callback`.

## Langkah 2: Tentukan Jalur Dokumen

Selanjutnya, kita perlu menentukan direktori tempat dokumen kita disimpan. Ini penting karena kita akan memuat dan menyimpan dokumen dari jalur ini.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Mengganti`"YOUR DOCUMENT DIRECTORY"` dengan jalur sebenarnya ke dokumen Anda.

## Langkah 3: Muat Dokumen

Sekarang, mari muat dokumen yang memerlukan tanda hubung.

```csharp
Document document = new Document(dataDir + "German text.docx");
```

Di sini, kami memuat dokumen teks Jerman. Anda bisa menggantinya`"German text.docx"` dengan nama file dokumen Anda.

## Langkah 4: Simpan Dokumen

Setelah memuat dokumen, kami menyimpannya ke file baru, menerapkan panggilan balik tanda hubung dalam prosesnya.

```csharp
document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
```

Baris ini menyimpan dokumen sebagai PDF dengan tanda hubung diterapkan.

## Langkah 5: Tangani Pengecualian Kamus Tanda Hubung yang Hilang

Terkadang, Anda mungkin mengalami masalah ketika kamus tanda hubung tidak ada. Mari kita atasi itu.

```csharp
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
    Console.WriteLine(e.Message);
}
finally
{
    Hyphenation.Callback = null;
}
```

Di blok ini, kami menangkap pengecualian spesifik yang terkait dengan kamus yang hilang dan mencetak pesannya.

## Langkah 6: Terapkan Kelas Panggilan Balik Tanda Hubung Kustom

 Sekarang, mari kita terapkan`CustomHyphenationCallback` kelas yang menangani permintaan kamus tanda hubung.

```csharp
public class CustomHyphenationCallback : IHyphenationCallback
{
    public void RequestDictionary(string language)
    {
        string dictionaryFolder = MyDir;
        string dictionaryFullFileName;
        switch (language)
        {
            case "en-US":
                dictionaryFullFileName = Path.Combine(dictionaryFolder, "hyph_en_US.dic");
                break;
            case "de-CH":
                dictionaryFullFileName = Path.Combine(dictionaryFolder, "hyph_de_CH.dic");
                break;
            default:
                throw new Exception($"Missing hyphenation dictionary for {language}.");
        }
        // Daftarkan kamus untuk bahasa yang diminta.
        Hyphenation.RegisterDictionary(language, dictionaryFullFileName);
    }
}
```

 Di kelas ini,`RequestDictionary` metode dipanggil setiap kali kamus tanda hubung diperlukan. Ia memeriksa bahasa dan mendaftarkan kamus yang sesuai.

## Kesimpulan

Dan itu dia! Anda baru saja mempelajari cara menerapkan panggilan balik tanda hubung di Aspose.Words untuk .NET. Dengan mengikuti langkah-langkah ini, Anda dapat memastikan dokumen Anda diformat dengan indah, apa pun bahasanya. Baik Anda menggunakan bahasa Inggris, Jerman, atau bahasa lainnya, metode ini memungkinkan Anda menangani tanda hubung dengan mudah.

## FAQ

### Apa itu Aspose.Words untuk .NET?
Aspose.Words for .NET adalah pustaka manipulasi dokumen canggih yang memungkinkan pengembang membuat, memodifikasi, dan mengonversi dokumen secara terprogram.

### Mengapa tanda hubung penting dalam pemformatan dokumen?
Tanda hubung meningkatkan tata letak teks dengan memecah kata-kata di tempat yang tepat, memastikan dokumen lebih mudah dibaca dan menarik secara visual.

### Bisakah saya menggunakan Aspose.Words secara gratis?
 Aspose.Words menawarkan uji coba gratis. Anda bisa mendapatkannya[Di Sini](https://releases.aspose.com/).

### Bagaimana cara mendapatkan kamus tanda hubung?
Anda dapat mengunduh kamus tanda hubung dari berbagai sumber online atau membuatnya sendiri jika diperlukan.

### Apa yang terjadi jika kamus tanda hubung tidak ada?
 Jika kamus tidak ada,`RequestDictionary`metode memunculkan pengecualian, yang dapat Anda tangani untuk memberi tahu pengguna atau menyediakan cadangan.