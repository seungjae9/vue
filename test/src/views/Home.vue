<template>
  <div>
    <h1>웰컴 to {{ title }}</h1>
    <h1>웰컴 to {{ title2 }}</h1>

    <!--사용자 데이터 받고 전달하기(양방향 데이터) -->
    <input type="text" v-model="input1">
    <button type="button" @click="getData">Get</button>
    <button type="button" @click="setData">set</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: '박승재',
      title2: '광주',
      input1: 'abed',
    };
  },
  // watch 내에서 정의한 데이터가 바뀌면 와치가 캐치해서 알 수 있다.
  // 특정 데이터를 모니터링 하고 있다가 그 데이터가 바뀌는 순간에 작업 지시가능하다.
  watch: {
    // 선언한 변수와 동일하게 함수이름을 정의하면 된다.
    input1() {
      console.log(this.input1)
    }
  },
  methods: {
    getData() {
      alert(this.input1)
    },
    setData() {
      this.input1 = '1234';
    }
  },

  // 라이프사이클(생명주기)

  // db와 같은곳에서 화면 보여주기 전에 미리 데이터 처리는 created
  beforeCreate() {
    console.log('beforeCreate')
  },
  created() {
    console.log('created')
  },
  // 실제 로딩(렌더링)
  beforeMount() {
    console.log('beforeMount')
  },
  mounted() {
    console.log('mounted')
  },
  beforeUpdate() {
    console.log('beforeUpdate')
  },
  updated() {
    console.log('update')
  },
  beforeDestroy() {
    console.log('beforeDestroy')
  },
  destroyed() {
    console.log('destroyed')
  }
}
</script>