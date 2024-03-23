[기능]
* 에디터에서 실행하면 ViewPort상의 커서 위치에 카드 위젯(CardImageWidget)이 붙어다님.
* 카드 안에 배치된 레이어(이미지)들은 커서 위치에 따라 카드와 완벽하게 동일하지 않음.
* 또한 커서 위치에 따라 카드 크기가 기울어진 것처럼 조금씩 좁혀짐.
* 카드 구성물이 카드 밖에 표시되지 않고, 카드가 화면 밖으로 탈출하지 않음.

[CardLayerData]
* ![image](https://github.com/RedChiken/UEHologramCardWidget_RnD/assets/7973257/5a5ded97-10f1-4a9c-87e5-737007b1f807)
* PresentationWidget에서 CardLayerData를 Row로 갖는 DataTable을 입력해서 카드 이미지를 입력.

* WidgetName: 이미지를 적용 할 CardImageWidget에서의 Image Widget 이름
* ![image](https://github.com/RedChiken/UEHologramCardWidget_RnD/assets/7973257/7ed90527-dc02-48ce-9750-fa368f7b8b61)
* 표시한 영역의 이름과 동일해야 함.

* ZOrder: 해당 이미지의 ZOrder
* ImageSize: 해당 이미지 사이즈. PresentationWidget 안의 CardImageWidget 크기와 동일해야 함.
* Material: 대상 이미지가 머테리얼(ex. 배경)일 경우의 이미지 지정 변수
* Texture: 대상 이미지가 텍스쳐일 경우의 이미지 지정 변수(Texture2D)
* Depth: Widget으로부터 사진이 튀어나온 거리.

[파라미터]
* RotateRate
* ![image](https://github.com/RedChiken/UEHologramCardWidget_RnD/assets/7973257/c41a1ffa-0496-4d22-bfe7-c262dfb4634c)
* ViewPort 중앙 지점을 원점으로 커서 위치에 따른 카드의 길이 변화에 대한 가중치
* 값이 클수록 커서 움직임에 대해 CardImage의 크기 변화가 커진다.(정확히는 cos 함수를 따라감)(cos(x_rate), cos(y_rate))

* DistanceWithScreen
* ![image](https://github.com/RedChiken/UEHologramCardWidget_RnD/assets/7973257/19070712-69a2-441e-bc05-61e9f13c49bb)
* CardImageWidget에서 지정
* CardImageWidget이 카메라로부터 출력되는 거리
* CardLayerData::Depth와 마찬가지로 절대 값(cm)이 아니라 대략적인 비례 값에 가까움
* CardImageWidget 안의 Image들의 위치가 보정(Adjust) 될 때 그 비례값을 해당 CardLayerData::Depth / DistanceWithScreen으로 결정된다.
* 즉, 해당 이미지가 좌표 변화에 대해 더 민감하게 반응하게 하려면 Depth를 키워줘야 한다.

[작업 qkd식]
1. CardImageWidget에 필요한 ImageWidget을 추가하고 변수로 지정합니다.
2. CardImageWidget에 추가한 ImageWidget들과 같은 이름을 모두 CardLayerWidgetName에 추가합니다.
3. CardLayerData를 Row로 갖는 DataTable을 만들고 값을 입력하여 테이블을 완성합니다.
4. 3에서 생성한 테이블을 PresentationWidget의 ImageLayerData 변수에 지정하고 에디터에서 게임을 실행합니다.

[주의사항]
* 에디터에서 실행 하고 ViewPort를 전체화면(F11) 할 시 전체화면 크기가 잘못 잡혀서 시각적으로 맞지 않게 나옵니다.
* 모바일 새로운 창 혹은 그냥 에디터 창으로 실행해야 그럴듯한 화면을 볼 수 있습니다.
