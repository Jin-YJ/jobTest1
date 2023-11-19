<template>
  <div>
    <div class="parent-container">
      <h2><p>당신과 어울리는 직업 유형은?</p></h2>
    </div>
    <div class="parent-container">
      <h2 class="fontStyle">
        <p>{{ type.typeName }}</p>
      </h2>
    </div>
    <div>
      <img :src="type.imgName" alt="animal" class="animal-image" />
    </div>
    <div class="info-box">
      <h3>
        <p style="text-align: left">{{ type.typeName }} 유형 결과 해석</p>
      </h3>
      <p style="text-align: left">{{ type.result }}</p>
      <br /><br />

      <p class="content-header">추천직업 :</p>
      <p style="text-align: left">{{ type.jobList }}</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      type: {
        typeName: "호기심 많은 고양이",
        result:
          "이 유형은 끊임없는 호기심과 탐구적인 마인드를 가지고 있습니다. 새로운 아이디어와 개념에 대해 항상 열린 태도를 가지며, 예상치 못한 상황에서도 창의적인 해결책을 제시하는 능력이 뛰어납니다. 이러한 개인은 지적 자극과 새로운 지식을 추구하며, 미지의 영역을 탐험하는 것을 즐깁니다. 이들은 변화에 민감하고, 다양한 관점에서 사물을 바라볼 수 있어, 복잡한 문제를 해결하는데 탁월한 능력을 보입니다.",
        imgName: require("@/assets/cat.png"),
        jobList: "연구원, 발명가, 작가, 마케팅 전략가, 크리에이티브 디렉터",
      },
    };
  },
  props: {
    jobType: {
      type: String,
      default: "",
    },
  },
  mounted() {
    this.resultMethods();
  },
  methods: {
    resultMethods() {
      if (this.jobType === "AAAA") {
        //호기심 많은 고양이
        this.type["typeName"] = "호기심 많은 고양이";
        this.type["result"] =
          "이 유형은 끊임없는 호기심과 탐구적인 마인드를 가지고 있습니다. 새로운 아이디어와 개념에 대해 항상 열린 태도를 가지며, 예상치 못한 상황에서도 창의적인 해결책을 제시하는 능력이 뛰어납니다. 이러한 개인은 지적 자극과 새로운 지식을 추구하며, 미지의 영역을 탐험하는 것을 즐깁니다. 이들은 변화에 민감하고, 다양한 관점에서 사물을 바라볼 수 있어, 복잡한 문제를 해결하는데 탁월한 능력을 보입니다.";
        this.type["imgName"] = require("@/assets/cat.png");
        this.type["jobList"] =
          "연구원, 발명가, 작가, 마케팅 전략가, 크리에이티브 디렉터";
        document.body.style.backgroundColor = "#E6E6FA";
      } else if (this.jobType === "AAAB") {
        this.type["typeName"] = "유연한 개구리";
        this.type["result"] =
          "이 유형의 사람들은 변화에 매우 유연하며 적응력이 뛰어납니다. 새로운 상황과 도전에 쉽게 적응하며, 스트레스가 많은 환경에서도 침착함을 유지합니다. 이들은 다양한 상황을 잘 관리하고, 갑작스러운 문제에 대해 즉각적이고 창의적인 해결책을 찾아내는 경향이 있습니다. 또한, 다른 사람들과의 관계에서도 유연하게 대처하며, 상호작용에 있어서 긍정적이고 조화로운 태도를 보입니다.";
        this.type["imgName"] = require("@/assets/frog.png");
        this.type["jobList"] =
          "프로젝트 매니저, 이벤트 코디네이터, 컨설턴트, HR 전문가, 심리치료사";
        document.body.style.backgroundColor = "#98FF98";
      } else if (this.jobType === "AABA") {
        this.type["typeName"] = "정리에 진심인 다람쥐";
        this.type["result"] =
          "이 유형은 매우 체계적이고 조직적입니다. 세부 사항에 집중하며, 계획과 질서를 중시합니다. 이들은 일을 체계적으로 관리하고, 목표를 설정하며 이를 달성하기 위한 구체적인 계획을 세웁니다. 높은 수준의 집중력과 꼼꼼함으로 복잡한 정보를 잘 다루며, 장기적인 프로젝트 관리에 강점을 보입니다. 이 유형은 정확성과 효율성을 중요시하며, 질서 정연한 환경에서 최고의 성과를 냅니다.";
        this.type["imgName"] = require("@/assets/squirrel.png");
        this.type["jobList"] =
          "회계사, 관리자, 데이터 분석가, 도서관 사서, 사무 관리자";
        document.body.style.backgroundColor = "#F5F5DC";
      } else if (this.jobType === "AABB") {
        this.type["typeName"] = "계획적인 개미 엔지니어";
        this.type["result"] =
          "이 유형의 사람들은 복잡한 시스템이나 프로세스를 잘 이해하고, 그 안에서 최적의 해결책을 찾아내는 데 능숙합니다. 그들은 꼼꼼한 세부 사항에 주의를 기울이면서도, 전체적인 목표와 큰 그림을 놓치지 않습니다. 계획적인 개미 엔지니어는 모든 작업을 미리 계획하고, 이 계획에 따라 일관성 있게 행동하는 것을 선호합니다. 이러한 체계적 접근은 프로젝트 관리, 팀 리딩, 그리고 복잡한 과제 해결에서 큰 장점으로 작용합니다. 이들은 또한, 팀 내에서 업무의 흐름을 조율하고, 모든 구성원이 일정에 맞춰 효과적으로 업무를 수행할 수 있도록 돕는 데 중요한 역할을 합니다.";
        this.type["imgName"] = require("@/assets/ant.png");
        this.type["jobList"] =
          "엔지니어, 프로젝트 플래너, 건축가, 운영 관리자, 시스템 분석가";
        document.body.style.backgroundColor = "#707070";
      } else if (this.jobType === "ABAA") {
        this.type["typeName"] = "자유로운 나비";
        this.type["result"] =
          "이 유형은 자유롭고 창의적인 사고를 선호합니다. 새롭고 다양한 아이디어를 즐기며, 전통적인 틀을 벗어난 접근을 추구합니다. 자유로운 나비는 유연하고 개방적인 사고방식을 가지고 있어, 새로운 환경과 변화에 잘 적응합니다. 이들은 종종 예술적 감각이 뛰어나며, 비전을 현실로 만드는 능력을 갖추고 있습니다.";
        this.type["imgName"] = require("@/assets/butterfly.png");
        this.type["jobList"] =
          "예술가, 디자이너, 작가, 창업가, 광고 크리에이터";
        document.body.style.backgroundColor = "#87CEFA";
      } else if (this.jobType === "ABAB") {
        this.type["typeName"] = "시간 관리가 철저한 벌";
        this.type["result"] =
          "이 유형은 높은 수준의 조직력과 시간 관리 능력을 갖추고 있습니다. 계획을 세우고, 업무를 체계적으로 관리하는 데 능숙합니다. 시간 관리가 철저한 벌은 효율성과 생산성을 중시하며, 목표 달성을 위해 체계적인 절차를 따르는 것을 선호합니다. 이들은 팀 내에서도 업무 진행 상황을 정리하고, 일정을 관리하는 중요한 역할을 합니다.";
        this.type["imgName"] = require("@/assets/bee.png");
        this.type["jobList"] =
          "프로젝트 매니저, 행정 관리자, 운영 관리자, 이벤트 플래너, 회계사";
        document.body.style.backgroundColor = "#FFFF00";
      } else if (this.jobType === "ABBA") {
        this.type["typeName"] = "질서 정연한 판다 사무관";
        this.type["result"] =
          "이 유형은 질서와 규칙을 중시하는 성향을 가지고 있습니다. 체계적이고 꼼꼼한 접근 방식으로 일을 처리하며, 안정과 일관성을 중요하게 여깁니다. 질서 정연한 판다는 세부 사항에 주의를 기울이며, 정확하고 체계적인 업무 수행을 선호합니다. 이들은 안정적이고 예측 가능한 환경에서 최고의 성과를 냅니다.";
        this.type["imgName"] = require("@/assets/panda.png");
        this.type["jobList"] =
          "사무직, 법률보조원, 품질 관리 전문가, 데이터 입력 및 분석가, 사서";
        document.body.style.backgroundColor = "#A8A8A8";
      } else if (this.jobType === "ABBB") {
        this.type["typeName"] = "꼼꼼한 비버 건축가";
        this.type["result"] =
          "이 유형은 세부 사항에 대한 주의와 정밀한 작업을 선호합니다. 구조적인 사고와 철저한 계획으로 복잡한 프로젝트를 성공적으로 관리합니다. 꼼꼼한 비버는 자신의 업무에 매우 집중하며, 정교하고 정밀한 결과물을 만드는 데 탁월한 능력을 가지고 있습니다. 이들은 기술적이고 정밀한 작업을 선호하며, 장기적인 프로젝트에서도 꾸준한 집중력을 유지합니다.";
        this.type["imgName"] = require("@/assets/beaver.png");
        this.type["jobList"] =
          "건축가, 엔지니어, 그래픽 디자이너, 캐드 드래프터, 제품 디자이너";
        document.body.style.backgroundColor = "#A52A2A";
      } else if (this.jobType === "BAAA") {
        this.type["typeName"] = "모험을 즐기는 여우";
        this.type["result"] =
          "이 유형은 모험적이고 적극적인 태도를 가지고 있습니다. 새롭고 도전적인 상황을 즐기며, 빠르게 변화하는 환경에서도 흥미를 느낍니다. 모험을 즐기는 여우는 리스크를 감수하고, 미지의 영역을 탐험하는 것을 두려워하지 않습니다. 이들은 창의적이고 혁신적인 사고를 가지고 있으며, 자신만의 독특한 방식으로 문제를 해결합니다.";
        this.type["imgName"] = require("@/assets/fox.png");
        this.type["jobList"] =
          "기업가, 마케팅 전략가, 여행 작가, 이벤트 기획자, 모험 관련 가이드";
        document.body.style.backgroundColor = "#FFA500";
      } else if (this.jobType === "BAAB") {
        this.type["typeName"] = "에너지 넘치는 강아지";
        this.type["result"] =
          "이 유형은 활기차고 열정적입니다. 어떤 상황에서도 긍정적인 태도를 유지하며, 팀에 에너지를 불어넣습니다. 에너지 넘치는 강아지는 빠르게 행동하고, 즉각적인 결과를 추구하는 경향이 있습니다. 이들은 팀워크를 중시하며, 열정적으로 소통하고 협력합니다. 이러한 성향은 활발하고 역동적인 작업 환경에서 빛을 발합니다.";
        this.type["imgName"] = require("@/assets/puppy.png");
        this.type["jobList"] =
          "영업 담당자, 고객 서비스 대표, 교육자, 홍보 전문가, 체육 교사";
        document.body.style.backgroundColor = "#FF6347";
      } else if (this.jobType === "BABA") {
        this.type["typeName"] = "효율을 중시하는 매";
        this.type["result"] =
          "이 유형은 효율성과 목적 달성을 중시합니다. 전략적인 사고와 목표 지향적인 접근 방식을 가지고 있으며, 결과를 빠르게 달성하기 위한 최적의 경로를 찾아냅니다. 효율을 중시하는 매는 분석적이고 논리적인 사고를 가지고 있으며, 복잡한 상황에서도 핵심을 파악하는 능력이 뛰어납니다. 이들은 자원을 최적화하고, 시간과 노력을 효과적으로 관리합니다.";
        this.type["imgName"] = require("@/assets/hawk.png");
        this.type["jobList"] =
          "비즈니스 분석가, 물류 관리 매니저, 재무 분석가, 시스템 엔지니어, 경영 컨설턴트";
        document.body.style.backgroundColor = "#4682B4";
      } else if (this.jobType === "BABB") {
        this.type["typeName"] = "실용적인 코뿔소 기술자";
        this.type["result"] =
          "이 유형은 실용적이고 현실적인 접근을 중시합니다. 구체적이고 현실적인 해결책을 찾으며, 실질적인 결과를 추구합니다. 실용적인 코뿔소는 복잡한 기술적 문제를 해결하는 데 능숙하며, 논리적이고 체계적인 사고를 통해 실제적인 솔루션을 제공합니다. 이들은 물리적인 작업이나 기술적인 작업에서 강점을 보이며, 구체적이고 실용적인 결과물을 만드는 데 탁월한 능력을 가지고 있습니다.";
        this.type["imgName"] = require("@/assets/rhinoceros.png");
        this.type["jobList"] =
          "기계 엔지니어, 전기 기술자, IT 기술 지원, 건축 기술자, 자동차 기술자";
        document.body.style.backgroundColor = "#B0C4DE";
      } else if (this.jobType === "BBAA") {
        this.type["typeName"] = "전문 지식을 가진 올빼미 교수";
        this.type["result"] =
          "이 유형은 깊은 지식과 전문성을 추구합니다. 학문적 탐구와 지적 호기심이 높으며, 복잡한 개념을 이해하고 가르치는 데 뛰어난 능력을 보입니다. 전문 지식을 가진 올빼미는 연구와 분석에 강하며, 지식을 체계적으로 정리하고 전달하는 데 능숙합니다. 이들은 깊이 있는 사고와 고차원적인 문제 해결 능력을 가지고 있습니다.";
        this.type["imgName"] = require("@/assets/owl.png");
        this.type["jobList"] =
          "대학 교수, 연구원, 고급 컨설턴트, 전문 작가, 과학자";
        document.body.style.backgroundColor = "#00008B";
      } else if (this.jobType === "BBAB") {
        this.type["typeName"] = "체계적인 거미 웹 디자이너";
        this.type["result"] =
          "이 유형은 체계적이고 구조적인 사고를 선호합니다. 복잡한 시스템이나 프로젝트를 효율적으로 관리하며, 세심한 계획과 정교한 디자인을 추구합니다. 체계적인 거미는 논리적이고 분석적인 접근으로 문제를 해결하며, 자신의 작업에 깊은 집중력을 보입니다. 이들은 정보를 체계적으로 정리하고, 구조화하는 데 능숙합니다.";
        this.type["imgName"] = require("@/assets/spider.png");
        this.type["jobList"] =
          "웹 개발자, 아키텍처 디자이너, 시스템 분석가, UX/UI 디자이너, 프로그래머";
        document.body.style.backgroundColor = "#8A2BE2";
      } else if (this.jobType === "BBBA") {
        this.type["typeName"] = "안정을 추구하는 코알라";
        this.type["result"] =
          "이 유형은 안정성과 일관성을 중시합니다. 예측 가능한 환경과 안정적인 작업 흐름을 선호하며, 규칙과 절차를 따르는 것에 편안함을 느낍니다. 안정을 추구하는 코알라는 신중하고 차분한 접근을 하며, 장기적인 관점에서 안정적인 결과를 추구합니다. 이들은 변동성이 적은 환경에서 꾸준한 성과를 보입니다.";
        this.type["imgName"] = require("@/assets/koala.png");
        this.type["jobList"] =
          "행정 관리자, 회계사, 고객 서비스 담당자, 은행원, 보험사 직원";
        document.body.style.backgroundColor = "#D3D3D3";
      } else if (this.jobType === "BBBB") {
        this.type["typeName"] = "전통을 중시하는 현자 거북이";
        this.type["result"] =
          "이 유형은 전통적이고 신중한 접근을 선호합니다. 검증된 방법과 경험에 기반하여 결정을 내리며, 변화보다는 일관성과 신뢰성을 중요시합니다. 전통을 중시하는 현자 거북이는 장기적이고 지속 가능한 솔루션을 추구하며, 신중하고 깊이 있는 사고를 통해 문제를 해결합니다. 이들은 신중한 계획과 심사숙고를 통해 결정을 내리는 경향이 있습니다.";
        this.type["imgName"] = require("@/assets/turtle.png");
        this.type["jobList"] =
          "법률가, 역사학자, 고전 문학 연구가, 품질 관리자, 정책 분석가";
        document.body.style.backgroundColor = "#013220";
      }
    },
  },
};
</script>
<style scoped>
.fontStyle {
  color: black;
}
.parent-container {
  /* 부모 컨테이너 클래스를 추가합니다. */
  display: flex;
  justify-content: center; /* 수평 중앙 정렬 */
}

.info-box {
  border: 1px solid #989dff; /* 테두리 */
  border-radius: 20px; /* 모서리 둥글게 */
  padding: 5%; /* 내부 여백 */
  margin: 5% 10%; /* 외부 여백 */
  background-color: #e0d9ff; /* 배경색 */
}
.content-header {
  text-align: left;
  font-weight: 900;
}
.content-substance {
  text-align: left;
}

.animal-image {
  width: 20%;
  height: 30%;
}
</style>
