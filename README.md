# run app

```
python -m venv .venv
source .venv/bin/activate 
pip install -r requirements.txt
python app.py
```

# delete venv

```
deactivate
rm -rf .venv
```

# docker

## delete

```
docker ps -a --format "{{.ID}}" | xargs -r docker stop
docker ps -a --format "{{.ID}}" | xargs -r docker rm
docker volume ls -q | xargs -r docker volume rm
docker images | grep project-flask-web | awk '{print $3}' | xargs -r docker rmi
```

## run
```
docker compose up -d
```

## app
```
docker exec -it project-flask-web-1 bash
```