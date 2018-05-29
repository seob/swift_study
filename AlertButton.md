<pre>
//  ViewController.swift
//  AlertButton
//
//  Created by seob on 2018. 5. 29..
//  Copyright © 2018년 seob. All rights reserved.
//

import UIKit

class ViewController: UIViewController {
    
    func setFrame(_ x: Int , _ y: Int , _ width: Int ,_ height: Int) -> CGRect {
        return CGRect(x: x , y: y, width: width, height: height)
    }
    
    var totalCount = 0 {
        didSet {
            label1.text = "\(totalCount)"
        }
    }
    
        //add count func
    func addCount(){
        self.totalCount += 1
        label1.text ="\(totalCount)"
    }
    //reset func
    func resetFunc(){
        self.totalCount = 0
        label1.text ="\(totalCount)"
        
    }
    
    let label1 = UILabel(frame: CGRect(x: 150, y: 100, width: 100, height: 100))
    
    override func viewDidLoad() {
        super.viewDidLoad()
        view.backgroundColor = .white
        
        
        label1.text = "\(totalCount)"
       
        // 아이콘을 사용할 경우
        //        let clickButton = UIButton(type: .contactAdd)
        //        clickButton.frame = setFrame(100, 200, 100, 100)
        
        let clickButton = UIButton(frame: setFrame(100, 200, 100, 100)) // 버튼생성하고 위치지정
        clickButton.setTitle("click", for: .normal) //버튼에 들어갈 텍스트 ,for : 버튼 이벤트  기본으로 .normal
        clickButton.setTitleColor(.black, for: .normal) // 텍스트의 색상 ,   for : 버튼 이벤트  기본으로 .normal
        clickButton.addTarget(self, action: #selector(showAlert(_:)), for: .touchUpInside)
        //(선택자 , 버튼을 눌렀을때의 함수호출 , for:버튼 이벤트
        
        view.addSubview(label1)
        view.addSubview(clickButton) // view화면 노출
    }
    
    
    @objc func showAlert(_ button: UIButton){
        
        let alertController = UIAlertController(title: "Count", message: nil, preferredStyle: .alert)
       
        
        let okAction = UIAlertAction(title: "Add Count", style: .default) { _ in
            self.totalCount += 1
        }
        
        let cancelAction = UIAlertAction(title: "Cancel", style: .cancel)
        
        let resetAction = UIAlertAction(title: "Reset", style: .destructive) { _ in
            self.totalCount = 0
        }
        
        let actions = [okAction , cancelAction ,  resetAction]
        
        for action in actions {
            alertController.addAction(action)
        }
        
        present(alertController, animated: true)
    }
    
}
</pre>
