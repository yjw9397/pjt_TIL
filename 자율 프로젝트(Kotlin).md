# 자율 프로젝트

- Modifier.weight
    - 전체 중에서 자식 요소가 차지하는 비율을 설정
        
        ```kotlin
        // 자식 요소가 가로 방향을 꽉 채우도록 설정한 것입니다.
        Row(modifier = Modifier.fillMaxWidth()) {
            Image(
                painter = painterResource(id = R.drawable.left_image),
                contentDescription = null,
                modifier = Modifier
                    .weight(1f) // 전체 너비의 1/3
                    .height(100.dp)
            )
            Image(
                painter = painterResource(id = R.drawable.right_image),
                contentDescription = null,
                modifier = Modifier
                    .weight(2f) // 전체 너비의 2/3
                    .fillMaxHeight()
            )
        }
        ```
        
- contentDescription: 이미지나 아이콘 등에 필수로 입력해야 함(시각적 지원이 필요한 사람들을 위함)
- Row 정렬
    - `horizontalArrangement = Arrangement.SpaceBetween`
    - Row 안에 하나는 가운데, 하나는 오른쪽 끝에
        
        ```kotlin
        Row(
            modifier = Modifier.fillMaxWidth(),
            horizontalArrangement = Arrangement.SpaceBetween
        ){
            Text(text = "결제 내역 조회", modifier = Modifier.weight(1f), textAlign = TextAlign.Center)
            Icon(Icons.Filled.ArrowForward, "결제 내역 조회 이동")
        }
        ```
        
    - 3개는 왼쪽, 하나는 오른쪽
        
        ```kotlin
        Row(
            verticalAlignment = Alignment.CenterVertically,
            modifier = Modifier
                .fillMaxWidth()
                .padding(10.dp)
        ) {
            
            Text(quantity.toString())
        		Text(quantity.toString())
        		Text(quantity.toString())
            
            OutlinedButton(
                onClick = { addGetCart() },
                border = BorderStroke(color = Main_blue, width = 2.dp),
                elevation = ButtonDefaults.elevation(2.dp),
                modifier = Modifier
                    .weight(1f)
                    .wrapContentWidth(align = Alignment.End)
            ) {
                Text("장볼구니", color = Main_gray)
            }
        }
        ```
        
- 수정자
    - 순서 중요!
        
        ```kotlin
        // 패딩을 포함한 전체가 clickable
        Modifier
            .padding(padding)
            .clickable(onClick = onClick)
        
        // 패딩을 제외한 부분만 clickable
        Modifier
            .clickable(onClick = onClick)
            .padding(padding)
        ```
        
    - clickable
        - `.*clickable* **{ 함수** **}**`
    - padding
        - `.*padding*(horizontal = 30.*dp*, vertical = 20.*dp*)`
        - `.*padding*(top = 30.*dp*)`
    - border
        - `.*border*(color = Color.Black, width = 1.5.*dp*, shape = *CircleShape*)`
    - 크기
        - `.*fillMaxWidth*()`, `.*fillMaxHeight*()`, `.*fillMaxSize*()`
            - 괄호 안에 fraction(1F, 2F…)
        - `.*width*()`, `.*height*()`, `.size()`
            - 괄호 안에 크기(10.dp, 5.5.dp…)
            - `.*height*(IntrinsicSize.*Max*)`현재 요소가 가질 수 있는 최대 높이
    - shadow
        
        ```kotlin
        modifier = Modifier
            .shadow(
                shape = CircleShape,
                elevation = 5.dp,
                ambientColor = Color.Black,
                clip = true
            ),
        ```
        
    - 스크롤
        - `.*verticalScroll*(state = *rememberScrollState*())`
- 안드로이드 스튜디오 - 찾아서 변경: ctrl + R
- Icon, IconButton
    
    ```kotlin
    Icon(
        imageVector = Icons.Default.Search,
        contentDescription = "검색 버튼",
        modifier = Modifier
            .clickable { search() }
            .size(30.dp),
        tint = Color.White
    )
    
    IconButton(
        onClick = { quantity-- },
        enabled = 1 < quantity  // 이 외엔 disabled
    ) {
        Icon(Icons.Default.KeyboardArrowLeft, contentDescription = "수량 감소")
    }
    ```
    
- 배경 이미지
    
    ```kotlin
    Image(
    		painter = painterResource(R.drawable.bg), // drawable에 있는 이미지
    		modifier = Modifier.fillMaxSize(),
    		contentDescription = "배경",
    		contentScale = ContentScale.FillBounds
    )
    ```
    
- Arrangement
    - `Row(horizontalArrangement = Arrangement.SpaceBetween){}`
    - `Column(verticalArrangement = Arrangement.SpaceBetween){}`
- state
    
    ```kotlin
    // 더 권장되는 방법
    
    var a: String? by remember { mutableStateOf(null) }
    a = "d"
    ```
    
    ```kotlin
    val a = remember{mutableStateOf("")} // a는 MutableState<String> 타입
    a.value = "d"
    ```
    
- OutlinedTextField(검색 기능)
    
    ```kotlin
    // 검색바
    @OptIn(ExperimentalComposeUiApi::class)
    @Composable
    fun searchBar(navController: NavController){
        var searchWord by remember { mutableStateOf("") }
    
        fun search(){
            navController.navigate("search/$searchWord")
        }
    
        fun barcodeSearch(){
            navController.navigate("barcodeScan")
        }
        
        // 키보드 조정
        val keyboardController = LocalSoftwareKeyboardController.current
        
        // 검색창
        OutlinedTextField(
            value = searchWord,
            onValueChange = { searchWord = it },
            shape = CircleShape,
            modifier = Modifier
                .fillMaxWidth()
                .height(100.dp)
                .padding(20.dp)
                .border(color = Color.Black, width = 1.5.dp, shape = CircleShape)
                .shadow(
                    shape = CircleShape,
                    elevation = 5.dp,
                    ambientColor = Color.Black,
                    clip = true
                ),
            colors = TextFieldDefaults.textFieldColors(
                backgroundColor = Main_yellow,
                textColor = Color.Black
            ),
            singleLine = true,
            textStyle = TextStyle(fontFamily = mainFont, fontSize = 15.sp),
    
    				// textfield 우측에 아이콘 추가
            trailingIcon = {
                Row(
                    modifier = Modifier
                        .padding(horizontal = 20.dp)
                ) {
                    Image(
                        painter = painterResource(R.drawable.barcode),
                        contentDescription = "바코드 검색",
                        modifier = Modifier
                            .size(30.dp)
                            .clickable { barcodeSearch() }
                    )
                    Spacer(modifier = Modifier.width(10.dp))
                    Image(
                        painter = painterResource(R.drawable.search),
                        contentDescription = "검색",
                        modifier = Modifier
                            .size(30.dp)
                            .clickable {
                                search()
                            }
                    )
    
                }
            },
    				// 키보드 모양 바꾸기
            keyboardOptions = KeyboardOptions(imeAction = ImeAction.Search),
    				// 엔터(키보드에서 search아이콘) 클릭 시 실행
            keyboardActions = KeyboardActions(onSearch = {
                search()
                keyboardController?.hide()
            })
        )
    }
    
    // 숫자 키패드
    keyboardOptions = KeyboardOptions(keyboardType = KeyboardType.Number)
    
    // 비밀번호
    visualTransformation = PasswordVisualTransformation() // 화면에 입력값 안 보이게
    keyboardOptions = KeyboardOptions(keyboardType = KeyboardType.Password)
    ```
    
- bottomBar
    
    ```kotlin
    Scaffold(
        bottomBar = {
            Row(
                modifier = Modifier
                    .fillMaxWidth()
                    .height(IntrinsicSize.Min)
            ) {
                Image(painter = painterResource(R.drawable.bottombar_1), contentDescription = "빠른장보기",
                    modifier = Modifier
                        .weight(1f) // 각각 1F 너비(똑같은 너비)
                        .fillMaxHeight()
                        .aspectRatio(1f / 1f) // 원본 비율 유지
                        .clickable(onClick = { navController.navigate("barcodeScan") })
                )
                Image(painter = painterResource(R.drawable.bottombar_2), contentDescription = "장볼구니",
                    modifier = Modifier
                        .weight(1f)
                        .fillMaxHeight()
                        .aspectRatio(1f / 1f)
                        .clickable(onClick = { navController.navigate("getCart") }))
                Image(painter = painterResource(R.drawable.bottombar_3), contentDescription = "장봤구니",
                    modifier = Modifier
                        .weight(1f)
                        .fillMaxHeight()
                        .aspectRatio(1f / 1f)
                        .clickable(onClick = { navController.navigate("gotCart") }))
                Image(painter = painterResource(R.drawable.bottombar_4), contentDescription = "마이페이지",
                    modifier = Modifier
                        .weight(1f)
                        .fillMaxHeight()
                        .aspectRatio(1f / 1f)
                        .clickable(onClick = { navController.navigate("myPage") }))
            }
        }
    )
    ```
    
- 폰트 적용
    - res 우클릭 > New > Android Resource Directory
        - Directory name: font
        - Resource type: font
    - font 폴더 안에 폰트 넣기
    - ui.theme > Type.kt
        - `val *mainFont* = F*ontFamily*(*Font*(R.font.*gmarket_sans_ttf_medium*))`
    - 기본 폰트 적용
        
        ```kotlin
        // ui.theme > Type.kt
        
        val mainFont = FontFamily(
            Font(R.font.gmarket_sans_ttf_medium),
            Font(R.font.gmarket_sans_ttf_light, FontWeight.Light),
            Font(R.font.gmarket_sans_ttf_bold, FontWeight.Bold)
        )
        
        val mainTypography = Typography(
            defaultFontFamily = mainFont)
        )
        ```
        
        ```kotlin
        // MainActivity.kt
        
        class MainActivity : ComponentActivity() {
            override fun onCreate(savedInstanceState: Bundle?) {
                super.onCreate(savedInstanceState)
                setContent {
                    MaterialTheme(typography = mainTypography) {
        						// content
        					}
                }
            }
        }
        ```
        
- 화면전환(navigate)
    - build.gradle
        
        ```kotlin
        implementation "androidx.navigation:navigation-compose:2.5.3"
        ```
        
    - MainActivity.kt
        
        ```kotlin
        class MainActivity : ComponentActivity() {
            override fun onCreate(savedInstanceState: Bundle?) {
                super.onCreate(savedInstanceState)
                setContent {
                    val navController = rememberNavController()
                    NavHost(navController = navController, startDestination = "main") {
                        composable(route = "main"){
                            Main(navController)
                        }
                        composable(route = "category/{categoryId}", arguments = listOf(navArgument("categoryId"){type = NavType.IntType})){ backStackEntry ->
                            Category(navController, backStackEntry.arguments?.getInt("categoryId"))
                        }
                    }
                }
            }
        }
        
        @Composable
        fun Main(navController: NavController) {
        		// 카테고리 별 상품보기
            fun category(categoryId: Int){
                navController.navigate("category/$categoryId")
            }
        
        		Image(
        	      painter = painterResource(R.drawable.category_1),
        	      contentDescription = "가공식품",
        	      modifier = Modifier
        	          .size(60.dp)
        	          .clickable { category(1) }
        	  )
        }
        ```
        
    - Category.kt
        
        ```kotlin
        @Composable
        fun Category(navController: NavController, categoryId: Int?){
            Row() {
                Text(text = "categotyId = ${categoryId}")
                Button(onClick = { navController.navigate("main") }) {
                    Text(text = "메인으로")
                }
            }
        }
        ```
        
    - 뒤로가기
        
        ```kotlin
        navController.popBackStack()
        
        // 백스택이 null이 아닐 때만 이동
        navController.previousBackStackEntry?.let {
        navController.popBackStack(it.destination.id, false)}
        ```
        
    - Back Stack을 다 지우고 startDestination으로 이동
        
        ```kotlin
        navController.popBackStack(navController.graph.startDestinationId, false)
        ```
        
    - 지금 화면을 backStack에 넣지 않고 이동
        
        ```kotlin
        // 로그인 화면 -> main 이동할 때
        navController.navigate(
            "main",
            NavOptions.Builder()
                .setPopUpTo("login", true)
                .build()
        )
        ```
        
    - BackStack을 다 지우고 특정 페이지로 이동
        
        ```kotlin
        // inclusive = true로 하면 main까지 backStack에서 지움
        navController.navigate("payment/${paymentIdx}"){
            popUpTo("main") { inclusive = false }
        }
        ```
        
- 한 번만 실행: `LaunchedEffect(키값) {}`, key값이 변경될 때마다 실행, Unit을 넣으면 이후 변경X
- Set, List, Map
    - Set
        - 순서X, 중복X, hashSetOf() 메서드 사용
        - `val set = hashSetOf(1, 2, 3)`
    - List
        - 순서O, 중복O, listOf() 메서드 사용
        - `val list = listOf(1, 50, 400)`
        - println → toString이 기본으로 구현되어 있어서 따로 toString 할 필요X
        - first, last, max, min 등 메서드 사용 가능
    - Map
        - key, value로 값을 가져옴, hashMapOf() 메서드 사용
        - `val map = hashMapOf(1 to "one", 2 to "two", 3 to "three")`
            - to는 키워드가 아니라 일반 함수임
            - map[1] ⇒ “one”
- http(Retrofit 이용)
    
    ```kotlin
    // build.gradle
    
    // Retrofit 추가
    implementation 'com.squareup.retrofit2:retrofit:2.9.0'
    implementation 'com.squareup.retrofit2:converter-gson:2.9.0'
    ```
    
    ```kotlin
    import com.google.gson.Gson
    import com.google.gson.GsonBuilder
    import retrofit2.Retrofit
    import retrofit2.converter.gson.GsonConverterFactory
    import retrofit2.http.GET
    import retrofit2.http.Query
    
    data class Result(
        var resultCode : String?,
       val result: ItemDetail
    )
    
    data class ItemDetail(
        val image: String,
        val itemDetail: Any, // 타입을 정확히 모를 때
    )
    
    interface APIS {
    
        // Query 사용(http://k8a405.p.ssafy.io:8090/api/v1/items/categories?userIdx=1&categoryIdx=1)
    		@GET("items/categories")
        suspend fun getCategories(@Query("userIdx") userIdx: Int, @Query("categoryIdx") categoryIdx: Int): Result
    
    		// Path 사용
    		@GET("getcarts/{userId}")
        suspend fun getCartsRead(@Path("userId") userId: Int): CartResult
    
    		// Post
    		@POST("_search")
        suspend fun getSearchResult(@Body body: Any): Response
    
        companion object {
            private const val BASE_URL = "http://k8a405.p.ssafy.io:8090/api/v1/"
    
            fun create(): APIS {
                val gson : Gson =   GsonBuilder().setLenient().create();
                return Retrofit.Builder()
                    .baseUrl(BASE_URL)
                    .addConverterFactory(GsonConverterFactory.create(gson))
                    .build()
                    .create(APIS::class.java)
            }
        }
    }
    ```
    
    ```kotlin
    import kotlinx.coroutines.*
    
    @Composable
    fun Category(navController: NavController, categoryId: Int?){
    
        val api = APIS.create()
        val coroutineScope = rememberCoroutineScope()
        var result: Any? by remember { mutableStateOf(null) }
    
    		// 한 번만 실행
        LaunchedEffect(true) {
            result = coroutineScope.async { api.getCategories(userId, categoryId!!) }.await().result
            println(result)
        }
    
        if (result != null) {
            Text(text = result.toString())
        }
    }
    ```
    
- 웹 이미지 로드
    
    ```kotlin
    implementation("io.coil-kt:coil-compose:2.3.0")
    ```
    
    ```kotlin
    AsyncImage(
        model = "https://mmart405.s3.ap-northeast-2.amazonaws.com/${item.thumbnail.replace("_thumb", "")}",
        contentDescription = "상품 썸네일",
        modifier = Modifier
            .fillMaxSize()
            .aspectRatio(1f) // 크기에 딱 맞게 됨
            .padding(5.dp),
        onSuccess = {isLoading = false} // 이미지 로딩에 성공했을 때 실행
    )
    ```
    
- LazyRow, LazyColumn, LazyGrid
    - 수평 스크롤 뷰를 생성, items 속성을 활용하여 하나씩 정의 가능
    - 1~8로 item을 설정하고 싶을 때, `items((1..8).toList())`
        - 그냥 숫자로 하면 0~숫자까지
    - 내부 패딩: `contentPadding = *PaddingValues*(bottom=100.*dp*)`
    
    ```kotlin
    LazyRow(
        horizontalArrangement = Arrangement.SpaceBetween,
        modifier = Modifier
            .fillMaxWidth()
            .padding(horizontal = 15.dp)
    ){
        items(4){
            item ->
            fun imageResource(num: Int): Int {
                return when(num){
                    0 -> R.drawable.category_1
                    1 -> R.drawable.category_2
                    2 -> R.drawable.category_3
                    3 -> R.drawable.category_4
                    else -> R.drawable.category_1
                }
            }
    				Image(
    		            painter = painterResource(imageResource(item)),
    		            contentDescription = "",
    		            modifier = Modifier
    		                .size(50.dp)
    		    )
    		}
    }
    ```
    
    ```kotlin
    // item이 하나더라도 item 안에 넣어줘야 에러X
    
    LazyColumn(){
        item {
            AsyncImage(
                model = "https://mmart405.s3.ap-northeast-2.amazonaws.com/${result!!.thumbnail.replace("_thumb", "")}",
                contentDescription = "상품 이미지")
    
            Text(text = result!!.itemName)
    		}
    }
    ```
    
    ```kotlin
    LazyVerticalGrid(GridCells.Fixed(2)) { // 가로 2개씩
    		item(span = { GridItemSpan(2) }){// 2개만큼의 너비}
        items(items!!) { item ->
            Row(
                horizontalArrangement = Arrangement.SpaceBetween,
                modifier = Modifier
                    .fillMaxWidth()
                    .clickable { navController.navigate("item/${item.itemIdx}") }
            ){
                AsyncImage(
                    model = "https://mmart405.s3.ap-northeast-2.amazonaws.com/${item.thumbnail}",
                    contentDescription = "상품 썸네일"
                )
    
                Text(text = item.itemName)
    
                Text(text = "${item.price}원")
            }
        }
    }
    ```
    
    ```kotlin
    // 스크롤 맨 위로 보내기
    val coroutineScope = rememberCoroutineScope()
    val listState = rememberLazyListState()
    
    Box(modifier = Modifier.fillMaxSize()){
    
    	LazyColumn(state=listState, contentPadding=PaddingValues(bottom=100.dp)){
    		items(items){item ->
    
    		}
    	}
    
    	FloatingActionButton(
    	    onClick = {
    	        coroutineScope.launch {
    	            listState.animateScrollToItem(index = 0)
    	        }
    	}) {
    	      Image(
    	          painter = painterResource(R.drawable.top),
    	          contentDescription = "TOP",
    	      )
    	}
    }
    ```
    
- Divider
    
    ```kotlin
    Divider(
        color = Color.Black,
        thickness = 1.dp,
        modifier = Modifier
            .fillMaxWidth()
            .padding(vertical = 8.dp)
    )
    ```
    
- Icon
    - `Icon(Icons.Default.Star, “별점”)`
    - Default, Filled, Outlined, Rounded, Sharp, TwoTone
- 반복: Repeat(횟수){}
- listOf(1..5).forEach{ if(star≥it){}else{} } → IntRange 타입의 범위 객체이므로 비교X, listOf(1,2,3,4,5) 처럼 각각 명시해야 함
- Dialog
    
    ```kotlin
    AlertDialog(
        onDismissRequest = { isDelete = false },
        title = { Text("타이틀") },
        text = { Text("텍스트") },
        // 잎에 나오는 버튼
        dismissButton = {
            Button() {}
    		},
        // 뒤에 나오는 버튼
        confirmButton = {
            Button() {}
        }
    )
    
    // Dialog는 보통 제목, 메시지 및 확인 버튼과 같은 사전 구성된 기능을 제공X
    ```
    
- `Text(text="", overflow = TextOverflow.Ellipsis)`
- ModalBottomSheetLayout
    
    ```kotlin
    @OptIn(ExperimentalMaterialApi::class)
    @Composable
    fun ModalBottomSheetExample(
        modifier: Modifier = Modifier
    ) {
        val coroutineScope = rememberCoroutineScope()
        val sheetState = rememberModalBottomSheetState(ModalBottomSheetValue.Hidden)
    
        // 모달 띄우는 버튼
        Button(onClick = {coroutineScope.launch {sheetState.show()}
        }){
            Text("하이하이")
        }
    
        ModalBottomSheetLayout(
            modifier = modifier,
            sheetState = sheetState,
            sheetContent = {
                // 안에 있는 부분
    						// 감추기
                Button(onClick = {coroutineScope.launch {sheetState.hide()}
                }){
                    Text("바이")
                }
            },
            content = {
                // 밖에 있는 부분
            }
        )
    }
    ```
    
- 모달 열면서 키보드 조절하기
    
    ```kotlin
    // 키보드 조정
    val keyboardController = LocalSoftwareKeyboardController.current
    // 포커스 조정
    val focusRequester = remember { FocusRequester() }
    
    Text(quantity.toString(), modifier = Modifier.clickable {
    		// 모달 열기
        coroutineScope.launch {sheetState.show()}
    		// 열리면서 포커스 조정
        focusRequester.requestFocus()
    })
    
    // 모달 보이냐 안 보이냐에 따라 키보드 조정
    // 처음 로드 시에는 키보드컨트롤러가 없어서 안됨 -> 포커스 조정으로 키보드 열기
    if (sheetState.isVisible) {
        keyboardController?.show()
    } else {
        keyboardController?.hide()
    }
    
    ModalBottomSheetLayout(
        sheetState = sheetState,
        sheetContent = {
            Row() {
                TextField(
                    value = numberInput,
                    onValueChange = { numberInput=it },
                    keyboardOptions = KeyboardOptions(keyboardType = KeyboardType.Number),
                    keyboardActions = KeyboardActions(
                        onDone = {
                            numberCheck()
                        }
                    ),
                    modifier = Modifier
                        // 포커스 (바로 키보드 열기위해)
                        .focusRequester(focusRequester),
                )
                Button(onClick = {
                    numberCheck()
                }) {
                    Text("확인")
                }
            }
    
            // 수량 키보드 입력 확인
    				if(wrongNumber){
                AlertDialog(
                    onDismissRequest = {
                        wrongNumber = false
                        keyboardController?.show()
                    },
                    text = { Text("수량을 확인하여 주십시오") },
                    confirmButton = {
                        Button(onClick = {
                            wrongNumber = false
                            keyboardController?.show()
                        }) {
                            Text("확인")
                        }
                    }
                )
            }
        },
        content = {}
    )
    ```
    
- Ellipsis ↔ 전체보기
    
    ```kotlin
    reviews.forEach { review ->
    		var expanded by remember { mutableStateOf(false) }
    		Text(
    				review.content,
    				modifier = Modifier.clickable { expanded = !expanded },
    				overflow = TextOverflow.Ellipsis,
    				maxLines = if (expanded) Int.MAX_VALUE else 3)
    		)
    }
    ```
    
- startDestination(Main) 따로 두고, 앱 처음 실행 시에 특정 페이지(로그인)로 이동
    
    ```kotlin
    if (savedInstanceState == null) {
        navController.navigate("login"){
            popUpTo(navController.graph.startDestinationId) { inclusive = true }
        }
    }
    ```
    
- 비동기
    
    ```kotlin
    try {
        coroutineScope.launch{
           val resultCode = api.addGetCart(body).resultCode
            if(resultCode == "SUCCESS"){
                goGetCart = true
            }
        }
    } catch (e: Exception){
        println("장볼구니 추가 에러------------------")
        e.printStackTrace()
        println("---------------------------------")
    }
    
    ```
    
    ```kotlin
    try {
        coroutineScope.launch{
           val resultCode = coroutineScope.async { api.addGetCart(body) }.await().resultCode
            if(resultCode == "SUCCESS"){
                goGetCart = true
            }
        }
    } catch (e: Exception){
        println("장볼구니 추가 에러------------------")
        e.printStackTrace()
        println("---------------------------------")
    }
    ```
    
    ```kotlin
    // 비동기 포함 에러를 잡아햐 하므로 예외 처리 블록을 더 넓게 해줘야 함!!
    
    coroutineScope.launch{
        try {
           val resultCode = api.addGetCart(body).resultCode
            if(resultCode == "SUCCESS"){
                goGetCart = true
            }
        } catch (e: Exception){
            println("장볼구니 추가 에러------------------")
            e.printStackTrace()
            println("---------------------------------")
            }
    }
    ```
    
- 바코드 스캔 (**[Zxing](https://stackoverflow.com/questions/68139363/using-zxing-library-with-jetpack-compose)**)
    
    ```kotlin
    // 바코드
    implementation('com.journeyapps:zxing-android-embedded:4.1.0') { transitive = false }
    implementation 'com.google.zxing:core:3.5.1'
    ```
    
    ```xml
    <!-- AndroidManifest.xml 카메라 권한-->
    
    <uses-permission android:name="android.permission.CAMERA"/>
    ```
    
    ```kotlin
    @Composable
    fun BarcodeScan(navController: NavHostController) {
        val context = LocalContext.current
        var scanFlag by remember {
            mutableStateOf(false)
        }
    
        val compoundBarcodeView = remember {
            CompoundBarcodeView(context).apply {
                val capture = CaptureManager(context as Activity, this)
                capture.initializeFromIntent(context.intent, null)
                this.setStatusText("")
                this.resume()
                capture.decode()
                this.decodeContinuous { result ->
                    if(scanFlag){
                        return@decodeContinuous
                    }
                    scanFlag = true
                    result.text?.let { barCodeOrQr->
                        println("$barCodeOrQr //////////////////////////////////////")
                        //Do something and when you finish this something
                        //put scanFlag = false to scan another item
    										// 다시 스캔을 시작하게 하려면
                        scanFlag = false
                    }
                    //If you don't put this scanFlag = false, it will never work again.
                    //you can put a delay over 2 seconds and then scanFlag = false to prevent multiple scanning
    
                }
            }
        }
    
    		// 화면이 켜져있을 때만 인식하게 함(안 하면 계속 인식)
    		DisposableEffect(key1 = "someKey" ){
            compoundBarcodeView.resume()
            onDispose {
                compoundBarcodeView.pause()
            }
        }
    
        Column(
            modifier = Modifier.fillMaxSize()
        ) {
            AndroidView(
                modifier = Modifier,
                factory = { compoundBarcodeView },
            )
        }
    }
    ```
    
    [https://stackoverflow.com/questions/68139363/using-zxing-library-with-jetpack-compose](https://stackoverflow.com/questions/68139363/using-zxing-library-with-jetpack-compose)
    
- "2023-05-16T14:40:45.399994”.substringBefore("T") → 2023-05-16
- DropdownMenu / sortedBy
    
    ```kotlin
    var sort: String by remember { mutableStateOf("추천순") }
    var expanded: Boolean by remember { mutableStateOf(false) }
    
    // 아이템 리스트
    val itemList =
        when(sort){
            "추천순" -> items
            "낮은 가격순" -> items.sortedBy { it.couponPrice }
            "높은 가격순" -> items.sortedByDescending { it.couponPrice }
            else -> items
        }
    
    Box(modifier = Modifier
        .fillMaxWidth()
        .wrapContentSize(Alignment.TopEnd)
        .padding(20.dp, 10.dp, 20.dp, 0.dp)){
        Row(verticalAlignment = Alignment.CenterVertically, modifier = Modifier.clickable { expanded = true }){
            Text(sort)
            Icon(imageVector = Icons.Default.Menu, contentDescription = "정렬", modifier = Modifier.padding(start=10.dp))
        }
        DropdownMenu(expanded = expanded, onDismissRequest = { expanded = false }) {
            listOf("추천순", "낮은 가격순", "높은 가격순").forEach {
                DropdownMenuItem(
                    onClick = {
                        sort = it
                        expanded = false
                    }
                ) {
                    Text(it)
                }
            }
        }
    }
    ```
    
- 인자 전달
    
    ```kotlin
    @Composable
    fun Category(navController: NavController, categoryIdx: Int){
    	var isLoading: Boolean by remember { mutableStateOf(true) }
    	val items = 리스트
    
    	items(navController, items) {isLoading = it}
    
    	if(isLoading){
            loadingView()
      }
    }
    
    @Composable
    fun items(navController:NavController, items: List<ItemInfo>, loading: (Boolean) -> Unit){
    	
    	items.forEach{item->
    		AsyncImage(
    	    model = "https://mmart405.s3.ap-northeast-2.amazonaws.com/${item.thumbnail.replace("_thumb", "")}",
    	    contentDescription = "상품 썸네일",
    	    onSuccess = { loading(false) }
    		)
    	}
    }
    ```
    
- 배경화면
    
    ```xml
    <!-- themes.xml (원래 회색이었는데 수정됨) -->
    
    <?xml version="1.0" encoding="utf-8"?>
    <resources>
        <style name="Theme.MmARt" parent="android:Theme.Material.Light.NoActionBar">
            <item name="android:windowBackground">@android:color/white</item>
            <item name="android:statusBarColor">@color/black</item>
        </style>
    </resources>
    ```
    
- 런처 아이콘 변경
    - File > New > ImageAsset을 통해 생성
    - AndroidManifest.xml 에서 icon 수정
- 뒤로가기 2번 눌렀을 때 종료
    
    ```kotlin
    // 뒤로 가기 두 번 눌렀을 때 앱 종료
    @Composable
    fun BackOnPressed() {
        val context = LocalContext.current
        var backPressedTime = 0L
    
        BackHandler() {
            if(System.currentTimeMillis() - backPressedTime >= 1500L) {
                backPressedTime = System.currentTimeMillis()
                Toast.makeText(context, "한 번 더 누르시면 앱이 종료됩니다.", Toast.LENGTH_SHORT).show()
            } else {
                // 앱 종료
                (context as Activity).finish()
            }
        }
    }
    
    @Composable
    fun Main(navController: NavController) {
    		BackOnPressed()
        Scaffold(///)
    }
    ```