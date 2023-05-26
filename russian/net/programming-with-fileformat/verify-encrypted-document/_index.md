---
title: Проверить зашифрованный документ
linktitle: Проверить зашифрованный документ
second_title: Справочник по API Aspose.Words для .NET
description: Пошаговое руководство по проверке того, что документ зашифрован с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-fileformat/verify-encrypted-document/
---

В этой статье представлено пошаговое руководство по использованию функции проверки зашифрованных документов с Aspose.Words для .NET. Мы подробно объясним каждую часть кода. В конце этого руководства вы сможете понять, как проверить, зашифрован ли документ.

Прежде чем начать, убедитесь, что вы установили и настроили библиотеку Aspose.Words for .NET в своем проекте. Вы можете найти библиотеку и инструкции по установке на веб-сайте Aspose.

## Шаг 1: Определите каталог документов

 Для начала вам нужно указать путь к каталогу, в котором находятся ваши документы. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу ваших документов.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Определите формат файла

 Далее мы используем`DetectFileFormat` метод`FileFormatUtil` класс для обнаружения информации о формате файла. В этом примере предполагается, что зашифрованный документ называется «Encrypted.docx» и находится в указанном каталоге документов.

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
```

## Шаг 3. Проверьте, зашифрован ли документ

 Мы используем`IsEncrypted` собственность`FileFormatInfo` объект, чтобы проверить, зашифрован ли документ. Это свойство возвращает`true` если документ зашифрован, иначе возвращает`false`. Выводим результат в консоль.

```csharp
Console.WriteLine(info.IsEncrypted);
```

Вот и все ! Вы успешно проверили, зашифрован ли документ с помощью Aspose.Words для .NET.

### Пример исходного кода для проверки зашифрованных документов с помощью Aspose.Words для .NET

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
	Console.WriteLine(info.IsEncrypted);
            
        
```
