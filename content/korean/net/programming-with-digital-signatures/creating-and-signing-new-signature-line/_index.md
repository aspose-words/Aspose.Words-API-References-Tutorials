---
title: 새 서명란 생성 및 서명
linktitle: 새 서명란 생성 및 서명
second_title: Aspose.Words 문서 처리 API
description: 이 단계별 튜토리얼을 통해 .NET용 Aspose.Words를 사용하여 Word 문서에서 서명란을 만들고 디지털 서명하는 방법을 알아보세요. 문서 자동화에 적합합니다.
type: docs
weight: 10
url: /ko/net/programming-with-digital-signatures/creating-and-signing-new-signature-line/
---
## 소개

안녕하세요! 따라서 Word 문서가 있고 서명란을 추가한 다음 디지털로 서명해야 합니다. 까다로운 것 같나요? 별말씀을요! .NET용 Aspose.Words 덕분에 단 몇 줄의 코드만으로 이 작업을 원활하게 수행할 수 있습니다. 이 튜토리얼에서는 환경 설정부터 반짝이는 새 서명으로 문서를 저장하는 것까지 전체 프로세스를 안내합니다. 준비가 된? 뛰어들어보자!

## 전제 조건

코드를 시작하기 전에 필요한 모든 것이 있는지 확인하겠습니다.
1.  .NET용 Aspose.Words - 다음을 수행할 수 있습니다.[여기에서 다운로드하십시오](https://releases.aspose.com/words/net/).
2. .NET 개발 환경 - Visual Studio를 적극 권장합니다.
3. 서명할 문서 - 간단한 Word 문서를 만들거나 기존 문서를 사용합니다.
4.  인증서 파일 - 디지털 서명에 필요합니다. 당신은 사용할 수 있습니다`.pfx` 파일.
5. 서명란용 이미지 - 선택적으로 서명용 이미지 파일입니다.

## 네임스페이스 가져오기

먼저 필요한 네임스페이스를 가져와야 합니다. 이 단계는 Aspose.Words 기능을 사용하기 위한 환경을 설정하므로 중요합니다.

```csharp
using System;
using System.IO;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Saving;
using Aspose.Words.Signing;
```

## 1단계: 문서 디렉토리 설정

모든 프로젝트에는 좋은 시작이 필요합니다. 문서 디렉터리의 경로를 설정해 보겠습니다. 여기에 귀하의 문서가 저장되고 검색됩니다.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2단계: 새 문서 만들기

이제 Aspose.Words를 사용하여 새로운 Word 문서를 만들어 보겠습니다. 이것이 서명란을 추가하는 캔버스가 됩니다.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3단계: 서명란 삽입

 이것이 바로 마법이 일어나는 곳입니다. 우리는 다음을 사용하여 문서에 서명란을 삽입합니다.`DocumentBuilder` 수업.

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## 4단계: 서명란이 포함된 문서 저장

서명란이 작성되면 문서를 저장해야 합니다. 이는 서명을 진행하기 전의 중간 단계입니다.

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

## 5단계: 서명 옵션 설정

이제 문서 서명 옵션을 설정해 보겠습니다. 여기에는 서명란 ID와 사용할 이미지 지정이 포함됩니다.

```csharp
SignOptions signOptions = new SignOptions
{
    SignatureLineId = signatureLine.Id,
    SignatureLineImage = File.ReadAllBytes(dataDir + "Enhanced Windows MetaFile.emf")
};
```

## 6단계: 인증서 로드

디지털 서명에는 인증서가 필요합니다. 여기서는 문서 서명에 사용될 인증서 파일을 로드합니다.

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

## 7단계: 문서에 서명하기

 이것이 마지막 단계입니다. 우리는`DigitalSignatureUtil`문서에 서명하는 클래스입니다. 서명된 문서가 새 이름으로 저장됩니다.

```csharp
DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
    dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);
```

## 결론

그리고 거기에 있습니다! 이러한 단계를 통해 새 Word 문서를 성공적으로 만들고, 서명란을 추가하고, Aspose.Words for .NET을 사용하여 디지털로 서명했습니다. 문서 자동화를 쉽게 만들어주는 강력한 도구입니다. 계약서, 동의서 또는 기타 공식 문서를 처리할 때 이 방법을 사용하면 문서의 안전한 서명 및 인증을 보장할 수 있습니다.

## FAQ

### 서명란에 다른 이미지 형식을 사용할 수 있나요?
예, PNG, JPG, BMP 등과 같은 다양한 이미지 형식을 사용할 수 있습니다.

###  꼭 사용해야 하나요?`.pfx` file for the certificate?
 예,`.pfx` 파일은 인증서 및 개인 키를 포함한 암호화 정보를 저장하기 위한 일반적인 형식입니다.

### 단일 문서에 여러 서명란을 추가할 수 있나요?
전적으로! 각 서명에 대해 삽입 단계를 반복하여 여러 서명란을 삽입할 수 있습니다.

### 디지털 인증서가 없으면 어떻게 되나요?
신뢰할 수 있는 인증 기관으로부터 디지털 인증서를 얻거나 OpenSSL과 같은 도구를 사용하여 디지털 인증서를 생성해야 합니다.

### 문서의 디지털 서명을 어떻게 확인하나요?
서명된 문서를 Word에서 열고 서명 세부 정보로 이동하여 서명의 신뢰성과 무결성을 확인할 수 있습니다.