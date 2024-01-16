---
title: Inserir campos aninhados
linktitle: Inserir campos aninhados
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como inserir facilmente campos aninhados em seus documentos do Word com Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-fields/insert-nested-fields/
---

Aqui está um guia passo a passo para explicar o código-fonte C# abaixo, que usa o recurso "Inserir campos aninhados" do Aspose.Words for .NET. Certifique-se de seguir cada etapa cuidadosamente para obter os resultados desejados.

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

## Passo 3: Inserindo quebras de página

Usamos um loop para inserir várias quebras de página no documento.

```csharp
for (int i = 0; i < 5; i++)
     builder. InsertBreak(BreakType.PageBreak);
```

## Etapa 4: mover para o rodapé

 Nós usamos o`MoveToHeaderFooter()` método do DocumentBuilder para mover o cursor para o rodapé principal.

```csharp
builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

## Etapa 5: Inserindo o campo aninhado

 Usamos o DocumentBuilder`InsertField()`método para inserir um campo aninhado no rodapé.

```csharp
Field field = builder. InsertField(@"IF ");
builder.MoveTo(field.Separator);
builder. InsertField("PAGE");
builder. Write(" <> ");
builder.InsertField("NUMPAGES");
builder.Write(" \"See next page\" \"Last page\" ");
```

 Por fim, chamamos o`Update()` método para atualizar o campo.

```csharp
field. Update();
```

### Exemplo de código-fonte para inserção de campos aninhados com Aspose.Words for .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crie o documento e o DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insira quebras de página.
for (int i = 0; i < 5; i++)
     builder. InsertBreak(BreakType.PageBreak);

// Vá para o rodapé.
builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

// Insira campo aninhado.
Field field = builder. InsertField(@"IF ");
builder.MoveTo(field.Separator);
builder. InsertField("PAGE");
builder. Write(" <> ");
builder.InsertField("NUMPAGES");
builder.Write(" \"See next page\" \"Last page\" ");

// Atualize o campo.
field. Update();

doc.Save(dataDir + "InsertNestedFields.docx");
```

Neste exemplo, criamos um novo documento, inserimos quebras de página, movemos o cursor para o rodapé e inserimos um campo aninhado no rodapé.

### Perguntas frequentes

#### P: Como posso inserir campos aninhados em um documento do Word usando Aspose.Words for .NET?

R: Para inserir campos aninhados em um documento do Word usando Aspose.Words for .NET, você pode seguir estas etapas:

1. Obtenha o parágrafo onde deseja inserir os campos aninhados.
2.  Criar uma`FieldStart` objeto para o campo pai.
3.  Adicione os campos filhos usando o`FieldStart.NextSibling` método passando o correspondente`FieldStart` objetos como parâmetros.

#### P: Quais são os benefícios de usar campos aninhados em um documento do Word com Aspose.Words for .NET?

R: O uso de campos aninhados oferece várias vantagens em um documento do Word com Aspose.Words for .NET. Isto permite maior flexibilidade na criação de modelos de documentos dinâmicos, permitindo a inserção de valores de variáveis e cálculos em campos aninhados. Os campos aninhados também podem facilitar a geração automatizada de conteúdo, como a geração de tabelas de conteúdo, números de páginas, etc.

#### P: Posso ter campos aninhados de vários níveis em um documento do Word com Aspose.Words for .NET?

 R: Sim, é possível ter campos aninhados de vários níveis em um documento do Word com Aspose.Words for .NET. Você pode criar hierarquias complexas de campos aninhados usando o comando`FieldStart.NextSibling` método para adicionar campos filho a campos pai existentes.

#### P: Como posso personalizar as propriedades dos campos aninhados em um documento do Word com Aspose.Words for .NET?

 R: Para personalizar as propriedades dos campos aninhados em um documento do Word com Aspose.Words for .NET, você pode acessar o arquivo correspondente`FieldStart`objetos e modifique suas propriedades conforme necessário. Você pode definir opções de formatação, valores, cálculos, etc., de campos aninhados para obter o resultado desejado.

#### P: A inserção de campos aninhados afeta o desempenho do documento Word com Aspose.Words for .NET?

R: A inserção de campos aninhados pode afetar o desempenho do documento Word com Aspose.Words for .NET, especialmente se o documento contiver um grande número de campos aninhados ou hierarquias complexas. Recomenda-se otimizar o código evitando operações desnecessárias ou repetidas em campos aninhados para melhorar o desempenho.