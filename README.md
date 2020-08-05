########
训练模型阶段：
1 uncased_L-12_H-768_A-12文件夹为预训练模型文件，此处为英文训练模型
2 data文件夹中train文件夹中的数据用于模型训练集、valid文件夹用于验证集
3 model文件存放的是训练好的h5文件
步骤：
将训练数据路径在load_data中定义好
运行model_train，生成h5模型文件
-----
代码需要变动的地方：
load_data的：f=open("data/train/train_20000.csv", 'r',encoding="UTF-8")，训练数据路径
model_train：model.save('model/question_sentence_classify_20000.h5')，保存模型文件名称
##########
预测阶段
根据上阶段生成的h5模型文件，进行预测
输入需要验证的txt文件（documents文件夹里），输出判定为正例的概率csv文件（output文件夹里）
----
代码需要变动的地方：模型文件名
load_model = load_model("model/question_sentence_classify_20000.h5")
运行过程中需要手动输入文件名
