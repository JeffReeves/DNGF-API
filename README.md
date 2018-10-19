# DNGF-API

Docker Nginx Gunicorn Flask API stack

## How Tos

### Setup Local Development Environment

Install Python 3.7 from <https://www.python.org/downloads/release/python-370/>

```shell
# Navigate to the Python37 directory
cd <path/to/Python37>

# Update pip and setuptools
python3 -m pip install --upgrade pip setuptools

# Create a virtual environment (venv)
python3 -m venv .venv

# Activate virtual environment
source .venv/Scripts/activate   # Windows
source .venv/bin/activate       # Linux / Mac

# Update pip and setuptools in the virtual environment
python3 -m pip install --upgrade pip setuptools

# Install all required modules from the requirements.txt file
python3 -m pip install -r requirements.txt
```

### Run Development Flask Server Locally

**NOTE**: Gunicorn does not work on Windows (see: <https://github.com/benoitc/gunicorn/issues/407>).

#### Flask without Gunicorn

```shell
cd Python37
python3 main.py
```

#### Flask with Gunicorn

```shell
cd Python37
gunicorn --bind 0.0.0.0:8080 wsgi:application -w 1
```

### Run Container

```shell
docker pull <this-image:latest>
docker run --name dngf-api -d -p 8080:80 <this-image:latest>
```