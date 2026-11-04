# 작은 뮤즈 · LITTLE MUSE

한국어 AI 이미지 블로그. 설치·빌드·유료 API 없이 HTML/CSS/JavaScript만으로 운영합니다. ChatGPT 계정이나 구독은 필요하지 않습니다.

## 내 블로그

- 사이트: https://hongsia2022-netizen.github.io/little-muse-blog/
- 작업실: https://hongsia2022-netizen.github.io/little-muse-blog/admin.html
- 저장소: https://github.com/hongsia2022-netizen/little-muse-blog

## 처음 배포하기

저장소 Settings → Pages → Build and deployment에서 **Deploy from a branch**, **main**, **/(root)**를 선택하고 Save를 누릅니다. GitHub Free는 공개 저장소의 Pages를 지원합니다. 처음 반영까지 몇 분 걸릴 수 있습니다.

## 글과 이미지 올리기

1. 블로그 상단의 **작업실**을 엽니다.
2. 제목, 날짜, 카테고리, 이미지, 본문, 태그를 입력합니다. 태그는 쉼표로 구분합니다.
3. **이 글 임시 저장**을 누릅니다. 이 단계는 현재 브라우저에만 저장됩니다.
4. 처음 한 번 GitHub Settings → Developer settings → Personal access tokens → Fine-grained tokens에서 토큰을 만듭니다. Resource owner는 본인, Repository access는 **Only select repositories → little-muse-blog**, Repository permissions → **Contents: Read and write**로 지정합니다. 나머지 권한은 추가하지 않습니다. 토큰 생성과 권한 승인은 본인이 수행하세요.
5. 작업실의 발행용 토큰 칸에 넣고 **GitHub에 발행**을 누릅니다. 발행은 임시 저장된 모든 글과 프로필을 한 번에 반영합니다. 토큰은 입력 칸에서 지워지고 저장되지 않습니다. 다음 발행 때 다시 입력하세요.
6. 몇 분 뒤 공개 블로그를 새로고침합니다. Pages 빌드 상태는 저장소 Actions에서 확인할 수 있습니다.

기존 글은 내 게시물 → 수정 → 임시 저장 → 발행 순서로 수정합니다. 삭제도 발행해야 공개 사이트에 반영됩니다. 대표 캐릭터와 이름은 프로필 메뉴에서 바꿉니다. 본문은 일반 텍스트이며 HTML은 실행되지 않습니다.

## 백업과 기기 이동

작업실 **전체 백업 다운로드**를 눌러 JSON을 보관하세요. 이미지도 포함됩니다. 다른 기기에서 백업 파일을 복원할 수 있습니다. 임시 저장은 IndexedDB를 사용하며 브라우저 데이터 삭제 시 사라질 수 있습니다. 입력만 하고 임시 저장하지 않은 글은 백업에 포함되지 않습니다.

여러 기기에서 동시에 편집하면 이전 기록을 덮어쓰지 않도록 발행을 거부합니다. 먼저 작업을 백업하고 **GitHub 최신 기록으로 다시 불러오기**를 누른 뒤 변경한 글을 다시 작성하세요. 자동 병합은 지원하지 않습니다.

## 크기와 공개 범위

- 한 게시물에 대표 이미지 한 장. JPG/PNG/WebP, 원본 최대 15MB. 자동으로 긴 변 1600px, WebP로 압축합니다. 압축 결과 약 525KB를 넘으면 더 작은 이미지를 요청합니다.
- 전체 데이터 8MB, 최대 200개 게시물을 지원합니다. 이미지가 많아지면 별도 이미지 저장소로 확장해야 합니다.
- 공개 저장소의 글, 이미지, Git 변경 이력은 누구나 볼 수 있습니다. 비밀 정보는 올리지 마세요. 삭제한 게시물도 Git 이력에는 남습니다.
- 작업실은 공개 정적 화면입니다. 비밀번호로 숨기는 방식이 아니라 GitHub가 발행 권한을 검사합니다. 방문자가 만든 임시 글은 본인 브라우저에만 남습니다.
- 샘플 6장은 이 사이트용 SVG 일러스트이며 AI 생성 이미지로 표시하지 않았습니다. 실제 AI 이미지를 업로드하면 샘플 표시가 해제됩니다.
- 댓글, 회원 가입, 방문자 간 좋아요 동기화는 포함하지 않았습니다.

## 파일 구성과 직접 수정

`index.html`: 블로그, `admin.html`: 작업실, `data.json`: 프로필 및 글, `assets/`: 샘플 그림. `style.css`에서 색상과 간격을 바꿀 수 있습니다. 게시물 상세 링크는 `#post/게시물ID` 형태라 GitHub Pages 하위 경로에서도 작동합니다.

다른 저장소로 옮기면 `admin.js`의 `REPO` 값을 `계정/저장소`로 바꾸세요. 외부 글꼴·CDN·분석 스크립트를 사용하지 않습니다.

로컬 미리보기: Node.js가 있으면 프로젝트 폴더에서 `node preview.mjs` 실행 후 표시되는 주소를 엽니다. 파일을 더블클릭하는 file:// 방식은 데이터 읽기가 제한될 수 있습니다. `preview.mjs`는 로컬 미리보기 전용입니다.

## 공식 안내

- [GitHub Pages 배포 설정](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
- [GitHub 파일 수정 API와 토큰 권한](https://docs.github.com/en/rest/repos/contents#create-or-update-file-contents)

