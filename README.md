# Steam item name ids

[![license](https://img.shields.io/github/license/somespecialone/steam-item-name-ids)](https://github.com/somespecialone/steam-item-name-ids/blob/master/LICENSE)
[![steam](https://shields.io/badge/steam-1b2838?logo=steam)](https://store.steampowered.com/)

List of `SteamMarket` item name id. Required to get the `itemordershistogram` of an item.

> [!WARNING]
> Does not include all items.

## Apps:

- [x] CS2 (ex. CSGO)
- [x] TF2

## Usage

### Structure

Each file is a dump of a `JSON` object with `market hash name` as key and `item_nameid` as value.

```json
{ "market hash name": 1234567 }
```

### How to get

#### Path

> GET https://steamcommunity.com/market/itemordershistogram

#### Params:

| Parameter name | Type            | Reference/Description                                                                                                                    |
| -------------- | --------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| country        | string          | Country code like "UA", "PL"                                                                                                             |
| language       | string          | [Language enum](https://github.com/somespecialone/aiosteampy/blob/22af4c174445332de3cc01d8c23f715246ee0902/aiosteampy/constants.py#L126) |
| currency       | integer         | [Currency enum](https://github.com/somespecialone/aiosteampy/blob/22af4c174445332de3cc01d8c23f715246ee0902/aiosteampy/constants.py#L60)  |
| item_nameid    | integer         | 👈                                                                                                                                       |
| norender       | integer/boolean | Whether to exclude `html` from the response                                                                                              |

**Example** params object:

```json5
{
  country: "UA",
  language: "ukrainian",
  currency: 18, // Ukrainian Hryvnia
  item_nameid: 123456, // <- item name id
  norender: 1, // exclude
}
```

**Example** `itemordershistogram` of [AK-47 | Slate (Field-Tested)](https://steamcommunity.com/market/listings/730/AK-47%20%7C%20Slate%20%28Field-Tested%29) request `URL`:

> https://steamcommunity.com/market/itemordershistogram?country=UA&language=ukrainian&currency=18&item_nameid=176241017&norender=1

## TODO 📃

- [ ] `github action` that validates `json` files for pull requests
- [ ] `github action` that creates `csv` files from originated `json` files for each pull request/commit

## See also 👀

- [Aiosteampy "fetch_item_orders_histogram" method](https://github.com/somespecialone/aiosteampy/blob/2a9af23dfe94550887e6643c1c130edbf2ef98f8/aiosteampy/mixins/public.py#L362)
