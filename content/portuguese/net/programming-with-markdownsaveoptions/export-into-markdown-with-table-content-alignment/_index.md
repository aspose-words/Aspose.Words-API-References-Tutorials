---
title: Exportar para Markdown com alinhamento de conteúdo de tabela
linktitle: Exportar para Markdown com alinhamento de conteúdo de tabela
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como exportar o conteúdo da tabela com diferentes alinhamentos para arquivos Markdown usando Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/programming-with-markdownsaveoptions/export-into-markdown-with-table-content-alignment/
---
Aqui está um guia passo a passo para explicar o seguinte código-fonte C# que ajuda a exportar conteúdo para um arquivo Markdown com alinhamento de conteúdo de tabela usando a biblioteca Aspose.Words para .NET. Certifique-se de incluir a biblioteca Aspose.Words em seu projeto antes de usar este código.

## Etapa 1: definir o caminho do diretório do documento

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Certifique-se de especificar o caminho correto para o diretório de documentos onde o documento editado será salvo.

## Passo 2: Crie um documento e um gerador de documentos

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Aqui criamos uma instância do`Document` classe e uma instância do`DocumentBuilder` classe que nos permitirá manipular o documento e adicionar elementos.

## Etapa 3: inserir células na tabela com diferentes alinhamentos de parágrafo

```csharp
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Cell1");
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Write("Cell2");
```

Usamos o Document Builder para inserir células na tabela e definir diferentes alinhamentos de parágrafo para cada célula.

## Etapa 4: defina as opções de exportação do Markdown e salve o documento modificado

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
{
     TableContentAlignment = TableContentAlignment.Left
};
doc.Save(dataDir + "Content_table_left_alignment.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Right;
doc.Save(dataDir + "Content_table_right_alignment.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Center;
doc.Save(dataDir + "Content_table_alignment_center.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Auto;
doc.Save(dataDir + "Content_table_auto_alignment.md", saveOptions);
```

Definimos as opções de exportação do Markdown com diferentes alinhamentos de conteúdo da tabela e, em seguida, salvamos o documento modificado usando cada opção de alinhamento.

### Exemplo de código-fonte para exportar para Markdown com alinhamento de conteúdo de tabela usando Aspose.Words for .NET

```csharp

            
	// O caminho para o diretório de documentos.
    string dataDir = "YOUR DOCUMENT DIRECTORY";
	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
	builder.Write("Cell1");
	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
	builder.Write("Cell2");

	// Faz com que todos os parágrafos dentro da tabela sejam alinhados.
	MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
	{
		TableContentAlignment = TableContentAlignment.Left
	};
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.LeftTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Right;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.RightTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Center;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.CenterTableContentAlignment.md", saveOptions);

	// O alinhamento neste caso será retirado do primeiro parágrafo da coluna correspondente da tabela.
	saveOptions.TableContentAlignment = TableContentAlignment.Auto;
	
	// Salve o documento modificado
	doc.Save(dataDir + "WorkingWithMarkdownSaveOptions.AutoTableContentAlignment.md", saveOptions);
            
        
```
