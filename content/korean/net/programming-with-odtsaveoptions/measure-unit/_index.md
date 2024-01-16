---
title: 측정 단위
linktitle: 측정 단위
second_title: Aspose.Words 문서 처리 API
description: Aspose.Words for .NET을 사용하여 Word 문서를 ODT로 변환할 때 측정 단위를 지정하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/programming-with-odtsaveoptions/measure-unit/
---

C# 응용 프로그램에서 Word 문서를 ODT(OpenDocument Text) 형식으로 변환할 때 측정 가능한 서식 및 콘텐츠 속성에 사용되는 측정 단위를 지정할 수 있습니다. .NET용 Aspose.Words 라이브러리를 사용하면 OdtSaveOptions 저장 옵션을 사용하여 이 기능을 쉽게 지정할 수 있습니다. 이 단계별 가이드에서는 OdtSaveOptions를 사용하여 측정 단위를 지정하여 .NET C# 소스 코드용 Aspose.Words를 사용하여 Word 문서를 ODT로 변환하는 방법을 안내합니다.

## Aspose.Words 라이브러리 이해

코드를 살펴보기 전에 .NET용 Aspose.Words 라이브러리를 이해하는 것이 중요합니다. Aspose.Words는 .NET을 포함한 다양한 플랫폼에서 Word 문서를 생성, 편집, 변환 및 보호하는 강력한 라이브러리입니다. 텍스트 삽입, 서식 변경, 섹션 추가 등과 같은 문서 조작을 위한 다양한 기능을 제공합니다.

## Word 문서 로드

첫 번째 단계는 ODT로 변환하려는 Word 문서를 로드하는 것입니다. Document 클래스를 사용하여 소스 파일에서 문서를 로드합니다. 예는 다음과 같습니다.

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

이 예에서는 문서 디렉터리에 있는 "Document.docx" 문서를 로드합니다.

## 백업 옵션 구성

다음 단계는 ODT로 변환하기 위한 백업 옵션을 구성하는 것입니다. OdtSaveOptions 클래스를 사용하고 MeasureUnit 속성을 원하는 값으로 설정합니다. 예를 들어 인치를 측정 단위로 사용하려면 MeasureUnit을 OdtSaveMeasureUnit.Inches로 설정합니다. 수행 방법은 다음과 같습니다.

```csharp
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };
```

새 OdtSaveOptions 개체를 만들고 MeasureUnit 속성을 원하는 값으로 설정합니다. 이 경우 OdtSaveMeasureUnit.Inches는 인치를 측정 단위로 사용합니다.

## 문서를 ODT로 변환

이제 저장 옵션을 구성했으므로 문서를 ODT로 변환할 수 있습니다. 저장 옵션을 지정하여 변환된 문서를 ODT 형식으로 저장하려면 Document 클래스의 Save 메서드를 사용합니다. 예는 다음과 같습니다.

```csharp
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

이 예에서는 지정된 저장 옵션을 사용하여 변환된 문서를 "WorkingWithOdtSaveOptions.MeasureUnit.odt"로 저장합니다.

### .NET용 Aspose.Words를 사용하여 "측정 단위" 기능을 갖춘 OdtSaveOptions의 예제 소스 코드



```csharp
// 문서 디렉토리 경로
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Word 문서 로드
Document doc = new Document(dataDir + "Document.docx");

// "측정 단위" 기능을 사용한 백업 옵션 구성
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };

// 문서를 ODT로 변환
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

## 결론

이 가이드에서는 .NET용 Aspose.Words 라이브러리와 함께 OdtSaveOptions 저장 옵션을 사용하여 측정 단위를 지정하여 Word 문서를 ODT로 변환하는 방법을 설명했습니다. 제공된 단계를 따르고 제공된 C# 소스 코드를 사용하면 C# 애플리케이션에 이 기능을 쉽게 적용할 수 있습니다. ODT로 변환할 때 측정 단위를 지정하면 특정 요구 사항에 따라 결과 문서의 형식과 크기를 제어할 수 있습니다.