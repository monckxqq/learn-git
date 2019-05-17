# Crowd Count

改动自人流密度算法[crowdcount-cascaded-mtl](https://github.com/svishwa/crowdcount-cascaded-mtl)

原项目将label dot作为gound truth，但人工标注样本仅支持label box。

因此使用label box计算出中心点作为label dot，然后生成gound truth文件。

### 主要工作

1. 实现python版本生成gound truth程序（原项目为matlab版本）
2. 在python程序中加上label box转label dot逻辑



### 生成GT文件

```sh
cd ROOT/own_data_preparation
python create_gt_train_set_shtech.py
```



### 测试结果

基于原项目训练出的模型，在人工标注的5张图片上做微调训练，约100 epoch，lr=0.0000001；

再利用人工标注的5张图片作为测试集进行测试：

|      | MAE  | MSE  |
| ---- | ---- | ---- |
| A    | 2.24 | 3.18 |






