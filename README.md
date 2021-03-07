<p align="center">
  <img src="https://raw.githubusercontent.com/awtkns/fastapi-crudrouter/master/docs/en/docs/assets/logo.png" height="200" />
</p>
<p align="center">
  <em>⚡ Create CRUD routes with lighting speed</em> ⚡</br>
  <sub>A dynamic FastAPI router that automatically creates CRUD routes for your models</sub>
</p>
<p align="center">
<img alt="Tests" src="https://github.com/awtkns/fastapi-crudrouter/workflows/Python%20application/badge.svg" />
<img alt="Docs" src="https://github.com/awtkns/fastapi-crudrouter/workflows/docs/badge.svg" />
  <a href="https://pypi.org/project/fastapi-crudrouter" target="_blank">
    <img src="https://img.shields.io/pypi/v/fastapi-crudrouter?color=%2334D058&label=pypi%20package" alt="Package version">
</a>
</p>

---

**Documentation**: <a href="https://fastapi-crudrouter.awtkns.com" target="_blank">https://fastapi-crudrouter.awtkns.com</a>

**Source Code**: <a href="https://github.com/awtkns/fastapi-crudrouter" target="_blank">https://github.com/awtkns/fastapi-crudrouter</a>

---
Tired of rewriting the same generic CRUD routes? Need to rapidly prototype a feature for a presentation
or a hackathon? Thankfully, [fastapi-crudrouter](https://github.com/awtkns/fastapi-crudrouter) has your back. As an 
extension to the APIRouter included with [FastAPI](https://fastapi.tiangolo.com/), the FastAPI CRUDRouter will automatically
generate and document your CRUD routes for you, all you have to do is pass your model and maybe your database connection.

FastAPI-CRUDRouter is also **lighting fast**, well tested, and **production ready**.


## Installation
```bash
pip install fastapi-crudrouter
```

## Basic Usage
Below is a simple example of what the CRUDRouter can do. In just ten lines of code, you can generate all 
the crud routes you need for any model.  A full list of the routes generated can be found [here](./routing).

```python
from pydantic import BaseModel
from fastapi import FastAPI
from fastapi_crudrouter import MemoryCRUDRouter as CRUDRouter

class Potato(BaseModel):
    id: int
    color: str
    mass: float

app = FastAPI()
app.include_router(CRUDRouter(schema=Potato))
```

## Advanced Usage
fastapi-crudrouter provides a number of features that allow you to get the most out of your automatically generated CRUD
routes. Listed below are some highlights.

- Automatic Pagination ([docs](https://fastapi-crudrouter.awtkns.com/pagination/))
- Ability to Provide Custom Create and Update Schemas ([docs](https://fastapi-crudrouter.awtkns.com/schemas/))
- Dynamic Generation of Create and Update Schemas ([docs](https://fastapi-crudrouter.awtkns.com/schemas/))
- Ability to Add, Customize, or Disable Specific Routes ([docs](https://fastapi-crudrouter.awtkns.com/routing/))
- Native Support for FastAPI Dependencies Injection ([docs](https://fastapi-crudrouter.awtkns.com/dependencies/))

## Supported Backends / ORMs
fastapi-crudrouter currently supports a number of backends / ORMs. Listed below are the backends currently supported. This list will
likely grow in future releases.

- In Memory ([docs](https://fastapi-crudrouter.awtkns.com/backends/memory/))
- SQLAlchemy ([docs](https://fastapi-crudrouter.awtkns.com/backends/sqlalchemy/))
- Databases (async) ([docs](https://fastapi-crudrouter.awtkns.com/backends/async/))
- Tortoise ORM  (async) ([docs](https://fastapi-crudrouter.awtkns.com/backends/tortoise/))

## OpenAPI Support
By default, all routes generated by the CRUDRouter will be documented according to OpenAPI spec.

Below are the default routes created by the CRUDRouter shown in the generated OpenAPI documentation.

![OpenAPI Route Overview](https://raw.githubusercontent.com/awtkns/fastapi-crudrouter/master/docs/en/docs/assets/RouteOverview.png)

The CRUDRouter is able to dynamically generate detailed documentation based on the models given to it.

![OpenAPI Route Detail](https://raw.githubusercontent.com/awtkns/fastapi-crudrouter/master/docs/en/docs/assets/RouteDetail.png)
