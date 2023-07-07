---
title: Вставить объект Ole в документ Word как значок
linktitle: Вставить объект Ole в документ Word как значок
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как вставить объект OLE в документ Word в виде значка с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon/
---

Ниже приведено пошаговое руководство по объяснению приведенного ниже исходного кода C#, которое иллюстрирует, как вставить объект OLE в документ Word в виде значка с помощью Aspose.Words для .NET.

## Шаг 1. Импортируйте необходимые ссылки
Прежде чем начать, убедитесь, что вы импортировали в свой проект необходимые ссылки для использования Aspose.Words for .NET. Сюда входит импорт библиотеки Aspose.Words и добавление необходимых пространств имен в исходный файл.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Шаг 2: Создайте новый документ и генератор документов
 На этом шаге мы создадим новый документ, используя`Document` класс и конструктор документов, использующий`DocumentBuilder` сорт.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 3. Вставьте объект OLE в качестве значка
 Используйте конструктор документов`InsertOleObjectAsIcon` способ вставки объекта OLE в качестве значка в документ. Укажите путь к OLE-файлу, флаг отображения, путь к значку и имя внедренного объекта.

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

## Шаг 4: Сохраните документ
 Используйте документ`Save` метод сохранения документа в файл.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

### Пример исходного кода для вставки объекта OLE в качестве значка с помощью Aspose.Words для .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

Это полный пример кода для вставки объекта OLE в качестве значка с помощью Aspose.Words для .NET. Обязательно импортируйте необходимые ссылки и выполните шаги, описанные ранее, чтобы интегрировать этот код в свой проект.

## Заключение

В заключение мы изучили пошаговое руководство по вставке объекта OLE в качестве значка в документ Word с помощью Aspose.Words для .NET.

Выполнив эти шаги, вы сможете успешно вставить объект OLE в качестве значка в документы Word с помощью Aspose.Words для .NET. Обязательно импортируйте необходимые ссылки и внимательно следуйте инструкциям, чтобы получить желаемые результаты.

### Часто задаваемые вопросы по вставке объекта ole в документ Word в виде значка

#### Вопрос. Какие ссылки необходимы для вставки объекта OLE в качестве значка в документ Word с помощью Aspose.Words для .NET?

О: Чтобы использовать Aspose.Words for .NET, вам необходимо импортировать в проект следующие ссылки:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### В. Как создать новый документ и генератор документов в Aspose.Words для .NET?

 A: Вы можете создать новый документ, используя`Document` класс и конструктор документов, использующий`DocumentBuilder`сорт. Вот пример:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### В. Как вставить объект OLE в качестве значка в документ?

 A: Используйте Document Builder`InsertOleObjectAsIcon` способ вставки объекта OLE в качестве значка. Укажите путь к OLE-файлу, флаг отображения, путь к значку и имя внедренного объекта. Вот пример:

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

#### Q. Как сохранить документ с OLE-объектом, вставленным в виде значка?

 О: Используйте документ`Save`метод сохранения документа в файл. Вот пример:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```