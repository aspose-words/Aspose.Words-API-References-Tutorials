---
title: Предпочтительный тип элемента управления в документе Word
linktitle: Предпочтительный тип элемента управления в документе Word
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по указанию предпочтительного типа элемента управления в документе Word при загрузке HTML-документа с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-htmlloadoptions/preferred-control-type/
---
В этой статье представлено пошаговое руководство по использованию функции предпочтительного типа управления с Aspose.Words для .NET. Мы подробно объясним каждую часть кода. В конце этого руководства вы сможете понять, как указать предпочтительный тип элемента управления при загрузке HTML-документа.

Прежде чем начать, убедитесь, что вы установили и настроили библиотеку Aspose.Words for .NET в своем проекте. Вы можете найти библиотеку и инструкции по установке на сайте Aspose.

## Шаг 1. Определите HTML-код

 Для начала вам необходимо определить HTML-код, который вы хотите загрузить в качестве документа. В этом примере мы определили`html` переменная, содержащая HTML-код селектора с опциями.

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

 Далее мы создаем`HtmlLoadOptions` объект и установите`PreferredControlType`собственность`HtmlControlType.StructuredDocumentTag`. Это говорит Aspose.Words использовать StructuredDocumentTags для представления HTML при загрузке.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };
```

## Шаг 3. Загрузите и сохраните документ.

 Мы используем`Document` класс для загрузки HTML-кода из потока памяти с параметрами загрузки, определенными ранее. Затем сохраняем документ в указанном каталоге с именем`.docx`формат файла.

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);
doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);
```

### Пример исходного кода для предпочтительного типа управления с помощью Aspose.Words для .NET

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

Вот и все! Вы успешно указали предпочтительный тип элемента управления при загрузке HTML-документа с помощью Aspose.Words для .NET.

## Заключение

 Следуя этому пошаговому руководству, вы узнали, как использовать функцию «Предпочитаемый тип управления» в Aspose.Words для .NET, чтобы указать желаемый тип элемента управления при загрузке HTML-документа. Установка`PreferredControlType`собственность`HtmlControlType.StructuredDocumentTag` Позволяет Aspose.Words использовать StructuredDocumentTags (SDT) для лучшего представления и обработки HTML-контента. Вы также можете изучить другие типы управления в соответствии с вашими конкретными требованиями. Использование этой функции помогает обеспечить точную и эффективную обработку HTML-документов в вашем приложении C# с помощью Aspose.Words.

### Часто задаваемые вопросы по предпочтительному типу элемента управления в документе Word

#### Вопрос: Что такое функция «Предпочитаемый тип управления» в Aspose.Words для .NET?

О: Функция «Предпочитаемый тип элемента управления» позволяет вам указать предпочтительный тип элемента управления для представления элементов HTML при загрузке документа HTML. Это помогает выбрать подходящий тип элемента управления для лучшего представления и обработки HTML-контента.

#### Вопрос: Как установить предпочтительный тип элемента управления при загрузке HTML-документа?

 О: Чтобы установить предпочтительный тип управления, вам необходимо создать`HtmlLoadOptions` объект и установите его`PreferredControlType` собственность на желаемое`HtmlControlType` . В приведенном примере`HtmlControlType.StructuredDocumentTag` используется.

#### Вопрос: В чем важность использования StructuredDocumentTags (SDT) в качестве предпочтительного типа элемента управления?

Ответ: StructuredDocumentTags (SDT) — это элементы на основе XML, которые можно использовать для представления сложного содержимого и элементов управления в документе Word. Использование SDT в качестве предпочтительного элемента управления типом может обеспечить лучшую совместимость и представление содержимого HTML.

#### Вопрос: Как я могу гарантировать, что Aspose.Words использует предпочтительный тип элемента управления при загрузке HTML-документа?

 О: Установив`PreferredControlType`собственность`HtmlControlType.StructuredDocumentTag`как показано в примере исходного кода, Aspose.Words будет использовать SDT для представления элементов HTML при загрузке документа.

#### Вопрос: Могу ли я использовать другие типы управления в качестве предпочтительного варианта?

 О: Да, кроме`HtmlControlType.StructuredDocumentTag` , Aspose.Words для .NET поддерживает другие типы элементов управления, такие как`HtmlControlType.ContentControl` и`HtmlControlType.CustomXmlMarkup`.