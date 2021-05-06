## 文件说明

- code : 存放所有相关代码的文件夹
    - train_data : 存放原始数据文件 guangdong1_round2_train2_20191004_Annotations  guangdong1_round2_train2_20191004_images
    - tcdata: 存放官方测试数据文件，docker 提交后会自动生成
    - data :训练数据路径设置 coco128.yaml中设置训练数据路径
    - models ： 网络相关的代码文件夹
    - weights ： 保存训练模型的文件夹，best.pt last.pt
    - convertTrainLabel.py：将官方的数据集转换成yolo数据的格式 运行生成convertor数据文件夹
    - process_data_yolo.py：滑动窗口处理convertor数据文件夹里面数据，将大图变成1024*1024小图，生成数据文件夹process_data
    - train.py :  训练代码， 运行该函数进行模型的训练，可以得到模型
    - detect.py : 预测代码
    - test.py :测试模型代码
    - run.sh : 预测测试集，生成结果的脚本   sh run.sh
    - train.sh : 训练脚本  sh trian.sh 

    


## 操作说明
- step1 : 将官方训练数据集解压后放入train_data 文件夹
- step2 : 训练运行  sh train.sh  
    - train.sh 有四步
        -python convertTrainLabel.py
        -python process_data_yolo.py
        -rm -rf ./convertor
        -python train.py
- step3 : 生成结果 sh run.sh

## 思路说明

-本方案采用了yolov5作为baseline
-数据处理：滑动窗口分割训练图片

