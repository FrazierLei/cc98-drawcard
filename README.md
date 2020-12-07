# cc98-drawcard
需要在**浙江大学内网**环境下使用。



## draw_card_v2

使用selenium获取抽卡中心的cookie，需要确保chromedriver在系统环境变量中。



## draw_card_v3

用requests完成全部登录、授权。



## draw_card_v4

增加抽卡情况总览和欧皇指数，需要pip安装`prettytable`和`pyecharts`

<img src="./images/overview.png" alt="overview" width=600px />

<img src="./images/gauge.png" alt="gauge" width=600px />


## 查看抽到的SSR和M卡

可以添加下面的代码来查看抽到的SSR和M卡，需要pip安装`scikit-image`。

```python
from skimage import io

SSR_M = SSR_cards + M_cards
if SSR_M:
    for i in SSR_M:
        img_src = i.find_all('img')[1]['src']
        image = io.imread('https://card.cc98.org'+img_src)
        io.imshow(image)
        io.show()
```
