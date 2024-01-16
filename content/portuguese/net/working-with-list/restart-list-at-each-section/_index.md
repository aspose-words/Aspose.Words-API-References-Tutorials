---
title: Lista de reinicialização em cada seção
linktitle: Lista de reinicialização em cada seção
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como redefinir uma lista numerada para cada seção de um documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-list/restart-list-at-each-section/
---

Neste tutorial passo a passo, mostraremos como redefinir uma lista numerada para cada seção de um documento do Word usando Aspose.Words for .NET. Explicaremos o código-fonte C# fornecido e mostraremos como implementá-lo em seus próprios projetos.

 Para começar, certifique-se de ter o Aspose.Words for .NET instalado e configurado em seu ambiente de desenvolvimento. Se ainda não o fez, baixe e instale a biblioteca em[Aspose.Releases]https://releases.aspose.com/words/net/.

## Etapa 1: Criando o Documento e a Lista

Primeiro, crie um novo documento e adicione uma lista numerada padrão:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;
```

## Passo 2: Adicionando itens à lista

 Então use um`DocumentBuilder` para adicionar itens à lista. Você pode usar um loop para adicionar vários itens à lista:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
     builder.Writeln($"List item {i}");

     if (i == 15)
         builder.InsertBreak(BreakType.SectionBreakNewPage);
}
```

Neste exemplo, estamos inserindo uma quebra de seção após o 15º item da lista para ilustrar a renumeração.

## Etapa 3: salve o documento modificado

Por fim, salve o documento modificado:

```csharp
OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);
```

Então ! Você redefiniu com êxito uma lista numerada para cada seção em um documento do Word usando Aspose.Words for .NET.

### Exemplo de código-fonte para redefinir a lista em cada seção

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;

DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
	 builder.Writeln($"List item {i}");

	 if (i == 15)
		 builder.InsertBreak(BreakType.SectionBreakNewPage);
}

OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);

```

Sinta-se à vontade para usar este código em seus próprios projetos e modificá-lo para atender às suas necessidades específicas.

### Perguntas frequentes

#### P: Como posso reiniciar uma lista em cada seção do Aspose.Words?

 R: Para reiniciar uma lista em cada seção do Aspose.Words, você precisa criar uma instância do`List` classe e atribua uma lista numerada a ela. Então você pode usar o`List.IsRestartAtEachSection` propriedade para especificar que a numeração deve ser reiniciada em cada seção. Você pode associar esta lista a uma ou mais seções do seu documento para que a numeração seja reiniciada corretamente a cada seção.

#### P: Posso personalizar o formato de numeração das listas no Aspose.Words?

R: Sim, você pode personalizar o formato de numeração das listas no Aspose.Words. O`List` class oferece diversas propriedades para isso, como`List.ListFormat.ListType`, `List.ListLevels`, `ListLevel.NumberFormat`, etc. Você pode usar essas propriedades para definir o tipo de lista (numerada, com marcadores, etc.), formato de numeração (algarismos arábicos, algarismos romanos, letras, etc.) e outras opções de formatação de numeração.

#### P: É possível adicionar níveis adicionais a uma lista numerada no Aspose.Words?

 R: Sim, é possível adicionar níveis adicionais a uma lista numerada no Aspose.Words. O`ListLevel` class permite definir propriedades de formatação para cada nível da lista. Você pode definir opções como prefixo, sufixo, alinhamento, recuo, etc. Isso permite criar listas com vários níveis de hierarquia.