---
title: Inserir campo
linktitle: Inserir campo
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como inserir um campo em seus documentos do Word com Aspose.Words for .NET. Personalize seus documentos com campos dinâmicos.
type: docs
weight: 10
url: /pt/net/working-with-fields/insert-field/
---

Aqui está um guia passo a passo para explicar o código-fonte C# abaixo, que usa o recurso "Inserir um campo" do Aspose.Words for .NET. Certifique-se de seguir cada etapa cuidadosamente para obter os resultados desejados.

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

## Passo 3: Inserindo o campo

 Nós usamos o`InsertField()` método do DocumentBuilder para inserir um campo no documento. Neste exemplo, inserimos um campo de mesclagem (MERGEFIELD) com nome de campo "MyFieldName" e formato de mesclagem.

```csharp
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");
```

### Exemplo de código fonte para inserção de campo com Aspose.Words for .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crie o documento e o DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insira o campo.
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");

doc.Save(dataDir + "InsertionField.docx");
```

Neste exemplo, criamos um novo documento, inicializamos um DocumentBuilder e, em seguida, inserimos um campo de mesclagem com o nome de campo "MyFieldName" e formato de mesclagem. O documento é então salvo com um nome de arquivo especificado.

Isso conclui nosso guia sobre como usar o recurso "Inserir um campo" com Aspose.Words for .NET.

### Perguntas frequentes

#### P: O que é um campo no Word?

R: Um campo no Word é um elemento que permite inserir e manipular dados dinâmicos em um documento. Ele pode ser usado para exibir informações variáveis, como datas, números de páginas, tabelas, fórmulas matemáticas, etc.

#### P: Como inserir um campo em um documento Word?

R: Para inserir um campo em um documento do Word, você pode seguir estas etapas:

1. Coloque o cursor onde deseja inserir o campo.
2. Vá para a guia “Inserir” na faixa de opções.
3. Clique no botão “Campo” no grupo “Texto” para abrir a caixa de diálogo dos campos.
4. Selecione o tipo de campo que deseja inserir na lista suspensa.
5. Configure as opções de campo conforme necessário.
6. Clique no botão “OK” para inserir o campo em seu documento.

#### P: Quais são os tipos de campo comumente usados no Word?

R: O Word oferece uma ampla variedade de tipos de campos que você pode usar em seus documentos. Aqui estão alguns dos tipos de campo comumente usados:

- Data e hora: exibe a data e hora atuais.
- Número da página: exibe o número da página atual.
- Índice: gera automaticamente um índice com base nos estilos de seus títulos.
- Cálculo: realiza cálculos matemáticos usando fórmulas.
- Texto de preenchimento: Gera texto aleatório para preencher seu documento.

#### P: Posso personalizar a aparência dos campos no Word?

R: Sim, você pode personalizar a aparência dos campos no Word usando as opções de formatação disponíveis. Por exemplo, você pode alterar a fonte, o tamanho, a cor e o estilo do texto em um campo. Você também pode aplicar efeitos de formatação como negrito, itálico e sublinhado.
  