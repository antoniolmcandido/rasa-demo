# RASA NLU Demo

## :surfer: Introduction

The purpose of this repo is to showcase a NLU model built using DIET Classifier of Rasa Open Source. This repository includes a pre-trained model for the demonstration. The data is taken from an official rasa demo bot: Sara.

For details on training of model and preparation of data, see:

The model can be used for:

-   Intent Classification
-   Entity recognition

## 👷‍ Setting up

### With Docker

1. Build container using Dockerfile from root directory

```
docker build -t rasa_nlu .
```

2. Start the NLU server using newly build docker container

```
docker run -p 5005:5005 rasa_nlu
```

This will build and start the a docker of the NLU server on the default port (`5005`) of the Rasa NLU.

### Without Docker

1. [Optional] Create a python environment and activate it.

2. Install dependencies

```
pip install -r requirements.txt
```

3. Start the Rasa NLU server using;

```
rasa run --enable-api -m models/nlu_model.gz
```

This will start the Rasa NLU server on the default port `5005`.

## To test the API:

After starting the server, test the api on the following endpoint `/model/parse`. Example-

```
curl localhost:5005/model/parse -d '{"text":"I am Candido"}'
```
