---
title: PDF 파일에서 주석 제거
linktitle: PDF 파일에서 주석 제거
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 PDF 파일에서 주석을 제거합니다.
type: docs
weight: 10
url: /ko/net/working-with-revisions/remove-comments-in-pdf/
---

이 단계별 가이드에서는 Aspose.Words for .NET을 사용하여 PDF 파일에서 주석을 제거하는 방법을 알려 드리겠습니다. 전체 소스 코드를 제공하고 마크다운 출력 형식을 지정하는 방법을 보여 드리겠습니다.

## 1단계: 문서 로드

첫 번째 단계는 주석이 포함된 문서를 로드하는 것입니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## 2단계: PDF에서 주석 숨기기

PDF를 생성할 때 주석을 숨기도록 레이아웃 옵션을 구성하겠습니다.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

## 3단계: 문서를 PDF로 저장

마지막으로 주석을 삭제하여 문서를 PDF 형식으로 저장하겠습니다.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## 마크다운 출력 형식

가독성을 높이기 위해 출력 형식을 마크다운으로 지정할 수 있습니다. 예를 들어 :

```markdown
- Comments are hidden in the generated PDF.
```

### .NET용 Aspose.Words를 사용하여 PDF에서 주석 제거에 대한 예제 소스 코드

다음은 .NET용 Aspose.Words를 사용하여 PDF 파일에서 주석을 제거하는 전체 소스 코드입니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");

// PDF에서 주석을 숨깁니다.
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;

doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.Words를 사용하여 PDF 파일에서 주석을 제거하는 방법을 배웠습니다. 적절한 레이아웃 옵션을 사용하여 PDF를 생성할 때 주석을 숨길 수 있었습니다. Aspose.Words for .NET은 Word 파일을 조작하고 PDF를 포함한 다른 형식으로 변환할 수 있는 뛰어난 유연성을 제공합니다. 이제 이 지식을 적용하여 .NET용 Aspose.Words를 사용하여 자신의 PDF 파일에서 주석을 제거할 수 있습니다.

### PDF 파일의 주석 제거에 대한 FAQ

#### Q: .NET용 Aspose.Words에서 문서를 업로드하는 방법은 무엇입니까?

 답변:`Document` 파일에서 문서를 로드하는 .NET용 Aspose.Words 클래스입니다. 전체 문서 경로를 지정할 수 있습니다.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Q: Aspose.Words for .NET으로 생성된 PDF에서 주석을 숨기는 방법은 무엇입니까?

 답변:`CommentDisplayMode` 의 재산`LayoutOptions` PDF를 생성할 때 주석이 표시되는 방식을 구성하는 개체입니다. 댓글을 숨기려면 이 속성을 다음으로 설정하세요.`CommentDisplayMode.Hide`.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

#### Q: Aspose.Words for .NET을 사용하여 문서를 PDF로 저장하는 방법은 무엇입니까?

 답변:`Save` 의 방법`Document` 문서를 PDF 형식으로 저장하는 개체입니다. PDF 파일의 전체 경로를 지정하십시오.

```csharp
doc.Save("path/to/the/file.pdf");
```