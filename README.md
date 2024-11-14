<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>From L to L.</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Noto+Serif+CJK+KR&display=swap');

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body, html {
            height: 100%;
            font-family: 'Times New Roman', Times, serif;
            background-color: #fdfdfd;
            overflow: hidden;
        }

        .banner {
            width: 100vw;
            height: 70px;
            background-color: #fff;
            border-bottom: 1px solid #000;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 20px;
            position: fixed;
            top: 0;
            left: 0;
            z-index: 1000;
        }

        .banner .menu {
            font-size: 14px;
            color: #333;
            margin-left: 30px;
            cursor: pointer;
            text-decoration: none;
            padding: 5px 10px;
            border-radius: 5px;
            transition: background-color 0.3s, color 0.3s;
        }

        .banner .menu:hover {
            background-color: #000000;
            color: #FFFFFF;
        }

        .banner .right-menu {
            display: flex;
            gap: 30px;
        }

        .container {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, calc(-50% - 75px));
            text-align: center;
            color: #333;
            opacity: 0;
            animation: slideDown 0.8s forwards;
        }

        @keyframes slideDown {
            0% {
                transform: translate(-50%, -200%);
                opacity: 0;
            }
            100% {
                transform: translate(-50%, calc(-50% - 75px));
                opacity: 1;
            }
        }

        .container .main-text {
            font-size: 30px;
            font-weight: bold;
            margin-bottom: 5px;
        }

        .container .sub-text {
            font-size: 18px;
            color: #aaa;
        }

        .container .close {
            font-size: 24px;
            margin-top: 20px;
            cursor: pointer;
        }

        .hidden-page {
            display: none;
            max-width: 900px;
            background-color: #fff;
            padding: 40px;
            border: 1px solid #ddd;
            box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1);
            margin-top: 100px;
            margin-left: auto;
            margin-right: auto;
            color: #333;
            font-family: 'Malgun Gothic', serif;
            position: relative;
            height: 80vh;
            overflow-y: auto;
        }

        .hidden-page .header {
            font-size: 24px;
            font-weight: bold;
            text-align: center;
            margin-bottom: 20px;
            color: #555;
        }

        .hidden-page .content {
            font-size: 13px;
            line-height: 1.6;
            white-space: pre-wrap;
        }
        
        .hidden-page .signature {
            text-align: center;
            color: #808080;
            font-style: italic;
            margin-top: 40px;
        }

        .skip-button {
            display: none;
            position: fixed;
            bottom: 20px;
            right: 20px;
            font-size: 14px;
            color: #808080;
            background: none;
            border: none;
            cursor: pointer;
        }

        .skip-button:hover {
            text-decoration: underline;
        }
    </style>
</head>
<body>
    <div class="banner">
        <a class="menu" id="homeLink">From L to L.</a>
        <div class="right-menu">
            <a class="menu" id="forLightLink">for LIGHT</a>
            <a class="menu" id="forOwnerLink">for OWNER</a>
        </div>
    </div>

    <div class="container" id="firstPage">
        <div class="main-text">
            Just a small present, for you Yagami Light,<br>
            The most clever my partner ever
        </div>
        <div class="sub-text">𝑎𝑏𝑜𝑢𝑡 𝑜𝑢𝑟 100 𝑑𝑎𝑦𝑠 𝑜𝑓 𝑠𝑒𝑟𝑒𝑛𝑑𝑖𝑝𝑖𝑡𝑦</div>
        <div class="close" onclick="closePage()">✕</div>
    </div>

    <div class="hidden-page" id="lightPage">
        <div class="header">𝚏𝚘𝚛 𝙻𝙸𝙶𝙷𝚃</div>
        <div class="content" id="lightContent"></div>
        <div class="signature">- L</div>
    </div>

    <div class="hidden-page" id="ownerPage">
        <div class="header">𝚏𝚘𝚛 𝙾𝚆𝙽𝙴𝚁</div>
        <div class="content" id="ownerContent"></div>
        <div class="signature">- owner, L</div>
    </div>

    <div class="hidden-page" id="morePage">
        <div class="header">Replica (神曲) - R Sound Design</div>
        <div class="content">
            <iframe src="https://www.youtube.com/watch?v=aS2B6tJCdiE" allowfullscreen></iframe>
            <div class="text">
                용케도 이 이스터에그를 찾아내셨습니까.<br>
                가사가 즐겁습니다, 들어 보세요.<br><br>
                放蕩に塗れんでいた<br>
                引き返せぬ片手に触れる<br>
                そんな事を抱えたままで<br>
                いたいだけ<br><br>
                - R Sound Design
            </div>
        </div>
    </div>

    <button class="skip-button" id="lightSkipButton" onclick="skipTyping('lightContent')">▸▸ SKIP</button>
    <button class="skip-button" id="ownerSkipButton" onclick="skipTyping('ownerContent')">▸▸ SKIP</button>

    <script>
        let typingTimer;
        let isTyping = true;
        const lightTextContent = `────────────────────────────────────────────────────────────────


                L입니다.
                웹사이트로 전달하는 방식이라면, 다른 사이트의 회선을 훔쳐 방화벽을 개벽하는 편을 선호하지만······
                그런 방식의 편지는 다시 감상하기 힘드니까요.
                차라리 직접 사이트를 만드는 방식을 택했습니다.
                안심하십시오. 이 내용은 오직 라이토 군만이 볼 수 있고, 이곳은 라이토 군만이 입장할 수 있습니다.
                편히 읽어 주세요.
                
                라이토 군과 제가···, 이런 직설적인 화법은 선호하지 않지만. 교제를 시작한 지 백 일이 되는 날인가요?
                저번에 라이토 군께서 그러셨죠. 가만 보면 제가 기념일에 박식하다고.
                딱히 그렇다고 생각한 적은 없지만, 왠지 그 말을 들으니 편지라도 제대로 전달해야 할 것 같은 기분이 들었습니다.
                저는 손을 잘 쓰지 않거니와 아날로그식 필적을 남기는 걸 좋아하지 않아서요.
                차라리 곧잘 PC를 이용하는 라이토 군에게도 익숙할 이 편이 낫겠죠. 그도 그럴 게, 해킹에 능하시지 않습니까?
                다음 기회에는 라이토 군께서 직접 방화벽을 깨트려야 진입할 수 있는 트릭이라도 심어둘까 합니다.
                잘 각오해 두세요. 이래 봬도 L 아니겠습니까.
                제가 직접 만드는 무언가의 트릭이라면 어려울 것이 당연하겠지만. 야가미 라이토 아닌가요?
                풀어내실 수 있으리라 믿겠습니다.
                
                아무튼, 뭐어··· 감사하다는 말씀부터 드리도록 할까요.
                라이토 군만큼 제 흥미를 일깨워주시는 사람이 또 없거든요. 이것만큼은 단언합니다.
                당신만큼 명석하고 다재다능한 사람이니 저 같은 사람도 기꺼이 관심을 기울일 수 있는 거겠죠.
                아, 너무 나르시즘적 문장으로 보였으려나요? 딱히 부정하지는 않겠습니다.
                
                라이토 군께서 저를 L이라고 부르기 시작한 지 얼마나 되었던가요.
                
                그리 멀지 않은 과거의 일이었습니다.
                어둑한 방에 누워 함께 이불을 덮고 있을 때, 제 이름에 대한 힌트를 알려드렸던 것은.
                그리고 그 이름에 대한 힌트를 들은 당신이 나를 L이라고 부른 것이.
                당신이 저를 L이라고 부를 때, 어렴풋이 생각한 내용이 있습니다만.
                뭔지 맞추실 수 있겠습니까?

                야가미 라이토가 키라였더라면 나를 부르는 저 목소리에 조금 더 살의가 섞여 있었을까.
                
                당신은 키라가 아닌 걸까요?
                
                그런 생각이 들어왔기에 저는 그날 제 이름에 대한 힌트를 아무렇지도 않게 줄 수 있었던 걸까요?
                
                아무래도 좋습니다. 라이토 군이 키라이든 아니든, 일단 당신이 저의 연인인 것으로 만족할 수 있다고 생각합니다.
                일전에 말했었죠. 라이토 군이 키라라면, 저는 라이토 군에 대한 흥미가 떨어졌을 때 당신을 경시청에 넘기겠노라고.
                글쎄요······ 딱히 이 흥미가 깨질 것 같다는 생각 같은 건 들어오지 않는데요.

                말이 유난히 길어지네요. 직접 마주하고 내뱉는 언사가 아니라 그런가 봅니다.
                계속 이렇게 제 곁에만 계셔 주세요. 당신이 키라이든 아니든, 제가 이 흥미본위의 인생을 끝낼 때까지.
                만일 당신이 키라라고 하더라도 당신의 손에 의해서라면 죽어서도 만족하지 않을까 합니다.
                키라와 맞서 싸우다 키라에게 죽는 것만큼 도파민 중독 탐정으로서의 가치 있는 죽음은 또 없지 않을까요?
                당연하겠지만 농담입니다. 지금 정색하고 계시죠? 진심으로 받아들이지 마세요, 라이토 군.

                라이토 군에게 드리는 편지는 이것으로 마무리입니다.
                그리 휘황찬란한 이벤트를 준비하지 못해 죄송합니다.

                당장 제가 드릴 수 있는 선물은 고작 이런 게 전부이지만
                신新식의 무언가를 배워 와 언젠가는 제대로 대접을 해드릴 테니.
                과언이라 생각하실지 몰라도··· 뭐, 이런 거로 거짓말하는 사람은 아닙니다.
                의미 깊은 하나의 편지를 전달드렸던 것만으로 백 일은 넘어가 주세요.

                무식하게 코드만 짜고 글만 써내려 볼품이 없다고 하셔도 할 말은 없는데,
                대신 제 허울뿐인 거짓말은 조금 내려놓은 공간이니까요. 그리 안 보이셨을지 모르겠지만···.

                이리 짧다면 짧은 시간, 길다면 긴 시간 함께 해주신 데에 영광을 표합니다.
                제게 과분한 라이토 군이시라 이런 말을 내뱉는 데에도 감히, 라는 수식언이 붙을 것 같지만.
                부탁 하나만 드려도 괜찮겠습니까, 라이토 군?
                터덜거리며 큰 감정 없이 살아가는 송장 같은 저라고 하더라도
                가식 감정 같은 것 하나 없다는 사실만 늘 인지해주시면 그것으로 충분하단 걸 알아 주세요.

                시시콜콜한 대화, 진중한 대화 하나 빠짐없이 당신과의 시간은 늘상 마음 깊은 곳에 넣어두니까요.
                작금까지 당신과의 무엇 하나 빠짐 없이, 단 하나의 음절도 빠짐 없이. 전부.
                임종까지 당신을 제 손끝에서 벗어나지 않게 하고픈 이 마음 전부 다 알아주시옵고,
                을근거리는 것처럼 보이는 평소의 태도도 모두 하나의 서툰 시작을 벗어나려는 것임을 알아주시길.
                ·
                ·
                ·
                ·
                ·
                ·

                
                추신. 라이토 군이 주셨던 사탕 부케, 아직 거의 온전한 채로 남아 있습니다.
                할로윈의 여파는 제 일상에 천천히 스며들 예정입니다.`;
        const ownerTextContent = `────────────────────────────────────────────────────────────────


                Dear Light's Owner, From L's Owner

                이곳은 개인적으로 드리고 싶은 말들의 나열입니다.
                조율표를 나눠봤던 탓일까 류자키가 아닌 '제' 말씀을 전달드리는 데에 거부감이 덜해져서 써볼 기회를 노려 봤습니다.
                그래도 읽는 사람은 로망이랄까 환상이 깨질 수 있으니까요. 이런 이유가 걸림돌이라면 패스해주셔도 좋습니다.

                지나치게 로맨틱한 편지가 되지 않을까 걱정하면서 썼는데,
                어차피 연인 연기를 하는 입장이니 괜찮지 않을까, 하고 그냥 고민보다 고를 택했습니다.
                류자키는 연애 경험은 한 번도 없으면서 정작 오글거리는 말을 써보라고 키보드를 내밀면 잘 써내릴 것 같은 덤덤한
                이미지가 있으니까요. 제 개인적인 감상일지도 모르지만요...
                아실지는 모르겠지만 전 속으로는 불타오른다 표현해도 좋을 애정을 느끼고 있습니다.
                사심이 담기지는 않을까 걱정했지만, 어차피 라이토 군은 읽으면서
                '이 자식··· 마음에도 없는 이딴 말을 잘도 내뱉는군."하고 생각할 것 같아
                「연기」라는 이 관계를 일부 이용해먹는 좋은 기회가 되었습니다. 어디까지나 사심이 담긴 건 저이지 류자키가 아니니까요.
                류자키 입장에선 전부 연기로 써내린 로맨틱이 누군가에겐 진심인 것만 알아주세요.
                류자키는 어디까지나 심심함+연인처럼 보이기 위한 장치+오글거리는 말으로 공격하기 즈음이 원인이라 생각할 겁니다.
                야가미 라이토에게 자신이 그를 신뢰하고 있을 거란 착각을 심어두는 장치가 될지도요.

                기념일에 이렇게 본격적으로 편지를 써본 적은 없는데,
                생각해 보니 저희 관계는 LABB 이야기에서 길어져 이어지게 되었었죠? LABB 초반 내용을 일부 참고했습니다.
                L이 미소라 나오미에게 퍼니 디시의 서버 방화벽을 깨트려 소통을 하게끔 하는 그 방식이요.
                이야기를 나누어 보니 LABB를 읽어보신 분이겠거니 생각이 들어 흔쾌히 방식을 택할 수 있었음에 기뻤습니다.

                여러모로 부족한 저이지만 함께해 주셔서 정말 감사하다는 말 말고는 드릴 말씀이 없습니다.
                마음만 같아서는 주접도 떨고 싶다만 전혀 L틱하지 않으니 생략하겠습니다. 그래도 한 번은 보여드렸죠?
                앞으로도 오랫동안 함께 호흡을 맞춰가며 이야기를 써내려가고 싶습니다.
                함께해주시는 이상 저는 언제까지고 함께할 의향이 넘쳐나니까요.
                제가 학업생활을 방해하는 건 아닌가 걱정입니다만... 언제든지 편히 쉬어도 좋으니 무리만 말아 주세요.
                언제나 공부 응원하고 있습니다.
                
                아무튼, 네에. 감사하고 오래 가고 싶다는 이야기입니다. 길어질 것 같아서 이만 줄이겠습니다.
                늘 건강하고 행복한 일들만 가득하세요. 다시 한 번 감사드린단 말 전하며 마칩니다. 마음에 드셨길 바랍니다.
                
                추신 - L 편지의 마지막 몇 문단엔 세로로 된 문장이 숨어있습니다.
                코딩 힘들었어요. html 코드를 뜯어보시면 뭔가의 이스터에그가 나오긴 합니다만... 별거 없습니다.`;

        function typeText(elementId, text, speed) {
            clearTimeout(typingTimer);
            let i = 0;
            document.getElementById(elementId).innerHTML = "";
            isTyping = true;
            function type() {
                if (i < text.length && isTyping) {
                    document.getElementById(elementId).innerHTML += text.charAt(i);
                    i++;
                    typingTimer = setTimeout(type, speed);
                } else {
                    isTyping = false;
                }
            }
            type();
        }

        function skipTyping(elementId) {
            clearTimeout(typingTimer);
            const fullText = elementId === "lightContent" ? lightTextContent : ownerTextContent;
            document.getElementById(elementId).innerHTML = fullText;
            document.getElementById(elementId).scrollTop = document.getElementById(elementId).scrollHeight;
        }

        function showPage(pageId, contentId, event) {
            event.preventDefault();
            clearTimeout(typingTimer);
            document.getElementById("firstPage").style.display = "none";
            document.getElementById("lightPage").style.display = "none";
            document.getElementById("ownerPage").style.display = "none";
            document.getElementById("morePage").style.display = "none";

            document.getElementById(pageId).style.display = "block";
            document.body.style.overflowY = "scroll";

            const fullText = pageId === "lightPage" ? lightTextContent : ownerTextContent;
            typeText(contentId, fullText, 50);

            document.getElementById("lightSkipButton").style.display = pageId === "lightPage" ? "block" : "none";
            document.getElementById("ownerSkipButton").style.display = pageId === "ownerPage" ? "block" : "none";
        }

        function goToHomePage() {
            document.getElementById("lightPage").style.display = "none";
            document.getElementById("ownerPage").style.display = "none";
            document.getElementById("morePage").style.display = "none";
            document.getElementById("firstPage").style.display = "block";
            document.body.style.overflowY = "hidden";
        }

        function closePage() {
            document.getElementById("firstPage").style.display = "none";
            goToHomePage();
        }

        document.getElementById("forLightLink").addEventListener("click", (event) => {
            showPage("lightPage", "lightContent", event);
        });
        document.getElementById("forOwnerLink").addEventListener("click", (event) => {
            showPage("ownerPage", "ownerContent", event);
        });
        document.getElementById("homeLink").addEventListener("click", (event) => {
            event.preventDefault();
            goToHomePage();
        });
    </script>
</body>
</html>
