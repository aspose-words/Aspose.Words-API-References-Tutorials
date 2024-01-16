---
title: Sisipkan Bidang Penulis
linktitle: Sisipkan Bidang Penulis
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara Menyisipkan bidang AUTHOR di dokumen Word Anda dengan Aspose.Words untuk .NET. Tentukan nama penulis untuk mempersonalisasi dokumen Anda.
type: docs
weight: 10
url: /id/net/working-with-fields/insert-author-field/
---


Berikut adalah panduan langkah demi langkah untuk menjelaskan kode sumber C# di bawah ini, yang menggunakan fitur "Sisipkan bidang AUTHOR" dari Aspose.Words untuk .NET. Pastikan untuk mengikuti setiap langkah dengan hati-hati untuk mendapatkan hasil yang diinginkan.

## Langkah 1: Pengaturan Direktori Dokumen

Dalam kode yang diberikan, Anda harus menentukan direktori dokumen Anda. Ganti nilai "DIREKTORI DOKUMEN ANDA" dengan jalur yang sesuai ke direktori dokumen Anda.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Langkah 2: Membuat Dokumen dan Paragraf

Kita mulai dengan membuat dokumen baru dan mengambil paragraf pertama.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## Langkah 3: Sisipkan kolom AUTHOR

 Kami menggunakan`AppendField()` metode untuk menyisipkan bidang AUTHOR ke dalam paragraf.

```csharp
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);
```

 Kami kemudian mengkonfigurasi bidang tersebut`AuthorName` properti untuk menentukan nama penulis.

```csharp
field. AuthorName = "Test1";
```

 Akhirnya, kami menelepon`Update()` metode untuk memperbarui bidang.

```csharp
field. Update();
```

### Contoh kode sumber untuk menyisipkan kolom AUTHOR dengan Aspose.Words untuk .NET

```csharp
// Jalur ke direktori dokumen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Pembuatan dokumen.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Masukkan bidang PENULIS.
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);

field. AuthorName = "Test1";

field. Update();

doc.Save(dataDir + "InsertionAuthorField.docx");
```

Dalam contoh ini, kita membuat dokumen baru, menyisipkan kolom AUTHOR, mengkonfigurasi nama penulis, dan menyimpan dokumen dengan nama file tertentu.

Ini menyimpulkan panduan kami tentang penggunaan fitur "Sisipkan Bidang AUTHOR" dengan Aspose.Words untuk .NET.

### FAQ

#### T: Apa yang dimaksud dengan bidang penulis di Aspose.Words?

A: Bidang Penulis di Aspose.Words adalah bidang khusus yang secara otomatis menyisipkan dan memperbarui nama penulis dalam dokumen Word. Hal ini sering digunakan untuk menunjukkan siapa yang membuat atau memodifikasi dokumen.

#### T: Bagaimana cara memperbarui bidang penulis di dokumen Word dengan Aspose.Words?

J: Bidang penulis di dokumen Word dapat diperbarui untuk mencerminkan nama penulis saat ini. Untuk ini, Anda dapat menggunakan metode UpdateFields yang tersedia di kelas Dokumen. Metode ini akan memperbarui semua kolom dalam dokumen, termasuk kolom penulis.

#### T: Apakah mungkin untuk mengkustomisasi format bidang penulis di dokumen Word?

J: Ya, dimungkinkan untuk menyesuaikan format bidang penulis di dokumen Word. Secara default, kolom penulis hanya menampilkan nama penulis. Namun, Anda dapat menambahkan informasi tambahan seperti tanggal dan waktu modifikasi menggunakan opsi pemformatan yang tersedia di Aspose.Words.

#### T: Apakah kolom penulis sensitif terhadap perubahan selanjutnya pada nama penulis?

J: Ya, kolom penulis sensitif terhadap perubahan selanjutnya pada nama penulis. Jika Anda mengubah nama penulis di properti dokumen, kolom penulis akan otomatis diperbarui dengan nama baru saat memperbarui kolom dokumen.