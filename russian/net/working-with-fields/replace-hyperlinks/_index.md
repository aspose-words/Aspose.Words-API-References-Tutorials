---
title: Заменить гиперссылки
linktitle: Заменить гиперссылки
second_title: Справочник по API Aspose.Words для .NET
description: Замените гиперссылки в документах Word с помощью Aspose.Words для .NET. Пошаговая инструкция по замене гиперссылок.
type: docs
weight: 10
url: /ru/net/working-with-fields/replace-hyperlinks/
---

Вот пошаговое руководство, объясняющее следующий исходный код C# для замены гиперссылок с помощью функций Aspose.Words for .NET. Перед использованием этого кода убедитесь, что вы включили библиотеку Aspose.Words в свой проект.

## Шаг 1. Установите путь к каталогу документов

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

 Обязательно укажите правильный путь к каталогу документов, содержащему`Hyperlinks.docx` файл.

## Шаг 2: Загрузите документ, содержащий гиперссылки

```csharp
Document doc = new Document(dataDir + "Hyperlinks.docx");
```

 Здесь мы создаем экземпляр`Document` класс из указанного файла.

## Шаг 3. Просмотрите поля, чтобы найти гиперссылки

```csharp
foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // Некоторые гиперссылки могут быть локальными (ссылки на закладки внутри документа), мы их игнорируем.
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com";
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}
```

 Этот цикл проходит по всем полям документа в поисках полей типа`FieldType.FieldHyperlink` . Как только поле этого типа найдено, мы проверяем, является ли оно локальной ссылкой, проверяя`SubAddress` свойство. Если нет, то заменяем адрес ссылки на`"http://www.aspose.com"`и результат с`"Aspose - The .NET & Java Component Editor"`.

## Шаг 4: Сохраните измененный документ

```csharp
doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

Наконец, мы сохраняем измененный документ с замененными гиперссылками в указанный файл.

### Пример исходного кода для замены гиперссылок на Aspose.Words для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Hyperlinks.docx");

foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // Некоторые гиперссылки могут быть локальными (ссылки на закладки внутри документа), мы их игнорируем.
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com";
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}

doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

Это пример исходного кода для замены гиперссылок в документе с использованием Aspose.Words для .NET.