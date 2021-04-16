# Python语法

### json格式转换

- loads：string转换为dict
- dumps：dict转换为string
- load：json格式字符串转换为dict（读取文件）
- dump：dict转换为json格式字符串（存入文件）



遍历每个case

​	遍历case中context的每个段落（只有一段）

​		遍历段落中的每个句子

​			遍历句子中的每个字符——将每个单词存入doc_tokens，将

​			

### argparse模块

> Python 内置的一个用于命令项选项与参数解析的模块，通过在程序中定义好我们需要的参数，argparse 将会从 sys.argv 中解析出这些参数，并自动生成帮助和使用信息。当然，Python 也有第三方的库可用于命令行解析，而且功能也更加强大，比如 `docopt`，`Click`。

- python命令行参数（sys.argv）

  - 写一些脚本处理任务时候往往需要提供一些命令行参数，在Python里，命令行的参数和C语言很类似（因为标准Python是用C语言实现的）。在C语言里，main函数的原型为int main(int argc, char ** argv)，这里主要指linux平台， argc指的是命令行传入的参数个数（程序的name为第一个参数），而argv则是一个指针数组，每一个元素为指向一个命令行参数的指针。**在Python里的命令行参数是存储在sys.argv里，argv是一个列表，第一个元素也为程序名称**。
- 使用步骤：
  - import argparse 首先导入模块
  - parser = argparse.ArgumentParser（） 创建一个解析对象
  - parser.add_argument() 向该对象中添加你要关注的命令行参数和选项
  - args = parser.parse_args() 进行解析
  - 在需要时使用args.XXX



### 关于str的一些函数用法

1. `str.find(str, beg=0, end=len(string))`

   Python find() 方法检测字符串中是否包含子字符串 str ，如果指定 beg（开始） 和 end（结束） 范围，则检查是否包含在指定范围内，如果包含子字符串返回开始的索引值，否则返回-1。

2. `str.join(sequence)`

   用于将序列中的元素以指定的字符连接生成一个新的字符串



### 关于list的一些函数用法

1. `list.append(obj)`向列表中添加一个**对象**obj
2. `list.extend(sequence)`把一个**序列**seq的内容添加到列表中



# NLP模型实现

### transfromers包

> 官方文档<https://pypi.org/project/transformers/>

1. 特点

   提供了对成千上万的预训练模型可用于多种NLP任务，提供了APIs来快速下载并使用这些在给定文本上的预训练模型，可以将它们在自己的数据集上进行微调；

   每个python module可以被独立使用和调整；

   支持两种最流行的深度学习框架：PyTorch和TensorFlow，并且可以无缝集成

2. 1

# 深度学习知识整理

### 卷积网络

> 花书C9                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     



# NLP理论学习

### 机器翻译

统计机器翻译需要学习两个模型：

1）翻译模型——从平行语料中学习如何翻译单词/短语

2）语言模型——从单语语料中学习如何生成流畅语言

神经机器翻译则没有以上两个模型，而是使用神经网络进行**端到端**的文本翻译

#### Seq2Seq模型



### 预训练语言模型

两种：

1. 基于特征的方法

> eg. word2vec，预训练模型的输出作为下游任务模型的输入

2. 基于微调的方法

> eg. BERT，语言模型本身也是下游任务模型的一部分，参数随着训练一起更新



#### 基于特征的方法

1. word2vec——缺：每个词只对应一个固定的、上下文无关的词向量

2. context2vec——词向量只和当前的上下文有关，但是忽略了词本身

   使用单层的Bi-LSTM对上下文信息进行编码，而不是简单的使用上下文词向量的平均

3. ELMo——上下文相关，网络深，字符级别输入（解决OOV）

   将每一层的隐状态结合在一起作为结合上下文的词向量



#### 基于微调的方法

> RNN存在梯度消失和梯度爆炸问题使其难以训练——两种无监督训练方法来改进：
>
> 1. 传统的语言模型
> 2. **序列自编码器（sequence autoencoder）**



ans_start_position

ans_end_position

para_start_end_position



