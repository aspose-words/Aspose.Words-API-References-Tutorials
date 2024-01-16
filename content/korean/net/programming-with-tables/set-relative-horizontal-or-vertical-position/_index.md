---
title: 상대 수평 또는 수직 위치 설정
linktitle: 상대 수평 또는 수직 위치 설정
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 테이블의 상대적 수평 또는 수직 위치를 설정하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-tables/set-relative-horizontal-or-vertical-position/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 테이블의 상대적 수평 또는 수직 위치를 설정하는 방법을 배우겠습니다. 코드를 이해하고 이 기능을 구현하기 위해 단계별 가이드를 따르겠습니다. 이 튜토리얼이 끝나면 Word 문서에서 표의 상대적 수평 또는 수직 위치를 설정할 수 있습니다.

## 1단계: 프로젝트 설정
1. Visual Studio를 시작하고 새 C# 프로젝트를 만듭니다.
2. .NET 라이브러리용 Aspose.Words에 대한 참조를 추가합니다.

## 2단계: 문서 로드
문서에서 단어 처리를 시작하려면 다음 단계를 따르세요.

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 문서를 로드하세요
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

"YOUR DOCUMENTS DIRECTORY"를 문서 디렉토리의 실제 경로로 바꾸고 올바른 파일 이름을 제공하십시오.

## 3단계: 테이블의 상대적 위치 설정
다음으로 테이블의 상대적 수평 또는 수직 위치를 설정하겠습니다. 다음 코드를 사용하세요.

```csharp
// 테이블 검색
Table table = doc.FirstSection.Body.Tables[0];

//테이블의 상대적 수평 위치 정의
table.HorizontalAnchor = RelativeHorizontalPosition.Column;

// 테이블의 상대적 수직 위치 정의
table.VerticalAnchor = RelativeVerticalPosition.Page;
```

 여기서는 문서를 사용하여 첫 번째 섹션의 본문에서 첫 번째 테이블을 검색합니다. 다음으로 테이블의 상대적 수평 위치를 설정합니다.`HorizontalAnchor` 을 사용하는 속성`RelativeHorizontalPosition.Column` 값. 마찬가지로 테이블의 상대적 수직 위치를 다음과 같이 설정합니다.`VerticalAnchor` 을 사용하는 속성`RelativeVerticalPosition.Page` 값.

## 4단계: 수정된 문서 저장
마지막으로 정의된 테이블의 상대 위치를 사용하여 수정된 문서를 저장해야 합니다. 다음 코드를 사용하세요.

```csharp
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

출력 문서의 올바른 경로와 파일 이름을 지정해야 합니다.

### .NET용 Aspose.Words를 사용하여 상대 수평 또는 수직 위치 설정에 대한 샘플 소스 코드 

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table wrapped by text.docx");
Table table = doc.FirstSection.Body.Tables[0];
table.HorizontalAnchor = RelativeHorizontalPosition.Column;
table.VerticalAnchor = RelativeVerticalPosition.Page;
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

## 결론
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 테이블의 상대적 수평 또는 수직 위치를 설정하는 방법을 배웠습니다. 이 단계별 가이드를 따르고 제공된 C# 코드를 구현하면 Word 문서의 테이블에 이 상대 위치를 적용할 수 있습니다.