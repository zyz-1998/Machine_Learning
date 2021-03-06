## keras_手写数字识别

### 数据来源：  
链接：https://pan.baidu.com/s/1mlhAS_oH6ttDS09N7fkFIg   
提取码：7yly 

### 文件说明  
* data.py  
  * 将文件处理成data:（42000，1，28，28）和label:（42000，1）  
* cnn.py
  * [参考链接：TensorFlow Keras 官方教程](https://www.jianshu.com/p/d02980fd7b54)
  * 训练集：0：30000； 测试集：30000：42000
    * 由于有shuffle数据的存在，每次训练会产生一定的误差  
  * 模型网络  
  ![plot_model](https://github.com/FangChao1086/Machine_learning/blob/master/B、深度学习/深度学习实例/keras_手写数字识别/model.png)  
* cnn_svm.py
  * **使用cnn提取特征，svm训练**；目前效果比SVM不佳，是个问题，待解决
    ```python
    import keras
     
    # 提取特征
    get_feature = keras.backend.function([origin_model.layers[0].input], [origin_model.layers[6].output])
    feature = get_feature([data])[0]
    ```
* get_feature_layer.py
  * layer1，可视化每个不同kernel输出的图片特征
  ![layer1](https://github.com/FangChao1086/Machine_learning/blob/master/B、深度学习/深度学习实例/keras_手写数字识别/layer1.png)  
  * layer_last，最后一层  
  ![layer_last](https://github.com/FangChao1086/Machine_learning/blob/master/B、深度学习/深度学习实例/keras_手写数字识别/layer_last.png)
