# Speaker Count Estimation using Deep Neural Networks

Estimating the number of concurrent speakers from single channel mixtures is a very challenging task that is a mandatory ﬁrst step to address any realistic “cocktail-party” scenario. It has various audio-based applications such as blind source separation, speaker diarisation, and audio surveillance. Building upon powerful machine learning methodology and the possibility to generate large amounts of learning data, Deep Neural Network (DNN) architectures are well suited to directly estimate speaker counts.

In this work a recurrent neural network was trained to generate speaker count estimates for 0 to 10 speakers. The model uses three BiLSTM layers based on a model proposed for singing voice separation by [Leglaive](https://perso.telecom-paristech.fr/leglaive/documents/presentationICASSP15.pdf) 

## Demos

A demo video is provided on the [accompanying website](https://www.audiolabs-erlangen.de/resources/2017-CountNet)

## Usage

This repository provides the [keras](https://keras.io/) model to be used from Python to infer count estimates. The preprocessing dependes on librosa and scikit-learn. Not that the provided model is trained on 16 kHz samples of 5 seconds duration. 

### Docker

[Docker](https://www.docker.com/) makes it easy to reproduce the results and install all requirements. If you have docker installed, run the following steps to predict a count from the provided test sample.

* Build the docker image: `docker build -t countnet .`
* Predict from example: `docker run -i countnet python predict_audio.py examples/5_speakers.wav`

### Manual Installation 

Make sure you have Python 3.6, `libsndfile` and `libhdf5` installed on your system (e.g. through Anaconda). To install the requirements run

`pip install -r requirements.txt`

You can now run the command line script and process wav files

`python predict_audio.py examples/5_speakers.wav`

## Reproduce Paper Results

We will provide the full test dataset soon.

## License

MIT