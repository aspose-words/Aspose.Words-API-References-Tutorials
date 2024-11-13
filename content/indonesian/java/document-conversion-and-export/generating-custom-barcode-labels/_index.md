---
title: Membuat Label Barcode Kustom di Aspose.Words untuk Java
linktitle: Membuat Label Barcode Kustom
second_title: API Pemrosesan Dokumen Java Aspose.Words
description: Buat Label Barcode Kustom di Aspose.Words untuk Java. Pelajari cara membuat solusi barcode yang dipersonalisasi menggunakan Aspose.Words untuk Java dalam panduan langkah demi langkah ini.
type: docs
weight: 10
url: /id/java/document-conversion-and-export/generating-custom-barcode-labels/
---

## Pengantar Pembuatan Label Barcode Kustom di Aspose.Words untuk Java

Dalam panduan lengkap ini, kita akan membahas proses pembuatan label kode batang kustom menggunakan Aspose.Words untuk Java. Aspose.Words untuk Java adalah API canggih yang memungkinkan pengembang untuk memanipulasi dokumen Word secara terprogram. Salah satu fiturnya yang luar biasa adalah kemampuan untuk bekerja dengan label kode batang, menjadikannya alat yang berharga bagi bisnis dan organisasi yang memerlukan solusi kode batang yang disesuaikan.

## Prasyarat

Sebelum kita menyelami detail pembuatan label kode batang khusus, mari pastikan kita memiliki prasyarat yang diperlukan:

1. Lingkungan Pengembangan Java: Pastikan Anda telah menginstal Java dan Lingkungan Pengembangan Terpadu (IDE) di sistem Anda.

2.  Aspose.Words untuk Java: Unduh dan instal Aspose.Words untuk Java dari[Di Sini](https://releases.aspose.com/words/java/).

3. Pengetahuan Dasar Java: Keakraban dengan pemrograman Java akan membantu karena kita akan menulis kode Java untuk membuat label kode batang khusus.

## Membuat Label Barcode Kustom

Sekarang, mari kita mulai membuat label kode batang khusus menggunakan Aspose.Words untuk Java. Kita akan membagi proses menjadi beberapa langkah dan menyediakan cuplikan kode Java untuk setiap langkah.

## Mengatur Tinggi Barcode

Untuk memulai, kita perlu mengatur tinggi kode batang dalam twips (1/1440 inci). Kita kemudian akan mengonversi nilai ini ke milimeter (mm). Berikut kode untuk melakukannya:

```java
	// Nilai masukan dalam 1/1440 inci (twips)
	int heightInTwips = tryParseInt(heightInTwipsString);
	if (heightInTwips == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect height - " + heightInTwipsString + ".");
	// Konversi ke mm
	return (float) (heightInTwips * 25.4 / 1440.0);
```

## Mengubah Warna Gambar Barcode

Selanjutnya, kita akan mengonversi warna gambar kode batang dari Word ke Aspose.BarCode. Warna input harus dalam format "0xRRGGBB" (heksadesimal). Berikut kode untuk konversi:

```java
/// <ringkasan>
/// Mengubah warna gambar kode batang dari Word ke Aspose.BarCode.
/// </ringkasan>
/// <param nama="warnainput"></param>
/// <mengembalikan></mengembalikan>
private static Color convertColor(String inputColor) throws Exception {
	// Input harus dari "0x000000" hingga "0xFFFFFF"
	int color = tryParseHex(inputColor.replace("0x", ""));
	if (color == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect color - " + inputColor + ".");
	return new Color((color >> 16), ((color & 0xFF00) >> 8), (color & 0xFF));
}
```

## Mengonversi Faktor Skala Barcode

Sekarang, kita akan mengonversi faktor skala kode batang dari persentase ke nilai float. Faktor skala ini menentukan ukuran kode batang. Berikut kode untuk konversi:

```java
/// <ringkasan>
/// Mengubah faktor skala kode batang dari persen menjadi float.
/// </ringkasan>
/// <param nama="faktorskala"></param>
/// <mengembalikan></mengembalikan>
private static float convertScalingFactor(String scalingFactor) throws Exception {
	boolean isParsed = false;
	int percent = tryParseInt(scalingFactor);
	if (percent != Integer.MIN_VALUE && percent >= 10 && percent <= 10000)
		isParsed = true;
	if (!isParsed)
		throw new Exception("Error! Incorrect scaling factor - " + scalingFactor + ".");
	return percent / 100.0f;
}
```

## Menerapkan Metode GetBarCodeImage()

 Pada langkah ini, kita akan menerapkan`getBarcodeImage`metode, yang menghasilkan gambar kode batang berdasarkan parameter yang diberikan. Kita akan menangani berbagai jenis kode batang, mengatur warna, menyesuaikan dimensi, dan banyak lagi. Berikut kode untuk metode ini:

```java
/// <ringkasan>
/// Implementasi metode GetBarCodeImage() untuk antarmuka IBarCodeGenerator.
/// </ringkasan>
/// <param nama="parameter"></param>
/// <mengembalikan></mengembalikan>
public BufferedImage getBarcodeImage(BarcodeParameters parameters) throws Exception {
	// Periksa apakah jenis dan nilai kode batang disediakan
	if (parameters.getBarcodeType() == null || parameters.getBarcodeValue() == null)
		return null;
	
	// Buat BarcodeGenerator berdasarkan jenis barcode
	BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.QR);
	String type = parameters.getBarcodeType().toUpperCase();
	switch (type)
	{
		case "QR":
			generator = new BarcodeGenerator(EncodeTypes.QR);
			break;
		// Tangani jenis kode batang lainnya di sini
	}
	
	// Mengatur teks kode batang
	generator.setCodeText(parameters.getBarcodeValue());
	
	// Mengatur warna kode batang
	if (parameters.getForegroundColor() != null)
		generator.getParameters().getBarcode().setBarColor(convertColor(parameters.getForegroundColor()));
	if (parameters.getBackgroundColor() != null)
		generator.getParameters().setBackColor(convertColor(parameters.getBackgroundColor()));
	
	// Atur tinggi dan dimensi simbol
	if (parameters.getSymbolHeight() != null)
	{
		generator.getParameters().getImageHeight().setPixels(convertSymbolHeight(parameters.getSymbolHeight()));
		generator.getParameters().setAutoSizeMode(AutoSizeMode.NONE);
	}
	
	// Sesuaikan lokasi teks kode
	generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.NONE);
	if (parameters.getDisplayText())
		generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.BELOW);
	
	// Penyesuaian tambahan untuk kode QR
	final float SCALE = 2.4f; // Faktor skala empiris untuk mengonversi kode batang Word ke Aspose.BarCode
	float xdim = 1.0f;
	if (generator.getBarcodeType().equals(EncodeTypes.QR))
	{
		generator.getParameters().setAutoSizeMode(AutoSizeMode.NEAREST);
		generator.getParameters().getImageWidth().setInches(generator.getParameters().getImageWidth().getInches() * SCALE);
		generator.getParameters().getImageHeight().setInches(generator.getParameters().getImageWidth().getInches());
		xdim = generator.getParameters().getImageHeight().getInches() / 25;
		generator.getParameters().getBarcode().getXDimension().setInches(xdim);
		generator.getParameters().getBarcode().getBarHeight().setInches(xdim);
	}
	
	// Terapkan faktor skala
	if (parameters.getScalingFactor() != null)
	{
		float scalingFactor = convertScalingFactor(parameters.getScalingFactor());
		generator.getParameters().getImageHeight().setInches(generator.getParameters().getImageHeight().getInches() * scalingFactor);
		if (generator.getBarcodeType().equals(EncodeTypes.QR))
		{
			generator.getParameters().getImageWidth().setInches(generator.getParameters().getImageHeight().getInches());
			generator.getParameters().getBarcode().getXDimension().setInches(xdim * scalingFactor);
			generator.getParameters().getBarcode().getBarHeight().setInches(xdim * scalingFactor);
		}
		generator.getParameters().setAutoSizeMode(AutoSizeMode.NONE);
	}
	
	// Hasilkan dan kembalikan gambar kode batang
	return generator.generateBarCodeImage();
}
```

## Menerapkan Metode GetOldBarcodeImage()

 Pada langkah ini, kita akan menerapkan`getOldBarcodeImage`metode, yang menghasilkan gambar kode batang untuk kode batang lama. Di sini, kita akan menangani jenis kode batang tertentu, seperti POSTNET. Berikut kode untuk metode ini:

```java
/// <ringkasan>
/// Implementasi metode GetOldBarcodeImage() untuk antarmuka IBarCodeGenerator.
/// </ringkasan>
/// <param nama="parameter"></param>
/// <mengembalikan></mengembalikan>
public BufferedImage getOldBarcodeImage(BarcodeParameters parameters)
{
	if (parameters.getPostalAddress() == null)
		return null;
	BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.POSTNET);
	{
		generator.setCodeText(parameters.getPostalAddress());
	}
	// Jenis kode keras untuk Barcode kuno
	return generator.generateBarCodeImage();
}
```

## Kesimpulan

Dalam artikel ini, kami telah menjelajahi proses pembuatan label kode batang kustom menggunakan Aspose.Words untuk Java. Kami membahas langkah-langkah penting, mulai dari pengaturan tinggi kode batang hingga penerapan metode untuk pembuatan kode batang. Aspose.Words untuk Java memberdayakan pengembang untuk membuat label kode batang yang dinamis dan kustom, menjadikannya alat yang berharga untuk berbagai industri.

## Pertanyaan yang Sering Diajukan

### Bagaimana cara menyesuaikan ukuran kode batang yang dihasilkan?

Anda dapat menyesuaikan ukuran kode batang yang dihasilkan dengan mengatur tinggi simbol dan faktor skala kode batang dalam cuplikan kode yang disediakan. Parameter ini memungkinkan Anda untuk mengontrol dimensi kode batang sesuai kebutuhan Anda.

### Bisakah saya mengubah warna kode batang?

Ya, Anda dapat mengubah warna kode batang dengan menentukan warna latar depan dan latar belakang dalam kode. Kustomisasi ini memungkinkan Anda untuk menyesuaikan tampilan kode batang dengan desain dokumen Anda.

### Jenis kode batang apa yang didukung oleh Aspose.Words untuk Java?

Aspose.Words untuk Java mendukung berbagai jenis kode batang, termasuk kode QR, CODE128, CODE39, EAN8, EAN13, UPCA, UPCE, ITF14, dan banyak lagi. Anda dapat memilih jenis kode batang yang sesuai dengan kebutuhan aplikasi Anda.

### Bagaimana cara mengintegrasikan kode batang yang dihasilkan ke dokumen Word saya?

Untuk mengintegrasikan kode batang yang dihasilkan ke dalam dokumen Word, Anda dapat menggunakan kemampuan manipulasi dokumen Aspose.Words for Java. Anda dapat menyisipkan gambar kode batang ke dalam dokumen di lokasi yang diinginkan.

### Apakah ada kode contoh yang tersedia untuk penyesuaian lebih lanjut?

 Ya, Anda dapat menemukan contoh potongan kode dan dokumentasi tambahan di situs referensi Aspose.Words untuk Java:[Referensi API Aspose.Words untuk Java](https://reference.aspose.com/words/java/).