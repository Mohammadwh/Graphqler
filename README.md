# Graphqler

Graphqler is a tool for inspecting GraphQL schemas and executing queries or mutations. It can load a schema from a file or fetch it live from a GraphQL endpoint.


## Features

- Load schema from file or fetch from endpoint
- Auto-completion for query and mutation names
- Construct and execute GraphQL queries and mutations
- Save requests and responses to logs

## Installation

To install the required dependencies, run:

```bash
pip install -r requirements.txt
```

## Usage
You can run Graphqler with either an introspection file or a live GraphQL endpoint. 

### Using an Introspection File
To load a schema from a file and inspect it:
```bash
python Graphqler.py -f <path_to_introspection_file.json>
```

Example
```bash
python Graphqler.py -f schema.json
```

### Using a Live GraphQL Endpoint
To fetch a schema from a live endpoint and inspect it:

```bash
python Graphqler.py -u <graphql_endpoint_url>
```

Example
```bash
python Graphqler.py -u https://example.com/graphql
```

Follow the prompts to select queries or mutations, provide arguments if necessary, and execute them.

## License
This project is licensed under the MIT License. 