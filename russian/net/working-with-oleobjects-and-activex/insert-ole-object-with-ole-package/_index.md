---
title: Вставьте объект Ole в Word с пакетом Ole
linktitle: Вставьте объект Ole в Word с пакетом Ole
second_title: API обработки документов Aspose.Words
description: Узнайте, как вставить объект OLE с пакетом OLE в документ с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-oleobjects-and-activex/insert-ole-object-with-ole-package/
---

Ниже приведено пошаговое руководство по объяснению приведенного ниже исходного кода C#, в котором показано, как вставить объект OLE в слово с пакетом OLE с помощью Aspose.Words для .NET.

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
 Используйте генератор документов`InsertOleObject`метод для вставки объекта OLE с пакетом OLE в документ. Укажите поток данных, тип объекта, параметры отображения и другие необходимые настройки.

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

## Заключение

В заключение мы рассмотрели пошаговое руководство по вставке объекта OLE в документ Word с помощью пакета OLE с использованием Aspose.Words для .NET.

Выполнив следующие действия, вы сможете успешно вставлять объекты OLE с пакетами OLE в документы Word с помощью Aspose.Words для .NET. Обязательно импортируйте необходимые ссылки и внимательно следуйте инструкциям, чтобы получить желаемые результаты.

### Часто задаваемые вопросы по вставке объекта ole в слово с пакетом ole

#### В: Какие учетные данные мне нужно импортировать, чтобы использовать Aspose.Words для .NET?

О: Чтобы использовать Aspose.Words для .NET, вам необходимо импортировать следующие ссылки:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

#### Q: Как создать новый документ и генератор документов?

 A: Вы можете создать новый документ, используя`Document` класс и конструктор документов, использующий`DocumentBuilder` класс, как показано ниже:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### В: Как вставить в документ OLE-объект с OLE-пакетом?

 О: Используйте`InsertOleObject` метод конструктора документов (`DocumentBuilder`), чтобы вставить объект OLE с пакетом OLE в документ. Укажите поток данных, тип объекта, параметры отображения и другие необходимые настройки. Вот пример:

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}
```

#### Q: Как сохранить документ?

 О: Используйте документ`Save`метод сохранения документа в файл. Вот пример:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

#### Вопрос. Можете ли вы предоставить полный пример вставки объекта OLE в пакет OLE с помощью Aspose.Words для .NET?

О: Вот полный пример кода для вставки объекта OLE в пакет OLE с помощью Aspose.Words для .NET. Обязательно импортируйте необходимые ссылки и выполните шаги, описанные ранее, чтобы интегрировать этот код в свой проект:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

На этом мы завершаем наше руководство по вставке объекта OLE с пакетом OLE в документ Word с помощью Aspose.Words для .NET. Не стесняйтесь импортировать необходимые ссылки и следуйте описанным шагам, чтобы интегрировать этот код в свой проект. Если у вас есть дополнительные вопросы, пожалуйста, не стесняйтесь обращаться к нам.