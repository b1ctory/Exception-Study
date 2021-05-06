### User Defaults

UserDefaults를 사용하면 앱의 어느 곳에서나 데이터를 쉽게 읽고 저장할 수 있게된다.

클래스는 float, double, integer 및 boolean과 같은 공통 유형에 액세스하기위한 메소드를 제공할 뿐만아니라, NSData, NSString, NSNumber, NSDate, NSArray 또는 NSDictionary 유형의 객체를 저장할 수도 있다.  (다른 객체 유형의 경우 NSKeyedArchiver를 사용하여 데이터를 저장하고 검색해야합니다.)

UserDefaults는 **사용자 기본 설정과 같은 단일 데이터 값에 적합**합니다.

**대량의 유사한 데이터 (테이블에 대한 레코드, 여러 사용자에 대한 데이터 등)를 저장해야하는 경우에는 sqlite 데이터베이스가 더 적합하다.**

또한, **UserDefaults는 [데이터, 키(key)]으로 데이터를 저장한**다. 이때 key의 값은 String. 즉, 문자열입니다.