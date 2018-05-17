# 2018.05.17 수업

1. 새로운 변수를 만들거나 새값을 넣지 않고 enum 의 값을 변경하려면 어떻게 해야할까요 ?
<pre>
enum RemoteControl{
    case on,off
    mutating func next(){
        //code
        switch self{
        case .on :
            self = .off
        case .off :
            self = .on
        }
    }
}


var remoteControl = RemoteControl.on
remoteControl.next()
remoteControl.next()
</pre>
<pre>
func test(n: Int) -> Int {
    guard n > 1 else {
        return n
    }
    return n * (test(n: n-1))
}

func fibona(_ n: Int) -> Int{
    guard n > 2 else {return n-1}
    var num1 = 0 , num2 = 1

    for i in 1 ..< n{
        switch i % 2{
        case 0 :
            num1 = num1 + num2

        default:
            num2 = num1 + num2
        }
    }
    return num1 > num2 ? num1 : num2
}
print(fibona(5))

func fibona2(_ n: Int){
    var num1 = 0 , num2 = 0, num3 = 1

    for _ in 1...n{
        num1 = num2 + num3
        num2 = num3
        num3 = num1
        print (num2)
    }
}

//fibona2(5)


func fibona3(_ n: Int) -> Int{
    guard n > 2 else { return n-1 }
     return (fibona3(n-1)) + (fibona3(n-2))
}
print(fibona3(5))
</pre>

2.searching
<pre>
func arrFn(str: String){
    let alphabet = ["A","B","C","D"]

    if let aa = alphabet.index(of: str){
        print ("\(aa)")
    }
}
arrFn(str: "A")
</pre>
<pre>
func arrRemove(str: String){
    var alphabet = ["A","B","C","D"]

    if let idx = alphabet.index(of: str){
        let removed = [alphabet.remove(at: idx)]
        print(alphabet)
    }
}
arrRemove(str: "C")
</pre>

* 배열끼리는 + 해도 별도의 함수를 사용하지 않아도 추가된다.

 - startindex = zero_index 때문에 0 부터 시작
 - endindex = 배열의 크기만큼 값을 가지고 있기에 -1 를 해줘야된다.
 - .append = 배열뒤에 추가
 - .insert = 내가 원하는 위치에 추가
