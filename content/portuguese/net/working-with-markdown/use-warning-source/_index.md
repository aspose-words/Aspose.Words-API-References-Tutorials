---
title: Usar fonte de aviso
linktitle: Usar fonte de aviso
second_title: API de processamento de documentos Aspose.Words
description: Aprenda como usar a fonte de aviso com o guia passo a passo Aspose.Words for .NET.
type: docs
weight: 10
url: /pt/net/working-with-markdown/use-warning-source/
---

Neste exemplo, mostraremos como usar a fonte de aviso com Aspose.Words for .NET. A fonte do aviso indica a origem do aviso ao usar a função de retorno de chamada.

## Passo 1: Carregando o documento

 Carregaremos um documento existente que contém avisos usando o`Load` método do`Document` aula.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");
```

## Etapa 3: usando a fonte de aviso

 Usaremos a fonte de aviso definindo o documento`WarningCallback` propriedade para uma coleção de`WarningInfo` objetos.

```csharp
WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;
```

## Passo 4: Salvando o documento

Finalmente, podemos salvar o documento no formato desejado.

```csharp
doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");
foreach (WarningInfo warningInfo in warnings)
{
if (warningInfo.Source == WarningSource.Markdown)
	Console.WriteLine(warningInfo.Description);
}
```

### Exemplo de código-fonte para usar fonte de aviso com Aspose.Words para .NET

```csharp
// O caminho para o diretório de documentos.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");

WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;

doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");

foreach (WarningInfo warningInfo in warnings)
{
	if (warningInfo.Source == WarningSource.Markdown)
		Console.WriteLine(warningInfo.Description);
}
```

Parabéns! Agora você aprendeu como usar a fonte de aviso com Aspose.Words for .NET.

### Perguntas frequentes

#### P: Podemos personalizar a aparência da tag "Aviso"?

 R: A formatação da tag "Warning" depende do renderizador Markdown usado. Na maioria dos casos, você pode personalizar a aparência usando CSS para direcionar o`blockquote` tag em seu documento.

#### P: É possível adicionar ícones à tag "Aviso"?

R: Sim, é possível adicionar ícones à tag "Aviso" usando código HTML em seu documento Markdown. Você pode inserir um`span` tag com a classe apropriada para exibir um ícone próximo ao texto de aviso.

#### P: A tag “Aviso” é compatível com todos os leitores Markdown?

 R: A compatibilidade da tag "Warning" depende da renderização do Markdown usada. A maioria dos leitores do Markdown apoiará o`blockquote` tag para exibir o texto destacado, mas a aparência exata pode variar.