---
title: Ole 패키지를 사용하여 Word에 Ole 개체 삽입
linktitle: Ole 패키지를 사용하여 Word에 Ole 개체 삽입
second_title: Aspose.Words 문서 처리 API
description: .NET용 Aspose.Words를 사용하여 Word 문서에 OLE 개체를 삽입하는 방법을 알아보세요. 파일을 원활하게 삽입하려면 자세한 단계별 가이드를 따르세요.
type: docs
weight: 10
url: /ko/net/working-with-oleobjects-and-activex/insert-ole-object-with-ole-package/
---
## 소개

Word 문서에 파일을 포함시키고 싶다면 올바른 위치에 오셨습니다. ZIP 파일, Excel 시트 또는 기타 파일 형식이든 Word 문서에 직접 포함시키는 것은 매우 유용할 수 있습니다. 문서에 온갖 종류의 보물을 보관할 수 있는 비밀 칸이 있는 것과 같다고 생각하세요. 오늘은 Aspose.Words for .NET을 사용하여 이를 수행하는 방법을 살펴보겠습니다. Word 마법사가 될 준비가 되셨나요? 뛰어들어보자!

## 전제 조건

시작하기 전에 다음 사항이 있는지 확인하세요.

1. .NET용 Aspose.Words: 아직 다운로드하지 않았다면 다음에서 다운로드하세요.[여기](https://releases.aspose.com/words/net/).
2. 개발 환경: Visual Studio 또는 기타 .NET 개발 환경.
3. C#에 대한 기본 이해: 전문가가 될 필요는 없지만 C#에 대한 지식이 있으면 도움이 됩니다.
4. 문서 디렉토리: 문서를 저장하고 검색할 수 있는 폴더입니다.

## 네임스페이스 가져오기

먼저 네임스페이스를 순서대로 정리하겠습니다. 프로젝트에 다음 네임스페이스를 포함해야 합니다.

```csharp
using System;
using System.IO;
using Aspose.Words;
using Aspose.Words.Drawing;
```

따라하기 쉽도록 이것을 한 입 크기의 단계로 나누어 보겠습니다.

## 1단계: 문서 설정

당신이 빈 캔버스를 가진 예술가라고 상상해 보세요. 먼저 Word 문서인 빈 캔버스가 필요합니다. 설정 방법은 다음과 같습니다.

```csharp
// 문서 디렉터리 경로
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

이 코드는 새 Word 문서를 초기화하고 문서에 내용을 삽입하는 데 사용할 DocumentBuilder를 설정합니다.

## 2단계: Ole 개체 읽기

다음으로 삽입하려는 파일을 읽어보겠습니다. 이것을 비밀 칸에 숨기고 싶은 보물을 찾는 것과 같다고 생각하세요.

```csharp
byte[] bs = File.ReadAllBytes(dataDir + "Zip file.zip");
```

이 줄은 ZIP 파일에서 모든 바이트를 읽고 이를 바이트 배열에 저장합니다.

## 3단계: Ole 개체 삽입

이제 마법의 부분이 나옵니다. 파일을 Word 문서에 포함하겠습니다.

```csharp
using (Stream stream = new MemoryStream(bs))
{
    Shape shape = builder.InsertOleObject(stream, "Package", true, null);
    OlePackage olePackage = shape.OleFormat.OlePackage;
    olePackage.FileName = "filename.zip";
    olePackage.DisplayName = "displayname.zip";
}
```

 여기서는 바이트 배열에서 메모리 스트림을 생성하고`InsertOleObject` 문서에 삽입하는 방법입니다. 또한 포함된 개체의 파일 이름과 표시 이름도 설정합니다.

## 4단계: 문서 저장

마지막으로 우리의 걸작을 저장해 보겠습니다.

```csharp
doc.Save(dataDir + "WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

그러면 지정된 디렉터리에 포함된 파일과 함께 문서가 저장됩니다.

## 결론

그리고 거기에 있습니다! .NET용 Aspose.Words를 사용하여 Word 문서에 OLE 개체를 성공적으로 포함했습니다. 이는 문서 안에 언제든지 공개할 수 있는 숨겨진 보석을 추가하는 것과 같습니다. 이 기술은 기술 문서부터 동적 보고서에 이르기까지 다양한 애플리케이션에 매우 유용할 수 있습니다. 

## FAQ

### 이 방법을 사용하여 다른 파일 형식을 포함할 수 있나요?
예, Excel 시트, PDF, 이미지 등 다양한 파일 형식을 포함할 수 있습니다.

### Aspose.Words에 대한 라이선스가 필요합니까?
 예, 유효한 라이센스가 필요합니다. 당신은 얻을 수 있습니다[임시 면허증](https://purchase.aspose.com/temporary-license/) 평가를 위해.

### OLE 개체의 표시 이름을 어떻게 사용자 정의할 수 있나요?
 당신은 설정할 수 있습니다`DisplayName` 의 재산`OlePackage` 그것을 사용자 정의합니다.

### Aspose.Words는 .NET Core와 호환됩니까?
예, Aspose.Words는 .NET Framework와 .NET Core를 모두 지원합니다.

### Word 문서 내에 포함된 OLE 개체를 편집할 수 있나요?
아니요, Word 내에서 직접 OLE 개체를 편집할 수 없습니다. 기본 응용 프로그램에서 열어야 합니다.