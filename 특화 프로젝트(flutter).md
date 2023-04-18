# 특화 프로젝트

- [데이터 참고 사이트](#데이터-참고-사이트)
- [공공데이터 포털의 OPEN API 사용방법](#공공데이터-포털의-open-api-사용방법)
- [flutter 기초정리](https://velog.io/@jaybon/flutter-%EA%B8%B0%EC%B4%88-%EC%A0%95%EB%A6%AC)
- [painter](#painter)
- [IconButton](#iconbutton)
- [http (axios)](#http-axios)
- [빌드 이후 한 번만 실행](#빌드-이후-한-번만-실행)
- **타입프린트: `print(변수명.runtimeType);`**
- [margin](#margin)
- [in, not in 리스트](#in-not-in-리스트)
- [Uint8List 이미지](#uint8list-이미지)
- [multipart request](#multipart-request)
- [전체 print](#전체-print)
- [base64Encode() → python에서 읽기](#base64encode--python에서-읽기)
- [confetti](#confetti)
- [etc](#etc)
- [AR](#ar)
- **일부 추출: `wordName = wordName.substring(1, wordName.length - 1);`**
- [전체 사이즈 대비 크기](#전체-사이즈-대비-크기)
- [GestureDetector에서 onPanStart](#gesturedetector에서-onpanstart)
- [Painter 외에 그림 그리기](#painter-외에-그림-그리기)
- [Column - MainAxisAlignment](#column---mainaxisalignment)
- [유튜브 임베드](#유튜브-임베드)
- [Outlined Text](#outlined-text)
- [검색 모달창(TextField)](#검색-모달창textfield)
- [배경 이미지](#배경-이미지)
- [노란색 밑줄 없애기](#노란색-밑줄-없애기)
- [tooltip](#tooltip)
- [No Material widget found error](#no-material-widget-found-error)
- [부모 위젯 크기에 맞게](#부모-위젯-크기에-맞게)
- **kIsWeb: 웹인지 아닌지 구분**
- **resizeToAvoidBottomInset : false, 키보드 올라갈 때 scaffold 안 올라가게**
- [TextField 엔터쳤을 때 넘어가기](#textfield-엔터쳤을-때-넘어가기)
- [audio](#audio)  

<br>
<br>


### 데이터 참고 사이트
    
- **1. 데이터스토어(민간, 공공) - 데이터산업진흥원**  
    **[https://www.datastore.or.kr/](https://www.datastore.or.kr/)**

- **2. 통계청 마이크로데이터(MDIS) - 통계청**  
    **[https://mdis.kostat.go.kr/index.do](https://mdis.kostat.go.kr/index.do)**

- **3. 공공/민간 오픈데이터 목록을 통째로 제공 - 통합데이터지도**  
    **[https://www.bigdata-map.kr/](https://www.bigdata-map.kr/)**

- **4. 서울시 빅데이터 캠퍼스**  
    **[https://bigdata.seoul.go.kr/main.do](https://bigdata.seoul.go.kr/main.do)**

- **5. AI Hub - 인공지능 학습데이터셋을 구할 수 있는 곳**  
    **[https://www.aihub.or.kr/](https://www.aihub.or.kr/)**

- **6. 스마트치안 빅데이터 플랫폼 - 경찰청**  
    **[https://bigdata-policing.kr/](https://bigdata-policing.kr/)**

- **7. 캐글 데이터 셋**  
    **[https://www.kaggle.com/datasets](https://www.kaggle.com/datasets)**

- **8. 공공데이터 포털 - OPEN API를 이용한 수집**  
    **[https://www.data.go.kr/](https://www.data.go.kr/)**

- **9. 서울 열린데이터 광장**  
    **[https://data.seoul.go.kr/](https://data.seoul.go.kr/)**

- **10. 문화 빅데이터 플랫폼**  
    **[https://www.bigdata-culture.kr/bigdata/user/main.do](https://www.bigdata-culture.kr/bigdata/user/main.do)**

- **11. 국토정보플랫폼**  
    **[http://map.ngii.go.kr/mn/mainPage.do](http://map.ngii.go.kr/mn/mainPage.do)**

- **12. Local Data**  
    **[https://www.localdata.go.kr/devcenter/dataDown.do?menuNo=20001](https://www.localdata.go.kr/devcenter/dataDown.do?menuNo=20001)**

- **13. 통합 데이터 지도**  
    **[https://www.bigdata-map.kr/](https://www.bigdata-map.kr/)**

- **14. 농림축산식품 공공데이터 포털**  
    **[https://data.mafra.go.kr/main.do](https://data.mafra.go.kr/main.do)**

- **15. 경기 데이터 드림**  
    **[https://data.gg.go.kr/portal/mainPage.do](https://data.gg.go.kr/portal/mainPage.do)**

- **16. 금융데이터 거래소**  
    **[https://www.findatamall.or.kr/fsec/main/main.do?cmnx=1](https://www.findatamall.or.kr/fsec/main/main.do?cmnx=1)**

- **17. KDX 한국데이터거래소**  
    **[https://kdx.kr/main](https://kdx.kr/main)**  
    
<br>
    
### 공공데이터 포털의 OPEN API 사용방법
- **[Python] 공공데이터 포털의 OPEN API 사용방법 - 1**  
    ****[https://wonhwa.tistory.com/5](https://wonhwa.tistory.com/5)****

- **[Python] 공공데이터 포털의 OPEN API 사용방법 - 2 (데이터셋을 JSON 형태로 변경, DataFrame으로 변환하는 방법)**  
    ****[https://wonhwa.tistory.com/9](https://wonhwa.tistory.com/9)****

- **[Python] 공공데이터 수집 (Open API - XML파일)**  
    ****[https://greendreamtrre.tistory.com/268](https://greendreamtrre.tistory.com/268)****

- **[Python] 공공데이터 OPEN API의 XML 파일을 DataFrame으로 변환하기(feat. 코로나 확진자 수)**  
    ****[https://wonhwa.tistory.com/16](https://wonhwa.tistory.com/16)****
        

<br>  

### painter  

```dart
// 처음 정의
PainterController _controller = _newController();

// 그림 그리는 부분
static PainterController _newController() {
  PainterController controller = PainterController();
  controller.thickness = 5.0;
  // controller.backgroundColor = Colors.amber;
  return controller;
}

// 툴 + 그림 그리는 부분
Container(
    margin:
        const EdgeInsets.symmetric(horizontal: 20, vertical: 10),
    decoration: BoxDecoration(
        border: Border.all(color: Colors.black, width: 1)),
    child: Column(children: [
      Container(
        decoration: const BoxDecoration(
          color: Color(0xffffb628),
        ),
        // 툴바
        child: Row(
          mainAxisAlignment: MainAxisAlignment.spaceBetween,
          children: [
            // 펜 or 지우개
            _controller.eraseMode
                ? RotatedBox(
                    quarterTurns: 2,
                    child: IconButton(
                        icon: const Icon(Icons.auto_fix_high),
                        tooltip: 'Enable eraser',
                        onPressed: () {
                          setState(() {
                            _controller.eraseMode =
                                !_controller.eraseMode;
                          });
                        }),
                  )
                : IconButton(
                    icon: const Icon(Icons.create),
                    tooltip: 'Disable eraser',
                    onPressed: () {
                      setState(() {
                        _controller.eraseMode =
                            !_controller.eraseMode;
                      });
                    }),
            // 펜, 지우개 굵기 조절 Slider
            Container(
              width: 150,
              child: SliderTheme(
                data: const SliderThemeData(
                  valueIndicatorShape:
                      PaddleSliderValueIndicatorShape(),
                ),
                child: Slider(
                  value: _controller.thickness,
                  onChanged: (double value) => setState(() {
                    _controller.thickness = value;
                  }),
                  min: 0.0,
                  max: 20.0,
                  divisions: 4,
                  label: _controller.thickness.round().toString(),
                  activeColor: Colors.black,
                ),
              ),
            ),

            // 되돌리기
            IconButton(
                icon: const Icon(
                  Icons.undo,
                ),
                tooltip: 'Undo',
                onPressed: () {
                  if (!_controller.isEmpty) {
                    _controller.undo();
                  }
                }),
            // 다 지우기
            IconButton(
                icon: const Icon(Icons.refresh),
                tooltip: 'Clear',
                onPressed: _controller.clear)
          ],
        ),
      ),

      // 그림 그리는 부분
      AspectRatio(
        aspectRatio: 1.2, // 사이즈 조절(크게할수록 작아짐)
        child: Painter(_controller),
      ),
    ]))

// 끝나고 새로운 창으로 바꿀 때
setState(() {
        _controller = _newController();
      });
```
<br>
    
### IconButton
- 사이즈 조절

    ```dart
    IconButton(
      iconSize: 200,
      icon: Image.network(
        'https://i.ytimg.com/vi/7XFFStC-XqA/mqdefault.jpg'),
        onPressed: () {
          Navigator.pushNamed(context, drawingRoute,
          arguments: DrawingView(id: 0));
          },
    )
    ```

- 기본 여백 삭제

    ```dart
    IconButton(
       padding: EdgeInsets.zero,
       iconSize: 20,
       constraints: BoxConstraints(), // 있을 때 없을 때 똑같았음
    ```

- 그래도 여백 있는 경우
    - Column 밑에 `crossAxisAlignment: CrossAxisAlignment.stretch,`추가
- 스크롤
    - Column 대신 ListView 사용
    - `crossAxisAlignment: CrossAxisAlignment.stretch` 안해도 됨
        
<br>

### http (axios)      
```dart
import 'package:http/http.dart' as http;
import 'dart:convert';

bool _1 = false;
void getItems() async {
  Uri url = Uri.https('jsonplaceholder.typicode.com', '/todos');
  try {
    http.Response response = await http.get(url);
    var jsonResponse = json.decode(response.body);
    _1 = jsonResponse[3]['completed'];
  } catch (e) {
    print('$e getItems 에러');
  }
}

```

```dart
// method가 post일 때는 content-type 지정해줘야함

import 'package:http/http.dart' as http;
import 'dart:convert';  // json
import 'dart:io'; // HttpHeaders

try {
      http.Response response = await http.post(
          Uri.parse('https://j8a401.p.ssafy.io/api/v1/quiz-tale-items'),
          headers: {
            HttpHeaders.authorizationHeader: 'Bearer ',
            'Content-Type': "application/json"
          },
          body: jsonEncode(<String, int>{"quizTaleItemListId": 1}));
      var jsonResponse = jsonDecode(response.body);
    } catch (e) {
      print('$e isCorrect 정답 확인 에러');
    }

// 결과가 한글일 경우 jsonDecode(utf8.decode(response.bodyBytes));
```

<br>

### 빌드 이후 한 번만 실행      
```dart
void initState() {
    super.initState();
    WidgetsBinding.instance
        .addPostFrameCallback((_) => yourFunction(context));
  }
```
    
<br>

### margin
- Container 안에 margin
- EdgeInsets.symmetric(horizontal: 좌우, vertical: 상하) → 상하/좌우 구분해서 줄 때
- EdgeInsets.fromLTRB(왼쪽, 위, 오른쪽, 아래)
- margin: EdgeInsets.all(전체),

<br>

### in, not in 리스트
```dart
List<String> fruits = ["apple", "banana", "orange"];
bool isContain = fruits.contains("banana");
print(isContain); // true
```

<br>

### Uint8List 이미지  
- Future<Uint8List> → Uint8List: await 쓰면 됨
- Uint8List → Image: var _image = MemoryImage(image);
- image → Uint8List: List stuff = image.toByteData().buffer.asUInt8List()  
    
```dart
img() async {
    PictureDetails picture = _controller.finish();
    Uint8List a = await picture.toPNG();
    var img = MemoryImage(a);

    showDialog(
        context: context,
        builder: (context) => Container(
              alignment: Alignment.center,
              child: Image(image: img),
            ));
  }
```

```dart
img() async {
    PictureDetails picture = _controller.finish();
    Uint8List a = await picture.toPNG();

    showDialog(
        context: context,
        builder: (context) => Container(
              alignment: Alignment.center,
              child: Image.memory(a),
            ));
  }
```

<br>

### multipart request

```dart
try {
  MultipartRequest request = new http.MultipartRequest('POST',
      Uri.parse('https://j8a401.p.ssafy.io/ai/predictions/drawings'));
  request.headers["authorization"] = 'Bearer $token';
  request.headers['Content-Type'] = 'multipart/form-data';

  request.files.add(await http.MultipartFile.fromBytes('file', a));

  var response = await request.send();
  final jsonBody = json.decode(await response.stream.bytesToString());
  print(jsonBody);
} catch (e) {
  print('$e 이미지 전송 에러');
}
```
<br>
    
### 전체 print
```dart
import 'dart:developer' as logDev;

logDev.log(프린트할거);
```

<br>
    
### base64Encode() → python에서 읽기

```python
import base64
from PIL import Image # pip install pillow
from io import BytesIO
import matplotlib.pyplot as plt # python -m pip install -U pip, python -m pip install -U matplotlib

img = Image.open(BytesIO(base64.b64decode(인코딩된거)))
    
# 좌표평면 위에 보임
plt.imshow(img)
plt.show()

# 사진으로 보임
img.show()
```

<br>
    
### confetti

```yaml
dependencies:
  confetti: ^0.7.0
```

```python
import 'package:confetti/confetti.dart';

class _MyAppState extends State<MyApp> {
  late ConfettiController _controllerCenter;
  late ConfettiController _controllerCenterRight;
  late ConfettiController _controllerCenterLeft;
  late ConfettiController _controllerTopCenter;
  late ConfettiController _controllerBottomCenter;

  @override
  void initState() {
    super.initState();
    _controllerCenter =
        ConfettiController(duration: const Duration(seconds: 10));
    _controllerCenterRight =
        ConfettiController(duration: const Duration(seconds: 10));
    _controllerCenterLeft =
        ConfettiController(duration: const Duration(seconds: 10));
    _controllerTopCenter =
        ConfettiController(duration: const Duration(seconds: 10));
    _controllerBottomCenter =
        ConfettiController(duration: const Duration(seconds: 10));
  }

  @override
  void dispose() {
    _controllerCenter.dispose();
    _controllerCenterRight.dispose();
    _controllerCenterLeft.dispose();
    _controllerTopCenter.dispose();
    _controllerBottomCenter.dispose();
    super.dispose();
  }

@override
  Widget build(BuildContext context) {
    return SafeArea(
      child: Stack(
        children: <Widget>[
          //CENTER -- Blast
          Align(
            alignment: Alignment.center,
            child: ConfettiWidget(
              confettiController: _controllerCenter,
              blastDirectionality: BlastDirectionality
                  .explosive, // don't specify a direction, blast randomly
              shouldLoop:
                  true, // start again as soon as the animation is finished
              colors: const [
                Colors.green,
                Colors.blue,
                Colors.pink,
                Colors.orange,
                Colors.purple
              ], // manually specify the colors to be used
              createParticlePath: drawStar, // define a custom shape/path.
            ),
          ),
                    //TOP CENTER - shoot down
          Align(
            alignment: Alignment.topCenter,
            child: ConfettiWidget(
              confettiController: _controllerTopCenter,
              blastDirection: pi / 2,
              maxBlastForce: 5, // set a lower max blast force
              minBlastForce: 2, // set a lower min blast force
              emissionFrequency: 0.05,
              numberOfParticles: 50, // a lot of particles at once
              gravity: 1,
            ),
          ),
```
    
<br>
    
### etc
- 배경 제거해서 투명으로 만들어주는 사이트
    - [https://www.remove.bg/ko](https://www.remove.bg/ko)
- 여러 PDF 파일을 하나의 PDF로 합쳐주는 사이트
    - [https://smallpdf.com/kr/merge-pdf](https://smallpdf.com/kr/merge-pdf)
- 온라인에서 포토샵 대신 쓸 수 있는 사이트
    - [https://www.photopea.com/](https://www.photopea.com/)
- 온라인에서 코틀린 언어를 사용할 수 있는 사이트
    - [https://play.kotlinlang.org/](https://play.kotlinlang.org/)
- JSON 파싱해주는 사이트
    - [http://json.parser.online.fr/](http://json.parser.online.fr/)
    - [https://jsonformatter.org/json-parser](https://jsonformatter.org/json-parser)
- JAVA 크론 만들어주는 사이트
    - [http://www.cronmaker.com/](http://www.cronmaker.com/)
- 리눅스 크론 만들어주는 사이트
    - [https://crontab.guru/](https://crontab.guru/)
- 가상 프린터를 통해 PDF 파일 만들어주는 프로그램 (모두의프린터)
    - [https://modu-print.tistory.com/category/%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C](https://modu-print.tistory.com/category/%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C)
- 무료 픽토그램 이미지 사이트
    - [https://www.flaticon.com/](https://www.flaticon.com/)
- 무료 폰트
    - 나눔고딕 : [https://hangeul.naver.com/2017/nanum](https://hangeul.naver.com/2017/nanum)
    - D2Coding : [https://github.com/naver/d2codingfont](https://github.com/naver/d2codingfont)
    - 제주고딕 : [https://www.jeju.go.kr/jeju/symbol/font/gothic.htm](https://www.jeju.go.kr/jeju/symbol/font/gothic.htm)

<br>
    
### AR  
```yaml
// pubspec.yaml

...
dependencies:
 flutter:
   sdk: flutter
 ar_flutter_plugin: ^0.6.2
...
```

```
// local.properties

flutter.minSdkVersion=24

//app-level build.gradle
android {
    defaultConfig {
        ...
        minSdkVersion localProperties.getProperty('flutter.minSdkVersion')
    }
}

or

// app-level build.gradle

android {
    defaultConfig {
        ...
        minSdkVersion 24
    }
}
```

```dart
import 'package:ar_flutter_plugin/ar_flutter_plugin.dart';
import 'package:ar_flutter_plugin/datatypes/node_types.dart';
import 'package:ar_flutter_plugin/managers/ar_anchor_manager.dart';
import 'package:ar_flutter_plugin/managers/ar_location_manager.dart';
import 'package:ar_flutter_plugin/managers/ar_object_manager.dart';
import 'package:ar_flutter_plugin/managers/ar_session_manager.dart';
import 'package:ar_flutter_plugin/models/ar_node.dart';
import 'package:flutter/material.dart';
import 'package:vector_math/vector_math_64.dart';

class LocalAndWebObjectsView extends StatefulWidget {
  const LocalAndWebObjectsView({Key? key}) : super(key: key);

  @override
  State<LocalAndWebObjectsView> createState() => _LocalAndWebObjectsViewState();
}

class _LocalAndWebObjectsViewState extends State<LocalAndWebObjectsView> {
  late ARSessionManager arSessionManager;
  late ARObjectManager arObjectManager;

  //String localObjectReference;
  ARNode? localObjectNode;

  //String webObjectReference;
  ARNode? webObjectNode;

  @override
  void dispose() {
    arSessionManager.dispose();
    super.dispose();
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text("Local / Web Objects"),
      ),
      body: Padding(
        padding: const EdgeInsets.symmetric(horizontal: 10),
        child: Column(
          mainAxisAlignment: MainAxisAlignment.spaceEvenly,
          children: [
            SizedBox(
              height: MediaQuery.of(context).size.height * .8,
              child: ClipRRect(
                borderRadius: BorderRadius.circular(22),
                child: ARView(
                  onARViewCreated: onARViewCreated,
                ),
              ),
            ),
            Row(
              children: [
                Expanded(
                  child: ElevatedButton(
                      onPressed: onLocalObjectButtonPressed,
                      child: const Text("Add / Remove Local Object")),
                ),
                const SizedBox(
                  width: 10,
                ),
                Expanded(
                  child: ElevatedButton(
                      onPressed: onWebObjectAtButtonPressed,
                      child: const Text("Add / Remove Web Object")),
                )
              ],
            ),
          ],
        ),
      ),
    );
  }

  void onARViewCreated(
      ARSessionManager arSessionManager,
      ARObjectManager arObjectManager,
      ARAnchorManager arAnchorManager,
      ARLocationManager arLocationManager) {
    this.arSessionManager = arSessionManager;
    this.arObjectManager = arObjectManager;

    this.arSessionManager.onInitialize(
          showFeaturePoints: false,
          showPlanes: true,
          customPlaneTexturePath: "assets/triangle.png",
          showWorldOrigin: true,
          handleTaps: false,
        );
    this.arObjectManager.onInitialize();
  }

  Future<void> onLocalObjectButtonPressed() async {
    if (localObjectNode != null) {
      arObjectManager.removeNode(localObjectNode!);
      localObjectNode = null;
    } else {
      var newNode = ARNode(
        type: NodeType.localGLTF2,
        uri: "assets/hello/hello.gltf",
        // scale: Vector3(0.5, 0.1, 0.1),
        // position: Vector3(0.0, 0.0, 0.0),
        // rotation: Vector4(1.0, 0.0, 0.0, 0.0)
      );
      bool? didAddLocalNode = await arObjectManager.addNode(newNode);
      localObjectNode = (didAddLocalNode!) ? newNode : null;
    }
  }

  Future<void> onWebObjectAtButtonPressed() async {
    if (webObjectNode != null) {
      arObjectManager.removeNode(webObjectNode!);
      webObjectNode = null;
    } else {
      var newNode = ARNode(
          type: NodeType.webGLB,
          uri:
              "https://github.com/KhronosGroup/glTF-Sample-Models/raw/master/2.0/Fox/glTF-Binary/Fox.glb",
          scale: Vector3(0.2, 0.2, 0.2));
      bool? didAddWebNode = await arObjectManager.addNode(newNode);
      webObjectNode = (didAddWebNode!) ? newNode : null;
    }
  }
}
```
<br>
    
    
### 전체 사이즈 대비 크기
- height: MediaQuery.of(context).size.height * 원하는 크기

```dart
MediaQuery.of(context).size             //앱 화면 크기 size  Ex> Size(360.0, 692.0)
MediaQuery.of(context).size.height      //앱 화면 높이 double Ex> 692.0 
MediaQuery.of(context).size.width       //앱 화면 넓이 double Ex> 360.0
MediaQuery.of(context).devicePixelRatio //화면 배율    double Ex> 4.0
MediaQuery.of(context).padding.top      //상단 상태 표시줄 높이 double Ex> 24.0
```

<br>
    
### GestureDetector에서 onPanStart
- It works in opposite direction of pageView direction. if you drag vertically in this horizontal pageView, it fires onPanStart and onPanEnd but not in same

```dart
class Home extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('demo'),
      ),
      body: GestureDetector(
        onPanCancel: () {
          print('pan cancel');
        },
        onPanDown: (_) {
          print('pan down');
        },
        onPanUpdate: (_) {
          print('pan update'); // won't trigger
        },
        onPanStart: (_) {
          print('pan start'); // won't trigger
        },
        onPanEnd: (_) {
          print('pan end'); // won't trigger
        },
        child: PageView.builder(
          itemBuilder: (ctx, index) {
            return Container(
                height: 100, color: Colors.blue, child: Text('$index'));
          },
        ),
      ),
    );
  }
```
    
<br>
    
### Painter 외에 그림 그리기
- 제스처를 디텍트 한 후 화면 위에 그리기

```dart
// 캔버스에 그림 그리기 위해 담는 리스트
List<List<Offset>> _points = [];
// AI쪽에 보낼 정보를 담는 리스트
List<List<List<int>>> path = [];

/////////////////////////////////////////////////////////////////////
GestureDetector(
    child: CustomPaint(
      painter: DrawingPainter(_points),
      size: Size(250, 250),
    ),
    onPanStart: (details) {
      setState(() {
        _points.add([details.localPosition]);
        path.add([
          [details.localPosition.dx.toInt()],
          [details.localPosition.dy.toInt()]
        ]);
      });
    },
    onPanUpdate: (details) {
      setState(() {
        // 범위(size)에서 벗어나면 리스트에 추가X
        if (details.localPosition.dx > 0 &&
            details.localPosition.dx < 250 &&
            details.localPosition.dy > 0 &&
            details.localPosition.dy < 250) {
          _points.last.add(details.localPosition);
          path.last[0].add(details.localPosition.dx.toInt());
          path.last[1].add(details.localPosition.dy.toInt());
        }
      });
    },
    )

///////////////////////////////////////////////////////////////////
// 제스처로 수집한 데이터를 화면에 나타내는 부분
class DrawingPainter extends CustomPainter {
  List<List<Offset>> points;

  DrawingPainter(this.points);

  @override
  void paint(Canvas canvas, Size size) {
    Paint paint = Paint()
      ..color = Colors.black
      ..strokeCap = StrokeCap.round
      ..strokeWidth = 5;

        // 획 별로 화면 위에 그림을 그리는 부분
    for (var pointList in points) {
      for (int i = 0; i < pointList.length - 1; i++) {
        canvas.drawLine(pointList[i], pointList[i + 1], paint);
      }
    }
  }

  // 바로바로 반영
  @override
  bool shouldRepaint(covariant CustomPainter oldDelegate) {
    return true;
  }
}
```
                                          
<br>
    
### Column - MainAxisAlignment
- MainAxisAlignment.start 상단부터 정렬
- MainAxisAlignment.center → 가운데 정렬 (가로축 가운데 정렬은 Center로)
- MainAxisAlignment.end 하단부터 정렬
- MainAxisAlignment.spaceAround 양 끝 + 위젯 사이에 간격 조절
- MainAxisAlignment.spaceBetween 양 끝 제외 간격 조절
- MainAxisAlignment.spaceEvenly
    - spaceAround는 각 위젯의 간격의 절반만 앞뒤로 여백을 가진다.
    - spaceEvenly는 각 위젯의 간격만큼 앞뒤로 여백을 가진다.
    
<br>
    
### 유튜브 임베드
- [https://pub.dev/packages/youtube_player_flutter](https://pub.dev/packages/youtube_player_flutter)
    - 유튜브 느낌 안 남, full screen일 때 따로 조절해줘야 함(다른 위젯 크기 포함해서 풀스크린으로 바뀜)
- [https://pub.dev/packages/youtube_player_iframe](https://pub.dev/packages/youtube_player_iframe)
    - 유튜브 그대로 옮긴 듯함, full screen시 다른 거 조절 안 해도 됨

<br>    
    
### Outlined Text
- 플러그인 없이 하기

    ```dart
    Stack(
      children: <Widget>[
        // Stroked text as border.
        Text(
          'Greetings, planet!',
          style: TextStyle(
            fontSize: 40,
            foreground: Paint()
              ..style = PaintingStyle.stroke
              ..strokeWidth = 6
              ..color = Colors.blue[700]!,
          ),
        ),
        // Solid text as fill.
        Text(
          'Greetings, planet!',
          style: TextStyle(
            fontSize: 40,
            color: Colors.grey[300],
          ),
        ),
      ],
    )
    ```

- [https://pub.dev/packages/outlined_text](https://pub.dev/packages/outlined_text)

 <br>   
    
### 검색 모달창(TextField)

```dart
import 'package:simplytranslate/simplytranslate.dart'; // 번역

final gt = SimplyTranslator(EngineType.google);
final searchController = TextEditingController();
String translate = '';

searchModal() async {
  return showDialog(
      barrierColor: Colors.transparent,  // 밖 배경 투명하게
      context: context,
      builder: (context) {
        searchController.text = '';  // TextField에 입력한 내용
        translate = '';              // 처음 모달 켰을 때 초기화
        return AlertDialog(
          backgroundColor: Colors.transparent,
          contentPadding: const EdgeInsets.all(0),
          content: StatefulBuilder(   // dialog 안 내용이 setState에 따라 바뀌게
              builder: (BuildContext context, StateSetter setState) {
            return Container(
              padding: const EdgeInsets.all(10),
              alignment: Alignment.bottomCenter,
              height: MediaQuery.of(context).size.height * 0.2,
              decoration: BoxDecoration(
                color: Colors.white,
                borderRadius: BorderRadius.circular(30),
                border: Border.all(
                  color: const Color(0xffffb628),
                  width: 5,
                ),
              ),
              child: Column(
                children: <Widget>[
                  Expanded(
                    child: TextField(
                        controller: searchController,
                        style: const TextStyle(
                            color: Colors.white, fontSize: 24),
                        cursorColor: Colors.white,
                        autofocus: true,
                        decoration: InputDecoration(
                            contentPadding: const EdgeInsets.all(15),
                            filled: true,
                            suffixIcon: IconButton(  // 뒷부분 아이콘
                                padding: const EdgeInsets.all(0),
                                onPressed: () async {
                                  String result = await gt.trSimply(
                                      (searchController.text), "en", 'ko');
                                  setState(() {
                                    translate = result;
                                  });
                                },
                                icon: const Icon(Icons.search_rounded,
                                    color: Colors.white, size: 40)),
                            fillColor: const Color(0xffffb628),
                            border: const OutlineInputBorder(
                                borderRadius:
                                    BorderRadius.all(Radius.circular(30))))),
                  ),
                  Container(
                      margin: EdgeInsets.only(
                          bottom: MediaQuery.maybeOf(context)!.size.height *
                              0.03),
                      child: Text(
                        translate,
                        style: const TextStyle(fontSize: 30),
                      ))
                ],
              ),
            );
          }),
        );
      });
}
```

- 수정

```dart
import 'package:learning_translate/learning_translate.dart';

Translator translator = Translator(from: ENGLISH, to: KOREAN); // 영어 -> 한국어
final searchController = TextEditingController(); // TextField 컨트롤러
String translate = '';
bool isSearching = false; // 검색 중일 때 로딩창 띄우기 위해
bool counterShow = false; // 제한 글자수 이상일 때 counterText 띄우기 위해

// 검색 모델 설치 여부 확인
isModelInstalled() async {
  bool isDownloaded = await TranslationModelManager.check(KOREAN)
  // 모델 미설치 시 설치
  if (!isDownloaded) {
    await TranslationModelManager.download(KOREAN);
  }
}

// 검색 모달창
searchModal() async {
  // 검색 모델 미설치 시 설치
  isModelInstalled();

  return showDialog(
      barrierColor: Colors.transparent,
      context: context,
      builder: (context) {
        // 모달 켰을 때, 데이터 초기화
        searchController.text = '';
        translate = '';
        counterShow = false;

        return AlertDialog(
          backgroundColor: Colors.transparent,
          contentPadding: const EdgeInsets.all(0),
          content: StatefulBuilder(  // setState하면 dialog 안에 내용 바뀌게
              builder: (BuildContext context, StateSetter setState) {
            return Container( // 보여지는 전체 모달
              padding: const EdgeInsets.all(10),
              alignment: Alignment.bottomCenter,
              height: MediaQuery.of(context).size.height * 0.2,
              decoration: BoxDecoration(
                color: Colors.white,
                borderRadius: BorderRadius.circular(30),
                border: Border.all(
                  color: const Color(0xffffb628),
                  width: 5,
                ),
              ),
              child: Column(
                children: <Widget>[
                  Expanded(
                    // 검색창
                    child: TextField(
                        // 글자수 30자로 제한
                        maxLengthEnforcement: MaxLengthEnforcement.enforced,
                        maxLength: 30,

                        controller: searchController, // TextField 컨트롤러
                        style: const TextStyle(
                            color: Colors.white, fontSize: 24),
                        cursorColor: Colors.white,
                        autofocus: true,
                        // 글자수가 30보다 크면 counterText 뜨게
                        onChanged: (text) {
                          if (text.length >= 30) {
                            setState(() {
                              counterShow = true;
                            });
                          }
                        },
                        decoration: InputDecoration(
                            counterText:
                                (counterShow) ? '30자 이내로 입력해주세요' : '',
                            contentPadding: const EdgeInsets.all(15), // 내부 패딩
                            filled: true,
                            suffixIcon: IconButton( // 검색 버튼
                                padding: const EdgeInsets.all(0),
                                onPressed: () async {
                                  setState(() {
                                    isSearching = true;
                                  });
                                  String result = await translator
                                      .translate(searchController.text);
                                  setState(() {
                                    translate = result;
                                    isSearching = false;
                                  });
                                },
                                icon: const Icon(Icons.search_rounded,
                                    color: Colors.white, size: 40)),
                            fillColor: const Color(0xffffb628),
                            border: const OutlineInputBorder(
                                borderRadius:
                                    BorderRadius.all(Radius.circular(30))))),
                  ),
                  // 결과 나오는 부분
                  Container(
                      margin: EdgeInsets.only(
                          bottom: MediaQuery.of(context).size.height * 0.03),
                      child: (isSearching)
                          ? const CircularProgressIndicator()
                          : Text(
                              translate,
                              style: const TextStyle(fontSize: 30),
                            ))
                ],
              ),
            );
          }),
        );
      });
}
```

<br>    
    
### 배경 이미지

```dart
    Container(
    height: MediaQuery.of(context).size.height,
    decoration: const BoxDecoration(
      image: DecorationImage(
        fit: BoxFit.cover,
        image: AssetImage('assets/home_background.png'),
      ),
    ),
    child: Column()
)
```

<br>    
    
### 노란색 밑줄 없애기
- 상위 위젯으로 Scaffold를 사용
- DefaultTextStyle 위젯 사용
- 화면 전환 [https://seosh817.tistory.com/211](https://seosh817.tistory.com/211)
- 크기 안에 딱 맞게

```dart
// 너비에 따라 폰트가 바뀜

SizedBox(
    width: MediaQuery.of(context).size.width * 0.4,
    child: FittedBox(
      fit: BoxFit.fitWidth, // 너비에 맞게
      child: OutlinedText(
          text: Text(title[id - 1],
              style: const TextStyle(
                  color: Colors.white)),
          strokes: [
            OutlinedTextStroke(
                color: const Color(0xff198100),
                width: 10),
          ]),
    ),
)
```

```dart
// 크기가 넘어가면 2줄로 바뀜

Flexible(
    child: Center(
      child: OutlinedText(
          text: Text(title[id - 1],
              textAlign: TextAlign.center,
              style: TextStyle(
                  color: Colors.white,
                  fontSize:
                      MediaQuery.of(context).size.width *
                          0.1)),
          strokes: [
            OutlinedTextStroke(
                color: const Color(0xff198100),
                width: 10),
          ]),
    ),
)

// or

SizedBox(
    width: MediaQuery.of(context).size.width * 0.4,
    child: Center(
      child: OutlinedText(
          text: Text(title[id - 1],
              textAlign: TextAlign.center,
              style: const TextStyle(
                  color: Colors.white, fontSize: 30)),
          strokes: [
            OutlinedTextStroke(
                color: const Color(0xff198100),
                width: 10),
          ]),
    ),
)
```

<br>    
    
### tooltip
- 버튼을 길게 누르면 설정한 텍스트가 나옴
- `tooltip: '지우기'`
    
<br>    
    
### No Material widget found error
- MaterialApp() or Scaffold()로 감싸기
- Material()로 감싸기

<br>    
    
### 부모 위젯 크기에 맞게
- LayoutBuilder
- Center or Align의 widthFactor, heightFactor
    
    
<br>    
    
### TextField 엔터쳤을 때 넘어가기

```dart
TextField(
    // 엔터키 이미지 바꾸기 
    textInputAction: TextInputAction.search,
    // 엔터키 눌렀을 때
    onSubmitted: (value) async {
      _focusNode.requestFocus();  // 키보드 안 내려가게
      searchController.text = value;
      searchController.selection =
          TextSelection.fromPosition(TextPosition(
              offset: searchController.text.length));  // 포커스 단어 맨 끝으로 가게
      setState(() {
        isSearching = true;
      });
      String result = await onDeviceTranslator
          .translateText(searchController.text);
      setState(() {
        translate = result;
        isSearching = false;
      });
    },
)
```

<br>    
    
### audio

```dart
import 'package:audioplayers/audioplayers.dart';

AudioPlayer audioPlayer = AudioPlayer();

audioPlayer.play(AssetSource('sound/clap.mp3'));
audioPlayer.stop();
```
