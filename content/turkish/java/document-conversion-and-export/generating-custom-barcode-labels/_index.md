---
title: Aspose.Words for Java'da Özel Barkod Etiketleri Oluşturma
linktitle: Özel Barkod Etiketleri Oluşturma
second_title: Aspose.Words Java Belge İşleme API'si
description: Aspose.Words for Java'da Özel Barkod Etiketleri oluşturun. Bu adım adım kılavuzdan Aspose.Words for Java'yı kullanarak kişiselleştirilmiş barkod çözümlerini nasıl oluşturacağınızı öğrenin.
type: docs
weight: 10
url: /tr/java/document-conversion-and-export/generating-custom-barcode-labels/
---

## Aspose.Words for Java'da Özel Barkod Etiketleri Oluşturmaya Giriş

Bu kapsamlı kılavuzda Aspose.Words for Java'yı kullanarak özel barkod etiketleri oluşturma sürecini ayrıntılı olarak ele alacağız. Aspose.Words for Java, geliştiricilerin Word belgelerini programlı olarak değiştirmesine olanak tanıyan güçlü bir API'dir. Dikkate değer özelliklerinden biri, barkod etiketleriyle çalışabilmesidir; bu da onu özelleştirilmiş barkod çözümlerine ihtiyaç duyan işletmeler ve kuruluşlar için değerli bir araç haline getirir.

## Önkoşullar

Özel barkod etiketleri oluşturmanın ayrıntılarına dalmadan önce ön koşulların yerine getirildiğinden emin olalım:

1. Java Geliştirme Ortamı: Sisteminizde Java ve Entegre Geliştirme Ortamının (IDE) kurulu olduğundan emin olun.

2.  Aspose.Words for Java: Aspose.Words for Java'yı şu adresten indirip yükleyin:[Burada](https://releases.aspose.com/words/java/).

3. Temel Java Bilgisi: Özel barkod etiketleri oluşturmak için Java kodu yazacağımız için Java programlamaya aşina olmak faydalı olacaktır.

## Özel Barkod Etiketleri Oluşturma

Şimdi Aspose.Words for Java'yı kullanarak özel barkod etiketleri oluşturmaya başlayalım. Süreci adımlara ayıracağız ve her adım için Java kod parçacıkları sağlayacağız.

## Barkod Yüksekliğini Ayarlama

Başlamak için barkodumuzun yüksekliğini twips (1/1440 inç) cinsinden ayarlamamız gerekiyor. Daha sonra bu değeri milimetreye (mm) dönüştüreceğiz. İşte bunu başarmak için kod:

```java
	// Giriş değeri 1/1440 inç (twip) cinsindendir
	int heightInTwips = tryParseInt(heightInTwipsString);
	if (heightInTwips == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect height - " + heightInTwipsString + ".");
	// mm'ye dönüştür
	return (float) (heightInTwips * 25.4 / 1440.0);
```

## Barkod Görüntü Rengini Dönüştürme

Daha sonra barkod görsel rengini Word'den Aspose.BarCode'a dönüştüreceğiz. Giriş rengi "0xRRGGBB" (onaltılık) biçiminde olmalıdır. İşte dönüşümün kodu:

```java
/// <özet>
/// Barkod görüntü rengini Word'den Aspose.BarCode'a dönüştürür.
/// </özet>
/// <param name="inputColor"></param>
/// <dönüşler></dönüşler>
private static Color convertColor(String inputColor) throws Exception {
	// Giriş "0x000000" ila "0xFFFFFF" arasında olmalıdır
	int color = tryParseHex(inputColor.replace("0x", ""));
	if (color == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect color - " + inputColor + ".");
	return new Color((color >> 16), ((color & 0xFF00) >> 8), (color & 0xFF));
}
```

## Barkod Ölçeklendirme Faktörünü Dönüştürme

Şimdi barkod ölçeklendirme faktörünü yüzdeden kayan değere dönüştüreceğiz. Bu ölçeklendirme faktörü barkodun boyutunu belirler. İşte dönüşümün kodu:

```java
/// <özet>
/// Barkod ölçeklendirme faktörünü yüzdeden kayan noktaya dönüştürür.
/// </özet>
/// <param name="scalingFactor"></param>
/// <dönüşler></dönüşler>
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

## GetBarCodeImage() Yöntemini Uygulama

 Bu adımda, uygulayacağız`getBarcodeImage` Sağlanan parametrelere göre barkod görüntüsünü oluşturan yöntem. Farklı barkod türlerini ele alacağız, renkleri ayarlayacağız, boyutları ayarlayacağız ve daha fazlasını yapacağız. İşte bu yöntemin kodu:

```java
/// <özet>
/// IBarCodeGenerator arayüzü için GetBarCodeImage() yönteminin uygulanması.
/// </özet>
/// <param name="parametreler"></param>
/// <dönüşler></dönüşler>
public BufferedImage getBarcodeImage(BarcodeParameters parameters) throws Exception {
	// Barkod türü ve değerinin sağlanıp sağlanmadığını kontrol edin
	if (parameters.getBarcodeType() == null || parameters.getBarcodeValue() == null)
		return null;
	
	// Barkod türüne göre bir BarcodeGenerator oluşturun
	BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.QR);
	String type = parameters.getBarcodeType().toUpperCase();
	switch (type)
	{
		case "QR":
			generator = new BarcodeGenerator(EncodeTypes.QR);
			break;
		// Diğer barkod türlerini burada işleyin
	}
	
	// Barkod metnini ayarlayın
	generator.setCodeText(parameters.getBarcodeValue());
	
	// Barkod renklerini ayarlama
	if (parameters.getForegroundColor() != null)
		generator.getParameters().getBarcode().setBarColor(convertColor(parameters.getForegroundColor()));
	if (parameters.getBackgroundColor() != null)
		generator.getParameters().setBackColor(convertColor(parameters.getBackgroundColor()));
	
	// Sembol yüksekliğini ve boyutlarını ayarlayın
	if (parameters.getSymbolHeight() != null)
	{
		generator.getParameters().getImageHeight().setPixels(convertSymbolHeight(parameters.getSymbolHeight()));
		generator.getParameters().setAutoSizeMode(AutoSizeMode.NONE);
	}
	
	//Kod metni konumunu özelleştirin
	generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.NONE);
	if (parameters.getDisplayText())
		generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.BELOW);
	
	// QR kodları için ek ayarlamalar
	final float SCALE = 2.4f; // Word barkodunu Aspose.BarCode'a dönüştürmek için ampirik ölçeklendirme faktörü
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
	
	// Ölçeklendirme faktörünü uygula
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
	
	// Barkod görüntüsünü oluşturun ve döndürün
	return generator.generateBarCodeImage();
}
```

## GetOldBarcodeImage() Yöntemini Uygulama

 Bu adımda, uygulayacağız`getOldBarcodeImage` eski moda barkodlar için barkod görüntüleri üreten yöntem. Burada POSTNET gibi belirli bir barkod türünü ele alacağız. İşte bu yöntemin kodu:

```java
/// <özet>
/// IBarCodeGenerator arayüzü için GetOldBarcodeImage() yönteminin uygulanması.
/// </özet>
/// <param name="parametreler"></param>
/// <dönüşler></dönüşler>
public BufferedImage getOldBarcodeImage(BarcodeParameters parameters)
{
	if (parameters.getPostalAddress() == null)
		return null;
	BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.POSTNET);
	{
		generator.setCodeText(parameters.getPostalAddress());
	}
	// Eski moda Barkod için sabit kod türü
	return generator.generateBarCodeImage();
}
```

## Çözüm

Bu makalede Aspose.Words for Java'yı kullanarak özel barkod etiketleri oluşturma sürecini inceledik. Barkod yüksekliğinin ayarlanmasından barkod oluşturma yöntemlerinin uygulanmasına kadar temel adımları ele aldık. Aspose.Words for Java, geliştiricilere dinamik ve özelleştirilmiş barkod etiketleri oluşturma olanağı vererek onu çeşitli endüstriler için değerli bir araç haline getiriyor.

## SSS'ler

### Oluşturulan barkodun boyutunu nasıl ayarlayabilirim?

Sağlanan kod parçacıklarında barkodun sembol yüksekliğini ve ölçeklendirme faktörünü ayarlayarak oluşturulan barkodun boyutunu ayarlayabilirsiniz. Bu parametreler barkodun boyutlarını ihtiyaçlarınıza göre kontrol etmenizi sağlar.

### Barkodun rengini değiştirebilir miyim?

Evet, kodda ön plan ve arka plan renklerini belirterek barkodun renklerini değiştirebilirsiniz. Bu özelleştirme, barkodun görünümünü belgenizin tasarımıyla eşleştirmenize olanak tanır.

### Aspose.Words for Java hangi barkod türlerini destekliyor?

Aspose.Words for Java, QR kodları, CODE128, CODE39, EAN8, EAN13, UPCA, UPCE, ITF14 ve daha fazlası dahil olmak üzere çeşitli barkod türlerini destekler. Uygulamanızın ihtiyaçlarına uygun barkod tipini seçebilirsiniz.

### Oluşturulan barkodu Word belgeme nasıl entegre ederim?

Oluşturulan barkodu Word belgenize entegre etmek için Aspose.Words for Java'nın belge işleme yeteneklerini kullanabilirsiniz. Barkod görselini belgenizin istediğiniz yerine ekleyebilirsiniz.

### Daha fazla özelleştirme için herhangi bir örnek kod var mı?

 Evet, Aspose.Words for Java'nın referans sitesinde örnek kod parçacıkları ve ek belgeler bulabilirsiniz:[Aspose.Words for Java API Referansı](https://reference.aspose.com/words/java/).