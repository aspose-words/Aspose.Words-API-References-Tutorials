---
title: Вставить первый объект в документ Word как значок
linktitle: Вставить первый объект в документ Word как значок
second_title: API обработки документов Aspose.Words
description: Узнайте, как вставить объект OLE в документ Word в виде значка с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon/
---

Ниже приведено пошаговое руководство, объясняющее приведенный ниже исходный код C#, в котором показано, как вставить объект OLE в документ Word в виде значка с помощью Aspose.Words для .NET.

## Шаг 1. Импортируйте необходимые ссылки.
Прежде чем начать, убедитесь, что вы импортировали необходимые ссылки для использования Aspose.Words for .NET в свой проект. Это включает в себя импорт библиотеки Aspose.Words и добавление необходимых пространств имен в исходный файл.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Шаг 2. Создайте новый документ и генератор документов.
 На этом этапе мы создадим новый документ, используя`Document` класс и построитель документов с использованием`DocumentBuilder` класс.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 3. Вставьте объект OLE в виде значка.
 Используйте конструктор документов`InsertOleObjectAsIcon`метод для вставки объекта OLE в виде значка в документ. Укажите путь к файлу OLE, флаг отображения, путь к значку и имя внедренного объекта.

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

## Шаг 4. Сохраните документ.
 Используйте документ`Save` метод сохранения документа в файл.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

### Пример исходного кода для вставки объекта OLE в виде значка с помощью Aspose.Words для .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

Это полный пример кода для вставки объекта OLE в виде значка с помощью Aspose.Words для .NET. Обязательно импортируйте необходимые ссылки и выполните ранее описанные шаги, чтобы интегрировать этот код в свой проект.

## Заключение

В заключение мы рассмотрели пошаговое руководство по вставке объекта OLE в виде значка в документ Word с помощью Aspose.Words для .NET.

Выполнив эти шаги, вы сможете успешно вставить объект OLE в качестве значка в документы Word с помощью Aspose.Words для .NET. Обязательно импортируйте необходимые ссылки и внимательно следуйте инструкциям, чтобы получить желаемые результаты.

### Часто задаваемые вопросы по вставке объекта ole в документ Word в виде значка

#### Вопрос. Какие ссылки необходимы для вставки объекта OLE в качестве значка в документ Word с помощью Aspose.Words for .NET?

О: Чтобы использовать Aspose.Words для .NET, вам необходимо импортировать в свой проект следующие ссылки:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### Вопрос. Как создать новый документ и генератор документов в Aspose.Words для .NET?

 О: Вы можете создать новый документ, используя`Document` класс и построитель документов с использованием`DocumentBuilder` класс. Вот пример:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### Вопрос. Как вставить объект OLE в качестве значка в документ?

 A: Используйте Document Builder`InsertOleObjectAsIcon` метод для вставки объекта OLE в виде значка. Укажите путь к файлу OLE, флаг отображения, путь к значку и имя внедренного объекта. Вот пример:

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

#### Вопрос. Как сохранить документ со вставленным в виде значка объектом OLE?

 A: Используйте документ`Save` метод сохранения документа в файл. Вот пример:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```