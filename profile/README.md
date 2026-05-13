# 📄 Document Summary & Classification System

문서 파일을 업로드하면 OCR 및 텍스트 추출을 통해 원문 내용을 저장하고,  
LLM을 활용하여 문서 요약과 카테고리 분류 결과를 제공하는 프로젝트입니다.

---

## 📌 Repositories

현재 Organization 내에서 관리될 주요 레포지토리입니다.

| Repository | Description | Status |
| --- | --- | --- |
| `project-sub` | 사용자 화면 및 파일 업로드 UI / FastAPI 기반 API 서버 | 예정 |
| `database` | DB 스키마 및 저장 구조 관리 | 예정 |
| `docs` | 프로젝트 문서 및 설계 ppt | 예정 |

---

## 🧭 Project Flow

아래 이미지는 전체 서비스 흐름을 나타냅니다.

<p align="center">
    <img width="1024" height="1536" alt="흐름도" src="https://github.com/user-attachments/assets/d6c6580c-bf65-4854-abfa-b4697a1ff926" />
</p>

---

## ⚙️ Main Features

### 1. 파일 업로드

사용자는 PDF, DOCX, HWP 등의 문서 파일을 업로드할 수 있습니다.

### 2. OCR 및 텍스트 추출

업로드된 파일에서 원문 텍스트를 추출합니다.

- 이미지 기반 문서: OCR 처리
- 텍스트 기반 문서: PDF, DOCX, HWP 등에서 텍스트 추출
- 텍스트 추출 : 간략히, 기본, 상세히 타입을 통해 요약 길이에 맞춰 추출

### 3. 원본 텍스트 저장

추출된 원본 텍스트는 DB에 저장됩니다.

### 4. LLM 분석

저장된 텍스트를 기반으로 LLM이 문서를 분석합니다.

- 문서 요약

### 5. 분석 결과 저장

요약 결과를 DB에 저장합니다.

### 6. 결과 화면 출력

사용자는 화면에서 문서 요약 결과와 카테고리 정보를 확인할 수 있습니다.

### 7. 결과 파일 다운로드

필요한 경우 요약 결과를 다운로드할 수 있습니다.

---

## 🏗️ System Architecture

```text
User
 └─ File Upload
      └─ OCR / Text Extraction
           └─ Save Original Text
                └─ LLM Summary & Classification
                     └─ Save Result
                          └─ Display Result
                               └─ Download Result File
