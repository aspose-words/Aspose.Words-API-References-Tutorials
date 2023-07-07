---
title: Чтение свойств Active XControl из файла Word
linktitle: Чтение свойств Active XControl из файла Word
second_title: Справочник по API Aspose.Words для .NET
description: Чтение свойств элементов управления ActiveX в файле Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---

В этом пошаговом руководстве мы покажем вам, как читать свойства элементов управления ActiveX в файле Word с помощью Aspose.Words для .NET. Мы предоставим вам полный исходный код и покажем, как форматировать выходные данные уценки.

## Шаг 1: Инициализация документа

 Первым шагом является инициализация`Document` объект, загрузив документ Word, содержащий элементы управления ActiveX. Обязательно замените`MyDir` с фактическим путем к каталогу, содержащему документ.

```csharp
Document doc = new Document(MyDir + "ActiveX controls.docx");
```

## Шаг 2. Восстановите элементы управления ActiveX

 На этом шаге мы пройдемся по каждому`Shape` документа, чтобы получить элементы управления ActiveX и прочитать их свойства.

```csharp
string properties = "";
foreach(Shape shape in doc.GetChildNodes(NodeType.Shape, true))
{
     if (shape.OleFormat is null) break;

     OleControl oleControl = shape.OleFormat.OleControl;
     if (oleControl.IsForms2OleControl)
     {
         Forms2OleControl checkBox = (Forms2OleControl)oleControl;
         properties = properties + "\nCaption: " + checkBox.Caption;
         properties = properties + "\nValue: " + checkBox.Value;
         properties = properties + "\nEnabled: " + checkBox.Enabled;
         properties = properties + "\nType: " + checkBox.Type;
         if (checkBox. ChildNodes != null)
         {
             properties = properties + "\nChildNodes: " + checkBox.ChildNodes;
         }

         properties += "\n";
     }
}

properties = properties + "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
Console.WriteLine("\n" + properties);
```

### Пример исходного кода для чтения свойств Active XControl с использованием Aspose.Words для .NET

Вот полный исходный код для чтения свойств элементов управления ActiveX с использованием Aspose.Words для .NET:

```csharp
	Document doc = new Document(MyDir + "ActiveX controls.docx");

	string properties = "";
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
	{
		if (shape.OleFormat is null) break;

		OleControl oleControl = shape.OleFormat.OleControl;
		if (oleControl.IsForms2OleControl)
		{
			Forms2OleControl checkBox = (Forms2OleControl) oleControl;
			properties = properties + "\nCaption: " + checkBox.Caption;
			properties = properties + "\nValue: " + checkBox.Value;
			properties = properties + "\nEnabled: " + checkBox.Enabled;
			properties = properties + "\nType: " + checkBox.Type;
			if (checkBox.ChildNodes != null)
			{
				properties = properties + "\nChildNodes: " + checkBox.ChildNodes;
			}

			properties += "\n";
		}
	}

	properties = properties + "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
	Console.WriteLine("\n" + properties);
```

## Заключение

В этом руководстве показано, как читать свойства элементов управления ActiveX в файле Word с помощью Aspose.Words для .NET. Следуя описанным шагам, вы можете инициализировать документ, получить элементы управления ActiveX и прочитать их свойства. Используйте образец кода, предоставленный в качестве отправной точки, и настройте его в соответствии со своими потребностями.

Чтение свойств элементов управления ActiveX позволяет извлекать важную информацию из файлов Word, содержащих эти элементы управления. Aspose.Words for .NET предлагает мощные функции для работы с элементами управления ActiveX и автоматизации обработки документов.

### Часто задаваемые вопросы

#### Вопрос. Что нужно сделать в первую очередь, чтобы прочитать свойства элементов управления ActiveX в файле Word?

 A: Первым шагом является инициализация`Document` объект, загрузив документ Word, содержащий элементы управления ActiveX. Обязательно замените`MyDir` с фактическим путем к каталогу, содержащему документ.

#### Вопрос. Как добавить элементы управления ActiveX в документ?

 О: Чтобы получить элементы управления ActiveX, вам необходимо выполнить итерацию по каждому элементу.`Shape` документа и проверьте, является ли он элементом управления ActiveX. Использовать`OleFormat` свойство`Shape` чтобы получить доступ к`OleControl` объект и получить необходимые свойства.

#### Вопрос. Какие свойства элементов ActiveX можно прочитать?

О: Вы можете прочитать различные свойства элементов управления ActiveX, такие как заголовок, значение, включенное или отключенное состояние, тип и дочерние узлы, связанные с элементом управления.

#### Вопрос. Как получить общее количество элементов управления ActiveX в документе?

 A: Чтобы получить общее количество элементов управления ActiveX в документе, вы можете использовать`GetChildNodes` метод`Document` объект, определяющий`NodeType.Shape` type и включая дочерние узлы.