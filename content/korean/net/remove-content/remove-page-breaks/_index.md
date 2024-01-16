---
title: Word 문서에서 페이지 나누기 제거
linktitle: 페이지 나누기 제거
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words 라이브러리를 사용하여 Word 문서에서 페이지 나누기를 제거하는 방법을 알아보세요. 원활한 레이아웃을 위해 단계별 가이드를 따르세요.
type: docs
weight: 10
url: /ko/net/remove-content/remove-page-breaks/
---
이 튜토리얼에서는 Aspose.Words for .NET 라이브러리를 사용하여 단어 문서에서 페이지 나누기를 제거하는 방법을 살펴보겠습니다. 페이지 나누기가 문서의 서식 및 레이아웃을 방해할 수 있으므로 프로그래밍 방식으로 제거해야 할 수도 있습니다. 프로세스를 이해하고 C# 프로젝트에 구현하는 데 도움이 되는 단계별 가이드를 제공합니다.

## 요구사항

시작하기 전에 다음 사항이 있는지 확인하세요.

- C# 프로그래밍 언어에 대한 기본 지식
- .NET 라이브러리용 Aspose.Words 설치됨
- Visual Studio 또는 기타 C# 개발 환경 설정

## 1단계: 환경 설정

시작하려면 원하는 개발 환경에서 새 C# 프로젝트를 만듭니다. .NET용 Aspose.Words 라이브러리가 프로젝트에서 올바르게 참조되는지 확인하세요.

## 2단계: 문서 로드

문서에서 페이지 나누기를 제거하려면 먼저 문서를 메모리에 로드해야 합니다. 다음 코드는 특정 디렉터리에서 문서를 로드하는 방법을 보여줍니다.

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

// 문서를 로드하세요
Document doc = new Document(dataDir + "your-document.docx");
```

 바꾸다`"YOUR DOCUMENT DIRECTORY"` 문서의 실제 경로와 함께.

## 3단계: 페이지 나누기 제거

문서가 로드되면 페이지 나누기 제거를 시작할 수 있습니다. 아래 코드 조각은 문서의 모든 단락을 반복하고, 페이지 나누기를 확인하고, 제거하는 방법을 보여줍니다.

```csharp
NodeCollection paragraphs = doc.GetChildNodes(NodeType.Paragraph, true);

foreach (Paragraph para in paragraphs)
{
     // 단락 이전에 페이지 나누기가 있는 경우 이를 지웁니다.
     if (para.ParagraphFormat.PageBreakBefore)
         para.ParagraphFormat.PageBreakBefore = false;

     // 페이지 나누기가 있는지 단락의 모든 실행을 확인하고 제거하십시오.
     foreach(Run run in para.Runs)
     {
         if (run.Text.Contains(ControlChar.PageBreak))
             run.Text = run.Text.Replace(ControlChar.PageBreak, string.Empty);
     }
}
```

위의 코드 조각은 문서의 모든 단락을 반복하고 각 단락 앞에 페이지 나누기가 있는지 확인합니다. 페이지 나누기가 감지되면 지워집니다. 그런 다음 단락 내의 각 실행에서 페이지 나누기를 확인하고 제거합니다.

## 4단계: 수정된 문서 저장

페이지 나누기를 제거한 후 수정된 문서를 저장해야 합니다. 다음 코드는 수정된 문서를 특정 위치에 저장하는 방법을 보여줍니다.

```csharp
doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```

 바꾸다`"modified-document.docx"`수정된 문서에 원하는 이름을 붙입니다.

### .NET용 Aspose.Words를 사용하여 페이지 나누기 제거에 대한 샘플 소스 코드 
```csharp

// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
// 문서를 로드하세요
Document doc = new Document(dataDir + "your-document.docx");

NodeCollection paragraphs = doc.GetChildNodes(NodeType.Paragraph, true);

foreach (Paragraph para in paragraphs)
{
	// 단락 앞에 페이지 나누기가 있는 경우 이를 지웁니다.
	if (para.ParagraphFormat.PageBreakBefore)
		para.ParagraphFormat.PageBreakBefore = false;

	// 페이지 나누기가 있는지 단락의 모든 실행을 확인하고 제거하십시오.
	foreach (Run run in para.Runs)
	{
		if (run.Text.Contains(ControlChar.PageBreak))
			run.Text = run.Text.Replace(ControlChar.PageBreak, string.Empty);
	}
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);        

```

## 결론

이 튜토리얼에서는 Aspose.Words for .NET 라이브러리를 사용하여 문서에서 페이지 나누기를 제거하는 방법을 배웠습니다. 단계별 가이드를 따르면 이제 자신의 C# 프로젝트에서 이 기능을 구현할 수 있습니다. 페이지 나누기를 제거하면 문서에서 일관된 레이아웃과 서식을 유지하는 데 도움이 됩니다.

### FAQ

#### Q: Word 문서에서 페이지 나누기를 제거하기 위해 Aspose.Words를 사용해야 하는 이유는 무엇입니까?

A: Aspose.Words는 .NET 애플리케이션에서 Word 문서를 조작하기 위한 강력하고 다양한 클래스 라이브러리입니다. Aspose.Words를 사용하면 문서에서 페이지 나누기를 제거하는 효과적이고 쉬운 솔루션을 얻을 수 있습니다. 이를 통해 문서 레이아웃을 사용자 정의하고, 원치 않는 페이지 나누기를 제거하고, 일관된 프레젠테이션을 유지할 수 있습니다.

#### Q: .NET용 Aspose.Words에서 문서를 어떻게 업로드합니까?

A: Word 문서에서 페이지 나누기를 제거하려면 먼저 Aspose.Words의 Load() 메서드를 사용하여 문서를 메모리에 로드해야 합니다. 다음은 특정 디렉터리에서 문서를 로드하는 샘플 코드입니다.

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 문서를 로드하세요
Document doc = new Document(dataDir + "your-document.docx");
```

 바꾸다`"YOUR DOCUMENTS DIRECTORY"` 문서의 실제 경로와 함께.

#### Q: Aspose.Words를 사용하여 문서에서 페이지 나누기를 제거하는 방법은 무엇입니까?

A: 문서가 로드되면 페이지 나누기 제거를 시작할 수 있습니다. 루프를 사용하여 문서의 모든 단락을 반복하고 페이지 나누기가 포함되어 있는지 확인하고 필요한 경우 제거하십시오. 다음은 샘플 코드입니다.

```csharp
NodeCollection paragraphs = doc.GetChildNodes(NodeType.Paragraph, true);

foreach (Paragraph para in paragraphs)
{
      // 단락 앞에 페이지 나누기가 있으면 제거하세요.
      if (para.ParagraphFormat.PageBreakBefore)
          para.ParagraphFormat.PageBreakBefore = false;

      // 페이지 나누기가 있는지 단락의 모든 Run 요소를 확인하고 제거합니다.
      foreach(Run run in para.Runs)
      {
          if (run.Text.Contains(ControlChar.PageBreak))
              run.Text = run.Text.Replace(ControlChar.PageBreak, string.Empty);
      }
}
```

이 코드는 문서의 모든 단락을 반복하여 앞에 페이지 나누기가 포함되어 있는지 확인한 다음 제거합니다. 그런 다음 단락의 각 Run 요소에서 페이지 나누기를 확인하고 제거합니다.

#### Q: .NET용 Aspose.Words에서 편집된 문서를 어떻게 저장합니까?

A: 페이지 나누기를 제거한 후 수정된 문서를 저장해야 합니다. 수정된 문서를 특정 위치에 저장하려면 Save() 메서드를 사용합니다. 다음은 샘플 코드입니다.

```csharp
doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```

 바꾸다`"modified-document.docx"`수정된 문서에 원하는 이름을 붙입니다.