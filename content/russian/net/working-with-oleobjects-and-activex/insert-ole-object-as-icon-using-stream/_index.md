---
title: Вставьте объект Ole как значок с помощью потока
linktitle: Вставьте объект Ole как значок с помощью потока
second_title: API обработки документов Aspose.Words
description: Узнайте, как вставить объект OLE в виде значка с помощью потока с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon-using-stream/
---

Ниже приведено пошаговое руководство, объясняющее приведенный ниже исходный код C#, в котором показано, как вставить объект OLE в виде значка с помощью потока с помощью Aspose.Words для .NET.

## Шаг 1. Импортируйте необходимые ссылки.
Прежде чем начать, убедитесь, что вы импортировали необходимые ссылки для использования Aspose.Words for .NET в свой проект. Это включает в себя импорт библиотеки Aspose.Words и добавление необходимых пространств имен в исходный файл.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

## Шаг 2. Создайте новый документ и генератор документов.
 На этом этапе мы создадим новый документ, используя`Document` класс и построитель документов с использованием`DocumentBuilder` сорт.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 3. Вставьте объект OLE в виде значка из потока.
 Используйте конструктор документов`InsertOleObjectAsIcon` метод для вставки объекта OLE в виде значка из потока в документ. Укажите поток данных, тип объекта, путь к значку и имя внедренного объекта.

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

## Шаг 4. Сохраните документ.
 Используйте документ`Save` метод сохранения документа в файл.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

### Пример исходного кода для вставки объекта OLE в виде значка с использованием потока с помощью Aspose.Words для .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

Это полный пример кода для вставки объекта OLE в виде значка с использованием потока с помощью Aspose.Words для .NET. Обязательно импортируйте необходимые ссылки и выполните ранее описанные шаги, чтобы интегрировать этот код в свой проект.

## Заключение

В приведенном выше пошаговом руководстве объясняется, как вставить объект OLE в виде значка в документ Word с помощью потока с помощью Aspose.Words для .NET. Выполнив описанные шаги, вы сможете интегрировать эту функциональность в свой проект. Обязательно импортируйте необходимые ссылки, создайте новый документ и генератор документов, вставьте объект OLE в виде значка из потока, затем сохраните документ. Используйте предоставленный пример кода в качестве отправной точки и настройте его в соответствии со своими потребностями.

### Часто задаваемые вопросы

#### Вопрос. Как импортировать необходимые ссылки для использования Aspose.Words for .NET?

A. Чтобы импортировать необходимые ссылки, необходимо выполнить следующие действия:

 Добавьте следующее`using` утверждения в верхней части исходного файла:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```
Убедитесь, что вы добавили библиотеку Aspose.Words в свой проект.

#### Вопрос. Как создать новый документ и построитель документов с помощью Aspose.Words for .NET?

A. Чтобы создать новый документ и генератор документов, вы можете выполнить следующие шаги:

 Использовать`Document` класс для создания нового документа:

```csharp
Document doc = new Document();
```
 Использовать`DocumentBuilder` класс для создания построителя документов, связанного с ранее созданным документом:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### Вопрос. Как вставить объект OLE в виде значка из потока с помощью Aspose.Words для .NET?

A. Чтобы вставить объект OLE в виде значка из потока, вы можете выполнить следующие действия:

 Использовать`InsertOleObjectAsIcon` метод генератора документов для вставки объекта OLE:

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
  builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

#### В. Как сохранить документ в файл?

A.  Чтобы сохранить документ в файл, вы можете использовать команду`Save` метод документа, определяющий путь назначения:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

#### Вопрос. Как внедрить код для вставки объекта OLE в виде значка из потока в мой проект?

A. Чтобы внедрить код для вставки OLE-объекта в виде значка из потока в ваш проект, выполните следующие действия:
- Импортируйте необходимые ссылки, добавив соответствующие`using` заявления.
-  Создайте новый документ и построитель документов, используя`Document` и`DocumentBuilder` занятия.
- Используйте код для вставки объекта OLE в виде значка из потока.
-  Сохраните документ с помощью`Save` метод с соответствующим путем назначения.

Выполнив эти шаги, вы сможете успешно вставить объект OLE в виде значка из потока с помощью Aspose.Words для .NET. Обязательно следуйте инструкциям и импортируйте необходимые ссылки, чтобы получить желаемые результаты.