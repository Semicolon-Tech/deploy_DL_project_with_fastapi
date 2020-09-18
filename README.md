# Deploy a Deep learning project with fastapi
This documents shows how to deploy a Deep learning model using fast api. It will be using this [MNIST-CNN Model](https://github.com/Semicolon-Tech/cnn_intro_with_mnist).

## Project setup
Before going through the steps make sure you have the following pre-installed

### Prerequisite
1. Python 3.6+
2. Virtualenv


Make sure to download/clone this repository and navigate to the folder in yout terminal. Now follow the indtructions below

1. Create the virtual environment.
```
    virtualenv /path/to/venv --python=/path/to/python3
```
You can find out the path to your `python3` interpreter with the command `which python3`.

2. Activate the environment and install dependencies.
    - #### Linux
    ```
        source /path/to/venv/bin/activate
        pip install -r requirements.txt
    ```

    - #### Windows
    ```
        ./path/to/venv/bin/activate
        pip install -r requirements.txt
    ```

3. Launch the service
```
    uvicorn main:app --workers 1 --host 0.0.0.0 --port 8008
```

## Posting requests locally
When the service is running, try this link in your browser
```
    127.0.0.1:8008/docs
```

You can test the model with the Sample MNIST Image from [How to Develop a CNN for MNIST Handwritten Digit Classification](https://machinelearningmastery.com/how-to-develop-a-convolutional-neural-network-from-scratch-for-mnist-handwritten-digit-classification/) below using postman 

| ![Download this sample image for testing](images/sample_mnist_image.png?raw=true) | 
|:--:| 
| *1. Download this sample image for testing* |

| ![Using Postman: upload image](images/postman_example_pre.PNG?raw=true) | 
|:--:| 
| *2. Using Postman: upload image* |

| ![Using Postman: send a Post Request](images/postman_example.PNG?raw=true) | 
|:--:| 
| *3. Using Postman: send a Post Request* |

# Refrences
1. MNIST CNN Model [repo](https://github.com/Semicolon-Tech/cnn_intro_with_mnist)
2. Tutorial: How to deploy your ConvNet classifier with Keras and FastAPI [article](https://www.machinecurve.com/index.php/2020/03/19/tutorial-how-to-deploy-your-convnet-classifier-with-keras-and-fastapi/#full-model-code)
3. [How to Develop a CNN for MNIST Handwritten Digit Classification](https://machinelearningmastery.com/how-to-develop-a-convolutional-neural-network-from-scratch-for-mnist-handwritten-digit-classification/)