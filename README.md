# YOLOPY
Pytorch2YOLO  
requirements.txt中包含需求库  
PTH下载:https://pan.dvrz.cn/s/JjHd    
VOC数据集:https://pan.dvrz.cn/s/Qvcz  
# 数据集的准备  
使用VOC格式进行训练，训练前需要下载好VOC07+12的数据集，解压后放在根目录  

# 数据集的处理  
修改voc_annotation.py里面的annotation_mode=2，运行voc_annotation.py生成根目录下的2007_train.txt和2007_val.txt  

# 开始网络训练  
train.py的默认参数用于训练VOC数据集，直接运行train.py即可开始训练  

# 训练结果预测  
训练结果预测需要用到两个文件，分别是yolo.py和predict.py。我们首先需要去yolo.py里面修改model_path以及classes_path，这两个参数必须要修改  
model_path指向训练好的权值文件，在logs文件夹里  
classes_path指向检测类别所对应的txt  
完成修改后就可以运行predict.py进行检测了。运行后输入图片路径即可检测  
# 预训练权重使用
PTH下载:https://pan.baidu.com/s/19PLgp85HpOP6B-7jq2m2sw?pwd=pthz  
下载完库后解压，在网盘下载yolo_weights.pth，放入model_data，运行predict.py，输入`img/street.jpg`
# 评估VOC07+12的测试集
使用VOC格式进行评估。VOC07+12已经划分好了测试集，无需利用voc_annotation.py生成ImageSets文件夹下的txt  
在yolo.py里面修改model_path以及classes_path。model_path指向训练好的权值文件，在logs文件夹里。classes_path指向检测类别所对应的txt  
运行get_map.py即可获得评估结果，评估结果会保存在map_out文件夹中  
# Reference
https://github.com/qqwweee/pytorch-yolo3
https://github.com/eriklindernoren/PyTorch-YOLOv3
https://github.com/BobLiu20/YOLOv3_PyTorch
https://github.com/bubbliiiing/yolo3-pytorch
本文使用自训练数据
