# 华佗AI

## 《支持中医，永远传承古老文化》 ##

> 本存储库包含一个针对中药的人工智能图像分类系统。该项目的目标是通过输入图像准确识别和分类各种中草药和成分。

### 个人授权许可证
```markdown
版权所有 2023至2050

特此授予任何获得华佗AI应用程序（以下简称“软件”）副本的人免费许可，可根据以下条件使用软件：

- 使用者被允许复制、修改、合并、出版发行、散布、再授权和/或销售本软件的副本。
- 在使用、复制、修改和分发软件的副本时，使用者必须在显著位置保留原始许可声明，包括对华佗AI应用程序的适当署名，
  并特别标明原作者的姓名为钟智强。
- 在使用者派生的作品中，如果使用了本软件的代码或借鉴了本软件的思想，使用者必须在相关代码、文档或其他材料中明确
  指出华佗AI应用程序及其对应的贡献，并提供华佗AI应用程序原作者钟智强的适当署名。
- 使用者不得将华佗AI应用程序标记为自己的作品，或以任何方式暗示华佗AI应用程序对派生作品的认可或支持。
- 如果使用者希望在本软件的基础上进行盈利或生产产品，必须获得原作者钟智强的书面许可。
- 华佗AI应用程序提供的是按"原样"提供的，不提供任何明示或暗示的担保或条件，包括但不限于对适销性、特定用途适用性
  和非侵权性的担保或条件。在任何情况下，华佗AI应用程序的作者或版权持有人均不承担因使用或无法使用本软件所引起的
  任何索赔、损害或其他责任。
- 华佗AI应用程序的作者或版权持有人不对因使用、复制、修改、合并、出版发行、散布、再授权和/或销售本软件而产生的
  任何索赔、损害或其他责任承担责任，无论是合同责任、侵权行为或其他原因，即使事先已被告知发生此类损害的可能性。 
  
  以上许可条款和限制适用于使用华佗AI应用程序的全部或部分功能。使用华佗AI应用程序即表示接受本许可证的条款和条件。
```

### 功能特点
- **图像分类**：该项目的核心功能是图像分类模型，利用深度学习技术对中草药和成分进行分类。模型使用了一种称为卷积神经网络（Convolutional Neural Network，CNN） 的算法。具体而言，模型通过一系列卷积层、池化层和全连接层来提取图像中的特征，并利用softmax函数将图像分为不同的类别。模型的数学表示如下：

<img src="https://raw.githubusercontent.com/johnmelodyme/HuaTuoAI/main/assets/imageclassificationformual.png" style="float: left; margin-right: 10px;" />

> 在这个公式中，`(f * g)(n)` 表示在位置 `n` 对两个函数 `f` 和 `g` 进行卷积操作的结果。符号 `*` 表示卷积操作，
求和符号 `\sum` 对 `m` 的范围进行求和计算。该公式在每个 `m` 值处将 `f(m)` 和 `g(n - m)` 相乘，并将它们相加，
以得到卷积结果 `(f * g)(n)`。

- **预处理和增强**：为提高模型的性能，该项目采用了强大的预处理技术来准备训练和推理的输入图像。此外，还使用数据增强方法来扩充数据集，改善模型对中草药和成分的泛化能力。
- **模型评估**：本存储库提供了评估脚本，用于评估图像分类模型的性能。计算准确率、精确率、召回率和F1分数等指标，以衡量分类系统的有效性。
- **部署**：存储库中提供了部署指南和资源，以便在生产环境中部署图像分类模型。这使得训练好的模型可以用于实时推理，并集成到现有的系统或应用程序中。

| Loss Function       | binary_crossentropy          |
|---------------------|------------------------------|
| Class Mode          | binary                       |
| Optimiser           | rmsprop                      |
| Deep Learning Model | Convolutional Neural Network |

### 揭示准确度
```markdown
18/18 [==========] - 1s 23ms/step - loss: 0.7025 - accuracy: 0.1667 - val_loss: -9.6575 - val_accuracy: 0.2500
```

### 配置
```bash
pip3 install -r requirements.txt
```

如果您遇到以下问题 (MacOS)：
```bash
ssl.SSLCertVerificationError: [SSL: CERTIFICATE_VERIFY_FAILED] certificate verify failed: 
unable to get local issuer certificate
```
请执行以下命令: 
```bash
/Applications/Python\{您的python版本}/Install\ Certificates.command ; exit;

# 目前我的版本是 Python 3.10 所以以下的是我命令:
/Applications/Python\3.10/Install\ Certificates.command ; exit;
```

> 为了训练更多数据，请将文件放置在数据集 [data/images] 文件夹中。
> 为了进行验证，请将您的输入数据添加到[data/input]文件夹中。

### 当前数据集如下: 
```markdown

HuaTuoAI/
:
:.. data/
:    :.. chinese_medicine.txt
:    :.. images/
:         :.. 金银花/
:             :.. 1.png
:             :.. 2.png
:             :.. 3.png
:         :.. 丁公藤/
:             :.. 1.png
:             :.. 2.png
:             :.. 3.png
:         :.. 罗汉果/
:             :.. 1.png
:             :.. 2.png
:             :.. 3.png
:         :.. 人参片/
:             :.. 1.png
:             :.. 2.png
:             :.. 3.png
:    :.. input 
:         :.. 金银花/
:             :.. 1.png
:         :.. 丁公藤/
:             :.. 1.png
:         :.. 罗汉果/
:             :.. 1.png
:         :.. 人参片/
:             :.. 1.png
```

> 若您对中药完全陌生，无需担心，我已经收集了一份中药清单。请点击此处[链接](./data/chinese_medicine.txt)查看。

### 用法

```bash
python3 main.py
```

### 以下是使用 chinese_medicine.h5 二进制文件进行程序演示的示例，以及输出结果:
<div style="display: flex;">
  <img src="https://github.com/johnmelodyme/HuaTuoAI/blob/main/example/2.jpeg?raw=true" alt="Image 2" width="250" />
  <img src="https://github.com/johnmelodyme/HuaTuoAI/blob/main/example/1.jpeg?raw=true" alt="Image 1" width="250" />
</div>

### 个人捐赠支持
如果您认为该项目对您有所帮助，并且愿意个人捐赠以支持其持续发展和维护，🥰我非常感激您的慷慨。
您的捐赠将帮助我继续改进和添加新功能到该项目中。 通过财务捐赠，您将有助于确保该项目保持免
费和对所有人开放。即使是一小笔捐款也能产生巨大的影响，也是对我个人的鼓励。

以下是我的支付宝二维码，您可以扫描二维码进行个人捐赠：

<br />
<img src="https://raw.githubusercontent.com/johnmelodyme/current_location/johnmelodyme-alipayqr/IMG_4026.JPG"  style="height: 500px !important;width: 350px !important;" >

**🥰😘🥰😘再次衷心感谢您的支持和慷慨！**

