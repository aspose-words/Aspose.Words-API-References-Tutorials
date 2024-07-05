---
title: 개정판 이용
linktitle: 개정판 이용
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 수정된 버전의 Word 문서에 액세스하세요.
type: docs
weight: 10
url: /ko/net/working-with-revisions/access-revised-version/
---

이 단계별 가이드에서는 Aspose.Words for .NET을 사용하여 수정된 버전의 Word 문서에 액세스하는 방법을 보여 드리겠습니다. 전체 소스 코드를 제공하고 마크다운 출력 형식을 지정하는 방법을 보여 드리겠습니다.

## 1단계: 문서 로드

첫 번째 단계는 개정 내용이 포함된 문서를 업로드하는 것입니다.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();
```

## 2단계: 개정된 버전에 액세스

이제 개정된 문서 버전으로 넘어가겠습니다.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

## 3단계: 버전 찾아보기

다음으로 문서에 있는 개정 내용을 반복하여 목록 항목인 단락에 대한 특정 정보를 표시합니다.

```csharp
foreach (Revision revision in doc.Revisions)
{
     if (revision.ParentNode.NodeType == NodeType.Paragraph)
     {
         Paragraph paragraph = (Paragraph)revision.ParentNode;
         if (paragraph.IsListItem)
         {
             Console.WriteLine(paragraph.ListLabel.LabelString);
             Console.WriteLine(paragraph.ListFormat.ListLevel);
         }
     }
}
```

### .NET용 Aspose.Words를 사용하는 Access Revised Version의 예제 소스 코드

다음은 .NET용 Aspose.Words를 사용하여 개정된 문서 버전에 액세스하기 위한 전체 소스 코드입니다.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();

// 문서의 수정된 버전으로 전환합니다.
doc.RevisionsView = RevisionsView.Final;

foreach (Revision revision in doc.Revisions)
{
	 if (revision.ParentNode.NodeType == NodeType.Paragraph)
	 {
		 Paragraph paragraph = (Paragraph)revision.ParentNode;
		 if (paragraph.IsListItem)
		 {
			 Console.WriteLine(paragraph.ListLabel.LabelString);
			 Console.WriteLine(paragraph.ListFormat.ListLevel);
		 }
	 }
}
```

## 결론

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 수정된 버전의 Word 문서에 액세스하는 방법을 배웠습니다. 문서를 로드하고, 개정된 버전으로 이동하고, 개정된 내용을 탐색함으로써 목록 항목인 단락에 대한 구체적인 정보를 얻을 수 있었습니다. Aspose.Words for .NET은 리뷰에 대한 액세스를 포함하여 Word 문서를 조작하기 위한 강력한 기능을 제공합니다. 이제 이 지식을 사용하여 Aspose.Words for .NET을 사용하여 자신의 Word 문서의 개정된 버전에 액세스할 수 있습니다.

### FAQ

#### Q: 수정된 문서를 Aspose.Words for .NET에 로드하려면 어떻게 해야 합니까?

 답변:`Document` 개정판이 포함된 파일에서 문서를 로드하는 .NET용 Aspose.Words 클래스입니다. 전체 문서 경로를 지정할 수 있습니다.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Q: Aspose.Words for .NET에서 수정된 버전의 문서에 어떻게 액세스합니까?

 답변:`RevisionsView` 의 재산`Document` 문서의 수정된 버전에 액세스하는 데 반대합니다. 의 값을 설정할 수 있습니다.`RevisionsView`재산`RevisionsView.Final` 수정 없이 최종 버전을 보여드리겠습니다.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

#### Q: .NET용 Aspose.Words에서 문서 개정판을 어떻게 찾아볼 수 있나요?

답변:`foreach` 문서에 있는 개정판을 반복하는 루프입니다. 당신은 사용할 수 있습니다`Revisions` 의 재산`Document` 문서의 모든 개정판 모음을 가져오는 개체입니다.

```csharp
foreach (Revision revision in doc.Revisions)
{
     // 여기에서 각 개정판을 처리하세요.
}
```

#### Q: .NET용 Aspose.Words에서 단락이 목록 항목인지 확인하는 방법은 무엇입니까?

 답변:`IsListItem` 의 재산`Paragraph` 단락이 목록 항목인지 확인하는 개체입니다. 그만큼`IsListItem` 재산 반환`true` 단락이 목록 항목이면 그렇지 않으면 반환됩니다.`false`.

```csharp
if (paragraph.IsListItem)
{
     // 단락이 목록 항목입니다.
}
else
{
     // 단락이 목록 항목이 아닙니다.
}
```