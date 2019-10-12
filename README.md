# Development

```sh
python -mvenv venv
source venv/activate
pip install -r requirements.txt
pelican --listen -sr pelicanconf.py
```


# Deployment
```
sudo pelican --port 8006 --listen
```
