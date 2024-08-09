---
title: Jangkar Vertikal
linktitle: Jangkar Vertikal
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mengatur posisi jangkar vertikal untuk kotak teks di dokumen Word menggunakan Aspose.Words untuk .NET. Panduan langkah demi langkah yang mudah disertakan.
type: docs
weight: 10
url: /id/net/programming-with-shapes/vertical-anchor/
---
## Perkenalan

Pernahkah Anda merasa perlu mengontrol dengan tepat di mana teks muncul di dalam kotak teks di dokumen Word? Mungkin Anda ingin teks Anda ditaruh di bagian atas, tengah, atau bawah kotak teks? Jika demikian, Anda berada di tempat yang tepat! Dalam tutorial ini, kita akan mempelajari cara menggunakan Aspose.Words untuk .NET untuk mengatur jangkar vertikal kotak teks di dokumen Word. Bayangkan penahan vertikal sebagai tongkat ajaib yang memposisikan teks Anda tepat di tempat yang Anda inginkan dalam wadahnya. Siap untuk terjun? Mari kita mulai!

## Prasyarat

Sebelum kita mendalami dasar-dasar penahan vertikal, Anda perlu menyiapkan beberapa hal:

1.  Aspose.Words for .NET: Pastikan Anda telah menginstal perpustakaan Aspose.Words for .NET. Jika Anda belum memilikinya, Anda bisa[unduh di sini](https://releases.aspose.com/words/net/).
2. Visual Studio: Tutorial ini mengasumsikan Anda menggunakan Visual Studio atau .NET IDE lainnya untuk pengkodean.
3. Pengetahuan Dasar tentang C#: Keakraban dengan C# dan .NET akan membantu Anda mengikutinya dengan lancar.

## Impor Namespace

Untuk memulai, Anda perlu mengimpor namespace yang diperlukan dalam kode C# Anda. Di sinilah Anda memberi tahu aplikasi Anda di mana menemukan kelas dan metode yang akan Anda gunakan. Berikut cara melakukannya:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

Namespace ini menyediakan kelas yang Anda perlukan untuk bekerja dengan dokumen dan bentuk.

## Langkah 1: Inisialisasi Dokumen

Hal pertama yang pertama, Anda perlu membuat dokumen Word baru. Anggap saja ini seperti menyiapkan kanvas sebelum Anda mulai melukis.

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Di Sini,`Document` adalah kanvas kosongmu, dan`DocumentBuilder` adalah kuas Anda, memungkinkan Anda menambahkan bentuk dan teks.

## Langkah 2: Sisipkan Bentuk Kotak Teks

Sekarang, mari tambahkan kotak teks ke dokumen kita. Di sinilah teks Anda akan ditampilkan. 

```csharp
Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
```

 Dalam contoh ini,`ShapeType.TextBox` menentukan bentuk yang Anda inginkan, dan`200, 200` adalah lebar dan tinggi kotak teks dalam poin.

## Langkah 3: Atur Jangkar Vertikal

Di sinilah keajaiban terjadi! Anda dapat mengatur perataan vertikal teks di dalam kotak teks. Ini menentukan apakah teks ditambatkan ke bagian atas, tengah, atau bawah kotak teks.

```csharp
textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
```

 Dalam hal ini,`TextBoxAnchor.Bottom`memastikan bahwa teks akan ditambatkan ke bagian bawah kotak teks. Jika Anda menginginkannya terpusat atau sejajar ke atas, Anda akan menggunakannya`TextBoxAnchor.Center` atau`TextBoxAnchor.Top`, masing-masing.

## Langkah 4: Tambahkan Teks ke Kotak Teks

Sekarang saatnya menambahkan beberapa konten ke kotak teks Anda. Anggap saja seperti mengisi kanvas Anda dengan sentuhan akhir.

```csharp
builder.MoveTo(textBox.FirstParagraph);
builder.Write("Textbox contents");
```

 Di Sini,`MoveTo` memastikan bahwa teks dimasukkan ke dalam kotak teks, dan`Write` menambahkan teks sebenarnya.

## Langkah 5: Simpan Dokumen

Langkah terakhir adalah menyimpan dokumen Anda. Ini seperti memasukkan lukisan Anda yang sudah selesai ke dalam bingkai.

```csharp
doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

## Kesimpulan

Dan itu dia! Anda baru saja mempelajari cara mengontrol perataan vertikal teks dalam kotak teks di dokumen Word menggunakan Aspose.Words untuk .NET. Baik Anda menempelkan teks ke atas, tengah, atau bawah, fitur ini memberi Anda kontrol tepat atas tata letak dokumen Anda. Jadi lain kali Anda perlu mengubah penempatan teks dokumen Anda, Anda akan tahu apa yang harus dilakukan!

## FAQ

### Apa itu penahan vertikal di dokumen Word?
Penahan vertikal mengontrol tempat teks diposisikan dalam kotak teks, seperti perataan atas, tengah, atau bawah.

### Bisakah saya menggunakan bentuk lain selain kotak teks?
Ya, Anda bisa menggunakan penahan vertikal dengan bentuk lain, meskipun kotak teks adalah kasus penggunaan yang paling umum.

### Bagaimana cara mengubah titik jangkar setelah membuat kotak teks?
 Anda dapat mengubah titik jangkar dengan mengatur`VerticalAnchor` properti pada objek bentuk kotak teks.

### Apakah mungkin untuk mengaitkan teks ke tengah kotak teks?
 Sangat! Gunakan saja`TextBoxAnchor.Center` untuk memusatkan teks secara vertikal di dalam kotak teks.

### Di mana saya dapat menemukan informasi selengkapnya tentang Aspose.Words untuk .NET?
 Lihat[Dokumentasi Aspose.Words](https://reference.aspose.com/words/net/) untuk lebih jelasnya dan panduannya.