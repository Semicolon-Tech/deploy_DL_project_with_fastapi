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
    uvicorn main:app --reload --workers 1 --host 0.0.0.0 --port 8008
```

## Posting requests locally
When the service is running, try this link in your browser
```
    127.0.0.1:8008/docs
```

You can test the model with the image below using postman 

![Sample MNIST Image](https://github.com/Semicolon-Tech/deploy_DL_project_with_fastapi/blob/master/sample_mnist_image.png?raw=true "Sample MNIST Image")
Sample MNIST Image

![Using Postman: upload image](https://github.com/Semicolon-Tech/deploy_DL_project_with_fastapi/blob/master/postman_example_pre.png?raw=true "Using Postman: upload image")
Using Postman: upload image

![Using Postman: send a Post Request](https://github.com/Semicolon-Tech/deploy_DL_project_with_fastapi/blob/master/postman_example.png?raw=true "Using Postman: send a Post Request")
Using Postman: send a Post Request

```
    curl -X POST "http://localhost:8008/predict" -H "accept: application/json" -H "Content-Type: application/json" -d "{\"file\":\"C:/Users/christian/Pictures/sample_mnist_image.png\"}"
```

# Refrences
1. MNIST CNN Model [repo](https://github.com/Semicolon-Tech/cnn_intro_with_mnist)
2. Tutorial: How to deploy your ConvNet classifier with Keras and FastAPI [article](https://www.machinecurve.com/index.php/2020/03/19/tutorial-how-to-deploy-your-convnet-classifier-with-keras-and-fastapi/#full-model-code)
3. 