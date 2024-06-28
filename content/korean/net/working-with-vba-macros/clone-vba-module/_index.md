---
title: Word 문서에서 Vba 모듈 복제
linktitle: Word 문서에서 Vba 모듈 복제
second_title: Aspose.Words 문서 처리 API
description: 이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 Word 문서에서 VBA 모듈을 복제하는 방법을 알아봅니다.
type: docs
weight: 10
url: /ko/net/working-with-vba-macros/clone-vba-module/
---

이 튜토리얼에서는 .NET용 Aspose.Words 라이브러리를 사용하여 매크로가 포함된 Word 문서에서 VBA 모듈을 복제하는 방법을 설명합니다. VBA 모듈을 복제하면 한 소스 문서의 VBA 코드를 다른 문서로 재사용하거나 복사할 수 있습니다. .NET 프로젝트에서 코드를 이해하고 구현하는 데 도움이 되도록 단계별로 안내해 드리겠습니다.

## 전제조건
시작하기 전에 다음 항목이 있는지 확인하세요.
- C# 프로그래밍 언어에 대한 실무 지식
- 프로젝트에 설치된 .NET용 Aspose.Words 라이브러리
- 복제하려는 모듈이 포함된 VBA 프로젝트가 포함된 Word 문서

## 1단계: 문서 디렉터리 정의
 먼저, Word 문서 위치에 대한 디렉터리 경로를 설정해야 합니다. 바꾸다`"YOUR DOCUMENT DIRECTORY"` 코드에서 적절한 경로를 사용하세요.

```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2단계: 소스 문서 로드
다음으로 VBA 프로젝트와 복제하려는 모듈이 포함된 소스 Word 문서를 로드합니다.

```csharp
// 원본 문서 로드
Document doc = new Document(dataDir + "VBA project.docm");
```

## 3단계: VBA 프로젝트로 새 문서 만들기 및 모듈 복제
빈 VBA 프로젝트로 새 문서를 만들고 소스 문서에서 지정된 모듈을 복제합니다.

```csharp
// 빈 VBA 프로젝트로 새 문서 만들기
Document destDoc = new Document { VbaProject = new VbaProject() };

// 모듈 복제
VbaModule copyModule = doc.VbaProject.Modules["Module1"].Clone();
destDoc.VbaProject.Modules.Add(copyModule);
```

## 4단계: 대상 문서 저장
마지막으로 복제된 VBA 모듈이 포함된 대상 문서를 파일에 저장합니다.

```csharp
destDoc.Save(dataDir + "WorkingWithVba.CloneVbaModule.docm");
```

### .NET용 Aspose.Words를 사용하는 Clone Vba 모듈의 샘플 소스 코드 
```csharp

// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "VBA project.docm");
Document destDoc = new Document { VbaProject = new VbaProject() };
VbaModule copyModule = doc.VbaProject.Modules["Module1"].Clone();
destDoc.VbaProject.Modules.Add(copyModule);

destDoc.Save(dataDir + "WorkingWithVba.CloneVbaModule.docm");

```

## 결론
이 튜토리얼에서는 Aspose.Words for .NET을 사용하여 매크로가 포함된 Word 문서에서 VBA 모듈을 복제하는 방법을 살펴보았습니다. VBA 모듈을 복제하면 한 소스 문서의 VBA 코드를 다른 문서에서 쉽게 재사용할 수 있습니다. 이 기능을 사용하여 다양한 문서의 매크로를 구성하고 관리할 수 있습니다.

### FAQ

#### Q: VBA 모듈 복제란 무엇입니까?

A: VBA 모듈 복제는 VBA 코드가 포함된 모듈을 소스 Word 문서에서 다른 문서로 복사하는 작업으로 구성됩니다. 이를 통해 VBA 코드를 다른 컨텍스트에서 재사용하거나 다른 문서와 공유할 수 있습니다.

#### Q: Word 문서에서 VBA 모듈을 복제하기 위한 전제 조건은 무엇입니까?

A: Word 문서에서 VBA 모듈을 복제하려면 C# 프로그래밍 언어에 대한 실무 지식이 있어야 합니다. 또한 프로젝트에 Aspose.Words for .NET 라이브러리를 설치해야 합니다. 또한 복제하려는 모듈이 포함된 VBA 프로젝트가 포함된 Word 문서가 필요합니다.

#### Q: 코드에서 문서 디렉터리를 어떻게 설정하나요?

 A: 제공된 코드에서 교체해야 합니다.`"YOUR DOCUMENTS DIRECTORY"` VBA 프로젝트가 포함된 Word 문서가 있는 디렉터리에 대한 적절한 경로를 사용합니다.

#### Q: 복제된 VBA 모듈을 사용하여 대상 문서를 저장하는 방법은 무엇입니까?

 A: 복제된 VBA 모듈과 함께 대상 문서를 저장하려면 다음을 사용할 수 있습니다.`Save` 의 방법`Document` 원하는 대상 경로와 파일 이름을 지정하여 클래스를 지정합니다.