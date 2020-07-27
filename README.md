
# pg_bigm

pg_bigm 中文支持 比 pg_trgm 要好，pg_trgm 在 Mac osx 中不支持中文等 Unicode 字符，原因如下：

<https://www.postgresql-archive.org/pg-trgm-not-recognizing-Chinese-characters-in-macOS-td6037655.html>

The pg_bigm module provides full text search capability in [PostgreSQL](https://www.postgresql.org/).
This module allows a user to create **2-gram** (bigram) index for faster full text search.

pg_bigm is released under the [PostgreSQL License](https://opensource.org/licenses/postgresql), a liberal Open Source license, similar to the BSD or MIT licenses.

For more information look at [the official pg_bigm web site](https://pgbigm.osdn.jp/index_en.html).

# How to build

    make USE_PGXS=1 PG_CONFIG=`which pg_config` install

# How to use

```bash

    # sudo -u postgres psql
    # \c dbname

    create extension pg_bigm
    select show_bigm('做软件的禅师')

    # 相似度 0.71428573
    select bigm_similarity('哇！故宫的二十四节气-芒种', '芒种-哇！故宫的二十四节气');

```

## Test Status
[![Build Status](https://travis-ci.org/pgbigm/pg_bigm.svg?branch=master)](https://travis-ci.org/pgbigm/pg_bigm)
