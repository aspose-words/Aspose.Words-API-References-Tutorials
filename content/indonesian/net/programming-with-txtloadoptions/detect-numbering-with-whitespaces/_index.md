---
title: Deteksi Penomoran Dengan Spasi Putih
linktitle: Deteksi Penomoran Dengan Spasi Putih
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara mendeteksi nomor daftar dengan spasi putih di Aspose.Words untuk .NET. Perbaiki struktur dokumen Anda dengan mudah.
type: docs
weight: 10
url: /id/net/programming-with-txtloadoptions/detect-numbering-with-whitespaces/
---
Dalam tutorial ini, kita akan menjelajahi kode sumber C# yang disediakan untuk fitur "Deteksi penomoran dengan spasi" dengan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda mendeteksi dan membuat daftar dari dokumen teks yang berisi nomor daftar diikuti dengan spasi.

## Langkah 1: Menyiapkan lingkungan

Sebelum memulai, pastikan Anda telah menyiapkan lingkungan pengembangan dengan Aspose.Words untuk .NET. Pastikan Anda telah menambahkan referensi yang diperlukan dan mengimpor namespace yang sesuai.

## Langkah 2: Membuat dokumen teks

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";

string textDoc = "Full stop delimiters:\n" +
                  "1. First list item 1\n" +
                  "2. First list item 2\n" +
                  "3. First list item 3\n\n" +
                  "Right bracket delimiters:\n" +
                  "1) Second list item 1\n" +
                  "2) Second list item 2\n" +
                  "3) Second list item 3\n\n" +
                  "Bullet delimiters:\n" +
                  "• Third list item 1\n" +
                  "• Third list item 2\n" +
                  "• Third list item 3\n\n" +
                  "Whitespace delimiters:\n" +
                  "1 Fourth list item 1\n" +
                  "2 Fourth list item 2\n" +
                  "3 Fourth list item 3";
```

Pada langkah ini, kita membuat string teks yang menyimulasikan dokumen teks yang berisi nomor daftar diikuti dengan spasi putih. Kami menggunakan pembatas daftar yang berbeda seperti titik, tanda kurung siku, simbol poin, dan spasi.

## Langkah 3: Mengonfigurasi opsi unggahan

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };
```

 Pada langkah ini, kami mengonfigurasi opsi pemuatan dokumen. Kami membuat yang baru`TxtLoadOptions` objek dan atur`DetectNumberingWithWhitespaces`properti ke`true`. Ini akan memungkinkan Aspose.Words mendeteksi nomor daftar meskipun diikuti oleh spasi.

## Langkah 4: Memuat dokumen dan menyimpannya

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
```

 Pada langkah ini, kita memuat dokumen menggunakan string teks yang ditentukan dan opsi memuat. Kami menggunakan a`MemoryStream` untuk mengubah string teks menjadi aliran memori. Kemudian kita simpan dokumen yang dihasilkan dalam format .docx.

### Contoh kode sumber untuk fitur Deteksi Penomoran Spasi Putih dengan Aspose.Words untuk .NET.

```csharp

            
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";
			
// Buat dokumen plaintext berbentuk string dengan bagian-bagian yang dapat diartikan sebagai daftar.
// Saat memuat, tiga daftar pertama akan selalu terdeteksi oleh Aspose.Words,
// dan objek Daftar akan dibuat untuknya setelah dimuat.
const string textDoc = "Full stop delimiters:\n" +
					   "1. First list item 1\n" +
					   "2. First list item 2\n" +
					   "3. First list item 3\n\n" +
					   "Right bracket delimiters:\n" +
					   "1) Second list item 1\n" +
					   "2) Second list item 2\n" +
					   "3) Second list item 3\n\n" +
					   "Bullet delimiters:\n" +
					   "• Third list item 1\n" +
					   "• Third list item 2\n" +
					   "• Third list item 3\n\n" +
					   "Whitespace delimiters:\n" +
					   "1 Fourth list item 1\n" +
					   "2 Fourth list item 2\n" +
					   "3 Fourth list item 3";

// Daftar keempat, dengan spasi di antara nomor daftar dan isi item daftar,
// hanya akan terdeteksi sebagai daftar jika "DetectNumberingWithWhitespaces" di objek LoadOptions disetel ke true,
// untuk menghindari paragraf yang dimulai dengan angka salah dideteksi sebagai daftar.
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };

// Muat dokumen sambil menerapkan LoadOptions sebagai parameter dan verifikasi hasilnya.
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
            
        
```

Sekarang Anda dapat menjalankan kode sumber untuk memuat dokumen teks yang berisi nomor daftar dengan spasi putih, lalu membuat dokumen .docx dengan daftar yang terdeteksi. File keluaran akan disimpan di direktori yang ditentukan dengan nama "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx".

## Kesimpulan
Dalam tutorial ini, kita menjelajahi fitur deteksi penomoran spasi putih di Aspose.Words untuk .NET. Kita mempelajari cara membuat daftar dari dokumen teks yang berisi nomor daftar diikuti dengan spasi.

Fitur ini sangat berguna untuk memproses dokumen yang berisi nomor daftar yang diformat dengan cara berbeda. Dengan menggunakan opsi pemuatan yang sesuai, Aspose.Words mampu mendeteksi nomor daftar ini, meskipun diikuti oleh spasi, dan mengubahnya menjadi daftar terstruktur di dokumen akhir.

Menggunakan fitur ini dapat menghemat waktu dan meningkatkan efisiensi alur kerja Anda. Anda dapat dengan mudah mengekstrak informasi dari dokumen teks dan mengubahnya menjadi dokumen terstruktur dengan baik dengan daftar yang tepat.

Ingatlah untuk mempertimbangkan opsi pemuatan, seperti mengonfigurasi deteksi panggilan spasi, untuk mencapai hasil yang diinginkan.

Aspose.Words untuk .NET menawarkan banyak fitur lanjutan untuk manipulasi dan pembuatan dokumen. Dengan menjelajahi lebih jauh dokumentasi dan contoh yang disediakan oleh Aspose.Words, Anda akan dapat memanfaatkan sepenuhnya kemampuan perpustakaan canggih ini.

Jadi, jangan ragu untuk mengintegrasikan deteksi penomoran spasi ke dalam proyek Aspose.Words untuk .NET Anda dan manfaatkan manfaatnya untuk membuat dokumen yang terstruktur dengan baik dan mudah dibaca.


