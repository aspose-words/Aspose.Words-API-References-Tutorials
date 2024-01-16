---
title: Inserir campo de mesclagem usando DOM
linktitle: Inserir campo de mesclagem usando DOM
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como inserir campos de mesclagem de campos personalizados em seus documentos do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-fields/insert-merge-field-using-dom/
---

Aqui está um guia passo a passo para explicar o código-fonte C# abaixo, que usa o recurso "Inserir campo de mesclagem de campo" do Aspose.Words for .NET. Certifique-se de seguir cada etapa cuidadosamente para obter os resultados desejados.

## Etapa 1: configuração do diretório de documentos

No código fornecido, você deve especificar o diretório dos seus documentos. Substitua o valor "SEU DIRETÓRIO DE DOCUMENTOS" pelo caminho apropriado para o diretório de documentos.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Etapa 2: Criando o Documento e o DocumentBuilder

Começamos criando um novo documento e inicializando um DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Etapa 3: mover o cursor para o parágrafo

 Nós usamos o`MoveTo()` método do DocumentBuilder para mover o cursor para o parágrafo onde queremos inserir o campo de mesclagem de campo.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## Etapa 4: Inserindo o campo de mesclagem de campo

 Usamos o DocumentBuilder`InsertField()` método para inserir um campo de mesclagem de campo no parágrafo.

```csharp
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);
```

Em seguida, configuramos as propriedades do campo de mesclagem de campo especificando as opções apropriadas, como o nome do campo, o texto antes e depois do campo e as opções de formatação vertical.

```csharp
field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;
```

 Por fim, chamamos o`Update()` método para atualizar o campo.

```csharp
field. Update();
```

### Exemplo de código-fonte para inserir um campo de mesclagem de campo com Aspose.Words for .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crie o documento e o DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Mova o cursor para o parágrafo.
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);

// Inserir campo de mesclagem de campo.
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);

field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;

// Atualize o campo.
field. Update();

doc.Save(dataDir + "InsertionChampMergeChamp.docx");
```

Neste exemplo, criamos um novo documento, movemos o cursor para o parágrafo desejado e, a seguir, inserimos um campo de mesclagem de campo no documento.

### Perguntas frequentes

#### P: Como posso inserir um campo de mesclagem em um documento do Word usando Aspose.Words for .NET com o DOM?

R: Para inserir um campo de mesclagem em um documento do Word usando Aspose.Words for .NET com DOM, você pode seguir estas etapas:

1. Navegue até o parágrafo onde deseja inserir o campo de mesclagem.
2.  Criar uma`FieldMergeField` objeto.
3. Defina as propriedades do campo de mesclagem, como nome do campo e opções de formatação.
4.  Adicione o campo de mesclagem ao parágrafo usando o`Paragraph.AppendChild` método.

#### P: Como posso especificar os dados de origem para o campo de mesclagem no Aspose.Words for .NET?

R: Para especificar os dados de origem para o campo de mesclagem no Aspose.Words for .NET, você pode usar o`FieldMergeField.FieldName` para definir o nome do campo de mesclagem, que é o nome de um campo em uma fonte de dados externa, como um arquivo CSV, banco de dados, etc.`FieldMergeField.Text` método para definir o valor do campo de mesclagem diretamente.

#### P: Posso personalizar a aparência do campo de mesclagem em um documento do Word com Aspose.Words for .NET?

 R: Sim, você pode personalizar a aparência do campo de mesclagem em um documento do Word com Aspose.Words for .NET. Você pode definir as opções de formatação como caixa, fonte, cor, etc. usando as propriedades do`FieldMergeField` objeto.

#### P: Como posso verificar se um campo de mesclagem foi inserido com sucesso em um documento do Word com Aspose.Words for .NET?

 R: Para verificar se um campo de mesclagem foi inserido com sucesso, você pode navegar pelo conteúdo do documento e procurar instâncias de campo de mesclagem. Você pode usar os métodos e propriedades do`Document` objeto para acessar parágrafos, campos e outros elementos do documento.

#### P: A inserção de um campo de mesclagem usando DOM afeta a estrutura do documento Word com Aspose.Words for .NET?

R: Inserir um campo de mesclagem usando o DOM não afeta diretamente a estrutura do documento Word. No entanto, adiciona um novo elemento de campo ao conteúdo do documento. Você pode manipular a estrutura do documento adicionando, excluindo ou modificando os elementos existentes de acordo com suas necessidades.