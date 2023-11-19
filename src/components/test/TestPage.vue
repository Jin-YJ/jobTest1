<template>
  <div  style="width : 80%;">
    <div class="parent-container">
      <div class="progress-indicator-container">
        <div
          class="progress-indicator"
          :style="{ width: progressValue + '%' }"
        ></div>
      </div>
    </div>
    <div class="questionx-container">
      <h1>{{ currentStep }}/{{ totalSteps }}</h1>
      <h2>{{ question[currentStep - 1].question }}</h2>
      <button class="buttonClass" @click="nextStep('A')">
        {{ question[currentStep - 1].A }}</button
      ><br />
      <button class="buttonClass" @click="nextStep('B')">
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
          question: "프로젝트 기획 단계에서 나는 주로:",
          A: "새롭고 창의적인 아이디어를 제시한다.",
          B: "팀이 설정한 목표를 달성하기 위한 실질적인 계획을 세운다.",
        },
        {
          question: "봉사 활동을 할 때 나는:",
          A: "사람들과 직접 상호작용하며 도움을 제공하는 것을 선호한다.",
          B: "조직의 배후에서 일하며 운영을 원활하게 하는데 기여한다.",
        },
        {
          question: "어려운 문제를 해결할 때 나는:",
          A: "복잡한 문제를 분석하고 체계적으로 접근하는 것을 좋아한다.",
          B: "직관과 경험을 바탕으로 문제에 접근한다.",
        },
        {
          question: "예술 관련 수업을 들을 때 나는:",
          A: "자유롭게 창작하는 활동에 더 몰입한다.",
          B: "예술 작품의 역사적 배경이나 이론을 배우는 것에 관심이 많다.",
        },
        {
          question: "야외 활동을 계획할 때 나는:",
          A: "모험을 즐기고 자연 속에서의 새로운 활동을 탐색한다.",
          B: "알려진 경로와 활동을 따라 안전하고 조직된 경험을 추구한다.",
        },

        {
          question: "프로젝트가 예기치 않게 변할 때 나는:",
          A: "유연하게 대처하고 새로운 상황에 적응한다.",
          B: "원래 계획을 최대한 유지하려고 노력한다.",
        },
        {
          question: "여러 업무를 처리해야 할 때 나는:",
          A: "한 번에 하나의 업무에 집중한다.",
          B: "동시에 여러 업무를 관리하며 다양성을 누린다.",
        },
        {
          question: "팀 프로젝트를 할 때 나는",
          A: "리더로서 팀을 조직하고 지휘하는 역할을 한다.",
          B: "중요한 구성원으로서 내 역할을 충실히 수행한다.",
        },
        {
          question: "긴급한 문제가 발생했을 때 나는:",
          A: "빠르게 판단하고 즉각적으로 행동에 옮긴다.",
          B: "신중하게 상황을 평가하고 다음 단계를 계획한다.",
        },
        {
          question: "복잡한 프로젝트를 맡게 되었을 때 나는:",
          A: "세부적인 사항을 관리하며 철저한 준비를 한다.",
          B: "큰 그림에 집중하며 전체적인 방향을 설정한다.",
        },

        {
          question: "수학 문제를 풀 때 나는:",
          A: "공식과 원리를 적용하여 문제를 해결한다.",
          B: "직관과 패턴 인식을 사용하여 답을 찾는다.",
        },
        {
          question: "기술적인 장비를 사용할 때 나는:",
          A: "설명서를 읽고 체계적으로 장비를 조작한다.",
          B: "시행착오를 통해 장비의 기능을 탐색한다.",
        },
        {
          question: "새로운 언어를 배울 때 나는:",
          A: "문법 규칙과 구조를 철저히 이해하고자 한다.",
          B: "대화와 실제 사용을 통해 언어를 익힌다.",
        },
        {
          question: "대중 앞에서 발표할 때 나는:",
          A: "철저히 준비하고 연습하여 발표한다.",
          B: "자연스럽고 즉흥적으로 관객과 소통한다.",
        },
        {
          question: "컴퓨터 소프트웨어를 배울 때 나는:",
          A: "공식적인 교육이나 튜토리얼을 통해 배운다.",
          B: "직접 사용해보며 기능을 탐색하고 배운다.",
        },

        {
          question: "정해진 근무시간에 대해 나는:",
          A: "일정한 근무시간을 선호하며 일과 생활의 균형을 중요시한다.",
          B: "유연한 근무시간을 선호하며 필요에 따라 근무시간을 조정한다.",
        },
        {
          question: "신체 활동이 많은 일에 대해 나는:",
          A: "신체적으로 활동적인 일을 선호한다.",
          B: "정신적으로 집중을 요하는 일을 선호한다.",
        },
        {
          question: "야외 작업에 대해 나는:",
          A: "야외에서 일하는 것을 즐긴다.",
          B: "실내에서 일하는 것을 더 편안하게 느낀다.",
        },
        {
          question: "고객과의 직접적인 상호작용에 대해 나는:",
          A: "고객과 직접 만나는 것을 즐긴다.",
          B: "백오피스에서 업무를 처리하는 것을 선호한다.",
        },
        {
          question: "직업으로 인한 자주 여행에 대해 나는:",
          A: "업무상 여행을 즐기며 새로운 환경에서 일하는 것을 기대한다.",
          B: "안정적인 근무 환경에서 지속적으로 일하는 것을 선호한다.",
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
  justify-content: center; /* 가운데 정렬 */
  align-items: center; /* 세로 방향 가운데 정렬 */
}

.questionx-container {
  flex-direction: column; /* 자식 요소들을 세로 방향으로 정렬 */
  width: 100%; /* 필요한 경우 가로 크기 조절 */
  margin-top: 20px; /* 상단 여백 조절 */
}

.buttonClass {
  background-color: rgb(150, 150, 255);
  width: 80%;
  color: white;
  font-weight: 900;
  border: 0px;
  margin-top: 10px;
}
</style>

