---
title: Especifique o nível da lista
linktitle: Especifique o nível da lista
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como especificar o nível da lista em um documento do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-list/specify-list-level/
---

Neste tutorial passo a passo, mostraremos como especificar o nível de lista em um documento do Word usando Aspose.Words for .NET. Explicaremos o código-fonte C# fornecido e mostraremos como implementá-lo em seus próprios projetos.

 Para começar, certifique-se de ter o Aspose.Words for .NET instalado e configurado em seu ambiente de desenvolvimento. Se ainda não o fez, baixe e instale a biblioteca em[Aspose.Releases]https://releases.aspose.com/words/net/.

## Etapa 1: Criando o Documento e o Gerador de Documentos

Primeiro, crie um novo documento e um gerador de documentos associado:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 2: Criando e aplicando uma lista numerada

Em seguida, crie uma lista numerada com base em um dos modelos de lista do Microsoft Word e aplique-a ao parágrafo atual no construtor de documentos:

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);
```

## Etapa 3: Especificação do nível de lista

 Use o construtor de documentos`ListLevelNumber` propriedade para especificar o nível da lista e adicionar texto ao parágrafo:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

Repita essas etapas para especificar os níveis da lista e adicionar texto em cada nível.

## Etapa 4: Criando e aplicando uma lista com marcadores

Você também pode criar e aplicar uma lista com marcadores usando um dos modelos de lista do Microsoft Word:

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);
```

## Etapa 5: adicionar texto aos níveis da lista com marcadores

 Use o`ListLevelNumber` propriedade novamente para especificar o nível da lista com marcadores e adicionar texto:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

## Etapa 6: parar de formatar a lista

 Para interromper a formatação da lista, defina`null` para o`List`propriedade do gerador de documentos:

```csharp
builder. ListFormat. List = null;
```

## Passo 7: Salvando o documento modificado

Salve o documento modificado:

```csharp
builder.Document.Save(dataDir + "SpecifyListLevel.docx");
```

Então ! Você especificou com êxito o nível da lista em um documento do Word usando Aspose.Words for .NET.

### Exemplo de código-fonte para especificar o nível da lista

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Crie uma lista numerada com base em um dos modelos de lista do Microsoft Word
// aplique-o ao parágrafo atual do construtor de documentos.
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);

// Existem nove níveis nesta lista, vamos experimentar todos eles.
for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// Crie uma lista com marcadores com base em um dos modelos de lista do Microsoft Word
// aplique-o ao parágrafo atual do construtor de documentos.
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);

for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// Esta é uma forma de interromper a formatação da lista.
builder.ListFormat.List = null;

builder.Document.Save(dataDir + "WorkingWithList.SpecifyListLevel.docx");
            
```

### Perguntas frequentes

#### P: Como posso especificar o nível da lista em Aspose.Words?

 R: Para especificar o nível da lista em Aspose.Words, você precisa criar uma instância do`List` classe e dê-lhe uma lista numerada. Então você pode usar o`Paragraph.ListFormat.ListLevelNumber` propriedade para especificar o nível de cada item da lista. Você pode associar esta lista a uma seção do seu documento para que os itens da lista tenham o nível desejado.

#### P: É possível alterar o formato de numeração dos itens da lista no Aspose.Words?

 R: Sim, você pode alterar o formato de numeração dos itens da lista em Aspose.Words. O`ListLevel` class oferece diversas propriedades para isso, como`ListLevel.NumberFormat`, `ListLevel.NumberStyle`, `ListLevel.NumberPosition`, etc. Você pode usar essas propriedades para definir o formato de numeração para itens de lista, como algarismos arábicos, algarismos romanos, letras, etc.

#### P: Posso adicionar níveis adicionais a uma lista numerada no Aspose.Words?

 R: Sim, é possível adicionar níveis adicionais a uma lista numerada no Aspose.Words. O`ListLevel`class permite definir propriedades de formatação para cada nível da lista. Você pode definir opções como prefixo, sufixo, alinhamento, recuo, etc. Isso permite criar listas com vários níveis de hierarquia.


