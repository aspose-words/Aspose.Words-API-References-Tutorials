---
title: Inserir campo de bloco de endereço de mala direta usando DOM
linktitle: Inserir campo de bloco de endereço de mala direta usando DOM
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como inserir um campo de bloco de endereço de mala direta em seus documentos do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-fields/insert-mail-merge-address-block-field-using-dom/
---

Aqui está um guia passo a passo para explicar o código-fonte C# abaixo, que usa o recurso "Inserir campo de bloco de endereço de mala direta" do Aspose.Words for .NET. Certifique-se de seguir cada etapa cuidadosamente para obter os resultados desejados.

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

 Usamos o DocumentBuilder`MoveTo()` método para mover o cursor para o parágrafo onde queremos inserir o campo do bloco de endereço de mala direta.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## Etapa 4: Inserindo o campo do bloco de endereço de mala direta

 Usamos o DocumentBuilder`InsertField()` método para inserir um campo de bloco de endereço de mala direta no parágrafo.

```csharp
FieldAddressBlock field = (FieldAddressBlock)builder.InsertField(FieldType.FieldAddressBlock, false);
```

Em seguida, configuramos as propriedades do campo do bloco de endereço especificando as opções apropriadas, como incluir o nome do país/região, formatar o endereço de acordo com o país/região, nomes de países/regiões excluídos, formato de nome e endereço e identificador de idioma.

```csharp
field.IncludeCountryOrRegionName = "1";
field.FormatAddressOnCountryOrRegion = true;
field.ExcludedCountryOrRegionName = "Test2";
field.NameAndAddressFormat = "Test3";
field.LanguageId = "Test 4";
```

 Por fim, chamamos o`Update()` método para atualizar o campo.

```csharp
field. Update();
```

### Exemplo de código-fonte para inserir um campo de bloco de endereço de mala direta com Aspose.Words for .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Paragraph para = (Paragraph) doc.GetChildNodes(NodeType.Paragraph, true)[0];

builder. MoveTo(para);

// Queremos inserir um bloco de endereço de mala direta como este:
// {ADDRESSBLOCK \\c 1 \\d \\e Teste2 \\f Teste3 \\l \"Teste 4\" }

FieldAddressBlock field = (FieldAddressBlock) builder.InsertField(FieldType.FieldAddressBlock, false);

// { BLOCO DE ENDEREÇO \\c 1" }
field.IncludeCountryOrRegionName = "1";

// { BLOCO DE ENDEREÇO \\c 1 \\d" }
field.FormatAddressOnCountryOrRegion = true;

// {ADDRESSBLOCK \\c 1 \\d \\e Teste2 }
field.ExcludedCountryOrRegionName = "Test2";

// {ADDRESSBLOCK \\c 1 \\d \\e Teste2 \\f Teste3 }
field.NameAndAddressFormat = "Test3";

// {ADDRESSBLOCK \\c 1 \\d \\e Teste2 \\f Teste3 \\l \"Teste 4\" }
field.LanguageId = "Test 4";

field. Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertMailMergeAddressBlockFieldUsingDOM.docx");
```
### Perguntas frequentes

#### P: Como posso personalizar o formato do endereço de correspondência em um documento do Word com Aspose.Words for .NET?

 R: Você pode personalizar o formato do endereço de correspondência em um documento do Word com Aspose.Words for .NET usando as propriedades do`FieldAddressBlock`objeto. Você pode definir as opções de formatação como estilo de endereço, separadores, itens opcionais, etc. para obter o formato desejado.

#### P: Como posso especificar os dados de origem para o campo de endereço de correspondência no Aspose.Words for .NET?

 R: Para especificar os dados de origem para o campo de endereço de correspondência no Aspose.Words for .NET, você pode usar o`FieldAddressBlock.StartAddress` e`FieldAddressBlock.EndAddress` propriedades. Essas propriedades são usadas para definir os intervalos de endereços na fonte de dados externa, como um arquivo CSV, banco de dados, etc.

#### P: Posso incluir elementos opcionais no campo de endereço de correspondência com Aspose.Words for .NET?

 R: Sim, você pode incluir elementos opcionais no campo de endereço de correspondência com Aspose.Words for .NET. Você pode definir elementos opcionais usando o comando`FieldAddressBlock.OmitOptional` método para especificar se deseja incluir ou excluir elementos opcionais, como nome do destinatário, nome da empresa, etc.

#### P: A inserção de um campo de endereço de correspondência usando o DOM afeta a estrutura do documento Word com Aspose.Words for .NET?

R: Inserir um campo de endereço postal usando o DOM não afeta diretamente a estrutura do documento Word. No entanto, adiciona um novo elemento de campo ao conteúdo do documento. Você pode manipular a estrutura do documento adicionando, excluindo ou modificando os elementos existentes de acordo com suas necessidades.