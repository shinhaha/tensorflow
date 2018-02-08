# GAN

![img1](https://github.com/shinhaha/MachineLearning_tensorflow/blob/master/Code/GAN/img/K-001.png)

```
GAN�̶� �����ڿ� �Ǻ��ڷ� �̷���� �������� �� ���� ��Ʈ��ũ�� �̿��� UnSupervised Learning�̴�.
���� �׸����� ���� ������ G�� ���� D�� ����ְ� GAN�� �����ϰ� �ִµ�, 
ó���� ���� �������� �������� ������ �������� �����Ѵ�. ������ �ܹڿ� �̰� ���������� ���� �ľ��Ѵ�. 
������, ���� �������� ������� ��� �����ϰ� ������ �ᱹ �̰� ��¥ �������� ������������ ������ �� ���� �ȴ�!
```
![img2](https://github.com/shinhaha/MachineLearning_tensorflow/blob/master/Code/GAN/img/K-002.png)

```
���� �׸����� ���� �������� ���� �׷����� �Ǻ����� �Ǵ��� �Ķ��� �׷���, G�� ������ ������ �ʷϻ� �׷����� ���캸��
(a)�� ���� ���� D�� �ɷ��� ǥ���Ѵ� ���� �����Ϳ� ��¥ �������� ���̰� Ŭ ���� D�� ������ ��鸮�� �ִ�. 
(b)�� D�� �ùٸ��� �����ϰ� �ִ� ���� Ȯ���� �� �ִ�. 
G�� ���� �н��ϰ� �Ǹ� �׸� (c)ó�� ���� ���� �����Ϳ� �����ϰ� �� ���̰� 
�ᱹ �����Ͱ� ��ġ�ϰ� �Ǹ� D�� �̰� ��¥ ���������� ��¥���� ������ �� ���� �׸�(d)�� p(G)=p(data)=0.5�� ���¿� �����Ѵ�.
```
![img3](https://github.com/shinhaha/MachineLearning_tensorflow/blob/master/Code/GAN/img/K-003.png)

```
�׷��ٸ� loss function�� ��� ������ �� ������?
���� ��ó�� ���ǰ� �Ǵµ� G�� ���� min ���� ���ϰ� D�� ���� max ���� ���Ѵ�. 
��� G ������ D ������ ���� �н��� ���� ��Ű��� ������ ������ �Ǿ��ֱ� ������ �����ϴ� ��ó�� �� ���� �ʴ´�.
�츮�� global optimum�� �ֳ��� �����ϰ� �ִٸ� ã�ƾ� �Ѵ�.
```

![img4](https://github.com/shinhaha/MachineLearning_tensorflow/blob/master/Code/GAN/img/K-010.jpg)

```
G�� �����ߴٰ� �����ϰ� D(G)�� D�� maxmize �ϴ� ���� ���ϱ� ���� �̺��Ѵٸ� ���� ���� ������ ��Ÿ�� �� �ִ�.
```

![img5](https://github.com/shinhaha/MachineLearning_tensorflow/blob/master/Code/GAN/img/K-004.png)

```
G ���忡�� D�� ��¥���� ��¥���� ������ ���ϰ� �ϴ� D(x)=0.5�� best case�̴�. 
�̰��� �Ŀ� �ְ� �����ϸ� JSD�� log�� ���� �����µ� JSD�� 0���� ũ�ų� �����Ƿ�
C(G)�� p(G)=p(data)�� global minimum�� ���� �ᱹ convex �ϴٴ� �����̴�.
```

![img6](https://github.com/shinhaha/MachineLearning_tensorflow/blob/master/Code/GAN/img/K-007.png)

```
convex �ϴٴ� ���� �����߱� ������ Gradient Descent�� �����ϸ� global minimum�� ������ �� �ִٰ� ���� �� �ִ�.
```
![img11](https://github.com/shinhaha/MachineLearning_tensorflow/blob/master/Code/GAN/img/K-11.jpg)

```
yunjey ���� ���� ���󿡼� ������ �ڷ��. ���� �׸����� G�� ���� �����ϴµ�
loss function���� ���� term�� G�� ������ ���� ���̰� �ᱹ ������ term���� ������ �ްԵȴ�.
```
![img7](https://github.com/shinhaha/MachineLearning_tensorflow/blob/master/Code/GAN/img/K-009.png)

```
G�� loss function log(1-D(G(z)))����
ó���� G�� �������� �̹����� ������ �ǰ� ���Ⱑ �۾Ƽ� ���� �ӵ��� �н��ϰ� �ȴ�.
�׷��� tricky �� ���̵� ������ �Ͽ��µ� D(G(z))�� sigmoid�� ��ġ�Ƿ� 0~1�����̴�.
�н��� ������ �����ϱ� ���� ���̵��� log(1-D(G(z)))�� minimize ���� ���� D(G(z))�� maxmize���ڴ� ���̴�.
�׷��� �ʹݿ� ���Ⱑ Ŀ���� �ǰ� ������ �н���ų �� �ִ�. 
������ �ʹ��� ���Ѵ뿡 ����� ����� ���� ƨ��� ������ ��Ÿ�� �� �ִ�.
�׷��� initialize���� ���Ժ����� ���ִ� �۾��� �߿��ϰ� initialize�� �� ������ ������ NaN�� ������ �ȴ�.
```

# MNIST Process(100 Epoch)

![1](https://github.com/shinhaha/MachineLearning_tensorflow/blob/master/Code/GAN/samples/000.png)
![2](https://github.com/shinhaha/MachineLearning_tensorflow/blob/master/Code/GAN/samples/009.png)
![3](https://github.com/shinhaha/MachineLearning_tensorflow/blob/master/Code/GAN/samples/019.png)
![4](https://github.com/shinhaha/MachineLearning_tensorflow/blob/master/Code/GAN/samples/029.png)
![5](https://github.com/shinhaha/MachineLearning_tensorflow/blob/master/Code/GAN/samples/039.png)
![6](https://github.com/shinhaha/MachineLearning_tensorflow/blob/master/Code/GAN/samples/049.png)
![7](https://github.com/shinhaha/MachineLearning_tensorflow/blob/master/Code/GAN/samples/059.png)
![8](https://github.com/shinhaha/MachineLearning_tensorflow/blob/master/Code/GAN/samples/069.png)
![9](https://github.com/shinhaha/MachineLearning_tensorflow/blob/master/Code/GAN/samples/079.png)
![10](https://github.com/shinhaha/MachineLearning_tensorflow/blob/master/Code/GAN/samples/089.png)
![11](https://github.com/shinhaha/MachineLearning_tensorflow/blob/master/Code/GAN/samples/099.png)