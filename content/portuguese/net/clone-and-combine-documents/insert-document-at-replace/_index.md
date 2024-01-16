---
title: Inserir documento em substituição
linktitle: Inserir documento em substituição
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como inserir um documento de substituição usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/clone-and-combine-documents/insert-document-at-replace/
---
Neste tutorial, orientaremos você sobre como inserir um documento em outro documento ao substituir usando o recurso Inserir documento ao substituir do Aspose.Words for .NET. Siga os passos abaixo para entender o código fonte e realizar a inserção do documento.

## Passo 1: Carregando o documento principal

Para começar, especifique o diretório dos seus documentos e carregue o documento principal em um objeto Document. Veja como:

```csharp
// Caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## Etapa 2: configurar opções de pesquisa e substituição

Agora configuraremos as opções de localizar e substituir especificando a direção da pesquisa e o retorno de chamada de substituição para inserir um documento em outro documento. Veja como:

```csharp
// Configure opções de pesquisa e substituição.
FindReplaceOptions options = new FindReplaceOptions
{
Direction = FindReplaceDirection.Backward,
ReplacingCallback = new InsertDocumentAtReplaceHandler()
};
```

## Etapa 3: chamar o método de substituição

Agora chamaremos o método replace para localizar e substituir o texto especificado por uma string vazia, usando as opções configuradas. Veja como:

```csharp
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

### Exemplo de código-fonte para inserir documento em substituição usando Aspose.Words for .NET

Aqui está o código-fonte completo do recurso Inserir Documento ao substituir Aspose.Words por .NET:

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

// Defina opções de localização e substituição.
FindReplaceOptions options = new FindReplaceOptions
{
	Direction = FindReplaceDirection.Backward, 
	ReplacingCallback = new InsertDocumentAtReplaceHandler()
};

// Chame o método de substituição.
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

## Conclusão

Neste tutorial, exploramos como inserir um documento em outro documento durante a substituição usando o recurso Inserir documento ao substituir do Aspose.Words for .NET. Ao configurar as opções de localizar e substituir e fornecer os dados necessários, você pode montar documentos dinamicamente, substituindo espaços reservados específicos pelo conteúdo de outros modelos ou seções de documentos. Aspose.Words for .NET oferece uma maneira poderosa e flexível de gerenciar tarefas complexas de manipulação de documentos, tornando-o uma ferramenta valiosa para automatizar a criação de documentos e cenários de inserção de conteúdo.

### Perguntas frequentes

#### P: Qual é o propósito de inserir um documento em outro documento durante a substituição?

R: Inserir um documento em outro documento durante a substituição permite substituir dinamicamente um espaço reservado específico pelo conteúdo de um documento separado. Este recurso é particularmente útil quando você deseja montar um documento maior combinando vários modelos ou seções de documentos predefinidos em espaços reservados específicos.

#### P: Como insiro um documento em outro documento durante a substituição usando Aspose.Words for .NET?

R: Para inserir um documento em outro documento durante a substituição usando Aspose.Words for .NET, siga estas etapas:
1. Carregue o documento principal que contém os espaços reservados em um objeto Document.
2. Configure as opções de localização e substituição, incluindo a direção da pesquisa e o retorno de chamada de substituição para lidar com a inserção do documento.
3. Chame o método replace com o padrão de pesquisa apropriado, substituindo os espaços reservados por uma string vazia, usando as opções configuradas.

#### P: Posso personalizar o comportamento de inserção durante a substituição?

R: Sim, você pode personalizar o comportamento de inserção durante a substituição implementando um ReplacingCallback personalizado. Ao herdar da interface IReplacingCallback, você pode controlar como os documentos são inseridos e mesclados com base em seus requisitos específicos ao substituir os espaços reservados.

#### P: Posso substituir vários espaços reservados por documentos diferentes?

R: Sim, você pode substituir vários espaços reservados por documentos diferentes especificando os padrões de pesquisa apropriados para cada espaço reservado e fornecendo os documentos correspondentes a serem inseridos.