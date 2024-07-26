---
title: 개정판 수락
linktitle: 개정판 수락
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서의 수정본을 수락하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/working-with-revisions/accept-revisions/
---

이 튜토리얼에서는 Aspose.Words for .NET의 수정본 수락 기능을 사용하여 Word 문서의 수정본을 수락하는 과정을 안내합니다. 소스 코드를 이해하고 문서 변경 사항을 적용하려면 아래 단계를 따르세요.

## 1단계: 문서 콘텐츠 추가 및 편집

이 예에서는 문서를 만들고 콘텐츠를 추가합니다. 우리는 변경 사항과 개정 사항을 설명하기 위해 여러 단락을 사용합니다. 방법은 다음과 같습니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

// 첫 번째 단락에 텍스트를 추가한 다음 두 개의 단락을 더 추가합니다.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2.");
body.AppendParagraph("Paragraph 3.");
```

## 2단계: 리뷰 추적 및 리뷰 추가

개정 추적을 활성화하고 문서에 개정을 추가합니다. 방법은 다음과 같습니다.

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);

// 이 단락은 개정판이며 해당 "IsInsertRevision" 플래그가 설정됩니다.
para = body.AppendParagraph("Paragraph 4.");
Assert.True(para.IsInsertRevision);
```

## 3단계: 단락 삭제 및 개정 관리

단락을 삭제하고 저장된 개정 내용을 확인합니다. 방법은 다음과 같습니다.

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// 개정 내용을 추적하는 동안 해당 단락은 여전히 문서에 존재하며 "IsDeleteRevision" 플래그가 설정됩니다.
// 모든 리뷰를 수락하거나 거부할 때까지 Microsoft Word에 리뷰로 표시됩니다.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);
```

## 4단계: 변경 사항 수락

우리는 문서의 모든 변경 사항을 수락합니다. 방법은 다음과 같습니다.

```csharp
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);
```

## 5단계: 리뷰 추적 중지

문서 변경 사항이 더 이상 수정본으로 표시되지 않도록 수정본 추적을 중단할 예정입니다. 방법은 다음과 같습니다.

```csharp
doc.StopTrackRevisions();
```
## 6단계: 문서 저장

 텍스트 입력 양식 필드를 삽입한 후,`Save`방법. 적절한 파일 경로를 제공해야 합니다.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```

### .NET용 Aspose.Words를 사용하여 개정 승인을 위한 예제 소스 코드

다음은 .NET용 Aspose.Words를 사용하여 문서의 변경 사항을 수락하는 전체 소스 코드입니다.


```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

// 첫 번째 단락에 텍스트를 추가한 다음 두 개의 단락을 더 추가합니다.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2. ");
body.AppendParagraph("Paragraph 3. ");

//세 개의 문단이 있는데 그 중 어느 것도 개정 유형으로 등록되지 않았습니다.
// 개정 내용을 추적하는 동안 문서의 내용을 추가/제거하는 경우,
// 문서에 그대로 표시되며 승인/거부될 수 있습니다.
doc.StartTrackRevisions("John Doe", DateTime.Now);

// 이 단락은 개정판이며 이에 따라 "IsInsertRevision" 플래그가 설정됩니다.
para = body.AppendParagraph("Paragraph 4. ");
Assert.True(para.IsInsertRevision);

// 문서의 단락 컬렉션을 가져오고 단락을 제거합니다.
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// 개정 내용을 추적하고 있으므로 해당 단락은 여전히 문서에 존재하며 "IsDeleteRevision"이 설정됩니다.
// 모든 수정본을 승인하거나 거부할 때까지 Microsoft Word에 수정본으로 표시됩니다.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);

// 변경 사항을 수락하면 개정 삭제 단락이 제거됩니다.
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);

// 개정판 추적을 중지하면 이 텍스트가 일반 텍스트로 표시됩니다.
// 문서가 변경되면 수정본은 계산되지 않습니다.
doc.StopTrackRevisions();

// 문서를 저장합니다.
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```
## 결론

이 튜토리얼에서는 Aspose.Words for .NET의 수정본 수락 기능을 사용하여 Word 문서의 수정본을 수락하는 방법을 배웠습니다. 우리는 문서 내용을 추가 및 편집하고, 개정 내용을 추적하고, 개정된 단락을 삭제하고, 모든 변경 사항을 수락하고, 개정 내용 추적을 중지하는 단계를 수행했습니다. 이제 이 지식을 적용하여 Aspose.Words for .NET을 사용하여 자신의 Word 문서의 수정본을 효과적으로 관리할 수 있습니다.

### 자주 묻는 질문

#### Q: .NET용 Aspose.Words에서 개정 추적을 어떻게 활성화합니까?

#### 해결 방법 1:

 A: .NET용 Aspose.Words에서 개정 추적을 활성화하려면`StartTrackRevisions` 의 방법`Document` 개체를 선택하고 작성자 이름과 개정 추적 시작 날짜를 지정합니다.

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);
```

#### 해결 방법 2:

 A: 다음을 사용하여 개정 추적을 활성화할 수도 있습니다.`Document` 받아들이는 생성자`trackRevisions`그리고`author` 매개변수.

```csharp
Document doc = new Document("document.docx", new LoadOptions { TrackRevisions = true, Author = "John Doe" });
```

#### Q: Aspose.Words for .NET을 사용하여 문서의 모든 변경 사항을 어떻게 수락합니까?

 답변:`AcceptAllRevisions` 의 방법`Document` 문서에 대한 모든 변경 사항을 수락하는 데 반대합니다.

```csharp
doc.AcceptAllRevisions();
```

#### Q: 승인된 수정본이 포함된 수정된 문서를 어떻게 저장합니까?

 사용`Save` 의 방법`Document` 승인된 수정본과 함께 수정된 문서를 저장하는 개체입니다. 올바른 파일 경로를 제공하십시오.

```csharp
doc.Save("path/to/the/document.docx");
```

#### Q: .NET용 Aspose.Words에서 개정 추적을 어떻게 중지합니까?

 답변:`StopTrackRevisions` 의 방법`Document` 추적 개정을 중지하려면 개체를 사용하세요.

```csharp
doc.StopTrackRevisions();
```

#### Q: Aspose.Words for .NET을 사용하여 문서에서 수정된 단락을 어떻게 삭제합니까?

 A: 문서에서 수정된 단락을 제거하려면`Remove` 단락 수집 방법.

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Paragraph para = paragraphs[2];
para.Remove();
```