# Everything Recognition

Works with web-cam to identify objects predefined in configuration file. Script uses [OpenCV](https://docs.opencv.org/4.x/index.html) library.

## Before you run

Make sure you have installed Python3.

Prepare virtual environment.

```shell
python -m venv env
```

Activate your virtual environment.

```shell
. ./env/bin/activate
# For Windows:
# . .\env\Scripts\activate
```

Install all requirements.

```shell
pip install -r requirements.txt
```

After that you are ready to use script with predefined settings in `config.py`

```shell
python run.py
```

Type `q` to exit from runing script.

## Setup and tuning

### Folder haarcascades

Folder contains two sub-folders (faces and road-signs) with xml files to use in OpenCV for detection different objects.

### Configuration with `config.py`

There is only one dictionary `CASCADES` with included Haar cascades.

You can easily add anothe files or remove already exists based on your curent needs.

`path` - relative path to predefined classifier.
`color` - frame color to hihglight an object `tuple[Blue, Green, Red]`.
`draw` - identify if frame should be drawn.

## Functions inside the Script

### is_user_wants_quit

Waits `q` from user to stop script execution.

### show_frame

Displays already processed frames.

Needs `numpy.ndaray` with processed current frame from web-cam.

### draw_sqare

Adds square around found object.

Needs `numpy.ndarray` of the current frame and frame color `tuple[Blue, Green, Red]`.

### get_cascades

Creates and prepare list of classifirs for objects recognition.
