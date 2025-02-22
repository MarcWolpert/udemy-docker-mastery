# use the README.md file for requirements to build this image
# If you get stuck, the answer/ directory has the solution
FROM python:slim

WORKDIR /app

COPY requirements.txt .

RUN pip install --no-cache-dir -r requirements.txt

COPY . .

# creates persistent data for the container
# when you run the container, the data will be stored in the host machine
# in the directory you specify with the -v flag
VOLUME /app/data

#runs the script when the container starts
ENTRYPOINT ["./docker-entrypoint.sh"]

# this is a web server
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]

# docker build -t assignment02 .
# docker run -v $(pwd)/data-default/ -p 8000:8000 assignment02