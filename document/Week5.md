 ### Week 5 - Project Feedback
 ### **내용** 
 계획했던 프로젝트 기간의 마지막주에 4주차에서 카메라에서 받아오는 이미지 Frame에서 라즈베리파이가 처리할 양을 
 줄여 Wifi로 이미지를 전달하는 Delay 줄인 후 최종적으로 자율주행테스트를 거쳤다. 결과는 완벽하지는 않았지만 
 그래도 과연 성공할수 있을까 싶었던 자율주행을 흉내내는 정도로는 성공이었던것 같다.   
 프로젝트의 마무리로 교수님께 프로젝트를 보여주며 문제점 Feedback 받았고 이후 한달동안의 프로젝트를 정리하는 시간을 
 가지며 이번 RC카를 이용한 자율주행 프로젝트를 끝마쳤다.   
 
 **교수님 피드백**   
 햐
와이파이를 통하여 통신하기 때문에 많은 delay가 생길수 밖에 없다. 
사소한 delay들이 쌓이면서 자율주행 자동차가 차선을 인식하고 동작하는데 문제를 발생시킨다. 
이 delay를 최소화하기 위해 
1. 카메라 line 감지하고 알고리즘을 수행하는데 걸리는 delay 측정 
2. 모터의 움직임 PWM을 활용하여 직진, 좌회전, 우회전테스트, 얼마나 가는지, 얼마나 꺽는지(곡률)
3. delay를 계산하여 알고리즘 만든다. 


빠르게 하는 방법으로는 조도센서를 활용할 수 있다.  검은색 테이프로 차선을 만들었기 때문에 조도센서가 검은색 테이프를 인식하였을 때 차를 움직이게 하면 된다. (우리의 목표와 맞지 않음)

라인 detecting할때 라인이 끊어지게 보이는데, erosion, dialation를 사용하여 라인을 연결해주면 된다. 
   
 ### **어려웠던점**
 4주차에서 학습한 모델의 정확도가 그리 높지 않았기 때문에 기존의 정주행으로 학습한 모델에다가 역주행으로
 운전하는 데이터셋을 넣어 추가로 학습하니 학습률이 어마무시하게 떨어지는 현상이 발생했다.
 
 ### **배운점**  
 교수님의 Feedback과 실제로 프로젝트를 진행하면서 아무래도 처음이라 전혀 고려하진 못한 
 점들(라즈베리파이의 연산속도를 고려하지 못한 코딩 + 물리적인 부품들 간 Response delay)에 대해 경험이 되었던것 같다.
 무엇보다 학교의 정규수업과정에서의 했던 팀프로젝트와는 달리 정말 밑바닥부터 한번 해보고싶은 아이디어를 부딫히면서 성공해냈다는
 경험이 무엇보다 가장 값졌던것 같다.
 
 
 **박재성**   
 우선적으로 처음 진행하는 프로젝트다 보니 여러가지로 부족한 부분이 많았고 특히 어떤 물리적인 Delay와 
 성능의 한계를 고려하여 SW를 설계하고 수정해나가야 한다는것을 배운것같다. 처음에는 실패하더라도 경험은 되겠지라는
  생각으로 되든안되는 한번 해보자라는 생각으로 시작했지만 정말 프로젝트를 하면서 함께 구글링을 통해 공부하고
  HW설계부터 모터 쉴드를 이용해 동작시키는것, 직접만든 데이터셋으로 인공지능 모델을 학습시켜 판단을 내리게 한것 등
  정말 밑바닥부터 시작한 만큼 많은것을 배우고 경험이 된 프로젝트였던것 같다.
 
 **양영우**   
 라즈베리파이가 연산을 하여 처리를 하는데 시간이 오래 걸려 line을 따라 주행을 하지 못하고 더 늦게 동작을 하였다.   
 이를 해결하기 위해서 받아서 처리하는 이미지 프레임 수를 줄여 연산을 처리하고 모터 드라이브에 명령을 전달하는데 어려움이 없도록 했다.   
 또한 속도를 줄이면서 RC카가 밀리는 현상을 제거하여 더 정확히 움직이도록 했다. delay를 고려하지 못한 상황에서 RC카가 동작하는 것을 보고
 delay를 해결하기 위해 연산 처리 속도를 생각하여 입력을 해줘야하는 것을 다시 한 번 생각할 수 있는 계기가 되었다.   
 또한 우회전 데이터가 부족하여 학습이 제대로 안 된 경우 경로를 이탈하였고 이를 해결하기 위해 추가 학습을 시켰는데 정확도가 현저히 낮아지는 상황이 발생을 했다.   
 이러한 문제점을 해결하기 위해 토론을 하며 더 나은 방식을 찾아 해결을 하며 이러한 상황이 발생하였을 때 해결하는 법을 알게 되었다.

 **권현수**  
 한찬호 교수님께서 자율주행 차를 구현하는데에 대한 전반적인 세미나를 열어주셨다. 우리에겐 보석같은 정보들이었고, 이것들을 처음부터 알았으면 어떨까 하는 마음이 들었다.  
 하지만 반대로, 우리가 이 정보들을 알고 프로젝트에 착수했다면 이 같은 깨달음은 없지 않았을까라는 생각도 들었다.  
 자율주행차에서 문제가 생긴것은 소프트웨어적으로의 delay였다. 카메라가 받아오는 만큼 컴퓨터에서 인식하는 시간이 따라가지 못했기 때문이다. 그래서 카메라가 받아오는 프레임 수를  
 줄여서 컴퓨터에서 연산하는 양을 줄여 이 두가지의 동기화를 시도했다.  어쩌면 쉽게 생각했을만도 하지만, 반대로 몰랐다면 끝까지 생각하지 못하고 포기했을만한 문제였던것 같다.  

 **윤동준**   
 학습한 내용을 바탕으로 RC카에 적용시켜 구동해봤다. 실시간으로 이미지를 받아들이는데 그것을 바로 계산하여 적용시킬려 하니 이미지를 받아오는 속도보다 RC카 움직이는
 속도가 더 빨라서 좌회전해야 하는 코스에서 직진을 하고 1~2초뒤에 좌회전을 하였다. 이 문제를 해결하기 위해 RC카의 속도를 줄이고, 1초당 12Frame을 받아와서 Frame 
 받아오는 수를 줄이니 그나마 우리가 원하는 대로 구동하였다. 
 <br/>어려웠던 점은 카메라 delay를 어떻게 줄여야 할지에 대해 해결책을 찾기 힘들었다. 
 아쉬운 점은 물리적인 delay도 고려하지 않았다는 것이 매우 아쉬웠다. 
 처음 학습을 시킬때 직진과 좌회전의 데이터 값이 많아서 우회전의 대한 학습이 너무 부족했다. 그래서 우회전 코스에서는 RC카가 정상적으로 작동하지 않았다.  
 원래 있던 학습된 데이터와 트랙을 거꾸로 구동시킨 RC카에서 얻은 데이터를 불러와서 학습시킨 결과 정확도가 9퍼센트가 나왔다. 다음에는 데이터를 합쳐서 학습시키면
 좀 더 높은 정확도가 나올거라 예상된다. 
 
 **이상목**   
 
 
 **이진우**   
 
 
