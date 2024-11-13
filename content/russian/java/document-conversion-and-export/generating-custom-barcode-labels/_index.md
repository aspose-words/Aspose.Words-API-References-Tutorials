---
title: Создание пользовательских этикеток штрихкода в Aspose.Words для Java
linktitle: Создание пользовательских этикеток со штрих-кодом
second_title: API обработки документов Java Aspose.Words
description: Генерация пользовательских этикеток штрихкодов в Aspose.Words для Java. Узнайте, как создавать персонализированные решения для штрихкодов с помощью Aspose.Words для Java в этом пошаговом руководстве.
type: docs
weight: 10
url: /ru/java/document-conversion-and-export/generating-custom-barcode-labels/
---

## Введение в создание пользовательских этикеток штрихкодов в Aspose.Words для Java

В этом подробном руководстве мы углубимся в процесс создания пользовательских этикеток со штрихкодами с помощью Aspose.Words для Java. Aspose.Words для Java — это мощный API, позволяющий разработчикам программно манипулировать документами Word. Одной из его замечательных особенностей является возможность работать с этикетками со штрихкодами, что делает его ценным инструментом для предприятий и организаций, которым требуются индивидуальные решения для штрихкодов.

## Предпосылки

Прежде чем углубиться в детали создания пользовательских этикеток со штрихкодом, давайте убедимся, что у нас выполнены все необходимые предварительные условия:

1. Среда разработки Java: убедитесь, что в вашей системе установлены Java и интегрированная среда разработки (IDE).

2.  Aspose.Words для Java: Загрузите и установите Aspose.Words для Java с сайта[здесь](https://releases.aspose.com/words/java/).

3. Базовые знания Java: знакомство с программированием на Java будет полезно, поскольку мы будем писать код Java для создания пользовательских этикеток со штрихкодами.

## Создание пользовательских этикеток со штрих-кодом

Теперь давайте начнем создавать пользовательские этикетки штрихкодов с помощью Aspose.Words для Java. Мы разобьем процесс на этапы и предоставим фрагменты кода Java для каждого этапа.

## Установка высоты штрих-кода

Для начала нам нужно задать высоту нашего штрихкода в твипах (1/1440 дюйма). Затем мы преобразуем это значение в миллиметры (мм). Вот код для этого:

```java
	// Вводимое значение указывается в 1/1440 дюйма (твипах).
	int heightInTwips = tryParseInt(heightInTwipsString);
	if (heightInTwips == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect height - " + heightInTwipsString + ".");
	// Конвертировать в мм
	return (float) (heightInTwips * 25.4 / 1440.0);
```

## Преобразование цвета изображения штрих-кода

Далее мы преобразуем цвет изображения штрихкода из Word в Aspose.BarCode. Входной цвет должен быть в формате "0xRRGGBB" (шестнадцатеричный). Вот код для преобразования:

```java
/// <резюме>
/// Преобразует цвет изображения штрихкода из Word в Aspose.BarCode.
/// </резюме>
/// <param name="inputColor"></param>
/// <возврат></возврат>
private static Color convertColor(String inputColor) throws Exception {
	// Ввод должен быть от «0x000000» до «0xFFFFFF»
	int color = tryParseHex(inputColor.replace("0x", ""));
	if (color == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect color - " + inputColor + ".");
	return new Color((color >> 16), ((color & 0xFF00) >> 8), (color & 0xFF));
}
```

## Преобразование коэффициента масштабирования штрих-кода

Теперь преобразуем коэффициент масштабирования штрихкода из процента в плавающее значение. Этот коэффициент масштабирования определяет размер штрихкода. Вот код для преобразования:

```java
/// <резюме>
/// Преобразует коэффициент масштабирования штрих-кода из процентов в число с плавающей точкой.
/// </резюме>
/// <param name="scalingFactor"></param>
/// <возврат></возврат>
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

## Реализация метода GetBarCodeImage()

 На этом этапе мы реализуем`getBarcodeImage`метод, который генерирует изображение штрихкода на основе предоставленных параметров. Мы будем обрабатывать различные типы штрихкодов, задавать цвета, настраивать размеры и многое другое. Вот код этого метода:

```java
/// <резюме>
/// Реализация метода GetBarCodeImage() для интерфейса IBarCodeGenerator.
/// </резюме>
/// <param name="параметры"></param>
/// <возврат></возврат>
public BufferedImage getBarcodeImage(BarcodeParameters parameters) throws Exception {
	// Проверьте, указаны ли тип и значение штрих-кода.
	if (parameters.getBarcodeType() == null || parameters.getBarcodeValue() == null)
		return null;
	
	// Создайте BarcodeGenerator на основе типа штрихкода
	BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.QR);
	String type = parameters.getBarcodeType().toUpperCase();
	switch (type)
	{
		case "QR":
			generator = new BarcodeGenerator(EncodeTypes.QR);
			break;
		// Обрабатывайте другие типы штрихкодов здесь
	}
	
	// Установите текст штрих-кода
	generator.setCodeText(parameters.getBarcodeValue());
	
	// Установить цвета штрих-кода
	if (parameters.getForegroundColor() != null)
		generator.getParameters().getBarcode().setBarColor(convertColor(parameters.getForegroundColor()));
	if (parameters.getBackgroundColor() != null)
		generator.getParameters().setBackColor(convertColor(parameters.getBackgroundColor()));
	
	// Установить высоту и размеры символа
	if (parameters.getSymbolHeight() != null)
	{
		generator.getParameters().getImageHeight().setPixels(convertSymbolHeight(parameters.getSymbolHeight()));
		generator.getParameters().setAutoSizeMode(AutoSizeMode.NONE);
	}
	
	// Настройте расположение текста кода
	generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.NONE);
	if (parameters.getDisplayText())
		generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.BELOW);
	
	// Дополнительные настройки для QR-кодов
	final float SCALE = 2.4f; // Эмпирический коэффициент масштабирования для преобразования штрихкода Word в Aspose.BarCode
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
	
	// Применить коэффициент масштабирования
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
	
	// Сгенерировать и вернуть изображение штрих-кода
	return generator.generateBarCodeImage();
}
```

## Реализация метода GetOldBarcodeImage()

 На этом этапе мы реализуем`getOldBarcodeImage`метод, который генерирует изображения штрихкодов для старых штрихкодов. Здесь мы будем обрабатывать определенный тип штрихкода, например POSTNET. Вот код этого метода:

```java
/// <резюме>
/// Реализация метода GetOldBarcodeImage() для интерфейса IBarCodeGenerator.
/// </резюме>
/// <param name="параметры"></param>
/// <возврат></возврат>
public BufferedImage getOldBarcodeImage(BarcodeParameters parameters)
{
	if (parameters.getPostalAddress() == null)
		return null;
	BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.POSTNET);
	{
		generator.setCodeText(parameters.getPostalAddress());
	}
	// Тип жесткого кода для устаревшего штрих-кода
	return generator.generateBarCodeImage();
}
```

## Заключение

В этой статье мы изучили процесс создания пользовательских этикеток штрихкодов с помощью Aspose.Words для Java. Мы рассмотрели основные шаги, от установки высоты штрихкода до внедрения методов генерации штрихкодов. Aspose.Words для Java позволяет разработчикам создавать динамические и настраиваемые этикетки штрихкодов, что делает его ценным инструментом для различных отраслей.

## Часто задаваемые вопросы

### Как изменить размер сгенерированного штрихкода?

Вы можете настроить размер сгенерированного штрихкода, установив высоту символа штрихкода и коэффициент масштабирования в предоставленных фрагментах кода. Эти параметры позволяют вам контролировать размеры штрихкода в соответствии с вашими требованиями.

### Могу ли я изменить цвета штрих-кода?

Да, вы можете изменить цвета штрих-кода, указав цвета переднего плана и фона в коде. Эта настройка позволяет вам сопоставить внешний вид штрих-кода с дизайном вашего документа.

### Какие типы штрихкодов поддерживает Aspose.Words для Java?

Aspose.Words for Java поддерживает различные типы штрихкодов, включая QR-коды, CODE128, CODE39, EAN8, EAN13, UPCA, UPCE, ITF14 и др. Вы можете выбрать тип штрихкода, который соответствует потребностям вашего приложения.

### Как интегрировать сгенерированный штрих-код в документ Word?

Чтобы интегрировать сгенерированный штрихкод в документ Word, вы можете использовать возможности Aspose.Words for Java по манипулированию документами. Вы можете вставить изображение штрихкода в документ в нужном месте.

### Есть ли какой-либо образец кода для дальнейшей настройки?

 Да, вы можете найти примеры фрагментов кода и дополнительную документацию на справочном сайте Aspose.Words for Java:[Справочник API Aspose.Words для Java](https://reference.aspose.com/words/java/).