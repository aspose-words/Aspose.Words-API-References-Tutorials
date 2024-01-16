---
title: Inserir campo avançado sem o Document Builder
linktitle: Inserir campo avançado sem o Document Builder
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como inserir um campo avançado em seus documentos do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-fields/insert-advance-field-with-out-document-builder/
---

Aqui está um guia passo a passo para explicar o código-fonte C# abaixo, que usa o recurso "Inserção de campo avançada sem DocumentBuilder" do Aspose.Words for .NET. Certifique-se de seguir cada etapa cuidadosamente para obter os resultados desejados.

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

## Etapa 3: Inserindo o campo avançado

 Nós usamos o`AppendField()` método para inserir um campo avançado no parágrafo.

```csharp
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);
```

Em seguida, configuramos as diversas propriedades do campo avançado especificando os valores desejados.

```csharp
field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";
```

 Por fim, chamamos o`Update()` método para atualizar o campo.

```csharp
field. Update();
```

### Exemplo de código fonte para inserção de campo avançado sem DocumentBuilder com Aspose.Words for .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Criação de documentos.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Insira o campo avançado.
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);

field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";

field. Update();

doc.Save(dataDir + "InsertionFieldAdvanceWithoutDocumentBuilder.docx");
```

Neste exemplo, criamos um novo documento, inserimos um campo avançado sem usar o DocumentBuilder, configuramos as diversas propriedades do campo e salvamos o documento com um nome de arquivo especificado.

Isso conclui nosso guia sobre como usar o recurso "Inserir campo avançado sem DocumentBuilder" com Aspose.Words for .NET.

### Perguntas frequentes

#### P: O que é um campo avançado no Aspose.Words?

R: Um campo avançado no Aspose.Words é um tipo especial de campo que permite realizar cálculos, incluir condições e realizar operações complexas em um documento do Word. Oferece grande flexibilidade para criar campos dinâmicos e personalizados.

#### P: Como inserir um campo avançado em um documento do Word sem usar o Document Builder no Aspose.Words?

R: Para inserir um campo avançado em um documento do Word sem usar o Document Builder no Aspose.Words, você pode seguir estas etapas:

1. Importe a classe Documento e Campo do namespace Aspose.Words.Fields.
2. Crie uma instância de Document carregando seu documento existente.
3. Use o método InsertField para inserir um campo avançado especificando o código do campo avançado.
4. Salve o documento.

#### P: Como obter o resultado de um campo avançado em um documento Word?

R: Para obter o resultado de um campo avançado em um documento Word, você pode usar a propriedade Result disponível na classe Field. Esta propriedade retorna o resultado calculado do campo.

#### P: Posso modificar a fórmula de um campo avançado após inseri-lo em um documento Word?

R: Sim, você pode editar a fórmula de um campo avançado após inseri-lo em um documento do Word. Você pode fazer isso acessando a propriedade FieldCode da classe Field e atualizando a fórmula modificando o texto da fórmula.