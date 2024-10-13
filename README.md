# sync-paperpile-notion

Generated from [maria-antoniak/maria-paperpile-notion](https://github.com/maria-antoniak/maria-paperpile-notion) & [https://github.com/seba-1511/sync-paperpile-notion](https://github.com/seba-1511/sync-paperpile-notion). Follow the setup provided by them.

Slight changes to sync.py & sync_to_notion.yaml:

- Updated lines to prevent error: `actions/checkout@v4` line 11; `actions/setup-python@v5` line 14; `python-version: '3.x'` line 16 in [sync_to_notion.yaml](https://github.com/Elahekhezri/maria-paperpile-notion/blob/main/.github/workflows/sync_to_notion.yaml) 
    
- These columns are removed from [sync.py](https://github.com/Elahekhezri/maria-paperpile-notion/blob/main/sync.py): `Authors`, `Keywords`.

# Common problems when forking above repositories

## 1. Deprecated node12 & Node.js version

Solution -> commit the following changes to [sync_to_notion.yaml](https://github.com/Elahekhezri/maria-paperpile-notion/blob/main/.github/workflows/sync_to_notion.yaml):
- `actions/checkout@v3` ✖️ -> `actions/checkout@v4` ✔️

- `actions/setup-python@v4` ✖️ -> `actions/setup-python@v5` ✔️

- add `with: python-version: '3.x'` after `actions/setup-python@v5`

- add `--upgrade pip` to `Install Dependencies`

## 2. `sync to notion` failing

- Make sure Read and write permissions for workflow are granted (repository settings -> general -> actions -> workflow permissions)

- Make sure you've used the correct DATABASE_IDENTIFIER: **<long_hash_1>** in [https://www.notion.so/<long_hash_1>?v=<long_hash_2>](https://www.notion.so/<long_hash_1>?v=<long_hash_2>)
