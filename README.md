# rge-campaign-py

Pure-Python reader for **Age of Empires / Genie engine campaign containers**:
classic AoC-style `**.cpn` / `.cpx`** and Definitive Edition `**.aoe2campaign**`.

## Scope

This package exposes the lightweight campaign-index read path currently used by
the Museum minimap flow.

Supported:

- `.cpn`
- `.cpx`
- `.aoe2campaign`

Explicitly unsupported:

- `.aoecpn` / DE1 campaign containers

## Install

From PyPI:

```bash
pip install rge-campaign-py
```

From [TestPyPI](https://test.pypi.org/) (staging - use a new version string on
each upload):

```bash
pip install --index-url https://test.pypi.org/simple/ --extra-index-url https://pypi.org/simple/ rge-campaign-py
```

From Git:

```bash
pip install git+https://github.com/UnluckyForSome/rge-campaign-py.git
```

## Usage

```python
from rge_campaign_py import parse_campaign_index

with open("campaign.aoe2campaign", "rb") as f:
    campaign_name, scenarios = parse_campaign_index(f.read())
```

Each scenario row contains:

- `index`
- `offset`
- `size`
- `file_name`
- `label`

## Notes

This is a Python port of the campaign index read path inspired by
[withmorten/rge_campaign](https://github.com/withmorten/rge_campaign).