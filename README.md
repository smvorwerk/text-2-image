<p align="center">
<img src="https://emojipedia-us.s3.dualstack.us-west-1.amazonaws.com/thumbs/240/apple/285/woman-artist_1f469-200d-1f3a8.png" width="60" alt="Dali">
  <h2 align="center">Text2Image Playground</h2>
</p>

A playground for ML enthusiasts to tinker with an open-source, WIP OSS version of
OpenAI's [DALL-E](https://openai.com/blog/dall-e/), with the main goal being to reduce the overall hardware requirements for training to an acceptable level where consumer-grade hardware can handle the full pipeline and complete it within a reasonable time frame.

## Using the Mega Model

The Mega model is substantially more capable than the Mini Model and therefore generates higher fidelity images. If you have the computing power--either through a Google Colab Pro+ subcription or by having a strong local machine, select the Mega model in the colab notebook or run the backend with a `Mega` or `Mega_full` parameter, e.g. `python text-2-image/backend/app.py --port 8000 --model_version mega`

## Local development

Follow these steps in case you'd like to clone and run the DALL-E playground locally:

1. Clone or fork this repository
2. Create a virtual environment `cd backend && python3 -m venv ENV_NAME`
3. Install requirements `pip install -r requirements.txt`
4. Make sure you have pytorch and its dependencies
   installed _[Installation guide](https://pytorch.org/get-started/locally/)_
5. Run web server `python3 app.py --port 8080 --model_version mini` (you can change from 8080 to your own port)
6. In a different terminal, install frontend's modules `cd interface && npm install` and run
   it `npm start`
7. Copy backend's url from step 5 and paste it in the backend's url input within the web app

## Local development with Docker-compose

1. Make sure you have [docker](https://docs.docker.com/get-docker/) and [The NVIDIA Container Toolkit](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html) installed 
2. Clone or fork this repository
3. start server `docker-compose up`, add `-d` to `docker-compose up` if you'd like to run it in the background
4. The first time will take some time to download the images, models and other dependencies. 
   models and other dependencies are downloaded only once, and then cached.
4. Copy backend's url from step 2 and paste it in the backend's url input within the web app.
   
   webapp at `http://localhost:3000/text-2-image`


