
# VectorDB

`VectorDB` is a simple and efficient Python library for managing and querying vector-based databases using FAISS and Transformer models. It is designed to help you create, manage, update, and search through embeddings with ease.

## Installation

Install `VectorDB` from PyPI using pip:

```bash
pip install free-search
```

## Usage

### Import the Library

Start by importing the necessary components:

```python
from free_search.db import VectorDB
```

### Initialize the Database

To initialize a vector database, create an instance of `VectorDB`:

```python
free_db = VectorDB()
```

### Create the Database

You can create a vector database with a list of texts. These texts will be embedded using a Transformer model, and the embeddings will be stored in the FAISS index.

```python
free_db.create_db(["天氣好", "心情好", "食慾好"])
```

### Add Data

To add new data to the existing database:

```python
free_db.add_data(["今天心情很棒", "早餐很好吃"])
```

### Update Data

To update a specific item in the database, provide the index of the item and the new text:

```python
free_db.update_data(1, "心情非常好")
```

### Delete Data

You can delete data by specifying the indices of the items you want to remove:

```python
free_db.delete_data([0])
```

### Search the Database

To search the database with a query, specify the query text and the number of top results (k) to return:

```python
results = free_db.search(["心情好"], k=2)
for result in results:
    print(result)
```

### Save and Load the Database

To save the current state of the database (index and texts) to files:

```python
free_db.save_index("index.faiss", "texts.json")
```

To load a previously saved database:

```python
free_db.load_index("index.faiss", "texts.json")
```

### Print All Data

You can print all the current data stored in the database:

```python
free_db.print_all_data()
```

### Export Data

To export all the data from the database as a list:

```python
exported_data = free_db.export_data()
print(exported_data)
```

## Batch Operations

`VectorDB` also supports batch operations for adding, updating, and deleting data.

- **Batch Add**:
  ```python
  free_db.batch_add(["新資料1", "新資料2"])
  ```

- **Batch Update**:
  ```python
  free_db.batch_update([0, 1], ["更新後資料1", "更新後資料2"])
  ```

- **Batch Delete**:
  ```python
  free_db.batch_delete([0, 1])
  ```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
