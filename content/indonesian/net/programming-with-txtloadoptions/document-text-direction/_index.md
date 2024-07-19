---
title: Arah Teks Dokumen
linktitle: Arah Teks Dokumen
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menentukan arah teks dalam dokumen Anda dengan Aspose.Words untuk .NET. Tingkatkan tampilan untuk bahasa kanan-ke-kiri.
type: docs
weight: 10
url: /id/net/programming-with-txtloadoptions/document-text-direction/
---

Dalam tutorial ini, kita akan menjelajahi kode sumber C# yang disediakan untuk fitur "Arah Teks Dokumen" dengan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda menentukan arah teks dalam dokumen, yang khususnya berguna untuk bahasa yang ditulis dari kanan ke kiri, seperti Ibrani atau Arab.

## Langkah 1: Menyiapkan lingkungan

Sebelum memulai, pastikan Anda telah menyiapkan lingkungan pengembangan dengan Aspose.Words untuk .NET. Pastikan Anda telah menambahkan referensi yang diperlukan dan mengimpor namespace yang sesuai.

## Langkah 2: Mengonfigurasi opsi unggahan

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";

TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection. Auto };
```

 Pada langkah ini, kami mengonfigurasi opsi pemuatan dokumen. Kami membuat yang baru`TxtLoadOptions` objek dan atur`DocumentDirection`properti ke`DocumentDirection.Auto`. Nilai ini memberitahu Aspose.Words untuk secara otomatis menentukan arah teks berdasarkan konten dokumen.

## Langkah 3: Memuat dokumen

```csharp
Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);
```

 Pada langkah ini, kami memuat dokumen menggunakan`Document` metode dan meneruskan jalur ke file teks untuk dimuat. Kami juga menggunakan opsi pemuatan yang ditentukan.

## Langkah 4: Memanipulasi paragraf dan menampilkan arah teks

```csharp
Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);
```

 Pada langkah ini, kita mengakses paragraf pertama dokumen menggunakan`FirstSection`Dan`Body` properti. Selanjutnya, kita mengakses`ParagraphFormat.Bidi` properti untuk mendapatkan arah teks paragraf. Kami kemudian menampilkan nilai ini di konsol.

## Langkah 5: Simpan dokumen

```csharp
doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
```

 Pada langkah terakhir ini, kami menyimpan dokumen yang dihasilkan dalam format .docx menggunakan`Save` metode dan meneruskan jalur ke file keluaran.

Sekarang Anda dapat menjalankan kode sumber untuk memuat dokumen teks dan menentukan arah teks. Dokumen yang dihasilkan akan disimpan di direktori yang ditentukan dengan nama "WorkingWithTxtLoadOptions.DocumentTextDirection.docx".

### Contoh kode sumber untuk fungsionalitas arah teks dokumen dengan Aspose.Words untuk .NET.


```csharp

            
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY";

TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection.Auto };

Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);

Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
            
        
```

## Kesimpulan

Dalam tutorial ini, kita menjelajahi fitur arah teks dokumen di Aspose.Words untuk .NET. Kami mempelajari cara menentukan arah teks dalam dokumen, khususnya untuk bahasa yang ditulis dari kanan ke kiri, seperti Ibrani atau Arab.

Fitur ini penting untuk memastikan teks ditampilkan dengan benar dalam dokumen multibahasa. Dengan menggunakan opsi pemuatan yang sesuai, Aspose.Words dapat secara otomatis mendeteksi arah teks dan menerapkannya pada dokumen.

Dengan Aspose.Words, Anda dapat dengan mudah memanipulasi arah teks dalam dokumen Anda, memberikan pengalaman membaca yang lancar dan intuitif bagi pengguna.

Penting untuk dicatat bahwa fitur ini sangat berguna ketika Pemrosesan Kata dengan bahasa yang memerlukan arah teks tertentu. Aspose.Words mempermudah tugas ini dengan menyediakan alat canggih untuk mengelola arah teks dalam dokumen Anda.

Ingatlah untuk menggunakan opsi pemuatan yang sesuai, seperti mengatur arah teks otomatis, untuk mendapatkan hasil yang Anda inginkan di dokumen Anda.

Aspose.Words untuk .NET menawarkan banyak fitur lanjutan untuk manipulasi dan pembuatan dokumen. Dengan menjelajahi lebih jauh dokumentasi dan contoh yang disediakan oleh Aspose.Words, Anda akan dapat memanfaatkan sepenuhnya kemampuan perpustakaan canggih ini.

Jadi, jangan ragu untuk mengintegrasikan arah teks dokumen ke dalam proyek Aspose.Words untuk .NET Anda dan manfaatkan manfaatnya untuk membuat dokumen multibahasa yang menarik dan berkualitas tinggi.