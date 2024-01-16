---
title: Создание пользовательских этикеток со штрих-кодом в Aspose.Words для Java
linktitle: Создание пользовательских этикеток со штрих-кодом
second_title: API обработки Java-документов Aspose.Words
description: Создавайте собственные этикетки со штрих-кодом в Aspose.Words для Java. Узнайте, как создавать персонализированные решения для штрих-кодов с помощью Aspose.Words для Java, в этом пошаговом руководстве.
type: docs
weight: 10
url: /ru/java/document-conversion-and-export/generating-custom-barcode-labels/
---

## Введение в создание пользовательских этикеток со штрих-кодом в Aspose.Words для Java

В этом подробном руководстве мы углубимся в процесс создания пользовательских этикеток со штрих-кодом с помощью Aspose.Words для Java. Aspose.Words for Java — это мощный API, который позволяет разработчикам программно манипулировать документами Word. Одной из его замечательных особенностей является возможность работы с этикетками со штрих-кодами, что делает его ценным инструментом для предприятий и организаций, которым требуются индивидуальные решения в области штрих-кодов.

## Предварительные условия

Прежде чем мы углубимся в детали создания пользовательских этикеток со штрих-кодом, давайте убедимся, что у нас есть необходимые условия:

1. Среда разработки Java: убедитесь, что в вашей системе установлены Java и интегрированная среда разработки (IDE).

2.  Aspose.Words для Java: Загрузите и установите Aspose.Words для Java с сайта[здесь](https://releases.aspose.com/words/java/).

3. Базовые знания Java. Знакомство с программированием на Java будет полезно, поскольку мы будем писать код Java для создания пользовательских этикеток со штрих-кодом.

## Создание пользовательских этикеток со штрих-кодом

Теперь давайте начнем создавать собственные этикетки со штрих-кодом с помощью Aspose.Words для Java. Мы разобьем процесс на этапы и предоставим фрагменты кода Java для каждого шага.

## Установка высоты штрих-кода

Для начала нам нужно установить высоту нашего штрих-кода в твипах (1/1440 дюйма). Затем мы преобразуем это значение в миллиметры (мм). Вот код для этого:

```java
	// Введите значение в 1/1440 дюйма (твипсах).
	int heightInTwips = tryParseInt(heightInTwipsString);
	if (heightInTwips == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect height - " + heightInTwipsString + ".");
	// Перевести в мм
	return (float) (heightInTwips * 25.4 / 1440.0);
```

## Преобразование цвета изображения штрих-кода

Далее мы преобразуем цвет изображения штрих-кода из Word в Aspose.BarCode. Входной цвет должен быть в формате «0xRRGGBB» (шестнадцатеричный). Вот код преобразования:

```java
/// <сводка>
/// Преобразует цвет изображения штрих-кода из Word в Aspose.BarCode.
/// </сводка>
/// <param name="inputColor"></param>
/// <возвращается></возвращается>
private static Color convertColor(String inputColor) throws Exception {
	// Ввод должен быть от «0x000000» до «0xFFFFFF».
	int color = tryParseHex(inputColor.replace("0x", ""));
	if (color == Integer.MIN_VALUE)
		throw new Exception("Error! Incorrect color - " + inputColor + ".");
	return new Color((color >> 16), ((color & 0xFF00) >> 8), (color & 0xFF));
}
```

## Преобразование коэффициента масштабирования штрих-кода

Теперь мы преобразуем коэффициент масштабирования штрих-кода из процента в значение с плавающей запятой. Этот коэффициент масштабирования определяет размер штрих-кода. Вот код преобразования:

```java
/// <сводка>
/// Преобразует коэффициент масштабирования штрих-кода из процентов в число с плавающей запятой.
/// </сводка>
/// <param name="scalingFactor"></param>
/// <возвращается></возвращается>
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

 На этом этапе мы реализуем`getBarcodeImage` метод, который генерирует изображение штрих-кода на основе предоставленных параметров. Мы будем обрабатывать различные типы штрих-кодов, устанавливать цвета, регулировать размеры и многое другое. Вот код этого метода:

```java
/// <сводка>
/// Реализация метода GetBarCodeImage() для интерфейса IBarCodeGenerator.
/// </сводка>
/// <param name="parameters"></param>
/// <возвращается></возвращается>
public BufferedImage getBarcodeImage(BarcodeParameters parameters) throws Exception {
	// Проверьте, указаны ли тип и значение штрих-кода
	if (parameters.getBarcodeType() == null || parameters.getBarcodeValue() == null)
		return null;
	
	// Создайте BarcodeGenerator на основе типа штрих-кода.
	BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.QR);
	String type = parameters.getBarcodeType().toUpperCase();
	switch (type)
	{
		case "QR":
			generator = new BarcodeGenerator(EncodeTypes.QR);
			break;
		// Здесь можно обрабатывать другие типы штрих-кодов.
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
	
	//Настройте расположение текста кода
	generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.NONE);
	if (parameters.getDisplayText())
		generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.BELOW);
	
	// Дополнительные настройки для QR-кодов
	final float SCALE = 2.4f; // Эмпирический коэффициент масштабирования для преобразования штрих-кода Word в Aspose.BarCode
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
	
	// Сгенерируйте и верните изображение штрих-кода
	return generator.generateBarCodeImage();
}
```

## Реализация метода GetOldBarcodeImage()

 На этом этапе мы реализуем`getOldBarcodeImage` метод, который генерирует изображения штрих-кодов для устаревших штрих-кодов. Здесь мы будем обрабатывать определенный тип штрих-кода, например POSTNET. Вот код этого метода:

```java
/// <сводка>
/// Реализация метода GetOldBarcodeImage() для интерфейса IBarCodeGenerator.
/// </сводка>
/// <param name="parameters"></param>
/// <возвращается></возвращается>
public BufferedImage getOldBarcodeImage(BarcodeParameters parameters)
{
	if (parameters.getPostalAddress() == null)
		return null;
	BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.POSTNET);
	{
		generator.setCodeText(parameters.getPostalAddress());
	}
	// Тип жесткого кода для старомодного штрих-кода
	return generator.generateBarCodeImage();
}
```

## Заключение

В этой статье мы рассмотрели процесс создания пользовательских этикеток со штрих-кодом с помощью Aspose.Words для Java. Мы рассмотрели основные шаги: от установки высоты штрих-кода до реализации методов генерации штрих-кода. Aspose.Words for Java позволяет разработчикам создавать динамические и настраиваемые этикетки со штрих-кодами, что делает его ценным инструментом для различных отраслей.

## Часто задаваемые вопросы

### Как я могу настроить размер создаваемого штрих-кода?

Вы можете настроить размер создаваемого штрих-кода, задав высоту символа штрих-кода и коэффициент масштабирования в предоставленных фрагментах кода. Эти параметры позволяют вам контролировать размеры штрих-кода в соответствии с вашими требованиями.

### Могу ли я изменить цвета штрих-кода?

Да, вы можете изменить цвета штрих-кода, указав в коде цвета переднего плана и фона. Эта настройка позволяет согласовать внешний вид штрих-кода с дизайном вашего документа.

### Какие типы штрих-кодов поддерживаются Aspose.Words для Java?

Aspose.Words для Java поддерживает различные типы штрих-кодов, включая QR-коды, CODE128, CODE39, EAN8, EAN13, UPCA, UPCE, ITF14 и другие. Вы можете выбрать тип штрих-кода, который соответствует потребностям вашего приложения.

### Как интегрировать сгенерированный штрих-код в документ Word?

Чтобы интегрировать сгенерированный штрих-код в документ Word, вы можете использовать возможности Aspose.Words для манипулирования документами Java. Вы можете вставить изображение штрих-кода в документ в нужное место.

### Есть ли образец кода для дальнейшей настройки?

 Да, вы можете найти примеры фрагментов кода и дополнительную документацию на справочном сайте Aspose.Words for Java:[Справочник по API Aspose.Words для Java](https://reference.aspose.com/words/java/).