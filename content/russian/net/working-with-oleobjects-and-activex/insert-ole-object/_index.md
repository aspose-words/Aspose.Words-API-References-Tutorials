---
title: Вставить объект Ole в документ Word
linktitle: Вставить объект Ole в документ Word
second_title: API обработки документов Aspose.Words
description: Узнайте, как вставить объект OLE в документ Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-oleobjects-and-activex/insert-ole-object/
---

Ниже приведено пошаговое руководство, объясняющее приведенный ниже исходный код C#, который иллюстрирует, как вставить объект OLE в документ Word с помощью Aspose.Words для .NET.

## Шаг 1. Импортируйте необходимые ссылки.
Прежде чем начать, убедитесь, что вы импортировали необходимые ссылки для использования Aspose.Words for .NET в свой проект. Это включает в себя импорт библиотеки Aspose.Words и добавление необходимых пространств имен в исходный файл.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Шаг 2. Создайте новый документ и генератор документов.
 На этом этапе мы создадим новый документ, используя`Document` класс и построитель документов с использованием`DocumentBuilder` сорт.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 3. Вставьте объект OLE
 Используйте конструктор документов`InsertOleObject`метод для вставки объекта OLE в документ. Укажите URL-адрес объекта OLE, тип объекта, параметры отображения и другие необходимые параметры.

```csharp
builder. InsertOleObject("http://www.aspose.com", "htmlfile", true, true, null);
```

## Шаг 4. Сохраните документ.
 Используйте документ`Save` метод сохранения документа в файл.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

### Пример исходного кода для вставки объекта OLE с помощью Aspose.Words для .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com", "htmlfile", true, true, null);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

Это полный пример кода для вставки объекта OLE с помощью Aspose.Words для .NET. Обязательно импортируйте необходимые ссылки и выполните ранее описанные шаги, чтобы интегрировать этот код в свой проект.

## Заключение

В заключение отметим, что вставка объектов OLE в документ Word — это мощная функция, предлагаемая Aspose.Words для .NET. Используя эту библиотеку, вы можете легко встраивать объекты OLE, такие как файлы HTML, электронные таблицы Excel, презентации PowerPoint и т. д., в свои документы Word.

В этой статье мы рассмотрели пошаговое руководство по объяснению исходного кода на C#, иллюстрирующего, как вставить объект OLE в документ Word. Мы рассмотрели необходимые ссылки, создание нового документа и генератора документов, а также шаги по вставке объекта OLE и сохранению документа.

### Часто задаваемые вопросы по вставке объекта OLE в документ Word

#### Вопрос: Какие учетные данные мне нужно импортировать, чтобы использовать Aspose.Words for .NET?

О: Чтобы использовать Aspose.Words для .NET, вам необходимо импортировать следующие ссылки:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### Вопрос: Как создать новый документ и генератор документов?

 О: Вы можете создать новый документ, используя`Document` класс и построитель документов с использованием`DocumentBuilder` класс, как показано ниже:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### Вопрос: Как вставить объект OLE в документ?

 А: Используйте`InsertOleObject` метод конструктора документов (`DocumentBuilder`), чтобы вставить объект OLE в документ. Укажите URL-адрес объекта OLE, тип объекта, параметры отображения и другие необходимые параметры. Вот пример:

```csharp
builder. InsertOleObject("http://www.aspose.com", "htmlfile", true, true, null);
```

#### Вопрос: Как сохранить документ?

 A: Используйте документ`Save`метод сохранения документа в файл. Вот пример:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

#### Вопрос: Можете ли вы предоставить полный пример вставки объекта OLE с помощью Aspose.Words для .NET?

О: Вот полный пример кода для вставки объекта OLE с помощью Aspose.Words для .NET. Обязательно импортируйте необходимые ссылки и выполните ранее описанные шаги, чтобы интегрировать этот код в свой проект:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com", "htmlfile", true, true, null);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```
