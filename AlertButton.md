//
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
    
    let label1 = UILabel(frame: CGRect(x: 150, y: 100, width: 100, height: 100))
    
    override func viewDidLoad() {
        super.viewDidLoad()
        view.backgroundColor = .white
        
        
        label1.text = "\(totalCount)"
        
        //ibdesignable
        //ibinspectable
        
        let clickButton = UIButton(frame: setFrame(100, 200, 100, 100))
//        let clickButton = UIButton(type: .contactAdd)
//        clickButton.frame = setFrame(100, 200, 100, 100)
        clickButton.setTitle("click", for: .normal)
        clickButton.setTitleColor(.black, for: .normal)
        clickButton.addTarget(self, action: #selector(showAlert(_:)), for: .touchUpInside)
        
        clickButton.setTitle("click", for: .selected)
        clickButton.setTitleColor(.red, for: .selected)
        
        clickButton.isSelected = false
        view.addSubview(label1)
        view.addSubview(clickButton)
    }
    
   
    @objc func showAlert(_ button: UIButton){
        button.isSelected = !button.isSelected
        
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

