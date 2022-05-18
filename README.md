A boilerplate for the baseten backend take home challenge using async python.

**See [PROBLEM.md](PROBLEM.md) for the problem definition**

# Prerequisite

- python > 3.9
- [poetry](python-poetry.org/)

# Libraries Documentation

- Strawberry: https://strawberry.rocks/docs
- FastAPI: https://fastapi.tiangolo.com/
- AIOHTTP: https://docs.aiohttp.org/en/stable/

Feel free to replace any of those, we've provided a boilerplate to ease the start of the take home and free you some time.

# Run

There's a simple makefile available to help starting commands, you can read the makefile to start the project manually.

```sh
# Install dependencies
make install
# Run Mock API Server:
make mock_server
# Run Real Server:
make start
# Run linters+formatters
make lint
```

# Testing

Once the server runs `make start` you can open `http://localhost:8000/graphql` and test the API with a sample graphql query

```graphql
query {
  organizations {
    name
    id
  }
}
```
