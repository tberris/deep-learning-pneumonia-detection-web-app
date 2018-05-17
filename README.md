# flask/gunicorn based Heroku web app for pneumonia detection

[![](https://img.shields.io/badge/python-2.7%2C%203.5%2B-green.svg)]()
[![GPLv3 license](https://img.shields.io/badge/License-GPLv3-blue.svg)](http://perso.crans.org/besson/LICENSE.html)



------------------
## About the app
> This repository was created to help clarify how to utilise flask and gunicorn to easily deploy a python/keras deep learning model as a web app on Heroku. This example features code for online deployment of a binary medical image classification model, based on convolutional neural network architecture. The CNN has two hidden layers and has been trained on the following chest x-ray image dataset for pneumonia: <a href="https://data.mendeley.com/datasets/rscbjbr9sj/2">Kermany Daniel, Zhang Kang, Goldbaum Michael (2018). Labeled Optical Coherence Tomography (OCT) and Chest X-Ray Images for Classification. Mendeley Data, v2, http://dx.doi.org/10.17632/rscbjbr9sj.2</a>. The trained model achieved accuracy of more than 86% on the test set and its weights have been saved in the Models folder (see file: trained_model.h5) in the very useful HDF5 format. You may use your own saved trained model! Just make sure you put it in the Models folder and name it appropriately so that the flask app may call it.

> A JavaScript app running on the browser calls the Flask app (app.py) to load the model weights and return results to the JavaScript  app (through the 'GET' and 'POST' methods). More details may be found at: <a href="https://www.youtube.com/watch?v=SI1hVGvbbZ4">Deploy Keras Neural Network to Flask web service | Part 1 - Overview</a>

> This app is currently live and can be found at: <a href="https://pneumonia-detection.herokuapp.com/">https://pneumonia-detection.herokuapp.com/</a>.

> This web application has been created using code developed by Xin Fu (please see the following repository: <a href="https://github.com/mtobeiyf/keras-flask-deploy-webapp">https://github.com/mtobeiyf/keras-flask-deploy-webapp</a>. The changes to what Xin Fu had already prepared were the following:
<ul>
<li>Inclusion of a procfile to serve the app with gunicorn on the Heroku server after upload (for uploading this python app to Heroku please follow Heroku documentation on how to use git with Heroku)</li>
<li>As per Heroku requirements for stability and reproducibility, versions of all required python environments were specified in the requirements.txt file</li>
<li>Inclusion of gunicorn to the requirements.txt file</li>
<li>Changed the app.py (flask app) file to adapt it to the required functionality according to the trained binary image classification model. The program was also modified to delete every uploaded image after providing the prediction. This will prevent exceeding capacity limits on Heroku servers. The last lines of the file have been modified to work with gunicorn. The gevent serving code lines have been commented out, but are still there in case someone would like to run the code locally as Xin Fu explained in the README of his repo <a href="https://github.com/mtobeiyf/keras-flask-deploy-webapp">https://github.com/mtobeiyf/keras-flask-deploy-webapp</a></li>
<li>The Index.html and base.html files have been modified accordingly to include references and information about the model</li>
<li>This README file has bben adapted to provide instructions about heroku deployment. The part for customisation has been modified also</li>
</ul>

> To create a web app that runs locally, please see Xin Fu's repo (<a href="https://github.com/mtobeiyf/keras-flask-deploy-webapp">https://github.com/mtobeiyf/keras-flask-deploy-webapp</a>) and follow instructions in the README file, to run the model locally. Gevent or gunicorn may be used for local deployment too.

## Customization options

### Use your own model

Place your trained keras deep learning model to the models directory.


### Use other pre-trained model

See [Keras applications](https://keras.io/applications/) for more available models such as DenseNet, MobilNet, NASNet, etc.


### UI Modification

Modify files in `templates` and `static` directory.

`index.html`, `base.html` for the UI and `main.js` for all the behaviors

## Deployment

To deploy it for public use, you need to upload this app on heroku or other python enabled server. However heroku is pretty good at recognising and running python apps. There is also a free version!

## More resources

Check Siraj's ["How to Deploy a Keras Model to Production"](https://youtu.be/f6Bf3gl4hWY) video. The corresponding [repo](https://github.com/llSourcell/how_to_deploy_a_keras_model_to_production).

[Building a simple Keras + deep learning REST API](https://blog.keras.io/building-a-simple-keras-deep-learning-rest-api.html).

[How to deploy a Flask App to Heroku](https://progblog.io/How-to-deploy-a-Flask-App-to-Heroku/).

"# deep-learning-pneumonia-detection" 
"# deep-learning-pneumonia-detection-web-app" 
