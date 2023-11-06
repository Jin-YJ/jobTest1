<template>
    <div class="mainContainer">
        <img :src="image" />
        <div class="container">
            <button class="buttonClass" @click="testStart"> 테스트 시작하기</button>
        </div>
    </div>
    
</template>
<script>
import image from '@/assets/main.png';

export default {
    data() {
        return {
            image : image
        }
    },
    methods : {
        testStart() {
            this.$emit('changePage', 'TEST' , '');
        }
    }
}
</script>
<style>
.container {
  display: flex;
  justify-content: center; /* 가로 중앙 정렬 */
  align-items: center; /* 세로 중앙 정렬 */
}
.mainContainer {
    justify-content: center; /* 가로 중앙 정렬 */
    align-items: center; /* 세로 중앙 정렬 */
}
.buttonClass {
    background-color : rgb(150, 150, 255);
    width : 300px; 
    height : 50px; 
    color: white;
    font-weight: 900 ;
    border : 0px;
}
</style>