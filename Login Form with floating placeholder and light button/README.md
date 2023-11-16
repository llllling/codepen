# Login Form with floating placeholder and light button

- 따라한 코드 : https://codepen.io/soufiane-khalfaoui-hassani/pen/LYpPWda

A Pen created on CodePen.io. Original URL: [https://codepen.io/MISEONGKIM/pen/gOqGdgE](https://codepen.io/MISEONGKIM/pen/gOqGdgE).

## 진행하면서 알게된 점

- linear-gradient : 그라데이션 첫번째 인자 생략시 to bottom이 default
  ```
  background: linear-gradient(#141e30, #243b55);
  ```

* outline : 모든 외곽선 속성을 한꺼번에 지정하는 것.
  - border(테두리)와 매우 유사하지만 외곽선은 요소 콘텐츠의 밖에 그려지며 절대 공간을 차지하지 않는다는 차이점이 있음.
  * 많은 요소들은 해당 스타일이 기본적으로 none이여서 지정되어있지 않다. input요소만 예외로 브라우저의 기본 스타일이 적용됨.
  * input요소에서 포커스 될 때 outline 나옴, 이 값을 0 또는 none 값을 지정하면 브라우저의 기본 포커스 스타일이 사라짐. none으로 설정 시 웹 접근성을 위해서 다른 디자인으로 반드시 시각으로 포커스 여부를 나타낼 수 있도록 해야함.
