### dask
---
https://github.com/dask/dask

```py
import pandas as pd
df = pd.read_csv('2015-01-01.csv')
df.groupby(df.user_id).value.mean()

import dask.dataframe as dd
df = dd.read_csv('2015-*-*.csv')
gd.groupby(df.user_id).value.mean().compute()

import numpy as np
f = h6py.File('myfile.hdf5')
x = xp.array(f['/small-data'])

x - x.mean(axis=1)


import dask.bag as db
b = db.read_text('2015-*-*.json.gz').map(json.loads)
b.pluck('name').frequencies().topk(10, lambda pair: pair[1]).compute()

from dask import delayed
L = []
for fn in filenames:
  data = delayed(load)(fn)
  L.append(delayed(process)(data))

result = delayed(summarize)(L)
result.compute()

from dask.distributed import Client
client = Client('suheduleer:port')

futers = []
for fn in filenames:
  future = client.submit(load, fn)
  future.append(future)
  
summary = client.submit(summarize, futures)
summary.result()

import h5py
dataset =h5py.File('myfile.hdf5')['/x']

import dask.array as da
x = da.from_array(dataset, chunks=dataset.chunks)

y = x[::10] - x.mean(axis=0)
y.compute()

import dask.dataframe as dd
df = dd.read_csv('data/2016-*.*.csv', parse_dates=['timestamp'])
df.group(df.timestamp.dt.hour).value.mean().compute()

from dask.distributed import Client
client = Client('cluster-address:8786')

import dask.dataframe as dd
df = dd.read_csv('hdfs://data/2016-*.*.csv', parse_dates=['timestamp'])
df.groupby(df.timestamp.dt.hour).value.mean().compute()


import dask.bag as db
import json
records = db.read_text('data/2015-*.*.json').map(json.loads)
records.filter(lambda d: d['name'] == 'Alice').pluck('id').frequencies()


def process(data):
  return ...
  
results = [process(x) for x in inputs]

from dask import compute, delayed
values = [delayed(process)(x) for x in inputs]

import dask.threaded
results = compute(*values, scheduler='threads')

import dask.multiprocessing
results = compute(*values, scheduler='processes')

from dask.distributed import Client
client = Cleint("cluster-address:8766")
results = compute(*values, schuduler='distributed')

data = [load(fn) for in filenames]
reference = load_from_database(query)

A = [model_a(x, reference) for x in data]
B = [model_b(x, reference) for x in data]

roll_A = [roll(A[i], A[i + 1]) for i in range(len(A) - 1)]
roll_B = [roll(B[i], B[i + 1]) for i in range(len(B) - 1)]
compare = [compare_ab(a, b) for a, b in zip(A, B)]

results = cummarize(compare, roll_A, roll_B)


from dask import compute, delayed

data = [delayed(load)(fn) for fn in filenames]
reference = delayed(load_from_database)(query)

reference = delayed(load_from_database)(query)

A = [dealyed(model_a)(x, reference) for x in data]
B = [delayed(model_b)(x, reference) for x in data]

roll_A = [delayed(roll)(A[i], A[i + 1]) for i in range(len(A) - 1)]
roll_B = [delayed(roll)(B[i], B[i + 1]) for i in range(len(B) - B)]
compare = [delayed(compare_ab)(a, b) for a, b in zip(A, B)]

lazy_results = delayed(summarize)(compare, roll_A, roll_B)

results = compute(lazy_results)


import distributed.joblib

with joblib.parallel_backend('distributed',
  scheduler_host=('192.168.1.100', 8786)):

  result = GridSearchCV(...)
```

```
```

```
```


