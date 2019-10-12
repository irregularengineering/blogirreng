# [testingyourpatience.com](https://www.testingyourpatience.com/)

## Stack

This is a [Pelican](http://docs.getpelican.com/en/stable/) statically generated blog utilizing the [Hyde](https://github.com/jvanz/pelican-hyde) theme.

### Development

These instructions are for python3 installations. If your distribution releases python2 only, please see [pyenv](https://github.com/pyenv/pyenv)

```sh
python -mvenv venv
source venv/activate
pip install -r requirements.txt
pelican -lrs pelicanconf.py
```


### Deployment
```sh
sudo pelican -lp 8006
```
