A boilerplate for the baseten backend take home challenge using async python. It is optional to use this boilerplate but we do think it's gonna save you some precious time.

**See [PROBLEM.md](PROBLEM.md) for the problem definition**

# Prerequisite

- python >= 3.9
- [poetry](python-poetry.org/)

# Run

There's a simple makefile available to help starting commands, you can read the makefile to start the project manually. If you use vscode as code editor, we have defined basic project settings and some launch configurations you can use.

## With vscode

1. In a command line run `poetry install`
2. Open the workspace in vscode
3. `⇧⌘P` then choose `Python: Select Interpreter`
4. The interpreter is the virtual env associated with poetry it should be named `baseten-backend-take-home...`. 
   It can be found by looking at the first line of the `poetry install` command you ran earlier or by running `poetry env info`)
5. Make your changes
6. Open the run and debug tab `⇧⌘D` and run `Run: Server`

## With makefile
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

# Libraries Documentation

- Strawberry: https://strawberry.rocks/docs
- FastAPI: https://fastapi.tiangolo.com/
- AIOHTTP: https://docs.aiohttp.org/en/stable/
- Pydantic: https://pydantic-docs.helpmanual.io/

Feel free to replace any of those, we've provided a boilerplate to ease the start of the take home and free you some time.
