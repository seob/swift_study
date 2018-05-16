# 2018.05.16 실습문제

- 정수 하나를 입력받아 그 수의 Factorial 을 구하는 함수
<pre>
func factorial(_ n: Int) -> Int {
    guard n > 0 else {return 1}
    return n * factorial(n-1)
}
print(factorial(3))
</pre>

- 정수 두개를 입력받아 첫 번째 수를 두 번째 수의 횟수만큼 곱한 값을 반환하는 함수
<pre>
func repeatFn(num: Int ,num2: Int) -> Int{
    var sum = 0
    for _ in 0...num2 {
        sum = num * num2
    }
    return sum
}
print(repeatFn(num: 2,num2:2))
</pre>



- 정수 하나를 입력받아 각 자리수 숫자들의 합을 반환해주는 함수
<pre>
func addFn(_ num: Int) -> Int{
    var addTemp: Int = num
    var result: Int = 0

    while addTemp > 0 {
        result += addTemp % 10
        addTemp = addTemp / 10
    }
    return result

}

print(addFn(123))
</pre>

- 100 이하의 자연수 중 3과 5의 공배수를 모두 출력하는 함수
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
func diviseur(_ n: Int){
    for index in 1...n {
        if n%index == 0 {
            print(index)
        }
    }
}
//diviseur(10)


//- 2 이상의 정수를 입력받아, 소수인지 아닌지를 판별하는 함수
<pre>
func premier(_ n: Int) -> Bool{

    for i in 2...(n/2){
        if n%i == 0 {
            return false
        }
    }
    return true
}
print(premier(11))
</pre>
- 정수를 입력받아 입력받은 수에 해당하는 자리의 피보나치 숫자를 반환하는 함수
  - 재귀함수를 이용한 최종 합만 보여주는 예wp
<pre>
func fibona(_ n: Int) -> Int{
    if n  < 2 {
        return 0
    }else{
        //       return "\(fn(n-1)) \(fn(n-2))"
        return (fibona(n-1) + fibona(n-2))
    }

}
print(fibona(10))
</pre>
 - 피보나치 숫자 나열
<pre>

func fibona(_ n: Int){
    var result: Int = 0
    var mid: Int = 0
    var lastVal: Int = 1

    for _ in 1...n{
        mid = result + lastVal
        result = lastVal
        lastVal = mid

        print(result)
    }
}
fibona(10)
</pre>
