---
title: Panggilan Balik Penghematan Halaman
linktitle: Panggilan Balik Penghematan Halaman
second_title: API Pemrosesan Dokumen Aspose.Words
description: Pelajari cara menyesuaikan penyimpanan halaman dokumen ke gambar dengan Aspose.Words untuk .NET.
type: docs
weight: 10
url: /id/net/programming-with-imagesaveoptions/page-saving-callback/
---

Dalam tutorial ini, kita akan menjelajahi kode sumber C# yang disediakan untuk menggunakan callback penyimpanan halaman dengan opsi penyimpanan gambar Aspose.Words untuk .NET. Fitur ini memungkinkan Anda melakukan tindakan khusus saat menyimpan setiap halaman dokumen sebagai gambar.

## Langkah 1: Menyiapkan lingkungan

Sebelum memulai, pastikan Anda telah menyiapkan lingkungan pengembangan dengan Aspose.Words untuk .NET. Pastikan Anda telah menambahkan referensi yang diperlukan dan mengimpor namespace yang sesuai.

## Langkah 2: Memuat dokumen

```csharp
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 Pada langkah ini, kami memuat dokumen menggunakan`Document` metode dan meneruskan jalur ke file DOCX untuk dimuat.

## Langkah 3: Konfigurasikan opsi cadangan gambar

```csharp
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
     PageSavingCallback = new HandlePageSavingCallback()
};
```

 Pada langkah ini, kami mengonfigurasi opsi penyimpanan gambar dengan membuat yang baru`ImageSaveOptions` obyek. Kita tentukan format backup yang diinginkan, disini "Png" untuk format PNG. Kita gunakan`PageSet` untuk menentukan rentang halaman yang akan disimpan, di sini dari halaman pertama hingga halaman terakhir dokumen (`doc.PageCount - 1`). Kami juga mengatur`PageSavingCallback` ke contoh`HandlePageSavingCallback`, yang merupakan kelas khusus untuk menangani panggilan balik penyimpanan halaman.

## Langkah 4: Menerapkan Callback Simpan Halaman

```csharp
public class HandlePageSavingCallback : IPageSavingCallback
{
     public void PageSaving(PageSavingArgs args)
     {
         // Terapkan tindakan khusus Anda di sini
         // Anda dapat mengakses informasi halaman melalui properti "args.PageIndex".
         // Anda juga dapat mengubah opsi penyimpanan untuk setiap halaman satu per satu
     }
}
```

 Pada langkah ini, kami menerapkan`HandlePageSavingCallback` kelas yang mengimplementasikan`IPageSavingCallback` antarmuka. Anda dapat menyesuaikan kelas ini dengan menambahkan tindakan spesifik Anda di`PageSaving` metode. Anda dapat mengakses informasi halaman melalui`args.PageIndex` properti dari`PageSavingArgs` objek dilewatkan sebagai argumen.

## Langkah 5: Menyimpan halaman sebagai gambar

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

 Pada langkah terakhir ini, kami menyimpan setiap halaman dokumen sebagai gambar menggunakan`Save` metode dan meneruskan jalur ke file keluaran dengan`.png` ekstensi, bersama dengan opsi penyimpanan yang ditentukan.

Sekarang Anda dapat menjalankan kode sumber untuk melakukan tindakan khusus saat menyimpan setiap halaman dokumen sebagai gambar. File yang dihasilkan akan disimpan di direktori yang ditentukan dengan nama "WorkingWithImageSaveOptions.PageSavingCallback.png".

### Contoh kode sumber untuk Panggilan Balik Penyimpanan Halaman menggunakan Aspose.Words untuk .NET


```csharp 
// Jalur ke direktori dokumen Anda
string dataDir = "YOUR DOCUMENT DIRECTORY"; 


Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
	PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
	PageSavingCallback = new HandlePageSavingCallback()
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
        
```

## Kesimpulan

Dalam tutorial ini, kita menjelajahi fungsionalitas panggilan balik penyimpanan halaman dengan opsi penyimpanan gambar Aspose.Words untuk .NET. Kami mempelajari cara melakukan tindakan khusus saat menyimpan setiap halaman dokumen sebagai gambar.

Fitur ini berguna ketika Anda ingin melakukan operasi tertentu pada setiap halaman saat mengonversi ke gambar. Anda dapat mengakses informasi halaman dan menggunakannya untuk menyesuaikan opsi pencadangan atau melakukan pemrosesan khusus halaman lainnya.

Aspose.Words untuk .NET menawarkan beragam fitur canggih untuk manipulasi dan pembuatan dokumen. Pengingat Simpan Halaman adalah salah satu dari banyak alat canggih yang diberikan kepada Anda untuk menyesuaikan proses menyimpan halaman ke gambar.