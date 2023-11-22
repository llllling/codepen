# Tailwind - Simple Parallax Background Images

- 따라한 코드 : https://codepen.io/codetimeio/pen/mGxvXd

## Tech Requirement(Tech Stack)

- tailwindcss

## Initial Setting

- tailwind 설치 및 셋팅
  1. 패키지 설치
     ```sh
         npm install -D tailwindcss
     ```
  2. tailwind.config.js 파일 생성
     ```sh
         npx tailwindcss init
     ```
     ```js
     /** @type {import('tailwindcss').Config} */
     module.exports = {
       content: ["./src/**/*.{html,js}"],
       theme: {
         extend: {},
       },
       plugins: [],
     };
     ```
  3. 최상위 혹은 글로벌 CSS파일에 @tailwind 지시어들 추가
     ```css
     /* global.css */
     @tailwind base;
     @tailwind components;
     @tailwind utilities;
     ```
  4. CLI가 입력되는 코드들을 CSS로 컴파일 및 빌드하도록 실행
     - –watch : 파일의 변화를 감지하여 그 때마다 빌드를 해준다.
     ```sh
     npx tailwindcss -i ./src/input.css -o ./dist/output.css --watch
     ```
  5. HTML의 <head>에 컴파일된 Tailwind CSS 파일을 추가하고, 스타일링 코드를 작성
     ```html
     <head>
       <link href="../dist/output.css" rel="stylesheet" />
     </head>
     ```

## 진행하면서 알게 된 것들

- 더미 이미지가 필요할 때 : 로렘 픽숨(https://picsum.photos/)
- perspective : perspective를 사용하지 않으면 translateZ의 변화를 느낄수 없다. 원근감을 준다.

  - z값 변화해서 hover시 앞으로 튀어나오는 듯하게 보임
    `css
    .box:hover .tran{
transform: perspective(150px) translateZ(30px);
}
    `

  - z값 변화 X
    `css
    .box:hover .tran{
transform: translateZ(30px);
}
    `
  - perspective 의 숫자가 커질수록 멀리서 보는 느낌이 난다.

- perspective-origin : perspective와 함께사용해야하는 기준점을 지정해주는 속성, 지정안할 경우 default는 center
- backface-visibility : 뒤집어진 뒷면이 보일지/안보일지 결정
- background-attachment : 배경 이미지가 요소와 어떻게 스크롤되는지를 지정

  - local : 선택한 요소와 같이 움직입니다. 내용을 스크롤하면 배경 이미지도 스크롤
  - **fixed : 배경 이미지는 뷰포트에 고정됩니다. 요소가 스크롤되어도 배경 이미지는 고정된 위치에 유지(이 예제에서 이거 사용)**
  - scroll : 선택한 요소와 같이 움직입니다. 내용을 스크롤하면 배경 이미지는 스크롤되지 않는다.

- blockquote태그 : 긴 인용문을 담을 때 사용
  - q태그 : 짧은 인용문을 담을 때 사용
