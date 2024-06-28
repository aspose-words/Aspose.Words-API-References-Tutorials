---
title: Menghasilkan Label Barcode Kustom di Aspose.Words untuk Java
linktitle: Menghasilkan Label Barcode Kustom
second_title: API Pemrosesan Dokumen Java Aspose.Words
description: Hasilkan Label Barcode Kustom di Aspose.Words untuk Java. Pelajari cara membuat solusi kode batang yang dipersonalisasi menggunakan Aspose.Words untuk Java dalam panduan langkah demi langkah ini.
type: docs
weight: 10
url: /id/java/document-conversion-and-export/generating-custom-barcode-labels/
---

## Pengantar Membuat Label Barcode Kustom di Aspose.Words untuk Java

Dalam panduan komprehensif ini, kita akan mempelajari proses pembuatan label barcode khusus menggunakan Aspose.Words untuk Java. Aspose.Words untuk Java adalah API canggih yang memungkinkan pengembang memanipulasi dokumen Word secara terprogram. Salah satu fiturnya yang luar biasa adalah kemampuannya untuk bekerja dengan label barcode, menjadikannya alat yang berharga bagi bisnis dan organisasi yang memerlukan solusi barcode yang disesuaikan.

## Prasyarat

Sebelum kita mendalami detail pembuatan label kode batang khusus, pastikan kita memiliki prasyaratnya:

1. Lingkungan Pengembangan Java: Pastikan Anda telah menginstal Java dan Lingkungan Pengembangan Terpadu (IDE) di sistem Anda.

2.  Aspose.Words for Java: Unduh dan instal Aspose.Words for Java dari[Di Sini](https://releases.aspose.com/words/java/).

3. Pengetahuan Dasar tentang Java: Keakraban dengan pemrograman Java akan sangat membantu karena kita akan menulis kode Java untuk membuat label barcode khusus.

## Membuat Label Barcode Kustom

Sekarang, mari mulai membuat label kode batang khusus menggunakan Aspose.Words untuk Java. Kami akan membagi proses menjadi beberapa langkah dan memberikan cuplikan kode Java untuk setiap langkah.

## Mengatur Tinggi Barcode

Untuk memulai, kita perlu mengatur tinggi barcode kita dalam twips (1/1440 inci). Kami kemudian akan mengonversi nilai ini ke milimeter (mm). Berikut kode untuk mencapai hal ini:

```java
	// Nilai input dalam 1/1440 inci (twips)
	int heightInTwips = tryParseInt(heightInTwipsString);
	if (heightInTwips == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect height - " + heightInTwipsString + ".");
	// Konversikan ke mm
	return (float) (heightInTwips * 25.4 / 1440.0);
```

## Mengubah Warna Gambar Barcode

Selanjutnya kita akan mengubah warna gambar barcode dari Word menjadi Aspose.BarCode. Warna masukan harus dalam format "0xRRGGBB" (heksadesimal). Berikut kode untuk konversinya:

```java
/// <ringkasan>
/// Mengonversi warna gambar barcode dari Word ke Aspose.BarCode.
///</ringkasan>
/// <param nama="inputColor"></param>
/// <pengembalian></pengembalian>
private static Color convertColor(String inputColor) throws Exception {
	// Input harus dari "0x000000" hingga "0xFFFFFF"
	int color = tryParseHex(inputColor.replace("0x", ""));
	if (color == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect color - " + inputColor + ".");
	return new Color((color >> 16), ((color & 0xFF00) >> 8), (color & 0xFF));
}
```

## Mengonversi Faktor Penskalaan Barcode

Sekarang, kita akan mengonversi faktor penskalaan kode batang dari persentase menjadi nilai mengambang. Faktor skala ini menentukan ukuran barcode. Berikut kode untuk konversinya:

```java
/// <ringkasan>
/// Mengonversi faktor penskalaan kode batang dari persen menjadi mengambang.
///</ringkasan>
/// <param nama="scalingFactor"></param>
/// <pengembalian></pengembalian>
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

 Pada langkah ini, kami akan menerapkan`getBarcodeImage` metode, yang menghasilkan gambar barcode berdasarkan parameter yang disediakan. Kami akan menangani berbagai jenis kode batang, mengatur warna, menyesuaikan dimensi, dan banyak lagi. Berikut kode untuk metode ini:

```java
/// <ringkasan>
/// Implementasi metode GetBarCodeImage() untuk antarmuka IBarCodeGenerator.
///</ringkasan>
/// <param nama="parameter"></param>
/// <pengembalian></pengembalian>
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
	
	// Atur teks kode batang
	generator.setCodeText(parameters.getBarcodeValue());
	
	// Atur warna kode batang
	if (parameters.getForegroundColor() != null)
		generator.getParameters().getBarcode().setBarColor(convertColor(parameters.getForegroundColor()));
	if (parameters.getBackgroundColor() != null)
		generator.getParameters().setBackColor(convertColor(parameters.getBackgroundColor()));
	
	// Tetapkan tinggi dan dimensi simbol
	if (parameters.getSymbolHeight() != null)
	{
		generator.getParameters().getImageHeight().setPixels(convertSymbolHeight(parameters.getSymbolHeight()));
		generator.getParameters().setAutoSizeMode(AutoSizeMode.NONE);
	}
	
	//Sesuaikan lokasi teks kode
	generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.NONE);
	if (parameters.getDisplayText())
		generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.BELOW);
	
	// Penyesuaian tambahan untuk kode QR
	final float SCALE = 2.4f; // Faktor penskalaan empiris untuk mengonversi kode batang Word menjadi Aspose.BarCode
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
	
	// Terapkan faktor penskalaan
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

 Pada langkah ini, kami akan menerapkan`getOldBarcodeImage` metode, yang menghasilkan gambar barcode untuk barcode kuno. Di sini, kami akan menangani jenis barcode tertentu, seperti POSTNET. Berikut kode untuk metode ini:

```java
/// <ringkasan>
/// Implementasi metode GetOldBarcodeImage() untuk antarmuka IBarCodeGenerator.
///</ringkasan>
/// <param nama="parameter"></param>
/// <pengembalian></pengembalian>
public BufferedImage getOldBarcodeImage(BarcodeParameters parameters)
{
	if (parameters.getPostalAddress() == null)
		return null;
	BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.POSTNET);
	{
		generator.setCodeText(parameters.getPostalAddress());
	}
	// Jenis hardcode untuk Barcode kuno
	return generator.generateBarCodeImage();
}
```

## Kesimpulan

Pada artikel ini, kami telah menjelajahi proses pembuatan label kode batang khusus menggunakan Aspose.Words untuk Java. Kami membahas langkah-langkah penting, mulai dari mengatur tinggi barcode hingga menerapkan metode pembuatan barcode. Aspose.Words untuk Java memberdayakan pengembang untuk membuat label kode batang yang dinamis dan dapat disesuaikan, menjadikannya alat yang berharga untuk berbagai industri.

## FAQ

### Bagaimana cara menyesuaikan ukuran kode batang yang dihasilkan?

Anda dapat menyesuaikan ukuran kode batang yang dihasilkan dengan mengatur tinggi simbol kode batang dan faktor skala dalam cuplikan kode yang disediakan. Parameter ini memungkinkan Anda mengontrol dimensi kode batang sesuai kebutuhan Anda.

### Bisakah saya mengubah warna barcode?

Ya, Anda dapat mengubah warna barcode dengan menentukan warna latar depan dan latar belakang pada kode tersebut. Kustomisasi ini memungkinkan Anda mencocokkan tampilan kode batang dengan desain dokumen Anda.

### Jenis kode batang apa yang didukung oleh Aspose.Words untuk Java?

Aspose.Words untuk Java mendukung berbagai jenis kode batang, termasuk kode QR, CODE128, CODE39, EAN8, EAN13, UPCA, UPCE, ITF14, dan banyak lagi. Anda dapat memilih jenis barcode yang sesuai dengan kebutuhan aplikasi Anda.

### Bagaimana cara mengintegrasikan kode batang yang dihasilkan ke dalam dokumen Word saya?

Untuk mengintegrasikan kode batang yang dihasilkan ke dalam dokumen Word Anda, Anda dapat menggunakan Aspose.Words untuk kemampuan manipulasi dokumen Java. Anda dapat memasukkan gambar barcode ke dalam dokumen Anda di lokasi yang diinginkan.

### Apakah ada kode contoh yang tersedia untuk penyesuaian lebih lanjut?

 Ya, Anda dapat menemukan cuplikan kode contoh dan dokumentasi tambahan di situs referensi Aspose.Words untuk Java:[Aspose.Words untuk Referensi API Java](https://reference.aspose.com/words/java/).