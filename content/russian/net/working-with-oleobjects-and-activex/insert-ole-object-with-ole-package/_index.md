---
title: Вставить объект Ole в Word с помощью пакета Ole
linktitle: Вставить объект Ole в Word с помощью пакета Ole
second_title: API обработки документов Aspose.Words
description: Узнайте, как вставлять объекты OLE в документы Word с помощью Aspose.Words для .NET. Следуйте нашему подробному пошаговому руководству, чтобы легко вставлять файлы.
type: docs
weight: 10
url: /ru/net/working-with-oleobjects-and-activex/insert-ole-object-with-ole-package/
---
## Введение

Если вы когда-нибудь хотели встроить файл в документ Word, вы попали по адресу. Будь то ZIP-файл, лист Excel или файл любого другого типа, встраивание его непосредственно в документ Word может быть невероятно полезным. Думайте об этом как о секретном отделении в вашем документе, где вы можете хранить всевозможные сокровища. И сегодня мы рассмотрим, как это сделать с помощью Aspose.Words для .NET. Готовы стать мастером Word? Давайте погрузимся!

## Предварительные условия

Прежде чем мы начнем, убедитесь, что у вас есть следующее:

1. Aspose.Words для .NET: если вы еще этого не сделали, загрузите его с[здесь](https://releases.aspose.com/words/net/).
2. Среда разработки: Visual Studio или любая другая среда разработки .NET.
3. Базовое понимание C#. Вам не обязательно быть экспертом, но знание C# поможет.
4. Каталог документов: папка, в которой вы можете хранить и извлекать документы.

## Импортировать пространства имен

Прежде всего, давайте приведем в порядок наши пространства имен. В ваш проект необходимо включить следующие пространства имен:

```csharp
using System;
using System.IO;
using Aspose.Words;
using Aspose.Words.Drawing;
```

Давайте разобьем это на небольшие шаги, чтобы было легко следовать.

## Шаг 1. Настройте свой документ

Представьте, что вы художник с чистым холстом. Во-первых, нам нужен чистый холст, который является нашим документом Word. Вот как вы это настроили:

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Этот код инициализирует новый документ Word и устанавливает DocumentBuilder, который мы будем использовать для вставки содержимого в наш документ.

## Шаг 2. Прочтите свой объект Ole

Далее давайте прочитаем файл, который вы хотите встроить. Думайте об этом как о поиске сокровища, которое вы хотите спрятать в своем секретном отделении:

```csharp
byte[] bs = File.ReadAllBytes(dataDir + "Zip file.zip");
```

Эта строка считывает все байты из вашего ZIP-файла и сохраняет их в массиве байтов.

## Шаг 3. Вставьте объект Ole

Теперь наступает волшебная часть. Мы собираемся встроить файл в наш документ Word:

```csharp
using (Stream stream = new MemoryStream(bs))
{
    Shape shape = builder.InsertOleObject(stream, "Package", true, null);
    OlePackage olePackage = shape.OleFormat.OlePackage;
    olePackage.FileName = "filename.zip";
    olePackage.DisplayName = "displayname.zip";
}
```

 Здесь мы создаем поток памяти из массива байтов и используем метод`InsertOleObject` метод для встраивания его в документ. Мы также задаем имя файла и отображаемое имя для внедренного объекта.

## Шаг 4. Сохраните документ

Наконец, сохраним наш шедевр:

```csharp
doc.Save(dataDir + "WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

Это сохранит документ со встроенным файлом в указанном каталоге.

## Заключение

И вот оно! Вы успешно встроили объект OLE в документ Word с помощью Aspose.Words для .NET. Это похоже на добавление в документ скрытой жемчужины, которую можно открыть в любой момент. Этот метод может быть невероятно полезен для самых разных приложений: от технической документации до динамических отчетов. 

## Часто задаваемые вопросы

### Могу ли я вставлять другие типы файлов, используя этот метод?
Да, вы можете встраивать файлы различных типов, например листы Excel, PDF-файлы и изображения.

### Нужна ли мне лицензия для Aspose.Words?
 Да, вам нужна действующая лицензия. Вы можете получить[временная лицензия](https://purchase.aspose.com/temporary-license/) для оценки.

### Как настроить отображаемое имя объекта OLE?
 Вы можете установить`DisplayName` собственность`OlePackage` чтобы настроить его.

### Совместим ли Aspose.Words с .NET Core?
Да, Aspose.Words поддерживает как .NET Framework, так и .NET Core.

### Могу ли я редактировать встроенный объект OLE в документе Word?
Нет, вы не можете редактировать объект OLE непосредственно в Word. Вам нужно открыть его в родном приложении.