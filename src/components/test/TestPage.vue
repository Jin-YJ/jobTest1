<template>
  <div class="main-container">
    <div class="parent-container">
      <div class="progress-indicator-container">
        <div
          class="progress-indicator"
          :style="{ width: progressValue + '%' }"
        ></div>
      </div>
    </div>
    <div class="questionx-container cute-font" >
      <h1>{{ currentStep }}/{{ totalSteps }}</h1>
      <h2>{{ question[currentStep - 1].question }}</h2>
      <button class="buttonClass cute-font" @click="nextStep('A')">
        {{ question[currentStep - 1].A }}</button
      ><br />
      <button class="buttonClass cute-font" @click="nextStep('B')">
        {{ question[currentStep - 1].B }}
      </button>
    </div>
  </div>
</template>
<script>
export default {
  components: {},
  data() {
    return {
      question: [
        {
          question: "여행을 계획할때 나는?",
          A: "계획은 무슨 계획이야! 일단 출발하고 본다.",
          B: "시간별로 꼼꼼하게 어디를 갈지 계획을 세운다.",
        },
        {
          question: "친구들과의 모임에서 나는?",
          A: "타고난 썰부자! 이 구역 MC는 나야나!",
          B: "본투비 리스너👂, 이야기를 잘 들어주며 적절한 리액션으로 편안한 분위기를 만든다.",
        },
        {
          question: "설레는 소개팅을 마친 후 그(녀)와 약속이 잡혔다. 맛집을 찾을때 나는?",
          A: "리뷰부터 별점까지 리스트로 작성해서 선택한다",
          B: "위치, 메뉴, 분위기만 보고 끌리는 곳으로 선택한다.",
        },
        {
          question: "영화를 보러가기로 했다 이때 나는?",
          A: "외계생명체, 우주, 인조인간 얘기가 재밌지! SF영화를 고른다.",
          B: "감동적인 역사적 사실이나 인물 얘기가 좋아! 역사영화를 고른다.",
        },
        {
          question: "한 주가 지나고 주말이 왔다! 이때 나는?",
          A: "집에서 쉬기에는 주말이 너무 아까워! 뭐 할지 검색을 해본다!",
          B: "나가긴 어딜나가.. 집에서 넷플릭스나 봐야지!",
        },

        {
          question: "제주도 휴가의 마지막 날, 풍랑주의보 때문에 예매해뒀던 배편이 취소됐다. 이때 나는?",
          A: "그래도 회사는 가야지! 어떻게든 돌아갈 방법을 찾는다.",
          B: "이건 하루 더 쉬라는 하늘의 뜻이야!’ 빠르게 포기하고 휴가를 연장한다.",
        },
        {
          question: "일주일간의 여름휴가 끝! 회사로 복귀한 나, 그런데 밀린 일이 산더미처럼 쌓여있다. 이때 나는?",
          A: "천리길도 한 걸음부터! 차근차근 하나씩 계획적으로 처리한다.",
          B: "일이 이렇게 많은데.. 닥치는대로 한 번에 처리하자! 동시에 여러 업무를 진행한다.",
        },
        {
          question: "오늘 퇴근 후에 갑자기 부장님의 회식령이 떨어졌다!",
          A: "주도적으로 회식 장소를 정하고 장소와 일정 등을 동료들에게 전파한다.",
          B: "‘그런 걸 뭐하러 신경 써 알아서 정해서 알려주겠지’. 누군가 정해줄 때까지 기다린다.",
        },
        {
          question: "중요한 발표를 한 시간 앞둔 상황! 그런데 회의실의 빔프로젝터가 갑자기 고장 났다! 이때 나는?",
          A: "최대한 다른 회의실을 찾아보고, 여의치 않다면 프로젝터 없이라도 당일에 진행한다.",
          B: "양해를 구해 발표를 연기하고 다음을 기약한다.",
        },
        {
          question: "새로운 마음으로 새 출발을 기약하는 당신! 오랜만에 집안 대청소를 하려는데...",
          A: "거실, 부엌, 안방 순서로 “장소” 위주로 청소한다.",
          B: "먼지 털기, 청소기 돌리기, 걸레질 순서로 “행동” 위주로 청소한다. ",
        },

        {
          question: "여행에서 사용할 예산을 세울 때 나는?",
          A: "펜션 30만 원. 식비 10만 원. 교통비 10만 원. 대략적으로 크게 잡는다.",
          B: "펜션 1박 357,000원, 교통비 95,700원, 최대한 구체적으로 잡는다.",
        },
        {
          question: "오랜만에 큰 맘 먹고 최신형 휴대폰을 플렉스했다! 이때 나는?",
          A: "‘무슨 기능이 추가 됐지?’ 주요 기능 및 필수 프로그램을 꼼꼼히 알아보고 활용한다.",
          B: "‘오, 그립감 미쳤다!’ 디자인에 감탄하며 어울리는 케이스와 그립톡을 검색한다.",
        },
        {
          question: "3개월 뒤, 한 달 동안 해외여행을 가려고 한다. 최대한 현지어를 배워가려고 하는데 이럴 때 나는?",
          A: "‘모든 언어는 알파벳부터..’ 학원이나 인강을 등록해 공부를 시작한다.",
          B: "‘언어는 자신감!’ 언어 교환 모임이나 이태원 등을 찾아가 무작정 실전 감각부터 키운다.",
        },
        {
          question: "오랫동안 열심히 기획한 상품의 발표날이 잡혔다! 이때 나는?",
          A: "시간 여유를 갖고 자료와 대본을 꼼꼼하게 준비해 발표 전날까지 완벽하게 연습한다.",
          B: "일단 큰 그림만 세워 놓고 나머지는 그날의 애드립에 맡긴다.",
        },
        {
          question: "힘든 한 주가 끝나고 드디어 돌아온 주말! 수고한 만큼 나를 위한 시간을 보내고 싶은데.. 이때 나는?",
          A: "‘이 아까운 시간을 그냥 보낼 순 없어!’ 알찬 주말을 위해 이미 세워둔 일정이 있다.",
          B: "‘어차피 그때그때 맨날 바뀌어’ 주말 직전 혹은 당일에 정한다.",
        },

        {
          question: "내가 선호하는 근무 스케쥴은?",
          A: "일정한 근무시간을 선호하며 일과 생활의 균형을 중요시한다.",
          B: "유연한 근무시간을 선호하며 필요에 따라 근무시간을 조정한다.",
        },
        {
          question: "‘오늘 진짜 열심히 일했다!’ 싶은 마음이 드는 업무는?",
          A: "이리 뛰고, 저리 뛰고 온 몸이 땀범벅, 몸이 힘들어야 일한 맛이 난다.",
          B: "가만히 앉아서 코딩만 10시간 째... 정신이 고단해야 일한 맛이 난다.",
        },
        {
          question: "외근 vs 내근, 둘 중에 나는?",
          A: "‘실내는 너무 답답해!’ 상사 눈치도 피하고, 코에 바람도 쐬고! 외근이 더 좋아!",
          B: "‘돌아다니는 거 너무 힘들어..’ 여름엔 시원하고 겨울엔 따뜻한 내근이 더 좋아!",
        },
        {
          question: "내가 선호하는 업무 스타일은?",
          A: "고객과 직접 대면하거나 동료와의 협업이 더 좋다.",
          B: "처음부터 끝까지 혼자 기획하고 처리하는 일이 더 좋다.",
        },
        {
          question: "새로운 직장으로의 이직! 이때 나는?",
          A: "해외, 지방 출장 등 새로운 자극과 기회가 많은 곳이 좋다.",
          B: "변화가 많지 않은 익숙하고 편안한 환경이 더 좋다. ",
        },
      ],
      questionnaire: "",
      ans1: "",
      ans2: "",
      result: [],
      currentStep: 1,
      totalSteps: 20, // 여기서는 총 5단계로 가정
      progressValue: 5, // 처음에는 20%로 시작 (100 / 5 단계)
    };
  },
  methods: {
    nextStep(type) {
      if (this.result.length >= 19) {
        var count = 0;
        for (var i = 0; i < 5; i++) {
          //흥미와 선호
          if (this.result[i] === "A") {
            count++;
          }
        }
        res = count >= 3 ? "A" : "B";
        count = 0;

        for (i = 5; i < 10; i++) {
          //업무 스타일 및 선호도
          if (this.result[i] === "A") {
            count++;
          }
        }
        res += count >= 3 ? "A" : "B";
        count = 0;

        for (i = 10; i < 15; i++) {
          //개인 능력 및 자질
          if (this.result[i] === "A") {
            count++;
          }
        }
        res += count >= 3 ? "A" : "B";
        count = 0;

        for (i = 15; i < 20; i++) {
          //작업 환경 및 조건 선호
          if (this.result[i] === "A") {
            count++;
          }
        }
        res += count >= 3 ? "A" : "B";

        this.$emit("changePage", res);
      } else {
        this.currentStep += 1;
        this.progressValue = (this.currentStep / this.totalSteps) * 100;
        this.result.push(type);
        var res = "";
      }
    },
  },
};
</script>
<style>
.main-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 80%;
  margin: 0 auto; /* 가운데 정렬을 위해 자동 마진 적용 */
}
.progress-indicator-container {
  width: 70%;
  background-color: rgb(172, 215, 231);
  border-radius: 5px;
  overflow: hidden;
  height: 20px;
}

.progress-indicator {
  height: 100%;
  background-color: rgb(150, 150, 255);
  transition: width 0.5s ease;
}

.parent-container {
  display: flex;
  justify-content: center; /* 수평 중앙 정렬 */
  align-items: center; /* 세로 방향 가운데 정렬 */
}

.parent-container, .questionx-container {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%; /* 전체 너비 사용 */
}
.questionx-container {
  flex-direction: column;
  margin-top: 20px;
}

.buttonClass {
  background-color: rgb(150, 150, 255);
  width: 80%; /* 버튼 너비 조정 */
  color: white;
  font-weight: 900;
  border: 0px;
  margin-top: 10px;
  font-size: 20px;
}
</style>

