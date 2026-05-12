[![PyPI version](https://badge.fury.io/py/pyoverseerrcontinued.svg)](https://badge.fury.io/py/pyoverseerrcontinued)

# pyoverseerrcontinued

This is a project for retrieving information from an Overseerr instance using their API, this is the first project I'm taking up from someone else, as the last commit from vaparr was 3 years ago.


# Installation

Run the following to install:
```python
pip install pyoverseerrcontinued
```


# Usage


#### Creating an object of your Overseerr instance

**Note:** You have to supply an `api_key` to successfully authenticate. Language parameter is optional, default is "en"

```python
import pyoverseerr

overseerr = pyoverseerr.Overseerr(
    url="192.168.1.120:5055",
    api_key="pixf64thuh2m7kbwwgkqp52yznbj4oyo",
    language="en"
)
```

#### Authenticate

```python
overseerr.authenticate()
```

#### Testing connection to Overseerr

```python
try:
    overseerr.test_connection()
except pyoverseerr.OverseerrError as e:
    print(e)
    return
```

#### Retrieving data
```python
movies = overseerr.movie_requests
tv = overseerr.tv_requests
music = overseerr.music_requests

total = overseerr.total_requests
```

#### Searching

```python
# Searching for movies with "Movie Name on the first page"
movie_search = overseerr.search_movie("Movie Name", 1)
# Searching for movies with "TV show name on the second page"
tv_search = overseerr.search_tv("TV show name", 2)
```

#### Requesting
```python
overseerr.request_movie("theMovieDbId")
overseerr.request_tv("theTvDbId", request_latest=True)
```

# License

This project is licensed under the MIT License - see the LICENSE.txt file for details.
