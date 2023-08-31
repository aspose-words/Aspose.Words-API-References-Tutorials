---
title: Предпочтительный тип элемента управления в документе Word
linktitle: Предпочтительный тип элемента управления в документе Word
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по указанию предпочтительного типа элемента управления в документе Word при загрузке документа HTML с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-htmlloadoptions/preferred-control-type/
---
В этой статье представлено пошаговое руководство по использованию функции предпочтительного типа элемента управления с Aspose.Words для .NET. Мы подробно объясним каждую часть кода. В конце этого руководства вы сможете понять, как указать предпочтительный тип элемента управления при загрузке HTML-документа.

Прежде чем начать, убедитесь, что вы установили и настроили библиотеку Aspose.Words for .NET в своем проекте. Вы можете найти библиотеку и инструкции по установке на веб-сайте Aspose.

## Шаг 1. Определите HTML-код

 Для начала вам нужно определить код HTML, который вы хотите загрузить как документ. В этом примере мы определили`html` переменная, содержащая HTML-код селектора с опциями.

```csharp
const string html=@"
<html>
<select name='ComboBox' size='1'>
<option value='val1'>item1</option>
<option value='val2'></option>
</select>
</html>
";
```

## Шаг 2. Установите параметры загрузки HTML

 Далее мы создаем`HtmlLoadOptions` объект и установить`PreferredControlType` собственность на`HtmlControlType.StructuredDocumentTag`. Это говорит Aspose.Words использовать StructuredDocumentTags для представления HTML при загрузке.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };
```

## Шаг 3: Загрузите и сохраните документ

 Мы используем`Document` класс для загрузки HTML-кода из потока памяти с параметрами загрузки, определенными ранее. Затем мы сохраняем документ в указанную директорию с`.docx`формат файла.

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);
doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);
```

### Пример исходного кода для предпочтительного типа элемента управления с Aspose.Words для .NET

```csharp
	
	const string html = @"
		<html>
			<select name='ComboBox' size='1'>
				<option value='val1'>item1</option>
				<option value='val2'></option>                        
			</select>
		</html>
	";
	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };

	Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);

	doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);

```

Вот и все ! Вы успешно указали предпочтительный тип элемента управления при загрузке HTML-документа с помощью Aspose.Words для .NET.

## Заключение

 Следуя этому пошаговому руководству, вы узнали, как использовать функцию «Предпочитаемый тип элемента управления» в Aspose.Words для .NET, чтобы указать желаемый тип элемента управления при загрузке HTML-документа. Настройка`PreferredControlType` собственность на`HtmlControlType.StructuredDocumentTag` позволяет Aspose.Words использовать StructuredDocumentTags (SDT) для лучшего представления и обработки содержимого HTML. Вы также можете изучить другие типы элементов управления в соответствии с вашими конкретными требованиями. Использование этой функции помогает обеспечить точную и эффективную обработку документов HTML в вашем приложении C# с помощью Aspose.Words.

### Часто задаваемые вопросы по предпочтительному типу управления в документе Word

#### В: Что такое функция «Предпочтительный тип элемента управления» в Aspose.Words для .NET?

О: Функция «Предпочитаемый тип элемента управления» позволяет указать предпочтительный тип элемента управления для представления элементов HTML при загрузке документа HTML. Это помогает выбрать соответствующий тип элемента управления для лучшего представления и обработки содержимого HTML.

#### В: Как установить предпочтительный тип элемента управления при загрузке HTML-документа?

 О: Чтобы установить предпочтительный тип управления, вам необходимо создать`HtmlLoadOptions` объект и установить его`PreferredControlType` свойство до желаемого`HtmlControlType` . В приведенном примере`HtmlControlType.StructuredDocumentTag` используется.

#### Вопрос: Каково значение использования StructuredDocumentTags (SDT) в качестве предпочтительного типа элемента управления?

A: StructuredDocumentTags (SDT) — это элементы на основе XML, которые можно использовать для представления сложного содержимого и элементов управления в документе Word. Использование SDT в качестве предпочтительного типа элемента управления может обеспечить лучшую совместимость и представление содержимого HTML.

#### В: Как я могу убедиться, что Aspose.Words использует предпочтительный тип элемента управления при загрузке HTML-документа?

 О: Установив`PreferredControlType` собственность на`HtmlControlType.StructuredDocumentTag`как показано в исходном коде примера, Aspose.Words будет использовать SDT для представления элементов HTML при загрузке документа.

#### В: Могу ли я использовать другие типы управления в качестве предпочтительного варианта?

 О: Да, кроме`HtmlControlType.StructuredDocumentTag` , Aspose.Words for .NET поддерживает другие типы элементов управления, такие как`HtmlControlType.ContentControl` и`HtmlControlType.CustomXmlMarkup`.