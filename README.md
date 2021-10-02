# auto-clock-in
用于学校的疫情打卡，用的是playwright库，原理是模拟浏览器去访问网页，模拟点击。可以直接在github action运行。

playwright是一个类似于selenium的浏览器自动化的库，好处就是有一个可以录制脚本的功能，而且不用自己去下载驱动器、浏览器。
## 用法
只需要fork到自己的仓库，在设置——密钥那里添加账号、密码、名字、收件邮箱，变量名分别为username、password、name、email，然后在action那里选择立刻运行就可以自动打卡。
![image](https://user-images.githubusercontent.com/70441023/135620580-e7caeff0-8c5d-46df-9d0b-fb5d2ddc029e.png)
![image](https://user-images.githubusercontent.com/70441023/135620745-8c1d2d4a-efec-4603-b37e-91ed693bfc0e.png)

## 原理
action工作流会在每个小时的30分钟的时候运行一次，但是python程序会检测时间跟打卡状态，只有在0点和13点或者上次打卡失败才会运行打卡程序。
使用模拟浏览器的好处就是屏蔽底层繁琐的交互，playwright库还可以模拟时区、地区还有伪造地理位置（程序里的定位是在我学校）。
