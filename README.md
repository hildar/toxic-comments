# Toxic comments detect system

## About

The detection system to predict different types of toxicity. This project uses **NLP** (**TF-IDF**) and **XGBoost**. Set up
**back-end** and **front-end** servers via **Flask**, and wrapped them in **Docker**. Binary classification and multi-targets.

All steps you can see in main file [train.ipynb](https://github.com/hildar/python-flask-docker/blob/main/Train.ipynb).

<img src="example_probs.png" alt="example_probs" width="400"/>


#### Stack:

- ML: NLP, XGBoost, TF-IDF, sklearn, pandas, numpy, matplotlib
- API: Flask, Flask_wtf
- VM: Docker
- Data from kaggle: [Jigsaw Toxic comment competition](https://drive.google.com/file/d/1Vdj89P-V11ipZOCFpeM3ggWVWq3O29sj/view?usp=sharing)


Only one feature: comment_text (text)

Feature transform: 
- regex clean
- tfidf


## User guide

### 1. Prepare

1.1 Clone git:
```
$ git clone https://github.com/hildar/python-flask-docker.git
```

1.2 If you have some problem with downloading ML model yon can download it from [logreg_pipeline.dill](https://drive.google.com/file/d/1VqY_LIvb5O4PjSaqMh7vmU3XOE4Ui8cr/view?usp=sharing) or create it from [train.ipynb](https://github.com/hildar/python-flask-docker/blob/main/Train.ipynb) file and put at the folder `app/models/`;


1.3 Make docker image:
```
$ cd python-flask-docker/docker
$ docker build -t python-flask-docker app/
```

1.4 Run docker container:
```
$ docker run -d -p 8180:8180 -p 8181:8181 python-flask-docker
```


### 2. Usage

Now, there are two ways: 

#### 1-st one - Front server

Go to the address [http://localhost:8180](http://localhost:8180) and use front server. You can manually type some comment at the web form and enjoy the result:

<img src="example_front.png" alt="example_front" width="700"/>

#### 2-nd one - Jupiter Notebook

Use Jupiter Notebook "Client.ipynb" and step by step check server located [http://localhost:8181](http://localhost:8181).

