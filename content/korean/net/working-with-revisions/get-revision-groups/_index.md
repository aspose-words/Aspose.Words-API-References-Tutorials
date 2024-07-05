---
title: 개정 그룹 가져오기
linktitle: 개정 그룹 가져오기
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 개정 그룹을 가져옵니다.
type: docs
weight: 10
url: /ko/net/working-with-revisions/get-revision-groups/
---

이 단계별 가이드에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 개정 그룹을 얻는 방법을 알려 드리겠습니다. 전체 소스 코드를 제공하고 마크다운 출력 형식을 지정하는 방법을 보여 드리겠습니다.

## 1단계: 문서 로드

첫 번째 단계는 개정 내용이 포함된 문서를 업로드하는 것입니다.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## 2단계: 개정 그룹 찾아보기

다음으로 문서에 있는 개정 그룹을 반복하여 작성자, 개정 유형 및 개정된 텍스트와 같은 세부 정보를 표시합니다.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
     Console.WriteLine(group.Text);
}
```


### .NET용 Aspose.Words를 사용하여 개정 그룹 가져오기의 소스 코드 예

다음은 .NET용 Aspose.Words를 사용하여 문서의 개정 그룹을 가져오는 전체 소스 코드입니다.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach(RevisionGroup group in doc.Revisions.Groups)
{
	 Console.WriteLine("{0}, {1}:", group.Author, group.RevisionType);
	 Console.WriteLine(group.Text);
}
```

## 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 개정 그룹을 가져오는 방법을 배웠습니다. 문서를 로드하고 검토 그룹을 찾아 작성자 및 검토 유형과 같은 세부 정보를 표시하는 단계를 수행했습니다. 이제 이 지식을 적용하여 Aspose.Words for .NET을 사용하여 자신의 Word 문서의 개정판을 분석할 수 있습니다.

### FAQ

#### Q: .NET용 Aspose.Words에서 문서를 업로드하는 방법은 무엇입니까?

 답변:`Document` 파일에서 문서를 로드하는 .NET용 Aspose.Words 클래스입니다. 전체 문서 경로를 지정할 수 있습니다.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Q: Aspose.Words for .NET에서 문서의 개정 그룹을 어떻게 찾아보나요?

 답변:`Groups` 문서의 속성`Revisions`개정 그룹 컬렉션을 가져오는 개체입니다. 그런 다음 루프를 사용하여 각 검토 그룹을 반복할 수 있습니다.

```csharp
foreach(RevisionGroup group in doc.Revisions.Groups)
{
     // 여기에서 각 검토 그룹을 처리합니다.
}
```

#### Q: Aspose.Words for .NET에서 리뷰 그룹의 작성자를 어떻게 알 수 있나요?

 답변:`Author` 의 재산`RevisionGroup` 개정 그룹의 작성자를 가져오는 개체입니다.

```csharp
string author = group.Author;
```

#### Q: Aspose.Words for .NET에서 개정 그룹의 개정 유형을 얻는 방법은 무엇입니까?

 답변:`RevisionType` 의 재산`RevisionGroup` 그룹의 개정 유형을 가져오는 개체입니다.

```csharp
string revisionType = group.RevisionType;
```