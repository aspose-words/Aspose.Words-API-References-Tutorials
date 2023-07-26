---
title: Вставьте объект Ole в виде значка с помощью потока
linktitle: Вставьте объект Ole в виде значка с помощью потока
second_title: API обработки документов Aspose.Words
description: Узнайте, как вставить объект OLE в качестве значка с помощью потока с Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon-using-stream/
---

Ниже приведено пошаговое руководство по объяснению приведенного ниже исходного кода C#, которое иллюстрирует, как вставить объект OLE в качестве значка с помощью потока с Aspose.Words для .NET.

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

## Шаг 3. Вставьте объект OLE в качестве значка из потока
 Используйте конструктор документов`InsertOleObjectAsIcon` метод для вставки объекта OLE в качестве значка из потока в документ. Укажите поток данных, тип объекта, путь к значку и имя встроенного объекта.

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

## Шаг 4: Сохраните документ
 Используйте документ`Save` метод сохранения документа в файл.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

### Пример исходного кода для вставки объекта OLE в качестве значка с использованием потока с Aspose.Words для .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

Это полный пример кода для вставки объекта OLE в качестве значка с использованием потока с Aspose.Words для .NET. Обязательно импортируйте необходимые ссылки и выполните шаги, описанные ранее, чтобы интегрировать этот код в свой проект.

## Заключение

В приведенном выше пошаговом руководстве объясняется, как вставить объект OLE в качестве значка в документ Word, используя поток с Aspose.Words для .NET. Следуя описанным шагам, вы сможете интегрировать эту функциональность в свой проект. Обязательно импортируйте необходимые ссылки, создайте новый документ и генератор документов, вставьте объект OLE в качестве значка из потока, а затем сохраните документ. Используйте образец кода, предоставленный в качестве отправной точки, и настройте его в соответствии со своими потребностями.

### Часто задаваемые вопросы

#### В. Как импортировать необходимые ссылки для использования Aspose.Words for .NET?

A. Чтобы импортировать необходимые ссылки, необходимо выполнить следующие действия:

 Добавьте следующее`using` утверждения в верхней части исходного файла:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```
Убедитесь, что вы добавили библиотеку Aspose.Words в свой проект.

#### В. Как создать новый документ и конструктор документов с помощью Aspose.Words для .NET?

A. Чтобы создать новый документ и генератор документов, выполните следующие действия:

 Использовать`Document` класс для создания нового документа:

```csharp
Document doc = new Document();
```
 Использовать`DocumentBuilder` класс для создания построителя документов, связанного с ранее созданным документом:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### В. Как вставить объект OLE в качестве значка из потока с помощью Aspose.Words для .NET?

A. Чтобы вставить объект OLE в качестве значка из потока, выполните следующие действия.

 Использовать`InsertOleObjectAsIcon` метод генератора документов для вставки объекта OLE:

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
  builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

#### В. Как сохранить документ в файл?

A.  Чтобы сохранить документ в файл, вы можете использовать`Save` метод документа, указывающий путь назначения:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

#### Вопрос. Как внедрить код для вставки объекта OLE в качестве значка из потока в мой проект?

A. Чтобы внедрить код для вставки объекта OLE в качестве значка из потока в ваш проект, выполните следующие действия:
- Импортируйте необходимые ссылки, добавив соответствующие`using` заявления.
-  Создайте новый документ и построитель документов, используя`Document` и`DocumentBuilder` классы.
- Используйте код для вставки объекта OLE в качестве значка из потока.
-  Сохраните документ с помощью`Save` метод с соответствующим путем назначения.

Выполнив эти шаги, вы сможете успешно вставить объект OLE в качестве значка из потока с помощью Aspose.Words для .NET. Обязательно следуйте инструкциям и импортируйте необходимые ссылки, чтобы получить желаемые результаты.