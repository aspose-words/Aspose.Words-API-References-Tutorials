---
title: Aspose.Words for Java'da Özel Barkod Etiketleri Oluşturma
linktitle: Özel Barkod Etiketleri Oluşturma
second_title: Aspose.Words Java Belge İşleme API'si
description: Aspose.Words for Java'da Özel Barkod Etiketleri Oluşturun. Bu adım adım kılavuzda Aspose.Words for Java kullanarak kişiselleştirilmiş barkod çözümlerinin nasıl oluşturulacağını öğrenin.
type: docs
weight: 10
url: /tr/java/document-conversion-and-export/generating-custom-barcode-labels/
---

## Aspose.Words for Java'da Özel Barkod Etiketleri Oluşturmaya Giriş

Bu kapsamlı kılavuzda, Aspose.Words for Java kullanarak özel barkod etiketleri oluşturma sürecini inceleyeceğiz. Aspose.Words for Java, geliştiricilerin Word belgelerini programatik olarak düzenlemelerine olanak tanıyan güçlü bir API'dir. Dikkat çekici özelliklerinden biri, barkod etiketleriyle çalışabilme yeteneğidir ve bu da onu özelleştirilmiş barkod çözümlerine ihtiyaç duyan işletmeler ve kuruluşlar için değerli bir araç haline getirir.

## Ön koşullar

Özel barkod etiketlerinin oluşturulmasının ayrıntılarına dalmadan önce, ön koşulların yerinde olduğundan emin olalım:

1. Java Geliştirme Ortamı: Sisteminizde Java ve Entegre Geliştirme Ortamı'nın (IDE) yüklü olduğundan emin olun.

2.  Aspose.Words for Java: Aspose.Words for Java'yı indirin ve yükleyin[Burada](https://releases.aspose.com/words/java/).

3. Temel Java Bilgisi: Özel barkod etiketleri oluşturmak için Java kodu yazacağımızdan, Java programlamaya aşinalık faydalı olacaktır.

## Özel Barkod Etiketleri Oluşturma

Şimdi, Aspose.Words for Java kullanarak özel barkod etiketleri oluşturmaya başlayalım. Süreci adımlara böleceğiz ve her adım için Java kod parçacıkları sağlayacağız.

## Barkod Yüksekliğini Ayarlama

Başlamak için barkodumuzun yüksekliğini twip (1/1440 inç) cinsinden ayarlamamız gerekiyor. Daha sonra bu değeri milimetreye (mm) dönüştüreceğiz. Bunu başarmak için kod şu şekilde:

```java
	// Giriş değeri 1/1440 inç (twip) cinsindendir
	int heightInTwips = tryParseInt(heightInTwipsString);
	if (heightInTwips == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect height - " + heightInTwipsString + ".");
	// mm'ye dönüştür
	return (float) (heightInTwips * 25.4 / 1440.0);
```

## Barkod Görüntü Rengini Dönüştürme

Sonra, barkod görüntü rengini Word'den Aspose.BarCode'a dönüştüreceğiz. Giriş rengi "0xRRGGBB" (onaltılık) biçiminde olmalıdır. İşte dönüştürme için kod:

```java
/// <özet>
/// Barkod görüntü rengini Word'den Aspose.BarCode'a dönüştürür.
/// </özet>
/// <param adı="inputColor"></param>
/// <döndürür></döndürür>
private static Color convertColor(String inputColor) throws Exception {
	// Giriş "0x000000" ile "0xFFFFFF" arasında olmalıdır
	int color = tryParseHex(inputColor.replace("0x", ""));
	if (color == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect color - " + inputColor + ".");
	return new Color((color >> 16), ((color & 0xFF00) >> 8), (color & 0xFF));
}
```

## Barkod Ölçekleme Faktörünü Dönüştürme

Şimdi barkod ölçekleme faktörünü yüzdeden kayan nokta değerine dönüştüreceğiz. Bu ölçekleme faktörü barkodun boyutunu belirler. İşte dönüştürme için kod:

```java
/// <özet>
/// Barkod ölçekleme faktörünü yüzdeden kayan noktaya dönüştürür.
/// </özet>
/// <param name="ölçeklemeFaktörü"></param>
/// <döndürür></döndürür>
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

## GetBarCodeImage() Yönteminin Uygulanması

 Bu adımda, şunu uygulayacağız:`getBarcodeImage`sağlanan parametrelere göre barkod görüntüsünü üreten yöntem. Farklı barkod türlerini ele alacağız, renkleri belirleyeceğiz, boyutları ayarlayacağız ve daha fazlasını yapacağız. İşte bu yöntemin kodu:

```java
/// <özet>
/// IBarCodeGenerator arayüzü için GetBarCodeImage() metodunun uygulanması.
/// </özet>
/// <param name="parametreler"></param>
/// <döndürür></döndürür>
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
	
	// Barkod renklerini ayarla
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
	
	// Kod metin konumunu özelleştir
	generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.NONE);
	if (parameters.getDisplayText())
		generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.BELOW);
	
	// QR kodları için ek ayarlamalar
	final float SCALE = 2.4f; // Word barkodunu Aspose.BarCode'a dönüştürmek için deneysel ölçekleme faktörü
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
	
	// Ölçekleme faktörünü uygula
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
	
	// Barkod görüntüsünü oluştur ve döndür
	return generator.generateBarCodeImage();
}
```

## GetOldBarcodeImage() Yönteminin Uygulanması

 Bu adımda, şunu uygulayacağız:`getOldBarcodeImage`eski moda barkodlar için barkod görüntüleri üreten yöntem. Burada, POSTNET gibi belirli bir barkod türünü ele alacağız. İşte bu yöntem için kod:

```java
/// <özet>
/// IBarCodeGenerator arayüzü için GetOldBarcodeImage() metodunun uygulanması.
/// </özet>
/// <param name="parametreler"></param>
/// <döndürür></döndürür>
public BufferedImage getOldBarcodeImage(BarcodeParameters parameters)
{
	if (parameters.getPostalAddress() == null)
		return null;
	BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.POSTNET);
	{
		generator.setCodeText(parameters.getPostalAddress());
	}
	// Eski tip Barkod için Sabit Kod türü
	return generator.generateBarCodeImage();
}
```

## Çözüm

Bu makalede, Aspose.Words for Java kullanarak özel barkod etiketleri oluşturma sürecini inceledik. Barkod yüksekliğini ayarlamaktan barkod oluşturma yöntemlerini uygulamaya kadar temel adımları ele aldık. Aspose.Words for Java, geliştiricilerin dinamik ve özelleştirilmiş barkod etiketleri oluşturmasını sağlayarak onu çeşitli sektörler için değerli bir araç haline getirir.

## SSS

### Oluşturulan barkodun boyutunu nasıl ayarlayabilirim?

Üretilen barkodun boyutunu, sağlanan kod parçacıklarında barkodun sembol yüksekliğini ve ölçekleme faktörünü ayarlayarak ayarlayabilirsiniz. Bu parametreler barkodun boyutlarını ihtiyaçlarınıza göre kontrol etmenizi sağlar.

### Barkodun renklerini değiştirebilir miyim?

Evet, kodda ön plan ve arka plan renklerini belirterek barkodun renklerini değiştirebilirsiniz. Bu özelleştirme, barkodun görünümünü belgenizin tasarımıyla eşleştirmenize olanak tanır.

### Aspose.Words for Java hangi barkod tiplerini destekliyor?

Java için Aspose.Words, QR kodları, CODE128, CODE39, EAN8, EAN13, UPCA, UPCE, ITF14 ve daha fazlası dahil olmak üzere çeşitli barkod türlerini destekler. Uygulamanızın ihtiyaçlarına uygun barkod türünü seçebilirsiniz.

### Oluşturulan barkodu Word dokümanıma nasıl entegre edebilirim?

Oluşturulan barkodu Word belgenize entegre etmek için Aspose.Words for Java'nın belge düzenleme yeteneklerini kullanabilirsiniz. Barkod görüntüsünü belgenize istediğiniz yere ekleyebilirsiniz.

### Daha fazla özelleştirme için herhangi bir örnek kod var mı?

 Evet, Aspose.Words for Java'nın referans sitesinde örnek kod parçacıkları ve ek belgeler bulabilirsiniz:[Aspose.Words for Java API Referansı](https://reference.aspose.com/words/java/).