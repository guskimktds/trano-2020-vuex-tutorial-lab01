# Vuex 를 사용법을 확인한다.
# Vuetify 를 사용하여 화면을 구성하는 법을 익힌다.

vue create project-name 으로 프로젝트 생성

yarn serve 로 실행

# v-for 로 리스트를 표시할 때 아래와 같이 v-bind:key 를 처리해야한다.
<li v-for="(product,index) in products" v-bind:key="index">


npm install vuex --save 로 dependency 추가

src 하위에 store 디렉토리 생성
store.js 생성

main.js 에 store:store 추가

state 를 추가하여 해당 데이터를 사용하는 컴포넌트에서
this.$store.state 로 접근

getters 는 state 값을 원하는 방식으로 계산하여 돌려준다(return).

state, getters 에 값은 computed 에서 가져와서 표시하고

methods 는 mutations 로 정의된 메소드를 실행한 값을 전달한다.
이때 actions 에서 mutations 에서 정의된 메소드를 제어(setTimeout 등)할 수 있다.

마지막으로, 아래와 같이 다수의 action 과 getter 를 array 형태로 가져다 쓸 수 있다.

import { mapActions } from 'vuex';
import { mapGetters } from 'vuex';

... 중략 ...

...mapGetters([
  'saleProducts'
])

...mapActions([
  'reducePrice'
])
