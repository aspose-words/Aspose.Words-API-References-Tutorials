---
title: Insira ASKField sem o Document Builder
linktitle: Insira ASKField sem o Document Builder
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como inserir um campo ASK em seus documentos do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-fields/insert-askfield-with-out-document-builder/
---

Aqui está um guia passo a passo para explicar o código-fonte C# abaixo, que usa o recurso "Inserir um campo ASK sem DocumentBuilder" do Aspose.Words for .NET. Certifique-se de seguir cada etapa cuidadosamente para obter os resultados desejados.

## Etapa 1: configuração do diretório de documentos

No código fornecido, você deve especificar o diretório dos seus documentos. Substitua o valor "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho apropriado para o diretório de documentos.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Etapa 2: Criando o Documento e o Parágrafo

Começamos criando um novo documento e buscando o primeiro parágrafo.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## Passo 3: Inserindo o campo ASK

 Nós usamos o`AppendField()` método para inserir um campo ASK no parágrafo.

```csharp
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);
```

Em seguida, configuramos as diversas propriedades do campo ASK especificando os valores desejados.

```csharp
field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;
```

 Por fim, chamamos o`Update()` método para atualizar o campo.

```csharp
field. Update();
```

### Exemplo de código fonte para inserir um campo ASK sem DocumentBuilder com Aspose.Words for .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Criação de documentos.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Insira o campo ASK.
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);

field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;

field. Update();

doc.Save(dataDir + "InsertionChampASKSansDocumentBuilder.docx");
```

Neste exemplo, criamos um novo documento, inserimos um campo ASK sem usar o DocumentBuilder, configuramos as diversas propriedades do campo e salvamos o documento com um nome de arquivo especificado.

Isso conclui nosso guia sobre como usar o recurso "Inserir campo ASK sem DocumentBuilder" com Aspose.Words for .NET.

### Perguntas frequentes

#### P: O que é um campo ASK no Aspose.Words?

R: Um campo ASK no Aspose.Words é usado para fazer uma pergunta ao usuário ao abrir um documento. Muitas vezes é usado para solicitar informações ou comentários específicos que podem variar de usuário para usuário.

#### P: Como inserir o campo ASK em um documento do Word sem usar o Document Builder no Aspose.Words?

R: Para inserir um campo ASK em um documento do Word sem usar o Document Builder no Aspose.Words, você pode seguir estas etapas:

1. Importe a classe Documento e Campo do namespace Aspose.Words.Fields.
2. Crie uma instância de Document carregando seu documento existente.
3. Use o método InsertField para inserir um campo ASK especificando o nome da pergunta.
4. Salve o documento.

#### P: Como obtenho a resposta do usuário para um campo ASK em um documento do Word?

R: Para obter a resposta do usuário para um campo ASK em um documento do Word, você pode usar o método GetFieldNames disponível na classe Document. Este método retorna uma lista com os nomes dos campos presentes no documento. Você pode então verificar se o nome do campo ASK está presente na lista e recuperar a resposta associada.

#### P: O campo ASK pode ser usado para solicitar mais informações do usuário?

R: Sim, o campo ASK pode ser usado para solicitar diversas informações do usuário. Você pode inserir vários campos ASK em seu documento, cada um com uma pergunta diferente. Quando o documento for aberto, o usuário será solicitado a fornecer as respostas correspondentes.