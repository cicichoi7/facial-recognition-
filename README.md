# facial-recognition-

This model is used to detect people's emotions based on their facial expressions. It is trained on an imagenet Resnet-18 model using transer learning which is a technique for training a model on a new dataset which is faster than training a network for scratch. The idea is that the model can help people who have autism, aspergers, prosopagnosia, or any other conditions that make it harder for people to read facial expressions and emotions. 

![image](https://github.com/cicichoi7/facial-recognition-/assets/140643991/3df79d3e-a95d-48db-a017-473c9be635f2)

![image](https://github.com/cicichoi7/facial-recognition-/assets/140643991/c9f01e09-762b-49e2-8dd8-81eb70a0051c)

![image](https://github.com/cicichoi7/facial-recognition-/assets/140643991/3919885a-4f64-4fc9-93a9-38cbceb65d86)

![image](https://github.com/cicichoi7/facial-recognition-/assets/140643991/6b8fde61-750c-4ff9-92e4-add8a7bae3c4)


## The Algorithm

The algorithim is used by VSCODE and downloaded images supported by Jetson nano. It is trained to classify human facial expressions. The machine will guess the human expression it was given to the best of it's knowledge and then will print out the emotion it believes it was given. The user can then interpepret the information. This model needs to be trained with a lot of epochs because some facial expressions are very specific and hard for the machine to process. If you have emotions that are similar to each other, my pretrained model kept mixing them all up. I trained mine for about 300 epochs.
## Running this project
   
1. Make sure your Jetson Nano is connected to hotspot and ready to go
2. Transfer your dataset to your Jetson Nano using filezilla
3. Connect to your Jetson Nano to VSCODE
4. Sign into VSCODE with your Inet address and sign in with nvidia password
5. Open the terminal in VSCODE
7. Ensure you are not in the docker. If so, change directories into jetson-inference/python/training/classification using `cd jetson-inference/python/training/classification`.
8. To check if you have the resnet18.onnx file, use `ls models/human_emotions/`
9. Set the NET and DATASET variables by using `NET=models/human_emotions` and `DATASET=data/human_emotions`
10. To run the previous command I am going to use an angry image from the test folder for this example. I need to pick an image to use and then run this command: `imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$DATASET/labels.txt $DATASET/test/anger/anger1.png output1.jpg`
11. On the side bar in VSCODE, find your output image under classification, and then you have your image classified! 
[View a video explanation here](https://www.youtube.com/watch?v=PQJeOJlTzgA)
