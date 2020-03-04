# Vision-base-Pakistan-Sign-Language-to-Text-Conversion

## Project Area of Specialization
   Deep Learning, Artificial Intelligence, Natural Language Processing (NLP)
## Project Summary
   Vision base Sign Language to Text Conversion is one of the potential applications of
computer vision through deep learning. Communication is deeply intertwined with human existence. In
personal life, we communicate to deal with certain concerns and problems of daily life. In professional life
also, it is communication that helps us to build healthy relations with others. Unfortunately, people exist
among us with certain disabilities with whom we face problems while communicating or are completely
unable to communicate. One of them are hearing impaired people and Sign language is the most natural
and expressive way for them to communicate with other people but normal people never try to learn sign
language for interaction with deaf people which leads to the isolation and segregation of deaf people. In
order to get rid of this communication barrier, there is a need of such reliable system that can translate
sign language to regular text. The sign language on which this project is based-upon is Pakistan Sign
Language (PSL) which is the primary language of deaf people in Pakistan. There are two primary
approaches for hand gesture/sign recognition. The first one is sensor-based approach and the second one
is vision-based approach. The sensor-based approach includes the measurement of electric signals,
resistance etc. for recognition of hand gesture It is most accurate, but it is not user friendly, because gloves
with various sensors affixed on it, are put on by person (normally by a hearing-impaired person) and hence
it may make user annoy and may increase the overall development cost of the system. On the other hand,
vision-based approach uses cameras in order to detect the hand gesture without attaching any sensing
device to the human body, hence it is user friendly and more economical. The main aim of our project is
to develop a vision-based system which will recognize the hand gestures based on Pakistan Sign Language
(PSL) and generate the respective text in both English and Urdu languages. So, the focus is placed on
designing the system which will accurately detect the hand gestures in different lighting conditions,
perspective and on the hands of different age groups.
## Benefits of the Project
   This system uses the advanced deep learning technology in order to recognize hand gestures in real-time. This system if installed at public places provide deaf-dumb people an
efficacious means of expressing themselves and eradicates the need of sign language interpreter. This
system can be installed at different transportation facilities like airports, railway stations, bus stations,
police stations, hospitals, courts, government offices, schools, universities, and shopping complexes.
Further the system’s functional code can be used to make a browser widget which will generate captions
for every video played involving sign language.

# Installation

## Dependencies

Tensorflow Object Detection API depends on the following libraries:

*   Protobuf 3.0.0
*   Python-tk
*   Pillow 1.0
*   lxml
*   tf Slim (which is included in the "tensorflow/models/research/" checkout)
*   Jupyter notebook
*   Matplotlib
*   Tensorflow (>=1.12.0)
*   Cython
*   contextlib2
*   cocoapi

For detailed steps to install Tensorflow, follow the [Tensorflow installation
instructions](https://www.tensorflow.org/install/). A typical user can install
Tensorflow using one of the following commands:

``` bash
# For CPU
pip install tensorflow
# For GPU
pip install tensorflow-gpu
```

The remaining libraries can be installed on Ubuntu 16.04 using via apt-get:

``` bash
sudo apt-get install protobuf-compiler python-pil python-lxml python-tk
pip install --user Cython
pip install --user contextlib2
pip install --user jupyter
pip install --user matplotlib
```

Alternatively, users can install dependencies using pip:

``` bash
pip install --user Cython
pip install --user contextlib2
pip install --user pillow
pip install --user lxml
pip install --user jupyter
pip install --user matplotlib
```

<!-- common_typos_disable -->
**Note**: sometimes "sudo apt-get install protobuf-compiler" will install
Protobuf 3+ versions for you and some users have issues when using 3.5.
If that is your case, try the [manual](#Manual-protobuf-compiler-installation-and-usage) installation.

## COCO API installation

Download the
[cocoapi](https://github.com/cocodataset/cocoapi) and
copy the pycocotools subfolder to the tensorflow/models/research directory if
you are interested in using COCO evaluation metrics. The default metrics are
based on those used in Pascal VOC evaluation. To use the COCO object detection
metrics add `metrics_set: "coco_detection_metrics"` to the `eval_config` message
in the config file. To use the COCO instance segmentation metrics add
`metrics_set: "coco_mask_metrics"` to the `eval_config` message in the config
file.

```bash
git clone https://github.com/cocodataset/cocoapi.git
cd cocoapi/PythonAPI
make
cp -r pycocotools <path_to_tensorflow>/models/research/
```

## Protobuf Compilation

The Tensorflow Object Detection API uses Protobufs to configure model and
training parameters. Before the framework can be used, the Protobuf libraries
must be compiled. This should be done by running the following command from
the tensorflow/models/research/ directory:


``` bash
# From tensorflow/models/research/
protoc object_detection/protos/*.proto --python_out=.
```

**Note**: If you're getting errors while compiling, you might be using an incompatible protobuf compiler. If that's the case, use the following manual installation

## Manual protobuf-compiler installation and usage

**If you are on linux:**

Download and install the 3.0 release of protoc, then unzip the file.

```bash
# From tensorflow/models/research/
wget -O protobuf.zip https://github.com/google/protobuf/releases/download/v3.0.0/protoc-3.0.0-linux-x86_64.zip
unzip protobuf.zip
```

Run the compilation process again, but use the downloaded version of protoc

```bash
# From tensorflow/models/research/
./bin/protoc object_detection/protos/*.proto --python_out=.
```

**If you are on MacOS:**

If you have homebrew, download and install the protobuf with
```brew install protobuf```

Alternately, run:
```PROTOC_ZIP=protoc-3.3.0-osx-x86_64.zip
curl -OL https://github.com/google/protobuf/releases/download/v3.3.0/$PROTOC_ZIP
sudo unzip -o $PROTOC_ZIP -d /usr/local bin/protoc
rm -f $PROTOC_ZIP
```

Run the compilation process again:

``` bash
# From tensorflow/models/research/
protoc object_detection/protos/*.proto --python_out=.
```

## Add Libraries to PYTHONPATH

When running locally, the tensorflow/models/research/ and slim directories
should be appended to PYTHONPATH. This can be done by running the following from
tensorflow/models/research/:


``` bash
# From tensorflow/models/research/
export PYTHONPATH=$PYTHONPATH:`pwd`:`pwd`/slim
```

Note: This command needs to run from every new terminal you start. If you wish
to avoid running this manually, you can add it as a new line to the end of your
~/.bashrc file, replacing \`pwd\` with the absolute path of
tensorflow/models/research on your system.
