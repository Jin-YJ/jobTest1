<template>
    <div>
        <div class="parent-container">
            <h2><p>당신과 어울리는 직업 유형은?</p> </h2>

        </div>
        <div class="parent-container">
            <h2 class="fontStyle"><p>{{jobType}}</p></h2>
        </div>
        <div class="info-box">
            <h3><p style="text-align : left;">{{ jobType }} 유형 결과 해석</p></h3><br><br>
            <p class="content-header"> {{type1.headper}} </p> <p class="content-substance"> {{type1.content}} </p>
            
            <p class="content-header"> {{type2.headper}} </p> <p class="content-substance"> {{type2.content}} </p>
            
            <p class="content-header"> {{type3.headper}} </p> <p class="content-substance"> {{type3.content}} </p>
            
            <p class="content-header"> {{type4.headper}} </p> <p class="content-substance"> {{type4.content}} </p>
            
            <p class="content-header"> {{type5.headper}} </p> <p class="content-substance"> {{type5.content}} </p>
            
            <p class="content-header"> 추천직업 : </p>
            <ul>
                <li v-for ="(item,index) in content" :key="index" class="content-header"> {{item}} </li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            type1 : {
                headper : '',
                content: ''
            },
            type2 : {
                headper : '',
                content: ''
            },
            type3 : {
                headper : '',
                content: ''
            },
            type4 : {
                headper : '',
                content: ''
            },
            type5 : {
                headper : '',
                content: ''
            },
            content : [],
            finalContent : '',
        }
    },
    props: {
        jobType : {
            type : String,
            default : ''
        }
    },
    mounted() {
        this.resultMethods();
    },
    methods : {
        resultMethods() {
            const types = this.jobType.split('');
            if(types[0] === 'P') {
                this.type1.headper = '실용적 (Practical) : ';
                this.type1.content = '당신은 문제를 해결하는 데 있어 구체적이고 실제적인 접근 방식을 선호합니다. 당신은 이론보다는 실질적인 경험을 통해 배운 것들을 적용하는 것을 좋아합니다.';
            }else {
                this.type1.header = '창의적 (Creative): ';
                this.type1.content = ' 당신은 전통적인 방식을 넘어서 새롭고 혁신적인 해결책을 찾는 데 뛰어납니다. 문제에 직면했을 때, 당신은 기존의 틀을 벗어나 독창적인 아이디어를 제안하는 것을 선호합니다.';
            }

            if(types[1] === 'S') {
                this.type2.headper = '체계적 (Structured) : ';
                this.type2.content = '대인 관계에서 당신은 질서 정연하고 계획적입니다. 또한 타인과의 관계에서 예측 가능하고 신뢰할 수 있는 패턴을 선호합니다.';
            }else {
                this.type2.header = '공감적 (Empathetic) : ';
                this.type2.content = '대인 관계에서 당신은 다른 사람의 감정에 귀 기울이고 그들의 입장을 이해하려는 깊은 능력을 보유하고 있습니다. 이는 팀원들이나 고객들과의 관계에서 긍정적인 영향을 미칩니다.';
            }

            if(types[2] === 'O') {
                this.type3.headper = '조직적 (Organized) : ';
                this.type3.content = '당신의 업무 스타일은 매우 조직적이며 일에 대한 체계적인 접근을 중시합니다. 당신은 일의 순서와 정돈된 방식을 중요하게 생각합니다.';
            }else {
                this.type3.header = '적응력 있는 (Adaptable) :';
                this.type3.content = '업무 스타일에서 당신은 유연하고 변화에 빠르게 적응하는 특성을 가지고 있습니다. 계획의 변경이나 뜻밖의 상황에 당황하기보다는 쉽게 적응하고 그에 맞게 대응합니다.';
            }

            if(types[3] === 'G') {
                this.type4.headper = '목표 지향적 (Goal-Oriented) :';
                this.type4.content = '업무를 수행할 때 당신은 명확한 목표를 세우고, 이를 향해 집중적으로 나아갑니다. 당신은 달성해야 할 구체적인 결과에 초점을 맞추며 업무를 진행합니다.';
            }else {
                this.type4.header = '과정 지향적 (Process-Oriented) : ';
                this.type4.content = '일의 동기에 있어서 당신은 최종 결과물이 나오기까지의 과정을 중시합니다. 당신에게 중요한 것은 목표 달성을 위한 단계적인 접근과 그 과정에서의 배움과 성장입니다.';
            }

            if(types[4] === 'S') {
                this.type5.headper = '안정 추구형 (Stability-Seeking) : ';
                this.type5.content = '일에서 당신은 안정성을 중요시하며 장기적인 관점에서 경력을 계획합니다. 불확실성보다는 예측 가능한 환경에서 일하는 것을 선호합니다.';
            }else {
                this.type5.header = '다양성 추구형 (Variety-Seeking) : ';
                this.type5.content = '일의 가치에서 당신은 반복되는 루틴보다는 다양한 경험을 추구합니다. 새로운 프로젝트나 활동에 참여하는 것에서 큰 만족을 느끼며, 다양한 업무에 도전하는 것을 좋아합니다.';
            }

            switch(this.jobType) {
                case 'PSOGS' :      //1
                    this.content.push('프로젝트 매니저');
                    this.content.push('회계사');
                    this.content.push('시스템 분석가');
                    this.content.push('품질 관리 전문가');
                    this.content.push('로지스틱스 코디네이터');
                    this.finalContent = 'PSOGS 유형의 사람들은 자신의 업무를 체계적으로 관리하고, 안정적인 경력을 구축하며, 구체적인 결과를 창출하는 데 강점을 가지고 있습니다. 그들은 팀에서 신뢰성 높은 구성원으로 평가받으며, 계획에 따라 일을 진행하는 것을 선호합니다. 이러한 특성은 복잡한 프로젝트를 관리하거나 꼼꼼한 주의를 요하는 직업에서 특히 중요합니다.';
                    break
                case 'PSOGV' :  //2
                    this.content.push('창업가');
                    this.content.push('이벤트 플래너');
                    this.content.push('마케팅 전략가');
                    this.content.push('광고 크리에이티브 디렉터');
                    this.content.push('컨설턴트');
                    this.finalContent = 'PSOGV 유형의 사람들은 조직적이고 체계적인 방식으로 업무를 수행하면서도 새로운 아이디어와 변화를 즐기는 경향이 있습니다. 그들은 목표를 향해 일하는 동안에도 다양한 경험을 추구하며, 일상적인 루틴을 벗어나 새로운 방식으로 문제를 해결하고자 합니다. 이러한 특성은 창의력을 필요로 하고 일상적인 변화가 많은 환경에서 특히 중요합니다.';
                    break
                case 'PSOPS' :          //3
                    this.content.push('회계사');
                    this.content.push('프로젝트 관리자');
                    this.content.push('데이터 분석가');
                    this.content.push('시스템 관리자');
                    this.content.push('품질 관리 전문가');
                    this.content.push('운영 관리자');
                    this.finalContent = 'PSOPS 유형의 사람들은 체계적이고 조직적인 접근을 통해 일을 진행하며, 안정적인 환경에서의 작업을 선호합니다. 그들은 업무 과정의 각 단계를 중시하고, 일상의 안정성과 예측 가능한 결과를 추구하는 경향이 있습니다. 이러한 특성은 복잡한 데이터를 다루고, 엄격한 규정과 절차를 따라야 하는 직업군에서 특히 유용합니다.';
                    break
                case 'PSOPV' :      //4
                    this.content.push('프로젝트 매니저');
                    this.content.push('이벤트 기획자');
                    this.content.push('IT 컨설턴트');
                    this.content.push('마케팅 전략가');
                    this.content.push('기업가');
                    this.content.push('제품 개발자');
                    this.finalContent = 'PSOPV 유형의 사람들은 변화에 유연하게 대응하며 다양한 상황에서도 자신의 실용적인 지식을 활용하여 문제를 해결할 수 있습니다. 안정된 환경을 중시하는 구조화된 대인 관계와 다양성을 추구하는 업무 가치가 결합하여, 창의적이고 적응력 있는 업무 환경을 선호하는 경향이 있습니다.';
                    break
                case 'PSAGS' :      //5
                    this.content.push('회계사');
                    this.content.push('품질 관리 전문가');
                    this.content.push('운영 관리자');
                    this.content.push('시스템 분석가');
                    this.content.push('프로세스 엔지니어');
                    this.finalContent = 'PSAGS 유형의 사람들은 신뢰성이 높고, 자신의 직업에서 안정성을 중요하게 여깁니다. 그들은 잘 정립된 환경에서 목표를 달성하는 데 탁월하며, 업무에 있어서 신중하고 계획적인 접근을 선호합니다. 이러한 특성은 규칙과 절차를 따르는 것이 중요한 역할에서 그들을 이상적인 후보로 만듭니다.';
                    break
                case 'PSAGV' :      //6
                    this.content.push('프로젝트 매니저 : 다양한 프로젝트를 관리하면서 새로운 도전을 경험하고 실용적인 결정을 내릴 수 있습니다.');
                    this.content.push('제품 개발자 : 새로운 제품을 개발하는 과정에서 실용적인 아이디어를 실현하고, 변화하는 시장 요구에 빠르게 대응할 수 있습니다.');
                    this.content.push('경영 컨설턴트 : 다양한 산업과 기업에 대한 컨설팅을 제공하며, 목표를 달성하기 위한 전략을 개발합니다.');
                    this.content.push('이벤트 기획자 : 다양한 이벤트를 기획하고 실행하면서 창의적이고 유연한 해결책을 모색합니다.');
                    this.content.push('여행 기획자 : 매번 새로운 여행 상품을 기획하면서 다양성을 추구하고, 고객의 목표를 실현하는 데 도움을 줍니다.');
                    this.finalContent = 'PSAGV 유형의 사람들은 새롭고 다양한 프로젝트에 참여하는 것을 즐기며, 목표를 설정하고 이를 달성하기 위해 노력합니다. 변화를 두려워하지 않고 새로운 상황에 쉽게 적응할 수 있는 능력은 다양한 직업 분야에서 강점이 될 수 있습니다. 이 유형의 사람들은 빠르게 변하는 환경에서도 효과적으로 목표를 달성할 수 있으며, 다양한 사람들과의 협력에서도 능력을 발휘할 수 있습니다. 그들의 실용적인 접근 방식과 다양한 경험을 추구하는 경향은 지속적인 개인적 및 전문적 성장에 기여할 수 있습니다.';
                    break
                case 'PSAPS' :      //7
                    this.content.push('회계사 : 정확성과 체계성이 요구되며, 안정적인 업무 환경을 제공합니다.');
                    this.content.push('프로젝트 매니저: 조직적인 계획을 통해 복잡한 프로젝트를 성공적으로 이끌 수 있습니다.');
                    this.content.push('행정 관리자: 일상적인 운영을 체계적으로 관리하며, 기관이나 기업의 효율성을 증진시킵니다.');
                    this.content.push('시스템 분석가: 정보 시스템의 구조화와 개선에 중점을 두며 안정적인 IT 환경을 유지합니다.');
                    this.content.push('품질 관리 전문가: 제품이나 서비스의 일관된 품질을 유지하면서 기업의 명성을 지킵니다.');
                    this.finalContent = 'PSAPS 유형의 사람들은 일에 있어서 안정성과 예측 가능성을 중요시합니다. 그들은 자신의 업무를 철저하게 계획하고 조직화하여 목표를 달성하는 데 중점을 둡니다. 변동성이 적고 일정한 흐름을 유지하는 환경에서 잘 작동할 수 있습니다. PSAPS 유형의 사람들은 신중하고 체계적인 접근 방식으로 일을 처리하며, 그들의 일은 안정적이고 예측 가능해야 합니다. 그들은 불확실성과 자주 변하는 상황보다는 일정한 흐름에서 더 효과적으로 작동합니다.';
                    break
                case 'PSAPV' :      //8
                    this.content.push('프로젝트 매니저: 다양한 프로젝트를 관리하며 목표를 향해 나아가는 역할을 합니다.');
                    this.content.push('경영 컨설턴트: 다양한 산업과 기업을 대상으로 전략적인 조언을 제공하고 새로운 솔루션을 구현합니다.');
                    this.content.push('마케팅 전략가: 창의적인 마케팅 전략을 개발하고 실행하여 브랜드의 다양성을 홍보합니다.');
                    this.content.push('이벤트 플래너: 다양한 이벤트를 기획하고 조직하여 효과적으로 실행합니다.');
                    this.content.push('제품 개발자: 시장의 요구에 부응하여 새로운 제품을 기획하고 개발합니다.');
                    this.finalContent = 'PSAPV 유형의 개인들은 안정적이고 체계적인 방식으로 일을 진행하는 동시에 새로운 도전과 다양한 활동에 대한 갈망을 가지고 있습니다. 이들은 목표 달성을 위해 노력하지만, 그 과정에서 새로운 아이디어와 다양한 접근 방식을 채택하는 것을 두려워하지 않습니다. PSAPV 유형의 사람들은 변화와 새로움에 대한 열린 마음을 가지고 있으며, 이는 목표 지향적이고 조직적인 접근 방식과 결합될 때 강력한 시너지를 낼 수 있습니다. 그들은 안정된 환경에서 일하는 것과 더불어 새로운 아이디어와 방법을 탐색하는 것에서 만족을 느낍니다.';
                    break
                case 'PEOGS' :
                    this.content.push('제품 디자이너: 기능적이면서도 혁신적인 디자인을 통해 제품을 개발하고 개선합니다.');
                    this.content.push('시스템 분석가: 기업의 시스템을 분석하고 체계적으로 개선 방안을 제시합니다.');
                    this.content.push('인적 자원 관리자: 조직 내 인력 관리와 개발을 통해 안정적인 직장 환경을 조성합니다.');
                    this.content.push('건축가: 창의적인 설계로 기능적이고 안정적인 건축물을 창조합니다.');
                    this.content.push('프로젝트 매니저: 다양한 프로젝트를 체계적으로 관리하면서 창의적인 해결책을 도입합니다.');
                    this.finalContent = 'PEOGS 유형은 안정적인 환경에서 창의력을 발휘하길 원하는 사람들을 의미합니다. 이들은 관계에서 체계를 중요시하면서도 일에 있어서는 새롭고 창의적인 접근을 추구합니다. 목표를 설정하고 이를 달성하기 위한 명확한 계획을 세우면서도, 일상적인 안정을 중요하게 여깁니다. PEOGS 유형은 혁신과 안정 사이에서 균형을 이루며, 자신의 창의성을 안정적이고 조직적인 방법으로 표현할 수 있는 직업을 선호합니다.';
                    break
                case 'PEOGV' :
                    this.content.push('광고 크리에이티브 디렉터: 창의적인 광고 캠페인을 기획하고 실행합니다.');
                    this.content.push('마케팅 전략가: 다양한 마케팅 전략을 개발하여 조직의 목표를 달성합니다.');
                    this.content.push('UI/UX 디자이너: 사용자 경험을 최적화하는 창의적이고 혁신적인 디자인을 창조합니다.');
                    this.content.push('이벤트 플래너: 다양한 행사와 이벤트를 기획하고 조직하여 고객의 요구를 충족시킵니다.');
                    this.content.push('스타트업 창업자: 새로운 비즈니스 기회를 창출하고 다양한 도전을 즐깁니다.');
                    this.finalContent = 'PEOGV 유형의 사람들은 안정적이고 체계적인 방법으로 목표를 달성하면서도 일상에 변화와 다양성을 추구합니다. 이들은 새로운 아이디어를 실험하는 것을 즐기며, 변화에 유연하게 적응할 수 있는 환경에서 일하는 것을 선호합니다. PEOGV 유형은 일의 결과와 성취를 중시하지만, 그 과정에서의 다양한 경험과 변화를 두려워하지 않으며, 이를 환영하는 경향이 있습니다.';
                    break
                case 'PEOPS' :
                    this.content.push('프로젝트 매니저: 다양한 프로젝트를 관리하고 팀을 이끌어 목표를 달성합니다.');
                    this.content.push('프로덕트 매니저: 제품의 전 생애주기를 계획하고 관리하며 혁신을 주도합니다.');
                    this.content.push('데이터 분석가: 체계적인 데이터 분석을 통해 비즈니스 인사이트를 도출합니다.');
                    this.content.push('시스템 엔지니어: 복잡한 시스템의 설계와 통합에 대한 문제를 해결합니다.');
                    this.content.push('품질 보증 관리자: 제품이나 서비스의 일관된 품질을 유지하고 개선합니다.');
                    this.finalContent = 'PEOPS 유형의 사람들은 혁신적인 아이디어와 목표 달성을 중시하면서도 안정적인 환경에서 일하기를 원합니다. 변화를 추구하되, 변화가 있을 때 그 안에서 질서와 일관성을 찾아 효과적으로 대응합니다. 이들은 자신의 역할에서 안정성을 찾으며, 자신이 설정한 목표에 도달하기 위한 명확한 경로를 선호합니다. PEOPS 유형은 일에서의 성취뿐 아니라 일의 안정성과 예측 가능성을 중요시하는 경향이 있으며, 이를 통해 직업적 성장과 개인적 만족을 도모합니다.';
                    break
                case 'PEOPV' :
                    this.content.push('마케팅 전략가: 다양한 캠페인과 전략을 개발하고 실행하여 브랜드 성장을 이끕니다.');
                    this.content.push('비즈니스 개발 매니저: 새로운 시장 기회를 탐색하고 전략적 파트너십을 구축합니다.');
                    this.content.push('UI/UX 디자이너: 사용자 경험을 혁신하고 새로운 디자인 솔루션을 제공합니다.');
                    this.content.push('이벤트 플래너: 다양한 이벤트를 기획하고 실행하여 독특한 경험을 창출합니다.');
                    this.content.push('창업가: 새로운 비즈니스 아이디어를 개발하고 시장에 출시합니다.');
                    this.finalContent = 'PEOPV 유형의 사람들은 탁월한 목표 설정과 달성 능력을 가지고 있으며, 변화와 다양성을 환영하는 경향이 있습니다. 이들은 신뢰할 수 있는 대인 관계와 조직적인 업무 환경 내에서도 새로운 도전을 찾으며, 기존의 방식에 얽매이지 않고 유연하게 사고하는 것을 즐깁니다. PEOPV 유형은 다양한 환경에서 창의력을 발휘하고, 새롭고 독특한 경험을 추구하는 데 큰 가치를 두면서, 그들의 목표를 달성하기 위해 체계적인 방식으로 일합니다.';
                    break
                case 'PEAGS' :
                    this.content.push('프로젝트 매니저');
                    this.content.push('회계사');
                    this.content.push('시스템 분석가');
                    this.content.push('품질 관리 전문가');
                    this.content.push('로지스틱스 코디네이터');
                    this.finalContent = '';
                    break
                case 'PEAGV' :
                    this.content.push('프로젝트 매니저');
                    this.content.push('회계사');
                    this.content.push('시스템 분석가');
                    this.content.push('품질 관리 전문가');
                    this.content.push('로지스틱스 코디네이터');
                    this.finalContent = '';
                    break
                case 'PEAPS' :
                    this.content.push('프로젝트 매니저');
                    this.content.push('회계사');
                    this.content.push('시스템 분석가');
                    this.content.push('품질 관리 전문가');
                    this.content.push('로지스틱스 코디네이터');
                    this.finalContent = '';
                    break
                case 'PEAPV' :
                    this.content.push('프로젝트 매니저');
                    this.content.push('회계사');
                    this.content.push('시스템 분석가');
                    this.content.push('품질 관리 전문가');
                    this.content.push('로지스틱스 코디네이터');
                    this.finalContent = '';
                    break
                case 'CSOGS' :
                    this.content.push('프로젝트 매니저');
                    this.content.push('회계사');
                    this.content.push('시스템 분석가');
                    this.content.push('품질 관리 전문가');
                    this.content.push('로지스틱스 코디네이터');
                    this.finalContent = '';
                    break
                case 'CSOGV' :
                    this.content.push('프로젝트 매니저');
                    this.content.push('회계사');
                    this.content.push('시스템 분석가');
                    this.content.push('품질 관리 전문가');
                    this.content.push('로지스틱스 코디네이터');
                    this.finalContent = '';
                    break
                case 'CSOPS' :
                    this.content.push('프로젝트 매니저');
                    this.content.push('회계사');
                    this.content.push('시스템 분석가');
                    this.content.push('품질 관리 전문가');
                    this.content.push('로지스틱스 코디네이터');
                    this.finalContent = '';
                    break
                case 'CSOPV' :
                    this.content.push('프로젝트 매니저');
                    this.content.push('회계사');
                    this.content.push('시스템 분석가');
                    this.content.push('품질 관리 전문가');
                    this.content.push('로지스틱스 코디네이터');
                    this.finalContent = '';
                    break
                case 'CSAGS' :
                    this.content.push('프로젝트 매니저');
                    this.content.push('회계사');
                    this.content.push('시스템 분석가');
                    this.content.push('품질 관리 전문가');
                    this.content.push('로지스틱스 코디네이터');
                    this.finalContent = '';
                    break
                case 'CSAGV' :
                    this.content.push('프로젝트 매니저');
                    this.content.push('회계사');
                    this.content.push('시스템 분석가');
                    this.content.push('품질 관리 전문가');
                    this.content.push('로지스틱스 코디네이터');
                    this.finalContent = '';
                    break
                case 'CSAPS' :
                    this.content.push('프로젝트 매니저');
                    this.content.push('회계사');
                    this.content.push('시스템 분석가');
                    this.content.push('품질 관리 전문가');
                    this.content.push('로지스틱스 코디네이터');
                    this.finalContent = '';
                    break
                case 'CSAPV' :
                    this.content.push('프로젝트 매니저');
                    this.content.push('회계사');
                    this.content.push('시스템 분석가');
                    this.content.push('품질 관리 전문가');
                    this.content.push('로지스틱스 코디네이터');
                    this.finalContent = '';
                    break
                case 'CEOGS' :
                    this.content.push('프로젝트 매니저');
                    this.content.push('회계사');
                    this.content.push('시스템 분석가');
                    this.content.push('품질 관리 전문가');
                    this.content.push('로지스틱스 코디네이터');
                    this.finalContent = '';
                    break
                case 'CEOGV' :
                    this.content.push('프로젝트 매니저');
                    this.content.push('회계사');
                    this.content.push('시스템 분석가');
                    this.content.push('품질 관리 전문가');
                    this.content.push('로지스틱스 코디네이터');
                    this.finalContent = '';
                    break
                case 'CEOPS' :
                    this.content.push('프로젝트 매니저');
                    this.content.push('회계사');
                    this.content.push('시스템 분석가');
                    this.content.push('품질 관리 전문가');
                    this.content.push('로지스틱스 코디네이터');
                    this.finalContent = '';
                    break
                case 'CEOPV' :
                    this.content.push('프로젝트 매니저');
                    this.content.push('회계사');
                    this.content.push('시스템 분석가');
                    this.content.push('품질 관리 전문가');
                    this.content.push('로지스틱스 코디네이터');
                    this.finalContent = '';
                    break
                case 'CEAGS' :
                    this.content.push('프로젝트 매니저');
                    this.content.push('회계사');
                    this.content.push('시스템 분석가');
                    this.content.push('품질 관리 전문가');
                    this.content.push('로지스틱스 코디네이터');
                    this.finalContent = '';
                    break
                case 'CEAGV' :
                    this.content.push('프로젝트 매니저');
                    this.content.push('회계사');
                    this.content.push('시스템 분석가');
                    this.content.push('품질 관리 전문가');
                    this.content.push('로지스틱스 코디네이터');
                    this.finalContent = '';
                    break
                case 'CEAPS' :
                    this.content.push('프로젝트 매니저');
                    this.content.push('회계사');
                    this.content.push('시스템 분석가');
                    this.content.push('품질 관리 전문가');
                    this.content.push('로지스틱스 코디네이터');
                    this.finalContent = '';
                    break

                case 'CEAPV' :
                    this.content.push('디자이너');
                    this.content.push('인사 조직 전문가');
                    this.content.push('심리 상담사');
                    this.content.push('UX/UI 전문가');
                    this.content.push('프로젝트 매니저');
                    this.content.push('연구개발 전문가');
                    this.finalContent = 'CEAPV 유형의 사람들은 창의적이고 공감적인 태도로 일하면서, 업무를 수행함에 있어서 유연성을 발휘합니다. 그들은 과정 자체에서 의미와 성취를 찾으며, 일상에서 다양한 경험을 추구하고자 하는 특징을 가지고 있습니다. 이 유형은 특히 사용자 경험을 중시하고, 사람들과의 깊은 상호작용을 요구하는 직업군에서 강점을 발휘할 수 있습니다.';
                    this.finalContent = '';
                    break


                

            }

        }
    }
}
</script>
<style scoped>
.fontStyle {
    color : rgb(99, 138, 237)
}
.parent-container { /* 부모 컨테이너 클래스를 추가합니다. */
  display: flex;
  justify-content: center; /* 수평 중앙 정렬 */
}

.info-box {
  border: 1px solid #989dff; /* 테두리 */
  border-radius: 20px; /* 모서리 둥글게 */
  padding: 50px; /* 내부 여백 */
  margin: 100px 10%; /* 외부 여백 */
  background-color: #e0d9ff; /* 배경색 */
}
.content-header {
    text-align: left;
    font-weight: 900 ;
}
.content-substance {
    text-align: left;
}
</style>