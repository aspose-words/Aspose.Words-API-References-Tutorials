---
title: 부동 테이블 위치
linktitle: 부동 테이블 위치
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에서 부동 위치에 테이블을 배치하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-tables/floating-table-position/
---

이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 부동 위치에 테이블을 배치하는 방법을 배우겠습니다. 코드를 이해하고 이 기능을 구현하기 위해 단계별 가이드를 따르겠습니다. 이 튜토리얼이 끝나면 프로그래밍 방식으로 Word 문서에서 부동 테이블의 위치와 정렬을 제어할 수 있습니다.

## 1단계: 프로젝트 설정
1. Visual Studio를 시작하고 새 C# 프로젝트를 만듭니다.
2. .NET 라이브러리용 Aspose.Words에 대한 참조를 추가합니다.

## 2단계: 문서 로드 및 테이블 액세스
테이블로 단어 처리를 시작하려면 해당 테이블이 포함된 문서를 로드하고 액세스해야 합니다. 다음과 같이하세요:

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// 문서를 로드하세요
Document doc = new Document(dataDir + "Table wrapped by text.docx");

// 어레이에 대한 액세스
Table table = doc.FirstSection.Body.Tables[0];
```

"YOUR DOCUMENTS DIRECTORY"를 문서 디렉토리의 실제 경로로 바꾸십시오. 또한 문서에 부동 위치에 배치될 테이블이 포함되어 있는지 확인하십시오.

## 3단계: 플로팅 보드 위치 지정
다음으로 Aspose.Words for .NET에서 제공하는 속성을 사용하여 부동 위치에 테이블을 배치하겠습니다. 다음 코드를 사용하세요.

```csharp
// 플로팅 테이블 위치 지정
table. AbsoluteHorizontalDistance = 10;
table. RelativeVerticalAlignment = VerticalAlignment. Center;
```

 여기서 우리는`AbsoluteHorizontalDistance` 페이지 왼쪽 가장자리에서 테이블의 절대 수평 거리를 설정하는 속성입니다. 우리는 또한`RelativeVerticalAlignment` 주변 콘텐츠에 대한 테이블의 상대적 수직 정렬을 설정하는 속성입니다.

## 4단계: 수정된 문서 저장
마지막으로 테이블이 부동 위치에 배치된 수정된 문서를 저장해야 합니다. 다음 코드를 사용하세요.

```csharp
// 수정된 문서를 저장하세요
doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

출력 문서의 올바른 경로와 파일 이름을 지정해야 합니다.

### .NET용 Aspose.Words를 사용하는 부동 테이블 위치의 샘플 소스 코드 

```csharp
	// 문서 디렉터리 경로
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	Table table = doc.FirstSection.Body.Tables[0];
	table.AbsoluteHorizontalDistance = 10;
	table.RelativeVerticalAlignment = VerticalAlignment.Center;
	doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

## 결론
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 부동 위치에 테이블을 배치하는 방법을 배웠습니다. 이 단계별 가이드를 따르고 제공된 C# 코드를 구현하면 Word 문서에서 부동 테이블의 위치와 정렬을 프로그래밍 방식으로 제어할 수 있습니다.