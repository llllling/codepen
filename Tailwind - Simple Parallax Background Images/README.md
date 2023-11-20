# Tailwind - Simple Parallax Background Images
- 따라한 코드 : https://codepen.io/codetimeio/pen/mGxvXd

## Tech Requirement(Tech Stack)
* tailwindcss

## Initial Setting
* tailwind 설치 및 셋팅 
    1. 패키지 설치
        ```sh
            npm install -D tailwindcss
        ```
    2.  tailwind.config.js 파일 생성
        ```sh
            npx tailwindcss init
        ```
        ```js
            module.exports = {
            content: ["./*.html, js"], //tailwind 사용할 템플릿들이 존재하는 경로 지정
            theme: {
                extend: {},
            },
            plugins: [],
            }
        ```
    3. 최상위 혹은 글로벌 CSS파일에 @tailwind 지시어들 추가
        ```css
        /* global.css */
        @tailwind base;
        @tailwind components;
        @tailwind utilities;
        ```
    4. CLI가 입력되는 코드들을 CSS로 컴파일 및 빌드하도록 실행
        * –watch :  파일의 변화를 감지하여 그 때마다 빌드를 해준다.
    ```sh
    npx tailwindcss -i ./src/style.css -o ./dist/output.css --watch
    ```
    5. HTML의 <head>에 컴파일된 Tailwind CSS 파일을 추가하고, 스타일링 코드를 작성
    ```html
    <head>
         <link href="/dist/output.css" rel="stylesheet" />
    </head>
    ```
