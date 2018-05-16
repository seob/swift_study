# 2018.05.15 실습문제


1.두 개의 정수를 입력받아 두 수를 하나로 합친 결과를 출력하는 함수 (1, 5 입력 시 15 반환
<pre>
    func getAdd(_ num: Int , _ num2: Int) -> String{
        let result: String = String(num) + String(num2)
        return result
    }
    print(getAdd(1, 5))
</pre>
2.문자열 두 개를 입력받아 두 문자열이 같은지 여부를 판단해주는 함수
<pre>
      func getString(str: String ,str2: String) -> Bool{
        return str == str2 ? true : false
    }
    getString(str: "a", str2: "a")
</pre>
3.여러 등급을 입력받아 그 학점의 평균을 반환해주는 함수
<pre>
    func getAvg(_ points: Double...)->Double{
        var sum: Double = 0.0
        for point in points{
            sum += point
        }
        return sum/Double(points.count)
    }
    print(getAvg(3.0,4.0,2.0))
</pre>
4. 윤년 구하기 (2월 29일이 있는 해.  매 4년 마다 윤년. 매 100년 째에는 윤년이 아님. 매 400년 째에는 윤년)
<pre>
func getYear(num year:Int){
    if ((year % 4 == 0 && year % 100 != 0) || year % 400 == 0 ){
        print("윤년입니다")
    }else{
        print("윤년이 아닙니다")
    }
}
getYear(num: 2018)
</pre>
5.세 수를 입력받아 세 수의 곱이 양수이면 true , 음수이면 false 반환하는 함수
<pre>
func mulFn(_ num:Int , _ num2:Int , _ num3:Int)->Bool{
    var sum = 0
    sum = num * num2 * num3
    return sum > 0 ? true : false
}
mulFn(1,2,1)
</pre>

6.특정한 달을 숫자로 입력 받아 문자로 반환해주는 함수 (1 = "Jan" , 2 = "Feb")
<pre>
func Calender(_ num: Int) -> String{
    let calList = [1:"jan", 2:"feb",3:"mar",4:"apr",5:"may",6:"june",7:"july",8:"aug",9:"sep",10:"oct",11:"nov",12:"dec"]

    guard num > 0 , num < 13 else {return "잘못된 값 입니다"}

    return (calList[num]!)
}
print(Calender(8))
</pre>
<hr />
 7. 1~9 사이의 숫자를 입력받아 해당 숫자에 해당하는 구구단 함수
<pre>

func 구구단(_ num : Int){
    for k in 1...9 {
        print("\(num) * \(k) = \(num * k)")
    }
//    var k: Int = 1
//    while k < 10 {
//       print("\(num) * \(k) = \(num * k)")
//        k += 1
//    }
}

구구단(3)
</pre>
