<template>
    <div>
        <div class="parent-container">
            <div class="progress-indicator-container">
                <div class="progress-indicator" :style="{ width: progressValue + '%' }"></div>
            </div>
        </div>
        <div class="questionx-container">
            <h1>{{currentStep}}/{{totalSteps}}</h1>
            <h2>{{question[currentStep-1].question}}</h2>
            <button class="buttonClass" @click="nextStep('A')">{{question[currentStep-1].A}}</button><br>
            <button class="buttonClass" @click="nextStep('B')">{{question[currentStep-1].B}}</button>
        </div>
    </div>
</template>
<script>


export default {
    components: {
        
    },
    data () {
        return {
            question : [
                {
                    question: "새로운 문제에 직면했을 때, 나는...",
                    A: "바로 해결책을 찾기 위해 뛰어든다.",
                    B: "주변 사람들과 의견을 나눈다."
                },
                {
                    question: "복잡한 문제를 해결할 때, 나는...",
                    A: "체계적인 접근을 선호한다.",
                    B: "직관에 의존한다."
                },
                {
                    question: "특정 문제에 대한 해결책을 찾을 때, 나는...",
                    A: "이미 입증된 방법을 따른다.",
                    B: "독창적인 방법을 시도한다."
                },
                {
                    question: "문제 해결 과정에서, 나는...",
                    A: "세부 사항에 집중한다.",
                    B: "전체적인 그림을 본다."
                },
                {
                    question: "작업 중 문제에 부딪혔을 때, 나는...",
                    A: "전문가의 조언을 구한다.",
                    B: "자신의 경험에 의존한다."
                },

                {
                    question: "팀 프로젝트에서 나는...",
                    A: "구성원 각자의 업무를 조정한다.",
                    B: "팀의 분위기와 동기를 다진다."
                },
                {
                    question: "동료와의 갈등이 생겼을 때, 나는...",
                    A: "논리적으로 문제를 해결하려 한다.",
                    B: "감정의 조화를 우선시한다."
                },
                {
                    question: "의견을 조율할 때, 나는...",
                    A: "사실에 기반하여 의견을 제시한다.",
                    B: "다른 사람의 감정을 고려한다."
                },
                {
                    question: "팀 미팅에서 나는...",
                    A: "의제에 따라 정확하게 토론에 참여한다.",
                    B: "자유로운 토론을 선호한다."
                },
                {
                    question: "협력할 때 나는...",
                    A: "각자의 역할이 분명히 정의되길 원한다.",
                    B: "유동적인 역할 분담을 선호한다."
                },

                {
                    question: "프로젝트를 수행할 때, 나는...",
                    A: "목표를 세우고 체계적으로 진행한다.",
                    B: "탐색적으로 접근하며 아이디어를 모색한다."
                },
                {
                    question: "일정한 업무 리듬을 유지하는 것에 대해 나는...",
                    A: "안정감을 느낀다.",
                    B: "지루함을 느낀다."
                },
                {
                    question: "새로운 업무를 배울 때, 나는...",
                    A: "단계별로 배우길 원한다.",
                    B: "바로 실전에 투입되길 원한다."
                },
                {
                    question: "일을 처리하는 방식에 대해 나는...",
                    A: "계획적이고 조직적이다.",
                    B: "즉흥적이고 융통성이 있다."
                },
                {
                    question: "복잡한 업무를 처리할 때, 나는...",
                    A: "목록을 만들고 우선순위를 정한다.",
                    B: "가장 관심 가는 부분부터 시작한다."
                },

                {
                    question: "업무에 임할 때, 나는...",
                    A: "성과를 향한 명확한 동기가 필요하다.",
                    B: "과정 자체에서 만족을 찾는다."
                },
                {
                    question: "성공에 대해 나는...",
                    A: "구체적인 결과로 측정한다.",
                    B: "개인적 성장으로 측정한다."
                },
                {
                    question: "업무 성취감에 대해 나는...",
                    A: "완성된 결과물에서 얻는다.",
                    B: "과정의 창의성에서 얻는다."
                },
                {
                    question: "어려운 업무를 마주쳤을 때, 나는...",
                    A: "보상을 생각하며 동기를 부여한다.",
                    B: "도전 자체에서 의미를 찾는다."
                },
                {
                    question: "팀에서의 역할에 대해 나는...",
                    A: "명확한 성과를 내는 것이 중요하다고 생각한다.",
                    B: "팀의 발전에 기여하는 것이 중요하다고 생각한다."
                },

                {
                    question: "나에게 일이란...",
                    A: "생계를 위한 수단이다.",
                    B: "자아 실현의 방법이다."
                },
                {
                    question: "일에서 나는...",
                    A: "일에서 나는...",
                    B: "변화와 다양성을 추구한다."
                },
                {
                    question: "직업 선택에 있어서 나는...",
                    A: "장기적인 경력 계획을 중요시한다.",
                    B: "개인적 취향과 흥미를 중요시한다."
                },
                {
                    question: "업무에 있어서 나는...",
                    A: "전문성과 능력을 중시한다.",
                    B: "개인의 가치와 일치를 중시한다."
                },
                {
                    question: "경력 목표에 대해 나는...",
                    A: "높은 지위와 명성을 목표로 삼는다.",
                    B: "내가 중요하게 생각하는 일을 하는 것을 목표로 삼는다."
                }
                
            ],
            questionnaire : '',
            ans1 : '',
            ans2 : '',
            result : [],
            currentStep: 1,
            totalSteps: 25, // 여기서는 총 5단계로 가정
            progressValue: 4,// 처음에는 20%로 시작 (100 / 5 단계)
        }
    },
    methods : {
        nextStep(type) {

            if(this.result.length >= 24) {
                var count = 0;
                for(var i = 0 ; i < 5 ; i++) {  //문제해결
                    if(this.result[i] === 'A') {
                        count++;
                    }
                }
                res = count >= 3? 'P' : 'C';
                count = 0;
                

                for( i = 5 ; i < 10 ; i++) {  //대인관계 
                    if(this.result[i] === 'A') {
                        count++;
                    }
                }
                res += count >= 3? 'S' : 'E';
                count = 0;


                for( i = 10 ; i < 15 ; i++) {  //업무스타일
                    if(this.result[i] === 'A') {
                        count++;
                    }
                }
                res += count >= 3? 'O' : 'A';
                count = 0;

                for( i = 15 ; i < 20 ; i++) {  //일의동기
                    if(this.result[i] === 'A') {
                        count++;
                    }
                }
                res += count >= 3? 'G' : 'P';
                count = 0;

                for( i = 20 ; i < 25 ; i++) {  //일의가치
                    if(this.result[i] === 'A') {
                        count++;
                    }
                }
                res += count >= 3? 'S' : 'V';
                count = 0;

                console.log('>>>>>>>>>>>>>>' + res);
                this.$emit('changePage',res);
            }else {
                this.currentStep += 1;
                this.progressValue = this.currentStep / this.totalSteps * 100;
                this.result.push(type);
                var res = '';
            }

        }
    }
}
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
  background-color:  rgb(150, 150, 255); 
  transition: width 0.5s ease; 
}

.parent-container { /* 부모 컨테이너 클래스를 추가합니다. */
  display: flex;
  justify-content: center; /* 수평 중앙 정렬 */
}
.questionx-container { /* 부모 컨테이너 클래스를 추가합니다. */
  
}
.buttonClass {
    background-color : rgb(150, 150, 255);
    width : 700px; 
    height : 80px; 
    color: white;
    font-weight: 900 ;
    border : 0px;
    margin-top: 10px;
}
</style>