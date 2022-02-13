# Polars Cheatsheet
To help myself learn [polars](https://www.pola.rs)

* reading multiples files

```python
# use glob
df = pl.read_csv("*.csv")
```

* dealing with headers

```python
df.columns = [c.lower() for c in df.columns]
```

* filtering

* joining

* value counts

* missing values

* replacing missing values

* dropping columns

* dropping rows

* aggregation

* new columns
