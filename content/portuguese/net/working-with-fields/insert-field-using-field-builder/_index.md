---
title: Inserir campo usando o Field Builder
linktitle: Inserir campo usando o Field Builder
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como inserir campos personalizados em seus documentos do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-fields/insert-field-using-field-builder/
---

Aqui está um guia passo a passo para explicar o código-fonte C# abaixo, que usa o recurso "Inserir um campo usando FieldBuilder" do Aspose.Words for .NET. Certifique-se de seguir cada etapa cuidadosamente para obter os resultados desejados.

## Etapa 1: configuração do diretório de documentos

No código fornecido, você deve especificar o diretório dos seus documentos. Substitua o valor "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho apropriado para o diretório de documentos.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passo 2: Criando o documento

Começamos criando um novo documento.

```csharp
Document doc = new Document();
```

## Etapa 3: Construindo o campo IF usando FieldBuilder

Usamos a classe FieldBuilder para construir um campo IF com dois campos MERGEFIELD aninhados. Neste exemplo, o campo IF exibe o nome e o sobrenome com base em uma condição.

```csharp
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));
```

## Passo 4: Inserindo o campo IF no documento

 Nós usamos o`BuildAndInsert()` método para construir e inserir o campo IF em um local específico do documento.

```csharp
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();
```

### Exemplo de código-fonte para inserir um campo usando FieldBuilder com Aspose.Words for .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Criação de documentos.
Document doc = new Document();

// Construção do campo IF utilizando FieldBuilder.
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));

// Insira o campo IF no documento.
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();

doc.Save(dataDir + "InsertFieldWithFieldBuilder.docx");
```

Neste exemplo, criamos um novo documento, construímos um campo IF com campos MERGEFIELD aninhados e, em seguida, inserimos esse campo no documento em um local especificado. O documento é então salvo com um nome de arquivo específico.

### Perguntas frequentes

#### P: O que é um construtor de campo no Aspose.Words?

R: Um Field Builder no Aspose.Words é uma ferramenta poderosa para criar e manipular campos em um documento do Word. Oferece recursos avançados para construção e personalização de campos, incluindo inserção de códigos de campo e gerenciamento de opções de formatação.

#### P: Que tipos de campos podem ser inseridos usando o construtor de campos?

R: O construtor de campo em Aspose.Words permite inserir diferentes tipos de campos em um documento do Word. Aqui estão alguns exemplos de tipos de campo comumente usados:

- MERGEFIELD: usado para mesclar dados de fontes externas.
- DATA: exibe a data atual.
- PÁGINA: exibe o número da página atual.
- SE: permite condicionar a exibição de um conteúdo de acordo com uma condição.
- TOC: gera automaticamente um índice com base nos estilos de título do documento.

#### P: Como personalizar os campos inseridos com o construtor de campos?

R: O construtor de campos oferece opções de personalização para campos inseridos. Você pode usar métodos e propriedades do construtor de campo para definir opções como formatação de campo, argumentos, opções e valores padrão. Por exemplo, você pode definir o formato de data, formato de número, separador de milhares, etc.
  