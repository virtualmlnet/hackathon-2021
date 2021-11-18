# GymRogueOne Team

## Idea
Our aim is to provide a workflow from PyTorch OpenAI Gym [reinforcement learning (RL)] to ML.NET. OpenAI Gym is a popular toolkit for developing and comparing reinforcement learning algorithms. Our approach is to export ONNX from a trained python RL openAI gym model and use ML.NET  to consume that ONNX.

We use Godot as our 3D engine. So far, only a few attempts of developing RL using Godot. Almost all of them involves Godot as a client communicating to a **python server** running the RL service.

For PoC, we use [GymGodot](https://github.com/HugoTini/GymGodot), which comes with an interesting [mars landing example](https://github.com/HugoTini/GymGodot/blob/main/gym-godot/examples/mars_lander/mars_lander.md)

## Challenge
**Our challenge** is to do RL in Godot using ML.NET as inference engine **without using any (python/.NET) server**.

![image](https://user-images.githubusercontent.com/49812372/142351131-c5cd4a00-a0bd-4ee5-bc89-e86975011e65.png)

- First we need to train and create RL model in our chosen OS: Windows.

  - The provided solution runs only in Linux and the RL training is done through the provided python scripts (learn.py). It took some hacking of these scripts to make them run in Windows.

- Second, the python server is replaced with a .NET Web Socket server using the same messaging interface as that provided by the python RL server.

   - The trained PyTorch RL model is [exported to ONNX](https://stable-baselines3.readthedocs.io/en/master/guide/export.html)
   - ML.NET  consumes the ONNX and provide the RL inference service of the server.
   
- Third, the provided GymGodot's rocket model is replaced with a [SpaceX Starship model]((https://skfb.ly/6QWPo)) by MartianDays under [Creative Commons Attribution]((http://creativecommons.org/licenses/by/4.0/).)

## Team contact
For questions on this submission you can contact: Jim SEOW: JimFFM@outlook.com

Team members
- [Jim SEOW](github.com/JimFFM)
- [Shehroze Malik](github.com/shehrozeee) => who did most of the coding
- [Praveen Raghuvanshi](github.com/praveenraghuvanshi)

## Solution

Full Sorce Code: https://github.com/JimFFM/ml-hackathon-2021/
