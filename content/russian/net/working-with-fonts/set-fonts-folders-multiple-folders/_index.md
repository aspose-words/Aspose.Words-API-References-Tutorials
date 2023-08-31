---
title: Установить папки со шрифтами Несколько папок
linktitle: Установить папки со шрифтами Несколько папок
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по установке нескольких папок шрифтов при рендеринге документа с использованием Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-fonts/set-fonts-folders-multiple-folders/
---

В этом руководстве мы пошагово проведем вас через процесс установки нескольких папок шрифтов при рендеринге документа с использованием Aspose.Words для .NET. Мы объясним прилагаемый исходный код C# и предоставим вам исчерпывающее руководство, которое поможет вам понять и реализовать эту функцию в ваших собственных проектах. К концу этого руководства вы будете знать, как указать несколько папок шрифтов для использования при рендеринге ваших документов с помощью Aspose.Words для .NET.

## Шаг 1: Определите каталог документов
Во-первых, вам нужно указать путь к каталогу ваших документов. Это место, где вы хотите сохранить отредактированный визуализированный документ. Замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на соответствующий путь.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2: Загрузите документ для рендеринга
 Затем вы можете загрузить документ для рендеринга с помощью`Document` сорт. Обязательно укажите правильный путь к документу.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Шаг 3: Установите папки со шрифтами
 Теперь вы можете установить несколько папок шрифтов, используя`FontSettings` класс и`SetFontsFolders()` метод. Вы можете указать пути к папкам со шрифтами, которые хотите использовать в массиве. В этом примере мы указали две папки со шрифтами: «C:\MyFonts\" и "D:\Разное\Шрифты\".

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
```

## Шаг 4: Примените настройки шрифта
 Затем вам нужно применить настройки шрифта к вашему документу, используя`FontSettings` собственность`Document` сорт.

```csharp
doc.FontSettings = fontSettings;
```

## Шаг 5: Сохраните визуализированный документ
 Наконец, вы можете сохранить визуализированный документ в файл, используя`Save()` метод`Document` сорт. Обязательно укажите правильный путь и имя файла.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

### Пример исходного кода для установки нескольких папок для папок шрифтов с использованием Aspose.Words для .NET 

```csharp
//Путь к вашему каталогу документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Обратите внимание, что этот параметр переопределяет любые источники шрифтов по умолчанию, которые ищутся по умолчанию. Теперь будут искать только эти папки
// шрифты при рендеринге или встраивании шрифтов. Чтобы добавить дополнительный источник шрифта при сохранении системных источников шрифта, используйте как FontSettings.GetFontSources, так и
// Вместо этого FontSettings.SetFontSources.
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

## Заключение
В этом руководстве мы узнали, как установить несколько папок шрифтов при рендеринге документа с использованием Aspose.Words для .NET. Следуя этому пошаговому руководству, вы можете легко указать несколько папок шрифтов для использования при рендеринге ваших документов. Aspose.Words предлагает мощный и гибкий API для обработки слов со шрифтами в ваших документах. Обладая этими знаниями, вы можете контролировать и настраивать источники шрифтов, используемые при рендеринге ваших документов, в соответствии с вашими конкретными потребностями.

### Часто задаваемые вопросы

#### Q: Как я могу установить несколько папок шрифтов в Aspose.Words?

 A: Чтобы установить несколько папок шрифтов в Aspose.Words, вы можете использовать`SetFontsFolders` метод`Fonts` класс, предоставляющий список расположений папок пользовательских шрифтов.

#### В: Влияет ли установка нескольких папок шрифтов на все документы, обрабатываемые с помощью Aspose.Words?

О: Да, установка нескольких папок шрифтов влияет на все документы, обрабатываемые с помощью Aspose.Words. После того, как вы определили папки со шрифтами, Aspose.Words будет использовать их для поиска шрифтов во всех документах.

#### В: Сколько папок со шрифтами я могу определить в Aspose.Words?

О: Вы можете определить столько папок со шрифтами, сколько необходимо в Aspose.Words. Нет определенного ограничения на количество папок шрифтов, которые вы можете определить.

#### Q: Как я могу проверить папки со шрифтами, определенные в Aspose.Words?

 A: Чтобы проверить папки со шрифтами, определенные в Aspose.Words, вы можете использовать`GetFolders` метод`Fonts` class, чтобы получить расположение настроенных папок шрифтов.

#### В: Должны ли папки со шрифтами содержать определенные шрифты?

О: Да, папки со шрифтами должны содержать шрифты, которые вы хотите использовать в своих документах Word. Aspose.Words будет искать шрифты в указанных папках при обработке документов.