# swift_study
//: Playground - noun: a place where people can play

import UIKit

//## Question
//- 두 개의 정수를 입력받아 두 수를 하나로 합친 결과를 출력하는 함수 (1, 5 입력 시 15 반환)
func getAdd(_ num: Int , _ num2: Int) -> String{
    let result: String = String(num) + String(num2)
    return result
}
//print(getAdd(1, 5))

//- 문자열 두 개를 입력받아 두 문자열이 같은지 여부를 판단해주는 함수
func getString(str: String ,str2: String) -> Bool{
    return str == str2 ? true : false
}
//getString(str: "a", str2: "a")

//- 학점을 입력받아 각각의 등급을 반환해주는 함수 (4.5 = A+,  4.0 = A, 3.5 = B+ ...)
func getLevel(_ num: Double){

    switch(num){
    case  4.5 : print("A+")
    case  4.0 : print("A")
    case  3.5 : print("b+")
    case  3.0 : print("b")
    case  2.5 : print("c+")
    case  2.0 : print("c")
    default :
        print("false")
    }
}
//getLevel(4.0)
//- 여러 등급을 입력받아 그 학점의 평균을 반환해주는 함수
func getAvg(_ points: Double...)->Double{
    var sum: Double = 0.0
    for point in points{
        sum += point
    }
    return sum/Double(points.count)
}
//print(getAvg(3.0,4.0,2.0))

//- 윤년 구하기 (2월 29일이 있는 해.  매 4년 마다 윤년. 매 100년 째에는 윤년이 아님. 매 400년 째에는 윤년)
func getYear(num year:Int){
    if ((year % 4 == 0 && year % 100 != 0) || year % 400 == 0 ){
        print("윤년입니다")
    }else{
        print("윤년이 아닙니다")
    }
}
//getYear(num: 2002)
//- 세 수를 입력받아 세 수의 곱이 양수이면 true , 음수이면 false 반환하는 함수
func mulFn(_ num:Int , _ num2:Int , _ num3:Int)->Bool{
    var sum = 0
    sum = num * num2 * num3
    return sum > 0 ? true : false
}
//mulFn(1,2,1)

//- 특정한 달을 숫자로 입력 받아 문자로 반환해주는 함수 (1 = "Jan" , 2 = "Feb")
func Calender(_ num: Int) -> String{
    let calList = [1:"jan", 2:"feb",3:"mar",4:"apr",5:"may",6:"june",7:"july",8:"aug",9:"sep",10:"oct",11:"nov",12:"dec"]

    guard num > 0 , num < 13 else {return "잘못된 값 입니다"}

    return (calList[num]!)
}
//print(Calender(8))

/*********************************/
//1. 1~9 사이의 숫자를 입력받아 해당 숫자에 해당하는 구구단 함수
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

//for , while , repeat - while 등을 활용하여 아래 문제들을 구현해보세요.
//- 정수 하나를 입력받아 그 수의 Factorial 을 구하는 함수

func factorial(_ n: Int) -> Int {
    guard n > 0 else {return 1}
    return n * factorial(n-1)
}
//print(factorial(3))

//- 정수 두개를 입력받아 첫 번째 수를 두 번째 수의 횟수만큼 곱한 값을 반환하는 함수
func repeatFn(num: Int ,num2: Int) -> Int{
    var sum = 0
    for _ in 0...num2 {
        sum = num * num2
    }
    return sum
}
//print(repeatFn(num: 2,num2:2))

//- 정수 하나를 입력받아 각 자리수 숫자들의 합을 반환해주는 함수
func addFn(_ num: Int) -> Int{
    var addTemp: Int = num
    var result: Int = 0

    while addTemp > 0 {
        result += addTemp % 10
        addTemp = addTemp / 10
    }
    return result

}

//print(addFn(123))

//- 100 이하의 자연수 중 3과 5의 공배수를 모두 출력하는 함수
func 공배수(){
    for n in 1..<100 {
        //3 || 5£
        if n % 3 == 0  , n % 5 == 0{
            print(n)
        }
    }
}

//공배수()
//- 정수 하나를 입력받아 그 정수의 약수를 모두 출력하는 함수



//- 2 이상의 정수를 입력받아, 소수인지 아닌지를 판별하는 함수
//- 정수를 입력받아 입력받은 수에 해당하는 자리의 피보나치 숫자를 반환하는 함수
