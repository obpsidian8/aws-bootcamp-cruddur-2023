FROM python:3.10-slim-buster

#INSIDE THE CONTAINER, create a directory for the application
WORKDIR /backend-flask

#OUTDIDE THE CONTAINER, copy the requirements.txt file to the container
COPY requirements.txt requirements.txt

#INSIDE THE CONTAINER, install the requirements
RUN pip3 install -r requirements.txt

#OUTSIDE THE CONTAINER, copy the rest of the application to the container
# First period is the source which is the current directory (backend-flask,outide the container), 
# second period is the destination(backend-flask, inside the container). This works becasue we have set the working directory to /backend-flask
# For the source, you can also specify the path to the source directory
# For the destination, you can also specify the path to the destination directory
COPY . .

#Set the environment variables inside the container
ENV FLASK_ENV=development

EXPOSE ${PORT}

#Run the application
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]