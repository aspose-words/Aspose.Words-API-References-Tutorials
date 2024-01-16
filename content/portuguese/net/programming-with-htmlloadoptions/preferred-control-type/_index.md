---
title: Tipo de controle preferido em documento do Word
linktitle: Tipo de controle preferido em documento do Word
second_title: API de processamento de documentos Aspose.Words
description: Guia passo a passo para especificar o tipo de controle preferido em um documento Word ao carregar um documento HTML com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-htmlloadoptions/preferred-control-type/
---
Este artigo fornece um guia passo a passo sobre como usar o recurso de tipo de controle preferencial com Aspose.Words for .NET. Explicaremos cada parte do código em detalhes. Ao final deste tutorial, você poderá entender como especificar o tipo de controle preferido ao carregar um documento HTML.

Antes de começar, certifique-se de ter instalado e configurado a biblioteca Aspose.Words for .NET em seu projeto. Você pode encontrar a biblioteca e as instruções de instalação no site do Aspose.

## Passo 1: Defina o código HTML

 Para começar, você precisa definir o código HTML que deseja carregar como documento. Neste exemplo, definimos um`html` variável contendo o código HTML de um seletor com opções.

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

## Etapa 2: definir opções de carregamento de HTML

 A seguir, criamos um`HtmlLoadOptions` objeto e definir o`PreferredControlType`propriedade para`HtmlControlType.StructuredDocumentTag`. Isso diz ao Aspose.Words para usar StructuredDocumentTags para representar HTML durante o carregamento.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };
```

## Etapa 3: carregue e salve o documento

 Nós usamos o`Document` classe para carregar código HTML de um fluxo de memória com as opções de carregamento definidas anteriormente. Em seguida, salvamos o documento no diretório especificado com o`.docx`formato de arquivo.

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);
doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);
```

### Exemplo de código-fonte para tipo de controle preferido com Aspose.Words for .NET

```csharp
	
	const string html = @"
		<html>
			<select name='ComboBox' size='1'>
				<option value='val1'>item1</option>
				<option value='val2'></option>                        
			</select>
		</html>
	";
	// O caminho para o diretório de documentos.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };

	Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);

	doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);

```

Isso é tudo ! Você especificou com sucesso o tipo de controle preferido ao carregar um documento HTML com Aspose.Words for .NET.

## Conclusão

 Seguindo este guia passo a passo, você aprendeu como usar o recurso "Tipo de controle preferencial" no Aspose.Words for .NET para especificar o tipo de controle desejado ao carregar um documento HTML. Configurando o`PreferredControlType`propriedade para`HtmlControlType.StructuredDocumentTag` permite que Aspose.Words use StructuredDocumentTags (SDT) para melhor representação e processamento de conteúdo HTML. Você também pode explorar outros tipos de controle para atender às suas necessidades específicas. O uso desse recurso ajuda a garantir o manuseio preciso e eficiente de documentos HTML em seu aplicativo C# com Aspose.Words.

### Perguntas frequentes sobre o tipo de controle preferido em documentos do Word

#### P: Qual é o recurso "Tipo de controle preferencial" no Aspose.Words for .NET?

R: O recurso "Tipo de controle preferencial" permite especificar o tipo preferido de controle para representar elementos HTML ao carregar um documento HTML. Ajuda na seleção do tipo de controle apropriado para melhor representação e processamento do conteúdo HTML.

#### P: Como defino o tipo de controle preferido ao carregar um documento HTML?

 R: Para definir o tipo de controle preferido, você precisa criar um`HtmlLoadOptions` objeto e definir seu`PreferredControlType` propriedade ao desejado`HtmlControlType` . No exemplo fornecido,`HtmlControlType.StructuredDocumentTag` é usado.

#### P: Qual é a importância de usar StructuredDocumentTags (SDT) como tipo de controle preferencial?

R: StructuredDocumentTags (SDT) são elementos baseados em XML que podem ser usados para representar conteúdo e controles complexos em um documento do Word. Usar SDTs como tipo de controle preferencial pode fornecer melhor compatibilidade e representação do conteúdo HTML.

#### P: Como posso garantir que Aspose.Words use o tipo de controle preferido ao carregar o documento HTML?

 R: Ao definir o`PreferredControlType`propriedade para`HtmlControlType.StructuredDocumentTag`conforme mostrado no código-fonte de exemplo, Aspose.Words usará SDTs para representar elementos HTML ao carregar o documento.

#### P: Posso usar outros tipos de controle como opção preferencial?

 R: Sim, além de`HtmlControlType.StructuredDocumentTag` , Aspose.Words for .NET oferece suporte a outros tipos de controle, como`HtmlControlType.ContentControl` e`HtmlControlType.CustomXmlMarkup`.