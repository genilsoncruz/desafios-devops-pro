FROM python:3.9
WORKDIR /app
RUN pip install --upgrade pip
COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt
COPY . ./
EXPOSE 80
CMD [ "python", "app.py" ]