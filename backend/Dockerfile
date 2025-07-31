# Create an image based on the base image
# that contains the OS files and Python 3.9 interpreter.
FROM python:3.9

# Let's go to the /app directory in the image, which is where we'll store the project code.
# If there is no directory with the specified name, it will be created. 
# The directory name can be anything.
WORKDIR /app

RUN pip install gunicorn==20.1.0

# Further instructions will be executed in the /app directory.
# Copy the dependency file from the local computer
# to the current directory (the current directory is /app).
COPY requirements.txt .

# In the current directory, execute the terminal command
# to install dependencies.
RUN pip install -r requirements.txt --no-cache-dir

# Copy all the required contents 
# of the local computer's directory where the Dockerfile is saved
# to the current working directory of the image, i.e. /app.
COPY . .

# When the container starts, run the development server.
CMD ["gunicorn", "--bind", "0.0.0.0:8000", "backend.wsgi"]
