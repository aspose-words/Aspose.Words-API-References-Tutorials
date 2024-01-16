---
title: Inserir campo de autor
linktitle: Inserir campo de autor
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como inserir um campo AUTOR em seus documentos do Word com Aspose.Words for .NET. Especifique o nome do autor para personalizar seus documentos.
type: docs
weight: 10
url: /pt/net/working-with-fields/insert-author-field/
---


Aqui está um guia passo a passo para explicar o código-fonte C# abaixo, que usa o recurso "Inserir um campo AUTOR" do Aspose.Words for .NET. Certifique-se de seguir cada etapa cuidadosamente para obter os resultados desejados.

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

## Etapa 3: inserir o campo AUTOR

 Nós usamos o`AppendField()` método para inserir um campo AUTOR no parágrafo.

```csharp
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);
```

 Em seguida, configuramos o campo`AuthorName` propriedade para especificar o nome do autor.

```csharp
field. AuthorName = "Test1";
```

 Por fim, chamamos o`Update()` método para atualizar o campo.

```csharp
field. Update();
```

### Exemplo de código fonte para inserção de um campo AUTOR com Aspose.Words for .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Criação de documentos.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Insira o campo AUTOR.
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);

field. AuthorName = "Test1";

field. Update();

doc.Save(dataDir + "InsertionAuthorField.docx");
```

Neste exemplo, criamos um novo documento, inserimos um campo AUTOR, configuramos o nome do autor e salvamos o documento com um nome de arquivo especificado.

Isso conclui nosso guia sobre como usar o recurso "Inserir campo AUTOR" com Aspose.Words for .NET.

### Perguntas frequentes

#### P: O que é um campo de autor no Aspose.Words?

R: Um campo de autor em Aspose.Words é um campo especial que insere e atualiza automaticamente o nome do autor em um documento do Word. Muitas vezes é usado para indicar quem criou ou modificou o documento.

#### P: Como atualizar o campo do autor em um documento do Word com Aspose.Words?

R: O campo do autor em um documento do Word pode ser atualizado para refletir o nome do autor atual. Para isso, você pode utilizar o método UpdateFields disponível na classe Document. Este método atualizará todos os campos do documento, incluindo o campo do autor.

#### P: É possível personalizar o formato do campo autor em um documento Word?

R: Sim, é possível personalizar o formato do campo autor em um documento Word. Por padrão, o campo do autor exibe simplesmente o nome do autor. No entanto, você pode adicionar informações adicionais, como data e hora da modificação, usando as opções de formatação disponíveis em Aspose.Words.

#### P: O campo do autor é sensível a alterações subsequentes no nome do autor?

R: Sim, o campo do autor é sensível a alterações subsequentes no nome do autor. Se você alterar o nome do autor nas propriedades do documento, o campo do autor será atualizado automaticamente com o novo nome ao atualizar os campos do documento.