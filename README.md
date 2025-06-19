# Cloud Mini-DB (GCP)
A lightweight in-memory key-value store with support for undo/redo, deployed on Google App Engine and backed by Google Cloud Datastore.
This app exposes a simple RESTful interface for variable manipulation, including value tracking, deletion, rollback, and more — perfect for demonstrating stateful logic on a stateless platform.


## Variable Commands Example:

| Route                 | Description                             |
|-----------------------|-----------------------------------------|
| `/`                   | Returns “Hello, World!”                 |
| `/set?name=x&value=5` | Sets `x = 5`                            |
| `/get?name=x`         | Returns value of `x`, or `None`         |
| `/unset?name=x`       | Deletes variable `x`                    |
| `/numequalto?value=5` | Returns number of variables set to `5`  |
| `/undo`               | Undoes last `SET` or `UNSET`            |
| `/redo`               | Redoes the last undone command          |
| `/end`                | Cleans the database (removes all data)  |
| `/list`               | Lists all variables and their values    |


### Bonus Feature – `list` Endpoint (Question 6)
**Endpoint:**  
`/list`  
**Description:**  
Lists all currently defined variables and their values.
**Example Response:**
```json
{
  "a": "10",
  "b": "20",
  "c": "30"
}
```
### Testing

The project includes a test file to help validate key commands like `/set`, `/get`, `/undo`, and `/redo`.

To run it locally:

```bash
python test_app.py
```

### Dependencies

All required packages are listed in `requirements.txt`. To install them locally:

```bash
pip install -r requirements.txt
```
