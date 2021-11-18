# Dayo team

## Idea
There are a lot of files that makes Pytorch to easier for beginners. For example, in pytorch, 
```python
mnist_train = dsets.MNIST(root='MNIST_data/', 
                          train=True, 
                          transform=transforms.ToTensor(), 
                          download=True)

mnist_test = dsets.MNIST(root='MNIST_data/', 
                         train=False, 
                         transform=transforms.ToTensor(), 
                         download=True)
```
It is very easy to load test datas.

But in torchsharp, there are nothing has included. And you are required to create mini-batch manualy to use mini batch.

## What I did

C# contains IEnumerable interface which makes load data more easier and I make dataloader class for universal datas, As similar as `torch.utils.data` in pytorch. 

This repo is my project which was created for virtual ml.net hackertoon,

https://github.com/dayo05/TorchDataLoader

I use fruits360 datasets for test my dataloder but somethings are wrong on testing... (This is the first project of ml without tutorials, I'm waiting for help!)

Fruit360 class is the example of using my dataloader.

```cs
var trainData = new Fruit360();
var testData = new Fruit360(train: false);
Console.WriteLine($"Train data: {trainData.Count()}");
Console.WriteLine($"Test data: {testData.Count()}");

var train = new DataLoader(trainData, 32, true, torch.CUDA);
var test = new DataLoader(testData, 64, false, torch.CUDA);
Console.WriteLine($"Train batch count: {train.Count}");
Console.WriteLine($"Test batch Count: {test.Count}");
```

This is example for calling my dataloader, It is similar as what pytorch does.

## Thank you everyone, My project is just start, I'll keep going studying about it and In next year, I'll make more better project on this hackertoon :D

ps. I'm learning about VGG models, in now, my model is not working but I'll make that works fine soon!
