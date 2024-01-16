---
title: 풍선에 개정 내용 표시
linktitle: 풍선에 개정 내용 표시
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 풍선에 개정 내용을 표시합니다.
type: docs
weight: 10
url: /ko/net/working-with-revisions/show-revisions-in-balloons/
---

이 단계별 가이드에서는 Aspose.Words for .NET을 사용하여 Word 문서의 풍선에 수정 내용을 표시하는 방법을 보여 드리겠습니다. 전체 소스 코드를 제공하고 마크다운 출력 형식을 지정하는 방법을 보여 드리겠습니다.

## 1단계: 문서 로드

첫 번째 단계는 개정 내용이 포함된 문서를 업로드하는 것입니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## 2단계: 리뷰 표시 옵션 구성

풍선에 수정본이 표시되도록 표시 옵션을 구성하겠습니다.

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;
```

## 3단계: 문서를 PDF 형식으로 저장

마지막으로 풍선에 표시된 개정 내용과 함께 문서를 PDF로 저장합니다.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## 마크다운 출력 형식

가독성을 높이기 위해 출력 형식을 마크다운으로 지정할 수 있습니다. 예를 들어 :

```markdown
- Revisions are Showed in bubbles with revision bars on the right side.
```

### .NET용 Aspose.Words를 사용하여 풍선에 개정판 표시에 대한 예제 소스 코드

다음은 .NET용 Aspose.Words를 사용하여 문서의 풍선에 개정 내용을 표시하는 전체 소스 코드입니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(MyDir + "Revisions.docx");

// 삽입 개정을 인라인으로 렌더링하고, 풍선에서 개정을 삭제하고 형식을 지정합니다.
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
// 페이지 오른쪽에 개정 막대를 렌더링합니다.
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;

doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서의 풍선에 수정 내용을 표시하는 방법을 배웠습니다. 적절한 표시 옵션을 사용하여 오른쪽에 개정 막대가 있는 풍선에 개정 내용을 표시할 수 있었습니다. Aspose.Words for .NET은 개정 관리를 포함하여 Word 문서를 조작하기 위한 많은 강력한 기능을 제공합니다. 이제 이 지식을 사용하여 Aspose.Words for .NET을 사용하여 자신의 Word 문서에 풍선으로 수정 내용을 표시할 수 있습니다.


### FAQ

#### Q: .NET용 Aspose.Words에서 문서를 업로드하는 방법은 무엇입니까?

 답변:`Document` 파일에서 문서를 로드하는 .NET용 Aspose.Words 클래스입니다. 전체 문서 경로를 지정할 수 있습니다.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Q: Aspose.Words for .NET을 사용하여 풍선에 개정판을 표시하는 방법은 무엇입니까?

 답변:`ShowInBalloons` 의 재산`RevisionOptions` 풍선에 개정 표시를 구성하는 개체입니다. 이 속성을 설정할 수 있습니다.`ShowInBalloons.FormatAndDelete` 삭제 및 서식 수정 내용이 포함된 풍선에 수정 내용을 표시합니다.

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
```

#### Q: Aspose.Words for .NET을 사용하여 문서를 PDF 형식으로 저장하는 방법은 무엇입니까?

 답변:`Save` 의 방법`Document` 문서를 PDF 형식으로 저장하는 개체입니다. ".pdf" 확장자를 사용하여 전체 대상 경로를 지정해야 합니다.

```csharp
doc.Save("path/to/destination/document.pdf");
```