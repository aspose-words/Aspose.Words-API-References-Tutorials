---
title: Inserir campo incluir texto sem construtor de documentos
linktitle: Inserir FieldIncludeText sem o Document Builder
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como inserir um campo FieldIncludeText em seus documentos do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-fields/insert-field-include-text-without-document-builder/
---

Aqui está um guia passo a passo para explicar o código-fonte C# abaixo, que usa a funcionalidade "Inserir um campo FieldIncludeText" do Aspose.Words for .NET. Certifique-se de seguir cada etapa cuidadosamente para obter os resultados desejados.

## Etapa 1: configuração do diretório de documentos

No código fornecido, você deve especificar o diretório dos seus documentos. Substitua o valor "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho apropriado para o diretório de documentos.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Etapa 2: Criando o Documento e o Parágrafo

Começamos criando um novo documento e inicializando um parágrafo.

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## Etapa 3: Inserindo o campo FieldIncludeText

 Nós usamos o`AppendField()` método para inserir um campo FieldIncludeText no parágrafo.

```csharp
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);
```

Em seguida, configuramos as propriedades do campo FieldIncludeText especificando o nome do marcador e o nome do arquivo de origem.

```csharp
fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";
```

A seguir, adicionamos o parágrafo ao corpo do documento.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

 Por fim, chamamos o`Update()` método para atualizar o campo.

```csharp
fieldIncludeText.Update();
```

### Exemplo de código-fonte para inserir um campo FieldIncludeText com Aspose.Words for .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crie o documento e o parágrafo.
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// Insira o campo FieldIncludeText.
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);

fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";

doc.FirstSection.Body.AppendChild(para);

fieldIncludeText.Update();

doc.Save(dataDir + "InsertionFieldFieldIncludeTextWithoutDocumentBuilder.docx");
```

Neste exemplo, criamos um novo documento, inicializamos um parágrafo, inserimos um FieldIncludeTexten especificando o nome do marcador e o nome do arquivo de origem e salvamos o documento com um nome de arquivo especificado.

Isso conclui nosso guia sobre como usar o recurso "Inserir um FieldIncludeText" com Aspose.Words for .NET.

### Perguntas frequentes

#### P: Como posso especificar o arquivo de origem para o campo de inclusão de texto no Aspose.Words for .NET?

 R: Para especificar o arquivo de origem para o campo de inclusão de texto no Aspose.Words for .NET, você pode usar o`FieldIncludeText.SourceFullName`propriedade para definir o caminho completo do arquivo de origem. Certifique-se de que o arquivo de origem esteja acessível e contenha o conteúdo que você deseja incluir no campo de inclusão de texto.

#### P: Posso incluir texto de uma macro no campo de inclusão de texto com Aspose.Words for .NET?

 R: Sim, você pode incluir texto de uma macro no campo de inclusão de texto com Aspose.Words for .NET. Você pode usar o`FieldIncludeText.IncludeText` propriedade para especificar o nome da macro cujo conteúdo deve ser incluído no campo.

#### P: A inserção de um campo de inclusão de texto sem o construtor de documentos afeta a estrutura do documento Word com Aspose.Words for .NET?

R: Inserir um campo de inclusão de texto sem o construtor de documentos não afeta diretamente a estrutura do documento do Word. No entanto, adiciona um novo elemento de campo ao conteúdo do documento. Você pode manipular a estrutura do documento adicionando, excluindo ou modificando os elementos existentes de acordo com suas necessidades.

#### P: Posso personalizar a aparência do campo de inclusão de texto em um documento do Word com Aspose.Words for .NET?

R: A inclusão do campo de texto não personaliza diretamente sua aparência em um documento do Word. No entanto, você pode formatar o texto incluído usando as propriedades do parágrafo, propriedades da fonte e outros objetos de formatação disponíveis no Aspose.Words for .NET.