---
title: Penandaan Air Dokumen dan Pengaturan Halaman
linktitle: Penandaan Air Dokumen dan Pengaturan Halaman
second_title: API Pemrosesan Dokumen Java Aspose.Words
description: Pelajari cara menerapkan tanda air dan mengatur konfigurasi halaman dengan Aspose.Words untuk Java. Panduan komprehensif dengan kode sumber.
type: docs
weight: 13
url: /id/java/document-styling/document-watermarking-page-setup/
---
## Perkenalan

Dalam bidang manipulasi dokumen, Aspose.Words untuk Java berdiri sebagai alat yang ampuh, memungkinkan pengembang untuk memegang kendali atas setiap aspek pemrosesan dokumen. Dalam panduan komprehensif ini, kita akan mempelajari seluk-beluk watermarking dokumen dan pengaturan halaman menggunakan Aspose.Words untuk Java. Baik Anda seorang pengembang berpengalaman atau baru terjun ke dunia pemrosesan dokumen Java, panduan langkah demi langkah ini akan membekali Anda dengan pengetahuan dan kode sumber yang Anda perlukan.

## Penandaan Air Dokumen

### Menambahkan Tanda Air

Menambahkan tanda air ke dokumen bisa menjadi hal yang penting untuk memberi merek atau mengamankan konten Anda. Aspose.Words untuk Java membuat tugas ini mudah. Begini caranya:

```java
// Muat dokumen
Document doc = new Document("document.docx");

// Buat tanda air
Shape watermark = new Shape(doc, ShapeType.TEXT_PLAIN_TEXT);
watermark.getTextPath().setText("Confidential");
watermark.setWidth(300);
watermark.setHeight(100);

// Posisikan tanda air
watermark.setRelativeHorizontalPosition(RelativeHorizontalPosition.PAGE);
watermark.setRelativeVerticalPosition(RelativeVerticalPosition.PAGE);
watermark.setWrapType(WrapType.NONE);
watermark.setVerticalAlignment(VerticalAlignment.CENTER);
watermark.setHorizontalAlignment(HorizontalAlignment.CENTER);

// Masukkan tanda air
doc.getFirstSection().getBody().getFirstParagraph().appendChild(watermark);

// Simpan dokumennya
doc.save("document_with_watermark.docx");
```

### Menyesuaikan Tanda Air

Anda selanjutnya dapat menyesuaikan tanda air dengan menyesuaikan font, ukuran, warna, dan rotasi. Fleksibilitas ini memastikan tanda air Anda cocok dengan gaya dokumen Anda.

## Pengaturan halaman

### Ukuran dan Orientasi Halaman

Pengaturan halaman sangat penting dalam pemformatan dokumen. Aspose.Words untuk Java menawarkan kontrol penuh atas ukuran dan orientasi halaman:

```java
// Muat dokumen
Document doc = new Document("document.docx");

// Atur ukuran halaman menjadi A4
doc.getFirstSection().getPageSetup().setPageWidth(595.0);
doc.getFirstSection().getPageSetup().setPageHeight(842.0);

// Ubah orientasi halaman menjadi lanskap
doc.getFirstSection().getPageSetup().setOrientation(Orientation.LANDSCAPE);

// Simpan dokumen yang diubah
doc.save("formatted_document.docx");
```

### Margin dan Penomoran Halaman

Kontrol yang tepat atas margin dan penomoran halaman sangat penting untuk dokumen profesional. Capai ini dengan Aspose.Words untuk Java:

```java
// Muat dokumen
Document doc = new Document("document.docx");

// Tetapkan margin
doc.getFirstSection().getPageSetup().setLeftMargin(72.0);
doc.getFirstSection().getPageSetup().setRightMargin(72.0);
doc.getFirstSection().getPageSetup().setTopMargin(72.0);
doc.getFirstSection().getPageSetup().setBottomMargin(72.0);

// Aktifkan penomoran halaman
doc.getFirstSection().getPageSetup().setDifferentFirstPageHeaderFooter(true);
HeaderFooter firstPageHeader = doc.getFirstSection().getHeadersFooters().getByHeaderFooterType(HeaderFooterType.HEADER_FIRST);
firstPageHeader.appendParagraph("First Page Header");

// Simpan dokumen yang diformat
doc.save("formatted_document.docx");
```

## FAQ

### Bagaimana cara menghapus tanda air dari dokumen?

Untuk menghapus tanda air dari dokumen, Anda dapat mengulangi bentuk dokumen dan menghapus bentuk yang mewakili tanda air. Berikut cuplikannya:

```java
Document doc = new Document("document_with_watermark.docx");

for (Shape shape : doc.getChildNodes(NodeType.SHAPE, true).<Shape>toArray()) {
    if (shape.getText().contains("Confidential")) {
        shape.remove();
    }
}

doc.save("document_without_watermark.docx");
```

### Bisakah saya menambahkan beberapa tanda air ke satu dokumen?

Ya, Anda dapat menambahkan beberapa tanda air ke dokumen dengan membuat objek Bentuk tambahan dan memposisikannya sesuai kebutuhan.

### Bagaimana cara mengubah ukuran halaman menjadi legal dalam orientasi lanskap?

Untuk mengatur ukuran halaman menjadi legal dalam orientasi lanskap, ubah lebar dan tinggi halaman sebagai berikut:

```java
doc.getFirstSection().getPageSetup().setPageWidth(842.0);
doc.getFirstSection().getPageSetup().setPageHeight(595.0);
```

### Apa font default untuk tanda air?

Font default untuk watermark adalah Calibri dengan ukuran font 36.

### Bagaimana cara menambahkan nomor halaman mulai dari halaman tertentu?

Anda dapat mencapainya dengan mengatur nomor halaman awal di dokumen Anda sebagai berikut:

```java
doc.getFirstSection().getPageSetup().setPageStartingNumber(5);
```

### Bagaimana cara meratakan teks di tengah header atau footer?

Anda dapat meratakan tengah teks di header atau footer dengan menggunakan metode setAlignment pada objek Paragraph di dalam header atau footer.

## Kesimpulan

Dalam panduan ekstensif ini, kami telah menjelajahi seni penandaan air pada dokumen dan pengaturan halaman menggunakan Aspose.Words untuk Java. Berbekal cuplikan dan wawasan kode sumber yang disediakan, kini Anda memiliki alat untuk memanipulasi dan memformat dokumen Anda dengan baik. Aspose.Words untuk Java memberdayakan Anda untuk membuat dokumen bermerek profesional yang disesuaikan dengan spesifikasi Anda.

Menguasai manipulasi dokumen adalah keterampilan berharga bagi pengembang, dan Aspose.Words for Java adalah teman tepercaya Anda dalam perjalanan ini. Mulailah membuat dokumen menakjubkan hari ini!