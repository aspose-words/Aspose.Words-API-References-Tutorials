---
title: 단어의 개정 유형 가져오기
linktitle: 단어의 개정 유형 가져오기
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서의 단어 개정 유형을 가져옵니다.
type: docs
weight: 10
url: /ko/net/working-with-revisions/get-revision-types/
---

이 단계별 가이드에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 단어 개정 유형을 얻는 방법을 알려 드리겠습니다. 전체 소스 코드를 제공하고 마크다운 출력 형식을 지정하는 방법을 보여 드리겠습니다.

## 1단계: 문서 로드

첫 번째 단계는 개정 내용이 포함된 문서를 업로드하는 것입니다.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## 2단계: 단락을 단계별로 살펴봅니다.

다음으로, 문서의 단락을 살펴보고 각 단락과 관련된 단어 수정 유형을 확인하겠습니다.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     if (paragraphs[i].IsMoveFromRevision)
         Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
     if (paragraphs[i].IsMoveToRevision)
         Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

### .NET용 Aspose.Words를 사용하여 개정 유형 가져오기에 대한 예제 소스 코드

다음은 .NET용 Aspose.Words를 사용하여 문서의 개정 유형을 가져오는 전체 소스 코드입니다.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
	 if (paragraphs[i].IsMoveFromRevision)
		 Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
	 if (paragraphs[i].IsMoveToRevision)
		 Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

## 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 단어 개정 유형을 얻는 방법을 배웠습니다. 우리는 문서를 로드하고, 문단을 살펴보고, 각 문단과 관련된 단어 리뷰 유형을 확인하는 단계를 따랐습니다. 이제 이 지식을 적용하여 Aspose.Words for .NET을 사용하여 자신의 Word 문서에서 단어 리뷰를 분석할 수 있습니다.

### 단어 개정 유형을 얻기 위한 FAQ

#### Q: .NET용 Aspose.Words에서 문서를 업로드하는 방법은 무엇입니까?

 답변:`Document` 파일에서 문서를 로드하는 .NET용 Aspose.Words 클래스입니다. 전체 문서 경로를 지정할 수 있습니다.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Q: Aspose.Words for .NET에서 문서의 단락을 어떻게 반복합니까?

 답변:`Paragraphs` 문서 섹션의 속성을 사용하여 단락 모음을 가져옵니다. 그런 다음 루프를 사용하여 각 단락을 반복할 수 있습니다.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     // 여기에서 각 단락을 처리하세요.
}
```

#### Q: Aspose.Words for .NET에서 단락이 이동(삭제)되었는지 확인하는 방법은 무엇입니까?

 A: 단락을 사용하세요`IsMoveFromRevision` 속성이 이동(삭제)되었는지 확인합니다.

```csharp
if (paragraph. IsMove

FromRevision)
{
     // 해당 단락이 이동(삭제)되었습니다.
}
```

#### Q: Aspose.Words for .NET에서 단락이 이동(삽입)되었는지 확인하는 방법은 무엇입니까?

 A: 단락을 사용하세요`IsMoveToRevision`이동(삽입)되었는지 확인하는 속성입니다.

```csharp
if (paragraph.IsMoveToRevision)
{
     // 단락이 이동되었습니다(삽입됨).
}
```