# Graphqler

Graphqler is a tool for inspecting GraphQL schemas and executing queries or mutations. It can load a schema from a file or fetch it live from a GraphQL endpoint.


## Features

- Load schema from file or fetch from endpoint
- Auto-completion for query and mutation names
- Construct and execute GraphQL queries and mutations
- Save requests and responses to logs

### Example
```bash
python Graphqler.py -u https://example.com/graphql
```
```bash
  __     __     ______     ______   __     ______     __   __
 /\ \  _ \ \   /\  __ \   /\__  _\ /\ \   /\  __ \   /\ "-.\ \
 \ \ \/ ".\ \  \ \  __ \  \/_/\ \/ \ \ \  \ \ \/\ \  \ \ \-.  \
  \ \__/".~\_\  \ \_\ \_\    \ \_\  \ \_\  \ \_____\  \ \_\"\_ \
   \/_/   \/_/   \/_/\/_/     \/_/   \/_/   \/_____/   \/_/ \/_/
                https://github.com/TheWation/Graphqler

[~] Fetched schema from live endpoint.

[+] Queries: ['admins', 'products', 'product']
[+] Mutations: ['addAdmin', 'addProduct', 'addComment']
[?] Select a query/mutation (or type "exit" to quit): products

QUERY: products
  Arg: limit, Type: Int
  Arg: offset, Type: Int

Return Type: Product
  Field: id, Type: ID
  Field: name, Type: String
  Field: price, Type: Float
  Field: image, Type: String
  Field: comments, Type: Comment

[?] Do you want to create a query for this? (Y/n, default is no): y
[?] Enter value for limit (Int): 100
[?] Enter value for offset (Int): 0

Available fields for Product: id, name, price, image, comments
Enter fields to include (comma-separated): id,price,image

[?] Do you want to send this request? (y/N, default is no): y
Constructed GraphQL Query:

        query {
            products(limit: 100, offset: 0) {
                id price image
            }
        }


[+] Response from server:
{'data': {'products': [{'id': '1', 'price': 5990000, 'image': '6847927.jpg'}, {'id': '2', 'price': 4999000, 'image': '10578885.jpg'}, {'id': '3', 'price': 5590000, 'image': '3483290.jpg'}]}}

[?] Do you want to save this request and response? (y/N, default is no): y
```
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