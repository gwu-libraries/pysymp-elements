# pySympElements

A Python library for interacting with the Symplectic Elements API, providing easy access to publications, users, groups, and relationships as Python objects.

## Installation

```bash
pip install pysymp-elements
```

## Usage

```python
from pysymp_elements import APIClient

# Initialize the client
client = APIClient(
    base_url='https://your-instance.symplectic.co.uk/',
    username='your-username',
    password='your-password'
)

# Get a list of publications
publications = client.get_publications(detail='full')

# Get a specific user
user = client.get_object('users', 123, detail='full')

# Get relationships
relationships = client.get_relationships()

# Import a relationship
response = client.import_relationship(
    from_object='publication(1024)',
    to_object='user(4)',
    type_name='publication-user-authorship'
)
```

## Features

- Retrieve publications, users, groups, and journals
- Access relationship data
- Import relationships
- Automatic XML parsing to Python objects
- Support for different detail levels (ref, full, single-record)

## Testing

To run the test suite:

```bash
pip install pytest
pytest
```

## API Documentation

The library wraps the Symplectic Elements API v6.13. For detailed API documentation, refer to your Elements instance's API documentation or the Postman collection.

## Development

To set up for development:

```bash
git clone <repository-url>
cd pysymp-elements
pip install -e .
```