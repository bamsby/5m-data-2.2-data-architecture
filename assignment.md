# Assignment

## Brief

Write the Python codes for the following questions.

## Instructions

Paste the answer as Python in the answer code section below each question.

### Question 1

Question: How would you create a new hash in Redis to store information about a person, with `john_doe` as the key and include the name (`John Doe`), age (`35`), and email address (`john@email.com`)?

```python
import redis

r = redis.Redis(
  host='redis-10908.c252.ap-southeast-1-1.ec2.cloud.redislabs.com',
  port=10908,
  password='EgIvxgDuiuk2Sh5VnJzUGXDMtLrtK5Hk')
```

Answer:

```python
r.hset(
    'john_doe',
    mapping={
        "name": "John Doe",
        "age": 35,
        "email": "john@email.com",
    },
)
r.hgetall("john_doe")
```
{'name': 'John Doe', 'age': '35', 'email': 'john@email.com'}

### Question 2

Question: Write Python code to list the first 10 objects (blob name) in the "gcp-public-data-landsat" bucket, along with their sizes.

```python
from google.cloud import storage

client = storage.Client()
bucket = client.get_bucket("gcp-public-data-landsat")
```

Answer:

```python
blobs = bucket.list_blobs()

print("First 10 objects in {}:".format(bucket.name))
for ix, blob in enumerate(blobs):
    if ix < 10:
        print("Blob name: {}, Size: {} bytes".format(blob.name, blob.size))
    else:
        break
```
First 10 objects in gcp-public-data-landsat:
Blob name: LC08/01/001/002/LC08_L1GT_001002_20160817_20170322_01_T2/LC08_L1GT_001002_20160817_20170322_01_T2_ANG.txt, Size: 117255 bytes
Blob name: LC08/01/001/002/LC08_L1GT_001002_20160817_20170322_01_T2/LC08_L1GT_001002_20160817_20170322_01_T2_B1.TIF, Size: 75085385 bytes
Blob name: LC08/01/001/002/LC08_L1GT_001002_20160817_20170322_01_T2/LC08_L1GT_001002_20160817_20170322_01_T2_B10.TIF, Size: 40612836 bytes
Blob name: LC08/01/001/002/LC08_L1GT_001002_20160817_20170322_01_T2/LC08_L1GT_001002_20160817_20170322_01_T2_B11.TIF, Size: 39267654 bytes
Blob name: LC08/01/001/002/LC08_L1GT_001002_20160817_20170322_01_T2/LC08_L1GT_001002_20160817_20170322_01_T2_B2.TIF, Size: 76259448 bytes
Blob name: LC08/01/001/002/LC08_L1GT_001002_20160817_20170322_01_T2/LC08_L1GT_001002_20160817_20170322_01_T2_B3.TIF, Size: 76813565 bytes
Blob name: LC08/01/001/002/LC08_L1GT_001002_20160817_20170322_01_T2/LC08_L1GT_001002_20160817_20170322_01_T2_B4.TIF, Size: 78510140 bytes
Blob name: LC08/01/001/002/LC08_L1GT_001002_20160817_20170322_01_T2/LC08_L1GT_001002_20160817_20170322_01_T2_B5.TIF, Size: 80344717 bytes
Blob name: LC08/01/001/002/LC08_L1GT_001002_20160817_20170322_01_T2/LC08_L1GT_001002_20160817_20170322_01_T2_B6.TIF, Size: 76416634 bytes
Blob name: LC08/01/001/002/LC08_L1GT_001002_20160817_20170322_01_T2/LC08_L1GT_001002_20160817_20170322_01_T2_B7.TIF, Size: 73888286 bytes

## Submission

- Submit the URL of the GitHub Repository that contains your work to NTU black board.
- Should you reference the work of your classmate(s) or online resources, give them credit by adding either the name of your classmate or URL.
