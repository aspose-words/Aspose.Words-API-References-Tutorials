---
title: Вставить объект Ole с пакетом Ole
linktitle: Вставить объект Ole с пакетом Ole
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как вставить объект OLE с пакетом OLE в документ с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-oleobjects-and-activex/insert-ole-object-with-ole-package/
---

Ниже приведено пошаговое руководство по объяснению приведенного ниже исходного кода C#, в котором показано, как вставить объект OLE в пакет OLE с помощью Aspose.Words для .NET.

## Шаг 1. Импортируйте необходимые ссылки
Прежде чем начать, убедитесь, что вы импортировали в свой проект необходимые ссылки для использования Aspose.Words for .NET. Сюда входит импорт библиотеки Aspose.Words и добавление необходимых пространств имен в исходный файл.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

## Шаг 2: Создайте новый документ и генератор документов
 На этом шаге мы создадим новый документ, используя`Document` класс и конструктор документов, использующий`DocumentBuilder` сорт.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 3. Вставьте объект OLE с пакетом OLE.
 Используйте генератор документов`InsertOleObject` метод для вставки объекта OLE с пакетом OLE в документ. Укажите поток данных, тип объекта, параметры отображения и другие необходимые настройки.

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}
```

## Шаг 4: Сохраните документ
 Используйте документ`Save` метод сохранения документа в файл.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

### Пример исходного кода для вставки объекта OLE в пакет OLE с Aspose.Words для .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

Это полный пример кода для вставки объекта OLE в пакет OLE с помощью Aspose.Words для .NET. Обязательно импортируйте необходимые ссылки и выполните шаги, описанные ранее, чтобы интегрировать этот код в свой проект.