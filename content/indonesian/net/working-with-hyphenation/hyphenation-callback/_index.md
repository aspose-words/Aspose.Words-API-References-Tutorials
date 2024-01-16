---
title: Panggilan Balik Tanda Hubung
linktitle: Panggilan Balik Tanda Hubung
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menggunakan panggilan balik tanda hubung di Aspose.Words untuk .NET untuk menangani tanda hubung kata.
type: docs
weight: 10
url: /id/net/working-with-hyphenation/hyphenation-callback/
---

Dalam tutorial langkah demi langkah ini, kami akan menunjukkan kepada Anda cara menggunakan fitur panggilan balik tanda hubung di Aspose.Words untuk .NET. Kami akan menjelaskan kode sumber C# yang disediakan dan menunjukkan cara mengimplementasikannya di proyek Anda sendiri.

 Untuk memulai, pastikan Anda telah menginstal dan mengkonfigurasi Aspose.Words for .NET di lingkungan pengembangan Anda. Jika Anda belum melakukannya, unduh dan instal perpustakaan dari[Aspose.Rilis]https://releases.aspose.com/words/net/.

## Langkah 1: Simpan Pengingat Tanda Hubung

 Pertama, kita akan mendaftarkan callback tanda hubung menggunakan custom`CustomHyphenationCallback` kelas. Ini akan memungkinkan kita menangani tanda hubung kata sesuai dengan aturan kita sendiri:

```csharp
Hyphenation.Callback = new CustomHyphenationCallback();
```

 Pastikan Anda telah menerapkannya`CustomHyphenationCallback` kelas sesuai dengan kebutuhan spesifik Anda.

## Langkah 2: Memuat dokumen dan menerapkan tanda hubung

Selanjutnya, muat dokumen Anda dari direktori yang ditentukan dan beri tanda hubung pada kata-kata tersebut menggunakan Aspose.Words:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "German text.docx");
document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
```

## Langkah 3: Menangani Kesalahan Kamus yang Hilang

Jika kamus tanda hubung tidak ada, kami akan menangkap pengecualian yang sesuai dan menampilkan pesan kesalahan:

```csharp
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
     Console.WriteLine(e.Message);
}
```

## Langkah 4: Bersihkan dan Nonaktifkan Pengingat Tanda Hubung

Terakhir, untuk kebersihan dan mematikan pengingat tanda hubung, lakukan langkah-langkah berikut:

```csharp
finally
{
     Hyphenation. Callback = null;
}
```

Ini membersihkan dan menonaktifkan pengingat tanda hubung setelah pemrosesan selesai.

Jadi ! Anda telah berhasil menggunakan panggilan balik tanda hubung di Aspose.Words untuk .NET.

### Contoh Kode Sumber untuk Panggilan Balik Tanda Hubung dengan Aspose.Words untuk .NET

```csharp
try
{
	 // Daftarkan panggilan balik tanda hubung.
	 Hyphenation.Callback = new CustomHyphenationCallback();
	 string dataDir = "YOUR DOCUMENT DIRECTORY";
	 Document document = new Document(dataDir + "German text.docx");
	 document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
}
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
	 Console.WriteLine(e.Message);
}
finally
{
	 Hyphenation. Callback = null;
}

```

Jangan ragu untuk menggunakan kode ini di proyek Anda sendiri dan memodifikasinya agar sesuai dengan kebutuhan spesifik Anda.

### FAQ

#### T: Apa yang dimaksud dengan pengingat silabisasi di Aspose.Words?

J: Pengingat Suku Kata di Aspose.Words adalah fitur yang memungkinkan Anda menyesuaikan cara menyusun suku kata dalam dokumen Anda. Dengan menggunakan pengingat silabisasi, Anda dapat menentukan aturan khusus untuk silabisasi kata, yang dapat berguna untuk bahasa tertentu atau skenario tertentu di mana silabisasi default tidak memberikan hasil yang diinginkan.

#### T: Bagaimana cara mengatur pengingat silabisasi di Aspose.Words?

 J: Untuk menentukan callback tanda hubung di Aspose.Words, Anda perlu membuat kelas yang mengimplementasikan`HyphenationCallback` antarmuka dan mengimplementasikan`HandleWord()` metode. Metode ini akan dipanggil untuk setiap kata yang ditemui selama silabisasi. Anda dapat menerapkan aturan suku kata khusus padanya dan mengembalikan kata yang diberi suku kata. Kemudian Anda dapat mengikat panggilan balik tanda hubung menggunakan`Document.HyphenationCallback` milik dokumen Anda.

#### T: Apa keuntungan menggunakan pengingat silabisasi di Aspose.Words?

J: Manfaat menggunakan pengingat silabisasi di Aspose.Words adalah kemampuan untuk menyesuaikan cara kata-kata disusun dalam dokumen Anda. Hal ini memberi Anda kontrol lebih besar atas silabisasi, terutama untuk bahasa atau skenario tertentu di mana silabisasi default tidak memberikan hasil yang diinginkan. Anda dapat menerapkan aturan khusus pada setiap kata untuk mendapatkan silabisasi yang tepat sesuai kebutuhan Anda.

#### T: Apa sajakah skenario umum di mana penggunaan pengingat silabisasi dapat membantu?

J: Menggunakan penguat silabisasi dapat berguna dalam beberapa skenario, seperti:
- Sukukata kata dalam bahasa tertentu yang mempunyai aturan suku kata tertentu.
- Penerapan aturan silabisasi yang dipersonalisasi untuk akronim atau kata teknis.
- Penyesuaian suku kata menurut preferensi gaya atau standar tipografi.

#### T: Bagaimana cara menguji silabisasi khusus dengan pengingat silabisasi di Aspose.Words?

 J: Untuk menguji silabisasi kustom dengan pengingat silabisasi di Aspose.Words, Anda dapat membuat dokumen pengujian yang berisi kata-kata yang ingin Anda terapkan aturan silabisasi kustomnya. Kemudian Anda dapat mengatur panggilan balik silabisasi khusus Anda, panggil`Document.Range.Replace()` metode untuk mengganti kata-kata dalam dokumen, dan menggunakan`Hyphenate()` metode`Hyphenation` kelas untuk mendapatkan suku kata dari kata-kata tersebut. Anda kemudian dapat memformat kata-kata yang diberi suku kata sesuai kebutuhan, misalnya dengan menambahkan tanda hubung di antara suku kata.