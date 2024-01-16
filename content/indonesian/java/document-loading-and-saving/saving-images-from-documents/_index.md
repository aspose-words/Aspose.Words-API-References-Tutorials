---
title: Menyimpan Gambar dari Dokumen di Aspose.Words untuk Java
linktitle: Menyimpan Gambar dari Dokumen
second_title: API Pemrosesan Dokumen Java Aspose.Words
description: Pelajari cara menyimpan gambar dari dokumen menggunakan Aspose.Words untuk Java dengan panduan langkah demi langkah komprehensif kami. Sesuaikan format, kompresi, dan lainnya.
type: docs
weight: 17
url: /id/java/document-loading-and-saving/saving-images-from-documents/
---

## Pengantar Menyimpan Gambar dari Dokumen di Aspose.Words untuk Java

Dalam tutorial ini, kita akan mempelajari cara menyimpan gambar dari dokumen menggunakan Aspose.Words untuk Java. Kami akan membahas berbagai skenario dan opsi penyesuaian untuk penyimpanan gambar. Panduan ini memberikan petunjuk langkah demi langkah dengan contoh kode sumber.

## Prasyarat

 Sebelum memulai, pastikan Anda memiliki perpustakaan Aspose.Words untuk Java yang terintegrasi ke dalam proyek Anda. Anda dapat mengunduhnya dari[Di Sini](https://releases.aspose.com/words/java/).

## Langkah 1: Menyimpan Gambar sebagai TIFF dengan Kontrol Ambang Batas

Untuk menyimpan gambar sebagai format TIFF dengan kontrol ambang batas, ikuti langkah-langkah berikut:

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.TIFF);
saveOptions.setTiffCompression(TiffCompression.CCITT_3);
saveOptions.setImageColorMode(ImageColorMode.GRAYSCALE);
saveOptions.setTiffBinarizationMethod(ImageBinarizationMethod.FLOYD_STEINBERG_DITHERING);
saveOptions.setThresholdForFloydSteinbergDithering((byte) 254);
doc.save("Your Directory Path" + "ThresholdControlledImage.tiff", saveOptions);
```

## Langkah 2: Menyimpan Halaman Tertentu sebagai TIFF Multihalaman

Untuk menyimpan halaman tertentu sebagai TIFF multi halaman, gunakan kode berikut:

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.TIFF);
saveOptions.setPageSet(new PageSet(new PageRange(0, 1)));
saveOptions.setTiffCompression(TiffCompression.CCITT_4);
saveOptions.setResolution(160f);
doc.save("Your Directory Path" + "SpecificPageMultipage.tiff", saveOptions);
```

## Langkah 3: Menyimpan Gambar sebagai 1 PNG Terindeks BPP

Untuk menyimpan gambar sebagai 1 PNG terindeks BPP, ikuti langkah-langkah berikut:

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.PNG);
saveOptions.setPageSet(new PageSet(1));
saveOptions.setImageColorMode(ImageColorMode.BLACK_AND_WHITE);
saveOptions.setPixelFormat(ImagePixelFormat.FORMAT_1_BPP_INDEXED);
doc.save("Your Directory Path" + "1BPPIndexed.png", saveOptions);
```

## Langkah 4: Menyimpan Halaman sebagai JPEG dengan Kustomisasi

Untuk menyimpan halaman tertentu sebagai JPEG dengan opsi penyesuaian, gunakan kode ini:

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.JPEG);
options.setPageSet(new PageSet(0));
options.setImageBrightness(0.3f);
options.setImageContrast(0.7f);
options.setHorizontalResolution(72f);
doc.save("Your Directory Path" + "CustomizedJPEG.jpeg", options);
```

## Langkah 5: Menggunakan Panggilan Balik Penyimpanan Halaman

Anda dapat menggunakan panggilan balik untuk menyesuaikan penyimpanan halaman. Berikut ini contohnya:

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.PNG);
imageSaveOptions.setPageSet(new PageSet(new PageRange(0, doc.getPageCount() - 1)));
imageSaveOptions.setPageSavingCallback(new HandlePageSavingCallback());
doc.save("Your Directory Path" + "PageSavingCallback.png", imageSaveOptions);
```

```java
private static class HandlePageSavingCallback implements IPageSavingCallback {
    public void pageSaving(PageSavingArgs args) {
        args.setPageFileName(MessageFormat.format("Your Directory Path" + "Page_{0}.png", args.getPageIndex()));
    }
}
```

## Kode Sumber Lengkap Untuk Menyimpan Gambar dari Dokumen di Aspose.Words untuk Java

```java
public void exposeThresholdControlForTiffBinarization() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Rendering.docx");
	ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.TIFF);
	{
		saveOptions.setTiffCompression(TiffCompression.CCITT_3);
		saveOptions.setImageColorMode(ImageColorMode.GRAYSCALE);
		saveOptions.setTiffBinarizationMethod(ImageBinarizationMethod.FLOYD_STEINBERG_DITHERING);
		saveOptions.setThresholdForFloydSteinbergDithering((byte) 254);
	}
	doc.save("Your Directory Path" + "WorkingWithImageSaveOptions.ExposeThresholdControlForTiffBinarization.tiff", saveOptions);
}
@Test
public void getTiffPageRange() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Rendering.docx");
	doc.save("Your Directory Path" + "WorkingWithImageSaveOptions.MultipageTiff.tiff");
	ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.TIFF);
	{
		saveOptions.setPageSet(new PageSet(new PageRange(0, 1))); saveOptions.setTiffCompression(TiffCompression.CCITT_4); saveOptions.setResolution(160f);
	}
	doc.save("Your Directory Path" + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
}
@Test
public void format1BppIndexed() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Rendering.docx");
	ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.PNG);
	{
		saveOptions.setPageSet(new PageSet(1));
		saveOptions.setImageColorMode(ImageColorMode.BLACK_AND_WHITE);
		saveOptions.setPixelFormat(ImagePixelFormat.FORMAT_1_BPP_INDEXED);
	}
	doc.save("Your Directory Path" + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
}
@Test
public void getJpegPageRange() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Rendering.docx");
	ImageSaveOptions options = new ImageSaveOptions(SaveFormat.JPEG);
	// Setel "PageSet" ke "0" untuk mengonversi hanya halaman pertama dokumen.
	options.setPageSet(new PageSet(0));
	// Ubah kecerahan dan kontras gambar.
	// Keduanya berada pada skala 0-1 dan 0,5 secara default.
	options.setImageBrightness(0.3f);
	options.setImageContrast(0.7f);
	// Ubah resolusi horizontal.
	// Nilai default untuk properti ini adalah 96,0, untuk resolusi 96dpi.
	options.setHorizontalResolution(72f);
	doc.save("Your Directory Path" + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
}
@Test
public static void pageSavingCallback() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Rendering.docx");
	ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.PNG);
	{
		imageSaveOptions.setPageSet(new PageSet(new PageRange(0, doc.getPageCount() - 1)));
		imageSaveOptions.setPageSavingCallback(new HandlePageSavingCallback());
	}
	doc.save("Your Directory Path" + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
}
private static class HandlePageSavingCallback implements IPageSavingCallback
{
	public void pageSaving(PageSavingArgs args)
	{
		args.setPageFileName(MessageFormat.format("Your Directory Path" + "Page_{0}.png", args.getPageIndex()));
	}
```

## Kesimpulan

Anda telah mempelajari cara menyimpan gambar dari dokumen menggunakan Aspose.Words untuk Java. Contoh-contoh ini menunjukkan berbagai opsi penyesuaian untuk penyimpanan gambar, termasuk format, kompresi, dan penggunaan panggilan balik. Jelajahi lebih banyak kemungkinan dengan Aspose.Words untuk kemampuan Java yang canggih.

## FAQ

### Bagaimana cara mengubah format gambar saat menyimpan dengan Aspose.Words untuk Java?

 Anda dapat mengubah format gambar dengan menentukan format yang diinginkan di`ImageSaveOptions` . Misalnya, untuk menyimpan sebagai PNG, gunakan`SaveFormat.PNG` seperti yang ditunjukkan dalam kode:

```java
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.PNG);
```

### Bisakah saya menyesuaikan pengaturan kompresi untuk gambar TIFF?

Ya, Anda dapat menyesuaikan pengaturan kompresi gambar TIFF. Misalnya, untuk menyetel metode kompresi ke CCITT_3, gunakan kode berikut:

```java
saveOptions.setTiffCompression(TiffCompression.CCITT_3);
```

### Bagaimana cara menyimpan halaman tertentu dari dokumen sebagai gambar terpisah?

 Untuk menyimpan halaman tertentu sebagai gambar, gunakan`setPageSet`metode di`ImageSaveOptions` . Misalnya, untuk menyimpan halaman pertama saja, atur`PageSet` ke`new PageSet(0)`.

```java
saveOptions.setPageSet(new PageSet(0)); // Simpan halaman pertama sebagai gambar
```

### Bagaimana cara menerapkan pengaturan khusus pada gambar JPEG saat menyimpan?

Anda dapat menerapkan pengaturan khusus pada gambar JPEG menggunakan`ImageSaveOptions`. Sesuaikan properti seperti kecerahan, kontras, dan resolusi. Misalnya, untuk mengubah kecerahan menjadi 0,3 dan kontras menjadi 0,7, gunakan kode ini:

```java
options.setImageBrightness(0.3f);
options.setImageContrast(0.7f);
```

### Bagaimana cara menggunakan panggilan balik untuk menyesuaikan penyimpanan gambar?

 Untuk menggunakan panggilan balik untuk menyesuaikan penyimpanan gambar, atur`PageSavingCallback` di dalam`ImageSaveOptions` . Buat kelas yang mengimplementasikan`IPageSavingCallback` antarmuka dan menimpa`pageSaving` metode.

```java
imageSaveOptions.setPageSavingCallback(new HandlePageSavingCallback());
```

 Kemudian, buat kelas yang mengimplementasikan`IPageSavingCallback` antarmuka dan sesuaikan nama file dan lokasi di`pageSaving` metode.

```java
private static class HandlePageSavingCallback implements IPageSavingCallback {
    public void pageSaving(PageSavingArgs args) {
        args.setPageFileName(MessageFormat.format("Your Directory Path" + "Page_{0}.png", args.getPageIndex()));
    }
}
```