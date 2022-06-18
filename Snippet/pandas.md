<!-- omit in toc -->
# Introduction
Take note of some tips in pandas

<br />

<!-- omit in toc -->
# Table of Contents



# new columns from aggregation can be used by loc at the same time via referencing data as df
```python
ranking = (
        ratings.groupby("movieId")
        .agg(
            avg_rating=pd.NamedAgg(column="rating", aggfunc="mean"),
            num_ratings=pd.NamedAgg(column="userId", aggfunc="nunique"),
        )
        .loc[lambda df: df["num_ratings"] > min_ratings]
        .sort_values(["avg_rating", "num_ratings"], ascending=False)
    )
```