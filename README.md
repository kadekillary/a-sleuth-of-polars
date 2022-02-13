# Polars Cheatsheet
To help myself learn [polars](https://www.pola.rs)

* dataset used -> pokemon

```python
poke_url = https://gist.githubusercontent.com/armgilles/194bcff35001e7eb53a2a8b441e8b2c6/raw/92200bc0a673d5ce2110aaad4544ed6c4010f687/pokemon.csv
```

* reading multiples files

```python
# use glob
df = pl.read_csv("*.csv")
```

* reading from url -> used as example throughout

```python
df = pl.read_csv(poke_url)

# >> df
# shape: (800, 13)
# ┌─────┬────────────────┬─────────┬────────┬─────┬─────────┬───────┬────────────┬───────────┐
# │ #   ┆ Name           ┆ Type 1  ┆ Type 2 ┆ ... ┆ Sp. Def ┆ Speed ┆ Generation ┆ Legendary │
# │ --- ┆ ---            ┆ ---     ┆ ---    ┆     ┆ ---     ┆ ---   ┆ ---        ┆ ---       │
# │ i64 ┆ str            ┆ str     ┆ str    ┆     ┆ i64     ┆ i64   ┆ i64        ┆ bool      │
# ╞═════╪════════════════╪═════════╪════════╪═════╪═════════╪═══════╪════════════╪═══════════╡
# │ 1   ┆ Bulbasaur      ┆ Grass   ┆ Poison ┆ ... ┆ 65      ┆ 45    ┆ 1          ┆ false     │
# ├╌╌╌╌╌┼╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌┼╌╌╌╌╌╌╌╌╌┼╌╌╌╌╌╌╌╌┼╌╌╌╌╌┼╌╌╌╌╌╌╌╌╌┼╌╌╌╌╌╌╌┼╌╌╌╌╌╌╌╌╌╌╌╌┼╌╌╌╌╌╌╌╌╌╌╌┤
# │ 2   ┆ Ivysaur        ┆ Grass   ┆ Poison ┆ ... ┆ 80      ┆ 60    ┆ 1          ┆ false     │
# ├╌╌╌╌╌┼╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌┼╌╌╌╌╌╌╌╌╌┼╌╌╌╌╌╌╌╌┼╌╌╌╌╌┼╌╌╌╌╌╌╌╌╌┼╌╌╌╌╌╌╌┼╌╌╌╌╌╌╌╌╌╌╌╌┼╌╌╌╌╌╌╌╌╌╌╌┤
# │ 3   ┆ Venusaur       ┆ Grass   ┆ Poison ┆ ... ┆ 100     ┆ 80    ┆ 1          ┆ false     │
# ├╌╌╌╌╌┼╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌╌┼╌╌╌╌╌╌╌╌╌┼╌╌╌╌╌╌╌╌┼╌╌╌╌╌┼╌╌╌╌╌╌╌╌╌┼╌╌╌╌╌╌╌┼╌╌╌╌╌╌╌╌╌╌╌╌┼╌╌╌╌╌╌╌╌╌╌╌┤
# │ 3   ┆ VenusaurMega   ┆ Grass   ┆ Poison ┆ ... ┆ 120     ┆ 80    ┆ 1          ┆ false     │
# │     ┆ Venusaur       ┆         ┆        ┆     ┆         ┆       ┆            ┆           │
# └─────┴────────────────┴─────────┴────────┴─────┴─────────┴───────┴────────────┴───────────┘
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
