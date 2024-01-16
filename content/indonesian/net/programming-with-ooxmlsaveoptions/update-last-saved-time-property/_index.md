---
title: Perbarui Properti Waktu Tersimpan Terakhir
linktitle: Perbarui Properti Waktu Tersimpan Terakhir
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara memperbarui properti Waktu Tersimpan Terakhir secara otomatis saat menyimpan dokumen dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-ooxmlsaveoptions/update-last-saved-time-property/
---
Dalam tutorial ini, kita akan menjelajahi kode sumber C# yang disediakan untuk memperbarui properti penyimpanan waktu terakhir saat menyimpan dokumen menggunakan Aspose.Words untuk .NET. Fitur ini memungkinkan Anda memperbarui secara otomatis properti penyimpanan waktu terakhir dari dokumen yang dihasilkan.

## Langkah 1: Menyiapkan lingkungan

Sebelum memulai, pastikan Anda telah menyiapkan lingkungan pengembangan dengan Aspose.Words untuk .NET. Pastikan Anda telah menambahkan referensi yang diperlukan dan mengimpor namespace yang sesuai.

## Langkah 2: Memuat dokumen

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

 Pada langkah ini, kami memuat dokumen menggunakan`Document` metode dan meneruskan jalur ke file DOCX untuk dimuat.

## Langkah 3: Mengonfigurasi opsi pencadangan OOXML

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };
```

 Pada langkah ini, kami mengonfigurasi opsi penyimpanan OOXML menggunakan`OoxmlSaveOptions` kelas. Kami mengaktifkan pembaruan otomatis properti penghematan waktu terakhir dengan pengaturan`UpdateLastSavedTimeProperty` ke`true`.

## Langkah 4: Simpan dokumen dengan properti yang diperbarui

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
```

 Pada langkah terakhir ini, kita menyimpan dokumen menggunakan`Save` metode dan meneruskan jalur ke file keluaran dengan`.docx` ekstensi, bersama dengan opsi penyimpanan yang ditentukan.

Sekarang Anda dapat menjalankan kode sumber untuk secara otomatis memperbarui properti penyimpanan waktu terakhir saat menyimpan dokumen. File yang dihasilkan akan disimpan di direktori yang ditentukan dengan nama "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx".

### Contoh kode sumber untuk Memperbarui Properti Waktu Tersimpan Terakhir menggunakan Aspose.Words untuk .NET 

```csharp

// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
            
        
```

## Kesimpulan

Dalam tutorial ini, kita menjelajahi fitur pembaruan otomatis properti penyimpanan waktu terakhir saat menyimpan dokumen menggunakan Aspose.Words untuk .NET. Dengan mengaktifkan fitur ini dengan opsi penyimpanan OOXML, Anda dapat memastikan bahwa properti penyimpanan waktu terakhir diperbarui secara otomatis di dokumen yang dihasilkan.

Memperbarui properti penghematan waktu terakhir dapat berguna untuk melacak perubahan dan versi dokumen. Itu juga melacak kapan dokumen terakhir disimpan, yang dapat berguna dalam berbagai skenario.

Aspose.Words untuk .NET memudahkan pembaruan otomatis properti Waktu Pencadangan Terakhir dengan menyediakan opsi pencadangan yang fleksibel dan kuat. Anda dapat mengintegrasikan fitur ini ke dalam proyek Anda untuk memastikan bahwa dokumen yang dihasilkan memiliki informasi cadangan yang akurat.