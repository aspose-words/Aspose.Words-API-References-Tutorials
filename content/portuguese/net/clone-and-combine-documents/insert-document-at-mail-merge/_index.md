---
title: Inserir documento na mala direta
linktitle: Inserir documento na mala direta
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como inserir um documento em outro durante a mala direta usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/clone-and-combine-documents/insert-document-at-mail-merge/
---
Neste tutorial, orientaremos você sobre como inserir um documento em outro documento durante a mala direta usando o recurso Inserir documento durante a mala direta do Aspose.Words for .NET. Siga os passos abaixo para entender o código fonte e realizar a inserção do documento.

## Passo 1: Carregando o documento principal

Para começar, especifique o diretório dos seus documentos e carregue o documento principal em um objeto Document. Veja como:

```csharp
// Caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## Etapa 2: configurar mala direta

Agora vamos configurar a mala direta e especificar o retorno de chamada de mesclagem do campo para inserir um documento em outro documento. Veja como:

```csharp
mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
```

## Etapa 3: executando a mala direta

Executaremos a mala direta fornecendo os nomes dos campos de mesclagem e os dados correspondentes. Veja como:

```csharp
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

### Exemplo de código-fonte para inserir documento na mala direta usando Aspose.Words for .NET

Aqui está o código-fonte completo do recurso Inserir documento na mala direta do Aspose.Words for .NET:

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
// O documento principal possui um campo de mesclagem chamado "Documento_1".
// Os dados correspondentes para este campo contêm um caminho completo para o documento.
// Isso deve ser inserido neste campo.
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });

mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

Com este código você poderá inserir um documento em outro documento durante a mala direta usando Aspose.Words for .NET. O documento resultante será salvo com um novo nome


## Conclusão

Neste tutorial, exploramos como inserir um documento em outro documento durante a mala direta usando o recurso Inserir documento durante a mala direta do Aspose.Words for .NET. Ao configurar a mala direta e fornecer os dados necessários, você pode montar documentos dinamicamente mesclando vários modelos ou seções de documentos. Aspose.Words for .NET fornece uma maneira flexível e poderosa de gerenciar cenários complexos de geração de documentos, tornando-o uma ferramenta valiosa para automatizar tarefas de criação e manipulação de documentos.

### Perguntas frequentes

#### P: Qual é o propósito de inserir um documento em outro documento durante a mala direta?

R: Inserir um documento em outro durante a mala direta permite combinar diferentes modelos ou seções de documentos dinamicamente com base nos dados fornecidos durante o processo de mesclagem. Este recurso é particularmente útil quando você deseja montar documentos complexos mesclando vários modelos ou seções predefinidas em um documento final.

#### P: Como insiro um documento em outro documento durante a mala direta usando Aspose.Words for .NET?

R: Para inserir um documento em outro documento durante a mala direta usando Aspose.Words for .NET, siga estas etapas:
1. Carregue o documento principal que servirá de base em um objeto Document.
2. Configure a mala direta e especifique o retorno de chamada de mesclagem de campo para lidar com a inserção de documentos.
3. Execute a mala direta com os nomes dos campos de mesclagem e os dados correspondentes (caminho do documento a ser inserido).

#### P: Como posso personalizar o comportamento de inserção durante a mala direta?

R: Para personalizar o comportamento de inserção durante a mala direta, você pode implementar um FieldMergingCallback personalizado herdando da interface IFieldMergingCallback. Isso permite controlar como os documentos são inseridos e mesclados com base em seus requisitos específicos.

#### P: Posso inserir vários documentos durante a mala direta?

R: Sim, você pode inserir vários documentos durante a mala direta, fornecendo os dados apropriados para cada campo de mala direta. Para cada campo de mesclagem que requer inserção de documento, especifique o caminho para o documento correspondente como os dados.


