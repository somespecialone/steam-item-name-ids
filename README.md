# <p align="center">Steam item name ids</p>

---

[![license](https://img.shields.io/github/license/somespecialone/steam-item-name-ids)](https://github.com/somespecialone/steam-item-name-ids/blob/master/LICENSE)
[![steam](https://shields.io/badge/steam-1b2838?logo=steam)](https://store.steampowered.com/)

List of `steammarket` item name id. Needed to fetch `itemhistogram` of some item.

---

### Does not include all items fow now.
### ⚠ All are welcome to complete the list ⚠

---

> GET https://steamcommunity.com/market/itemordershistogram

with params

```json5
{
  "country": "UA",
  "language": "ukrainian",
  "currency": 18,
  "item_nameid": 123456, // item id there
  "norender": 1
}
```

**Example**:
> https://steamcommunity.com/market/itemordershistogram?country=UA&language=ukrainian&currency=18&item_nameid=49399568&norender=1
> 