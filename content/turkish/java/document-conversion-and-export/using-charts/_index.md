---
title: Aspose.Words for Java'da Grafikleri Kullanma
linktitle: Grafikleri Kullanma
second_title: Aspose.Words Java Belge İşleme API'si
description: Aspose.Words for Java'da grafikleri nasıl oluşturup özelleştireceğinizi öğrenin. Veri görselleştirmeye yönelik grafik türlerini, biçimlendirmeyi ve eksen özelliklerini keşfedin.
type: docs
weight: 12
url: /tr/java/document-conversion-and-export/using-charts/
---

## Aspose.Words for Java'da Grafik Kullanımına Giriş

Bu eğitimde Aspose.Words for Java kullanarak grafiklerle nasıl çalışılacağını inceleyeceğiz. Çeşitli grafik türlerini nasıl oluşturacağınızı, eksen özelliklerini nasıl özelleştireceğinizi, veri etiketlerini nasıl biçimlendireceğinizi ve daha fazlasını öğreneceksiniz. Hadi dalalım!

## Çizgi Grafiği Oluşturma

Çizgi grafiği oluşturmak için aşağıdaki kodu kullanın:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.insertChart(ChartType.LINE, 432.0, 252.0);
Chart chart = shape.getChart();
chart.getTitle().setText("Data Labels With Different Number Format");

// Varsayılan oluşturulan seriyi silin.
chart.getSeries().clear();

// Veri ve veri etiketleri içeren bir seri ekleme.
ChartSeries series1 = chart.getSeries().add("Aspose Series 1", 
    new String[] { "Category 1", "Category 2", "Category 3" }, 
    new double[] { 2.5, 1.5, 3.5 });

series1.hasDataLabels(true);
series1.getDataLabels().setShowValue(true);
series1.getDataLabels().get(0).getNumberFormat().setFormatCode("\"$\"#,##0.00");
series1.getDataLabels().get(1).getNumberFormat().setFormatCode("dd/mm/yyyy");
series1.getDataLabels().get(2).getNumberFormat().setFormatCode("0.00%");

// Veya biçim kodunu bir kaynak hücreye bağlayın.
series1.getDataLabels().get(2).getNumberFormat().isLinkedToSource(true);

doc.save("Your Directory Path" + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

## Diğer Grafik Türlerini Oluşturma

Benzer teknikleri kullanarak sütun, alan, kabarcık, dağılım ve daha fazlası gibi farklı türde grafikler oluşturabilirsiniz. Basit bir sütun grafiği eklemenin bir örneğini burada bulabilirsiniz:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.insertChart(ChartType.COLUMN, 432.0, 252.0);
Chart chart = shape.getChart();

// Varsayılan oluşturulan seriyi silin.
chart.getSeries().clear();

// Kategori oluşturma ve veri ekleme.
String[] categories = new String[] { "Category 1", "Category 2" };
chart.getSeries().add("Aspose Series 1", categories, new double[] { 1.0, 2.0 });
chart.getSeries().add("Aspose Series 2", categories, new double[] { 3.0, 4.0 });

doc.save("Your Directory Path" + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

## Eksen Özelliklerini Özelleştirme

Eksen türünü değiştirme, onay işaretlerini ayarlama, etiketleri biçimlendirme ve daha fazlası gibi eksen özelliklerini özelleştirebilirsiniz. Aşağıda XY ekseni özelliklerini tanımlamaya ilişkin bir örnek verilmiştir:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.insertChart(ChartType.AREA, 432.0, 252.0);
Chart chart = shape.getChart();

// Varsayılan seriyi temizleyin ve verilerinizi ekleyin.

ChartAxis xAxis = chart.getAxisX();
ChartAxis yAxis = chart.getAxisY();

// X eksenini tarih yerine kategori olacak şekilde değiştirin.
xAxis.setCategoryType(AxisCategoryType.CATEGORY);
xAxis.setCrosses(AxisCrosses.CUSTOM);
xAxis.setCrossesAt(3.0); // ekseninin görüntü birimleri (yüzlerce) cinsinden ölçülür.
xAxis.setReverseOrder(true);
xAxis.setMajorTickMark(AxisTickMark.CROSS);
xAxis.setMinorTickMark(AxisTickMark.OUTSIDE);
xAxis.setTickLabelOffset(200);

yAxis.setTickLabelPosition(AxisTickLabelPosition.HIGH);
yAxis.setMajorUnit(100.0);
yAxis.setMinorUnit(50.0);
yAxis.getDisplayUnit().setUnit(AxisBuiltInUnit.HUNDREDS);
yAxis.getScaling().setMinimum(new AxisBound(100.0));
yAxis.getScaling().setMaximum(new AxisBound(700.0));

doc.save("Your Directory Path" + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

## Veri Etiketlerini Biçimlendirme

Veri etiketlerini farklı sayı biçimleriyle biçimlendirebilirsiniz. İşte bir örnek:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.insertChart(ChartType.COLUMN, 432.0, 252.0);
Chart chart = shape.getChart();

// Varsayılan seriyi temizleyin ve verilerinizi ekleyin.

chart.getAxisY().getNumberFormat().setFormatCode("#,##0");

doc.save("Your Directory Path" + "WorkingWithCharts.NumberFormatForAxis.docx");
```

## Ek Grafik Özelleştirmeleri

Sınırları, etiketler arasındaki aralık birimlerini ayarlayarak, grafik eksenlerini gizleyerek ve daha fazlasını yaparak grafiklerinizi daha da özelleştirebilirsiniz. Bu seçenekler hakkında daha fazla bilgi edinmek için sağlanan kod parçacıklarını inceleyin.

## Çözüm

Bu eğitimde Aspose.Words for Java kullanarak grafiklerle nasıl çalışılacağını araştırdık. Çeşitli grafik türlerini nasıl oluşturacağınızı, eksen özelliklerini özelleştirmeyi, veri etiketlerini biçimlendirmeyi ve daha fazlasını öğrendiniz. Aspose.Words for Java, belgelerinize verilerin görsel temsillerini eklemek için güçlü araçlar sağlayarak bilgileri sunma şeklinizi geliştirir.

## SSS'ler

### Bir grafiğe birden fazla seriyi nasıl ekleyebilirim?

 kullanarak bir grafiğe birden fazla seri ekleyebilirsiniz.`chart.getSeries().add()` yöntem. Seri adını, kategorileri ve veri değerlerini belirttiğinizden emin olun.

### Veri etiketlerini özel sayı biçimleriyle nasıl biçimlendirebilirim?

Veri etiketlerini şuraya erişerek biçimlendirebilirsiniz:`DataLabels` bir serinin özellikleri ve kullanılarak istenilen format kodunun ayarlanması`getNumberFormat().setFormatCode()`.

### Bir grafikte eksen özelliklerini nasıl özelleştiririm?

 Yazım, onay işaretleri, etiketler ve daha fazlası gibi eksen özelliklerini,`ChartAxis` gibi özellikler`setCategoryType()`, `setCrosses()` , Ve`setMajorTickMark()`.

### Dağılım veya alan grafikleri gibi diğer grafik türlerini nasıl oluşturabilirim?

 Uygun grafik türlerini belirterek çeşitli grafik türleri oluşturabilirsiniz.`ChartType` kullanarak grafiği eklerken`builder.insertChart(ChartType.TYPE, width, height)`.

### Bir grafik eksenini nasıl gizleyebilirim?

 ayarlayarak bir grafik eksenini gizleyebilirsiniz.`setHidden(true)` eksenin özelliği.