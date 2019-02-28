# 仿 QQ tabbar 拖动动画


效果如下

![image](https://github.com/SherlockQi/HKNote/blob/master/HKTabBar_QQ.gif)

```swift
class HKTabBarViewController: UITabBarController {

override func viewDidLoad() {
    super.viewDidLoad()
    ...
    viewControllers = [vc0, vc1, vc2]

    /**
     * imageName 图片名称
     * title 文字
     * distance 最大的便宜距离
     * mini_x_Coef 小图x偏移系数
     * mini_y_Coef 小图y偏移系数
     */
    let item = HKTabBarModel(imageName: "recent", title: "消息", distance: 10, mini_x_Coef: 0.2, mini_y_Coef: 0.4)
    let item1 = HKTabBarModel(imageName: "buddy", title: "联系人")
    let item2 = HKTabBarModel(imageName: "qworld", title: "动态", distance: 10, mini_x_Coef: -0.2, mini_y_Coef: 0.2)

    // let tabbar = HKTabBar(items: [item, item1, item2])
    // tabbar.hk_delegate = self

    let tabbar = HKTabBar(items: [item, item1, item2]) { (btn, index) in
        print(btn?.title ?? "title")
        self.selectedIndex = index
    }

        self.setValue(tabbar, forKey: "tabBar")
    }
}

//extension HKTabBarViewController: HKTabBarDelegate {
//    func hk_tabBar(_ tabBar: HKTabBar, didSelect item: HKDragButton, index: Int) {
//         self.selectedIndex = index
//    }
//}
```



每个barItem 需要如下4张图片
命名规则如下

![image](https://github.com/SherlockQi/HKTabBar_QQ/blob/master/Resource/image.png)

![image](https://github.com/SherlockQi/HKTabBar_QQ/blob/master/Resource/image2.png)



