FROM continuumio/anaconda3:2023.07-1
EXPOSE 5000
WORKDIR /usr/app/
RUN apt-get update && apt-get install -y build-essential libglib2.0-0 libsm6 libxext6 libxrender-dev
COPY requirements.txt ./
RUN pip install --upgrade pip
RUN pip install -r requirements.txt --verbose
COPY . ./
CMD ["python", "flask_api.py"]