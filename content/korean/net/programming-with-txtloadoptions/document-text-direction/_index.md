---
title: 문서 텍스트 방향
linktitle: 문서 텍스트 방향
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 문서에서 텍스트 방향을 지정하는 방법을 알아보세요. 오른쪽에서 왼쪽으로 쓰는 언어에 대한 표시를 개선합니다.
type: docs
weight: 10
url: /ko/net/programming-with-txtloadoptions/document-text-direction/
---

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 "문서 텍스트 방향" 기능에 제공되는 C# 소스 코드를 살펴보겠습니다. 이 기능을 사용하면 문서의 텍스트 방향을 지정할 수 있습니다. 이는 히브리어나 아랍어와 같이 오른쪽에서 왼쪽으로 쓰는 언어에 특히 유용합니다.

## 1단계: 환경 설정

시작하기 전에 Aspose.Words for .NET을 사용하여 개발 환경을 설정했는지 확인하세요. 필요한 참조를 추가하고 적절한 네임스페이스를 가져왔는지 확인하세요.

## 2단계: 업로드 옵션 구성

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";

TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection. Auto };
```

 이 단계에서는 문서 로드 옵션을 구성합니다. 우리는 새로운 것을 만듭니다`TxtLoadOptions` 객체를 설정하고`DocumentDirection`재산`DocumentDirection.Auto`. 이 값은 Aspose.Words가 문서 내용에 따라 텍스트 방향을 자동으로 결정하도록 지시합니다.

## 3단계: 문서 로드

```csharp
Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);
```

 이 단계에서는 다음을 사용하여 문서를 로드합니다.`Document` 메서드를 사용하고 로드할 텍스트 파일의 경로를 전달합니다. 또한 지정된 로딩 옵션을 사용합니다.

## 4단계: 단락 조작 및 텍스트 방향 표시

```csharp
Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);
```

 이 단계에서는 다음을 사용하여 문서의 첫 번째 단락에 액세스합니다.`FirstSection`그리고`Body` 속성. 다음으로 우리는`ParagraphFormat.Bidi` 단락의 텍스트 방향을 가져오는 속성입니다. 그런 다음 이 값을 콘솔에 표시합니다.

## 5단계: 문서 저장

```csharp
doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
```

 이 마지막 단계에서는 다음을 사용하여 결과 문서를 .docx 형식으로 저장합니다.`Save` 메서드를 사용하고 경로를 출력 파일에 전달합니다.

이제 소스 코드를 실행하여 텍스트 문서를 로드하고 텍스트 방향을 결정할 수 있습니다. 결과 문서는 "WorkingWithTxtLoadOptions.DocumentTextDirection.docx"라는 이름으로 지정된 디렉터리에 저장됩니다.

### .NET용 Aspose.Words를 사용한 문서 텍스트 방향 기능의 샘플 소스 코드입니다.


```csharp

            
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection.Auto };

Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);

Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
            
        
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.Words의 문서 텍스트 방향 기능을 살펴보았습니다. 특히 히브리어나 아랍어와 같이 오른쪽에서 왼쪽으로 쓰는 언어의 경우 문서에서 텍스트 방향을 지정하는 방법을 배웠습니다.

이 기능은 다국어 문서에서 텍스트가 올바르게 표시되도록 하는 데 필수적입니다. Aspose.Words는 적절한 로딩 옵션을 사용하여 텍스트 방향을 자동으로 감지하고 이를 문서에 적용할 수 있습니다.

Aspose.Words를 사용하면 문서의 텍스트 방향을 쉽게 조작하여 사용자에게 부드럽고 직관적인 읽기 환경을 제공할 수 있습니다.

이 기능은 특정 텍스트 방향이 필요한 언어로 단어를 처리할 때 특히 유용하다는 점을 기억하는 것이 중요합니다. Aspose.Words는 문서의 텍스트 방향을 관리하는 강력한 도구를 제공하여 이 작업을 쉽게 만듭니다.

문서에서 원하는 결과를 얻으려면 자동 텍스트 방향 설정과 같은 적절한 로드 옵션을 사용해야 합니다.

Aspose.Words for .NET은 문서 조작 및 생성을 위한 다양한 고급 기능을 제공합니다. Aspose.Words에서 제공하는 문서와 예제를 더 자세히 살펴보면 이 강력한 라이브러리의 기능을 완전히 활용할 수 있습니다.

따라서 문서 텍스트 방향을 Aspose.Words for .NET 프로젝트에 통합하고 그 이점을 활용하여 매력적이고 고품질의 다국어 문서를 만드는 것을 주저하지 마십시오.