[기능]
* 에디터에서 실행하면 ViewPort상의 커서 위치에 카드 위젯(CardImageWidget)이 붙어다님.
* 카드 안에 배치된 레이어(이미지)들은 커서 위치에 따라 카드와 완벽하게 동일하지 않음.
* 또한 커서 위치에 따라 카드 크기가 기울어진 것처럼 조금씩 좁혀짐.
* 카드 구성물이 카드 밖에 표시되지 않고, 카드가 화면 밖으로 탈출하지 않음.

[CardLayerData]
![image](https://github.com/RedChiken/UEHologramCardWidget_RnD/assets/7973257/c5061798-bacf-477a-bd7f-ffbd5796d452)
* PresentationWidget에서 CardLayerData를 Row로 갖는 DataTable을 입력해서 카드 이미지를 입력.

* WidgetName: 이미지를 적용 할 CardImageWidget에서의 Image Widget 이름
* ![image](https://github.com/RedChiken/UEHologramCardWidget_RnD/assets/7973257/7ed90527-dc02-48ce-9750-fa368f7b8b61)
* 표시한 영역의 이름과 동일해야 함.

* ZOrder: 해당 이미지의 ZOrder
* ImageSize: 해당 이미지 사이즈. PresentationWidget 안의 CardImageWidget 크기와 동일해야 함.
* Material: 대상 이미지가 머테리얼(ex. 배경)일 경우의 이미지 지정 변수
* Texture: 대상 이미지가 텍스쳐일 경우의 이미지 지정 변수(Texture2D)

[작업 장식]
1. CardImageWidget에 필요한 ImageWidget을 추가하고 변수로 지정합니다.
2. CardImageWidget에 추가한 ImageWidget들과 같은 이름을 모두 CardLayerWidgetName에 추가합니다.
3. CardLayerData를 Row로 갖는 DataTable을 만들고 값을 입력하여 테이블을 완성합니다.
4. 3에서 생성한 테이블을 PresentationWidget의 ImageLayerData 변수에 지정하고 에디터에서 게임을 실행합니다.

[주의사항]
* 에디터에서 실행 하고 ViewPort를 전체화면(F11) 할 시 전체화면 크기가 잘못 잡혀서 시각적으로 맞지 않게 나옵니다.
* 모바일 새로운 창 혹은 그냥 에디터 창으로 실행해야 그럴듯한 화면을 볼 수 있습니다.
