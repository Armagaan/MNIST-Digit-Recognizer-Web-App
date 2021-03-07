# MNIST-Digit-Recognizer-Web-App
Deploying MNIST digit recognizer using Streamlit and Heroku

![Screenshot of the web-app](https://github.com/Cossak/MNIST-Digit-Recognizer-Web-App/blob/main/Screenshot.png?raw=true)
Check out: https://mnist-clf-st.herokuapp.com/

_(For anyone who is looking to tweak the background color of the canvas, I would suggest not to, as the classifier starts giving garbage output when I set canvas background as white and brush stroke as black. If it works for you, kindly let me know too.)_

## Description

* mnist.ipynb is the training notebook.
* mnist.py contains the streamlit code.
* mnist.h5 is the trained model trained in mnist.ipynb notebook.
* Procfile, requirements.txt and setup.sh are required by Heroku for deployment.

To get the version numbers of various libraries which you will write in requirements.txt:
* open cmd
* type conda activate
* type conda list

Take note of a few things in the `requirements.txt` file:
* I've used `opencv-contrib-python-headless` instead of `opencv-contrib-python` as Heroku throws an error otherwise.
* `tensorflow-cpu` instead of `tensorflow` as tensorflow makes the file too big for Heroku when using a free account.
* `dataclasses` is needed by streamlit canvas. The canvas makes the call `from dataclasses import dataclass` which will give an error if you don't include it in the requirements.txt file.
