---
title: Menggunakan Opsi Muat di Aspose.Words untuk Java
linktitle: Menggunakan Opsi Muat
second_title: API Pemrosesan Dokumen Java Aspose.Words
description: Menguasai Opsi Muat di Aspose.Words untuk Java. Sesuaikan pemuatan dokumen, tangani enkripsi, konversi bentuk, atur versi Word, dan lainnya untuk pemrosesan dokumen Java yang efisien.
type: docs
weight: 11
url: /id/java/document-loading-and-saving/using-load-options/
---

## Pengantar Bekerja dengan Opsi Muat di Aspose.Words untuk Java

Dalam tutorial ini, kita akan mempelajari cara bekerja dengan Load Options di Aspose.Words untuk Java. Opsi Muat memungkinkan Anda menyesuaikan cara dokumen dimuat dan diproses. Kami akan membahas berbagai skenario, termasuk memperbarui bidang kotor, memuat dokumen terenkripsi, mengonversi bentuk ke Office Math, mengatur versi MS Word, menentukan folder sementara, menangani peringatan, dan mengonversi metafile ke PNG. Mari selami langkah demi langkah.

## Perbarui Bidang Kotor

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setUpdateDirtyFields(true);

Document doc = new Document("Your Directory Path" + "Dirty field.docx", loadOptions);
doc.save("Your Directory Path" + "WorkingWithLoadOptions.UpdateDirtyFields.docx");
```

 Cuplikan kode ini menunjukkan cara memperbarui bidang kotor dalam dokumen. Itu`setUpdateDirtyFields(true)` metode ini digunakan untuk memastikan bahwa bidang kotor diperbarui selama pemuatan dokumen.

## Muat Dokumen Terenkripsi

```java
@Test
public void loadEncryptedDocument() throws Exception {
    Document doc = new Document("Your Directory Path" + "Encrypted.docx", new LoadOptions("docPassword"));
    doc.save("Your Directory Path" + "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt", new OdtSaveOptions("newPassword"));
}
```

 Di sini, kami memuat dokumen terenkripsi menggunakan kata sandi. Itu`LoadOptions` konstruktor menerima kata sandi dokumen, dan Anda juga dapat menentukan kata sandi baru saat menyimpan dokumen menggunakan`OdtSaveOptions`.

## Ubah Bentuk menjadi Matematika Office

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setConvertShapeToOfficeMath(true);

Document doc = new Document("Your Directory Path" + "Office math.docx", loadOptions);
doc.save("Your Directory Path" + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx", SaveFormat.DOCX);
```

 Kode ini menunjukkan cara mengonversi bentuk menjadi objek Office Math selama pemuatan dokumen. Itu`setConvertShapeToOfficeMath(true)`metode memungkinkan konversi ini.

## Atur Versi MS Word

```java
@Test
public void setMsWordVersion() throws Exception {
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.setMswVersion(MsWordVersion.WORD_2010);

    Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
    doc.save("Your Directory Path" + "WorkingWithLoadOptions.SetMsWordVersion.docx");
}
```

 Anda dapat menentukan versi MS Word untuk memuat dokumen. Dalam contoh ini, kami menyetel versi ke Microsoft Word 2010 menggunakan`setMswVersion`.

## Gunakan Folder Sementara

```java
@Test
public void useTempFolder() throws Exception {
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.setTempFolder("Your Directory Path");

    Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
}
```

 Dengan mengatur folder sementara menggunakan`setTempFolder`, Anda dapat mengontrol lokasi penyimpanan file sementara selama pemrosesan dokumen.

## Peringatan Panggilan Balik

```java
@Test
public void warningCallback() throws Exception {
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.setWarningCallback(new DocumentLoadingWarningCallback());

    Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
}

public static class DocumentLoadingWarningCallback implements IWarningCallback {
    public void warning(WarningInfo info) {
        // Tangani peringatan yang muncul selama pemuatan dokumen.
        System.out.println(MessageFormat.format("WARNING: {0}, source: {1}", info.getWarningType(), info.getSource()));
        System.out.println(MessageFormat.format("\tDescription: {0}", info.getDescription()));
    }
}
```

Kode ini menunjukkan cara menyiapkan panggilan balik peringatan untuk menangani peringatan selama pemuatan dokumen. Anda dapat menyesuaikan perilaku aplikasi Anda saat peringatan muncul.

## Konversi Metafile ke PNG

```java
@Test
public void convertMetafilesToPng() throws Exception {
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.setConvertMetafilesToPng(true);

    Document doc = new Document("Your Directory Path" + "WMF with image.docx", loadOptions);
}
```

 Untuk mengonversi metafile (misalnya WMF) ke gambar PNG selama pemuatan dokumen, Anda dapat menggunakan`setConvertMetafilesToPng(true)` metode.

## Kode Sumber Lengkap Untuk Bekerja dengan Opsi Muat di Aspose.Words untuk Java

```java
public void updateDirtyFields() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setUpdateDirtyFields(true);
	}
	Document doc = new Document("Your Directory Path" + "Dirty field.docx", loadOptions);
	doc.save("Your Directory Path" + "WorkingWithLoadOptions.UpdateDirtyFields.docx");
}
@Test
public void loadEncryptedDocument() throws Exception {
	Document doc = new Document("Your Directory Path" + "Encrypted.docx", new LoadOptions("docPassword"));
	doc.save("Your Directory Path" + "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt", new OdtSaveOptions("newPassword"));
}
@Test
public void convertShapeToOfficeMath() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setConvertShapeToOfficeMath(true);
	}
	Document doc = new Document("Your Directory Path" + "Office math.docx", loadOptions);
	doc.save("Your Directory Path" + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx", SaveFormat.DOCX);
}
@Test
public void setMsWordVersion() throws Exception {
	// Buat objek LoadOptions baru, yang akan memuat dokumen sesuai spesifikasi MS Word 2019 secara default
	// dan ubah versi pemuatan ke Microsoft Word 2010.
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setMswVersion(MsWordVersion.WORD_2010);
	}
	Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
	doc.save("Your Directory Path" + "WorkingWithLoadOptions.SetMsWordVersion.docx");
}
@Test
public void useTempFolder() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setTempFolder("Your Directory Path");
	}
	Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
}
@Test
public void warningCallback() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setWarningCallback(new DocumentLoadingWarningCallback());
	}
	Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
}
public static class DocumentLoadingWarningCallback implements IWarningCallback {
	public void warning(WarningInfo info) {
		//Mencetak peringatan dan rinciannya saat muncul selama pemuatan dokumen.
		System.out.println(MessageFormat.format("WARNING: {0}, source: {1}", info.getWarningType(), info.getSource()));
		System.out.println(MessageFormat.format("\tDescription: {0}", info.getDescription()));
	}
}
@Test
public void convertMetafilesToPng() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setConvertMetafilesToPng(true);
	}
	Document doc = new Document("Your Directory Path" + "WMF with image.docx", loadOptions);
}
@Test
public void loadChm() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setEncoding(Charset.forName("windows-1251"));
	}
	Document doc = new Document("Your Directory Path" + "HTML help.chm", loadOptions);
}
```

## Kesimpulan

Dalam tutorial ini, kami telah mempelajari berbagai aspek bekerja dengan Load Options di Aspose.Words untuk Java. Opsi Pemuatan memainkan peran penting dalam menyesuaikan cara dokumen dimuat dan diproses, memungkinkan Anda menyesuaikan pemrosesan dokumen dengan kebutuhan spesifik Anda. Mari kita rekap poin-poin penting yang dibahas dalam panduan ini:

## FAQ

### Bagaimana cara menangani peringatan saat memuat dokumen?

 Anda dapat mengatur panggilan balik peringatan seperti yang ditunjukkan di`warningCallback()` metode di atas. Sesuaikan`DocumentLoadingWarningCallback` kelas untuk menangani peringatan sesuai dengan kebutuhan aplikasi Anda.

### Bisakah saya mengonversi bentuk menjadi objek Office Math saat memuat dokumen?

 Ya, Anda bisa mengonversi bentuk menjadi objek Office Math dengan menggunakan`loadOptions.setConvertShapeToOfficeMath(true)`.

### Bagaimana cara menentukan versi MS Word untuk memuat dokumen?

 Menggunakan`loadOptions.setMswVersion(MsWordVersion.WORD_2010)` untuk menentukan versi MS Word untuk memuat dokumen.

###  Apa tujuan dari`setTempFolder` method in Load Options?

 Itu`setTempFolder`metode ini memungkinkan Anda menentukan folder tempat file sementara disimpan selama pemrosesan dokumen.