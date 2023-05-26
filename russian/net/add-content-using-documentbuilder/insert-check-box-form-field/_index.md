---
title: Вставить поле формы флажка
linktitle: Вставить поле формы флажка
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как вставлять поля формы флажка в документы Word с помощью Aspose.Words для .NET. Пошаговое руководство.
type: docs
weight: 10
url: /ru/net/add-content-using-documentbuilder/insert-check-box-form-field/
---

В этом подробном руководстве вы узнаете, как вставить поле формы флажка в документ Word с помощью Aspose.Words для .NET. Мы проведем вас через весь процесс и предоставим необходимые фрагменты кода C#. К концу этого руководства вы сможете добавлять поля форм флажков с настраиваемыми свойствами в свои документы.

## Предпосылки
Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:
- В вашей системе установлена библиотека Aspose.Words for .NET.

## Шаг 1: Создайте новый документ и DocumentBuilder
Для начала создайте новый документ с помощью класса Document и инициализируйте объект DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 2. Вставьте поле формы с флажком
Затем используйте метод InsertCheckBox класса DocumentBuilder, чтобы вставить поле формы флажка. Укажите имя, проверенное состояние, состояние по умолчанию и параметры размера в качестве аргументов:

```csharp
builder.InsertCheckBox("CheckBox", true, true, 0);
```

## Шаг 3: Сохраните документ
После вставки поля формы флажка сохраните документ в файл с помощью метода Save класса Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertCheckBoxFormField.docx");
```

### Пример исходного кода для поля формы «Вставить флажок» с использованием Aspose.Words для .NET
Вот полный исходный код для вставки поля формы флажка с использованием Aspose.Words для .NET:

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.InsertCheckBox("CheckBox", true, true, 0);

	doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertCheckBoxFormField.docx");
	
```

Не забудьте настроить код в соответствии с вашими конкретными требованиями и добавить в него дополнительные функции по мере необходимости.

## Заключение
Поздравляем! Вы успешно научились вставлять поле формы флажка в документ Word, используя Aspose.Words для .NET. Следуя пошаговому руководству и используя предоставленный исходный код, теперь вы можете дополнить свои документы интерактивными полями формы флажков.
