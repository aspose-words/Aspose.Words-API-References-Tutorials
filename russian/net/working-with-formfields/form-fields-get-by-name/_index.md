---
title: Поля формы получают по имени
linktitle: Поля формы получают по имени
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как извлекать и изменять поля формы по имени в документах Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-formfields/form-fields-get-by-name/
---

В этом пошаговом руководстве мы расскажем, как использовать Aspose.Words для .NET для извлечения полей формы по имени из документа Word. Мы объясним предоставленный исходный код C# и покажем вам, как реализовать его в ваших собственных проектах.

Для начала убедитесь, что Aspose.Words for .NET установлен и настроен в вашей среде разработки. Если вы этого не сделали, скачайте и установите библиотеку с официального сайта.

## Шаг 1: Инициализация объекта документа

 Сначала инициализируйте`Document` объект, указав путь к исходному документу, содержащему поля формы:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");
```

## Шаг 2: Получение полей формы

 Далее войдите в`FormFields` собственность`Range` объект в документе, чтобы получить все поля формы:

```csharp
FormFieldCollection documentFormFields = doc.Range.FormFields;
```

Вы можете получить поля формы либо по индексу, либо по имени. В этом примере мы получаем поле формы, используя оба метода:

```csharp
FormField formField1 = documentFormFields[3]; // Получение по индексу
FormField formField2 = documentFormFields["Text2"]; // Получение по имени
```

## Шаг 3. Изменение свойств поля формы

 После того, как вы получили поля формы, вы можете изменить их свойства по мере необходимости. В этом примере мы меняем размер шрифта`formField1` до 20 и цвет шрифта`formField2` к красному:

```csharp
formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;
```

## Шаг 4: Сохранение документа

Наконец, сохраните измененный документ:

```csharp
doc.Save(dataDir + "ModifiedFormFields.docx");
```

Вот и все! Вы успешно извлекли поля формы по имени и изменили их свойства в документе Word с помощью Aspose.Words для .NET.

### Пример исходного кода для получения полей формы по имени с использованием Aspose.Words для .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");

FormFieldCollection documentFormFields = doc.Range.FormFields;

FormField formField1 = documentFormFields[3];
FormField formField2 = documentFormFields["Text2"];

formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;

doc.Save(dataDir + "ModifiedFormFields.docx");
```

Не стесняйтесь использовать этот код в своих проектах и модифицировать его в соответствии с вашими конкретными требованиями.
