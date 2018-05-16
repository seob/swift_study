# 2018.05.16 실습문제

<h2>2018.05.15 실습문제</h2>

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
