---
title: 상대 수평 또는 수직 위치 설정
linktitle: 상대 수평 또는 수직 위치 설정
second_title: Aspose.Words 문서 처리 API
description: 이 단계별 가이드를 통해 .NET용 Aspose.Words를 사용하여 Word 문서에서 테이블의 상대적 수평 및 수직 위치를 설정하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-tables/set-relative-horizontal-or-vertical-position/
---
## 소개

Word 문서에서 원하는 대로 표를 배치하는 방법이 막힌 적이 있습니까? 글쎄, 당신은 혼자가 아닙니다. 전문적인 보고서를 작성하든 세련된 브로셔를 작성하든 테이블을 정렬하면 세상이 달라집니다. 이것이 바로 .NET용 Aspose.Words가 유용한 곳입니다. 이 튜토리얼은 Word 문서에서 표의 상대적 수평 또는 수직 위치를 설정하는 방법을 단계별로 안내합니다. 뛰어들어보자!

## 전제 조건

시작하기 전에 다음 사항이 있는지 확인하세요.

1.  .NET용 Aspose.Words: 아직 다운로드하지 않았다면 다운로드할 수 있습니다.[여기](https://releases.aspose.com/words/net/).
2. 개발 환경: Visual Studio 또는 기타 .NET 호환 IDE.
3. C# 기본 지식: 이 자습서에서는 사용자가 C# 프로그래밍의 기본 사항에 익숙하다고 가정합니다.

## 네임스페이스 가져오기

먼저 필요한 네임스페이스를 가져와야 합니다. 이는 Aspose.Words 기능에 액세스하는 데 필수적입니다.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

## 1단계: 문서 로드

시작하려면 Word 문서를 프로그램에 로드해야 합니다. 방법은 다음과 같습니다.

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

이 코드 조각은 문서 디렉터리 경로를 설정하고 작업하려는 특정 문서를 로드합니다. 로드 문제를 방지하려면 문서 경로가 올바른지 확인하세요.

## 2단계: 테이블에 액세스

다음으로 문서 내의 테이블에 액세스해야 합니다. 일반적으로 본문 섹션의 첫 번째 테이블을 사용하여 작업하려고 합니다.

```csharp
Table table = doc.FirstSection.Body.Tables[0];
```

이 코드 줄은 문서 본문에서 첫 번째 테이블을 가져옵니다. 문서에 여러 개의 테이블이 있는 경우 이에 따라 색인을 조정할 수 있습니다.

## 3단계: 수평 위치 설정

이제 특정 요소를 기준으로 테이블의 가로 위치를 설정해 보겠습니다. 이 예에서는 열을 기준으로 위치를 지정하겠습니다.

```csharp
table.HorizontalAnchor = RelativeHorizontalPosition.Column;
```

 설정하여`HorizontalAnchor` 에게`RelativeHorizontalPosition.Column`, 테이블이 위치한 열을 기준으로 수평으로 정렬되도록 테이블을 지시합니다.

## 4단계: 수직 위치 설정

수평 위치 지정과 유사하게 수직 위치도 설정할 수 있습니다. 여기서는 페이지를 기준으로 위치를 지정합니다.

```csharp
table.VerticalAnchor = RelativeVerticalPosition.Page;
```

 설정`VerticalAnchor` 에게`RelativeVerticalPosition.Page` 페이지에 따라 테이블이 수직으로 정렬되었는지 확인합니다.

## 5단계: 문서 저장

마지막으로 변경 사항을 새 문서에 저장합니다. 이는 변경 사항을 보존하는 데 중요한 단계입니다.

```csharp
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

이 명령은 수정된 문서를 새 이름으로 저장하여 원본 파일을 덮어쓰지 않도록 합니다.

## 결론

그리고 거기에 있습니다! .NET용 Aspose.Words를 사용하여 Word 문서에서 테이블의 상대적 수평 및 수직 위치를 성공적으로 설정했습니다. 이 새로운 기술을 사용하면 문서의 레이아웃과 가독성을 향상시켜 문서를 더욱 전문적이고 세련되게 만들 수 있습니다. 다양한 자세로 계속 실험하고 귀하의 필요에 가장 적합한 것이 무엇인지 확인하십시오.

## FAQ

### 다른 요소를 기준으로 테이블을 배치할 수 있나요?  
예, Aspose.Words를 사용하면 여백, 페이지, 열 등과 같은 다양한 요소를 기준으로 테이블 위치를 지정할 수 있습니다.

### .NET용 Aspose.Words를 사용하려면 라이선스가 필요합니까?  
 예, 라이센스를 구매할 수 있습니다[여기](https://purchase.aspose.com/buy) 아니면 임시면허를 취득하세요.[여기](https://purchase.aspose.com/temporary-license/).

### .NET용 Aspose.Words에 대한 무료 평가판이 있습니까?  
 전적으로! 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).

### Aspose.Words를 다른 프로그래밍 언어와 함께 사용할 수 있나요?  
Aspose.Words는 주로 .NET용으로 설계되었지만 Java, Python 및 기타 플랫폼에서 사용할 수 있는 버전도 있습니다.

### 더 자세한 문서는 어디서 찾을 수 있나요?  
더 자세한 내용은 Aspose.Words 문서를 확인하세요.[여기](https://reference.aspose.com/words/net/).