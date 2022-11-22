```
usage: clean [-f {rfill,cfill,rbfill,cbfill,rffill,bffill}] [--drop {rdrop,cdrop}] [-d {}] [-h] [-l LIMIT]
```

Clean a dataset by filling and/or dropping NaN values.

```
optional arguments:
  -f {rfill,cfill,rbfill,cbfill,rffill,bffill}, --fill {rfill,cfill,rbfill,cbfill,rffill,bffill}
                        The method of filling NaNs. This has options to fill rows (rfill, rbfill, rffill) or fill columns (cfill, cbfill, cffill).
                        Furthermore, it has the option to forward fill and backward fill (up to --limit) which refer to how many rows/columns can be
                        set equal to the last non-NaN value (default: )
  --drop {rdrop,cdrop}  The method of dropping NaNs. This either has the option rdrop (drop rows that contain NaNs) or cdrop (drop columns that contain
                        NaNs) (default: )
  -d {}, --target-dataset {}
                        The name of the dataset you want to select (default: None)
  -h, --help            show this help message (default: False)
  -l LIMIT, --limit LIMIT
                        Number of entries to show in data. (default: 5)

For more information and examples, use 'about clean' to access the related guide.
```

Example:
```
(🦋) /forecast/ $ show TSLA

TSLA dataset has shape (row, column): (611, 7)

                    Dataset TSLA | Showing 10 of 611 rows
┏━━━┳━━━━━━━━━━━━┳━━━━━━━━┳━━━━━━━━┳━━━━━━━━┳━━━━━━━━┳━━━━━━━━━━━┳━━━━━━━━━━━┓
┃   ┃ date       ┃ open   ┃ high   ┃ low    ┃ close  ┃ adj_close ┃ volume    ┃
┡━━━╇━━━━━━━━━━━━╇━━━━━━━━╇━━━━━━━━╇━━━━━━━━╇━━━━━━━━╇━━━━━━━━━━━╇━━━━━━━━━━━┩
│ 0 │ 2020-01-02 │ 84.90  │ 86.14  │ 84.34  │ 86.05  │ 86.05     │ 47660500  │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┤
│ 1 │ 2020-01-03 │ 88.10  │ 90.80  │ 87.38  │ 88.60  │ 88.60     │ 88892500  │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┤
│ 2 │ 2020-01-06 │ 88.09  │ 90.31  │ 88.00  │ 90.31  │ 90.31     │ 50665000  │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┤
│ 3 │ 2020-01-07 │ 92.28  │ 94.33  │ 90.67  │ 93.81  │ 93.81     │ 89410500  │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┤
│ 4 │ 2020-01-08 │ 94.74  │ 99.70  │ 93.65  │ 98.43  │ 98.43     │ 155721500 │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┤
│ 5 │ 2020-01-09 │ 99.42  │ 99.76  │ 94.57  │ 96.27  │ 96.27     │ 142202000 │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┤
│ 6 │ 2020-01-10 │ 96.36  │ 96.99  │ 94.74  │ 95.63  │ 95.63     │ 64797500  │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┤
│ 7 │ 2020-01-13 │ 98.70  │ 105.13 │ 98.40  │ 104.97 │ 104.97    │ 132588000 │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┤
│ 8 │ 2020-01-14 │ 108.85 │ 109.48 │ 104.98 │ 107.58 │ 107.58    │ 144981000 │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┤
│ 9 │ 2020-01-15 │ 105.95 │ 107.57 │ 103.36 │ 103.70 │ 103.70    │ 86844000  │
└───┴────────────┴────────┴────────┴────────┴────────┴───────────┴───────────┘

```
```
(🦋) /forecast/ $ rsi TSLA --period 30
Successfully added 'RSI_30' to 'TSLA' dataset

(🦋) /forecast/ $ show TSLA
TSLA dataset has shape (row, column): (611, 8)

                         Dataset TSLA | Showing 10 of 611 rows
┏━━━┳━━━━━━━━━━━━┳━━━━━━━━┳━━━━━━━━┳━━━━━━━━┳━━━━━━━━┳━━━━━━━━━━━┳━━━━━━━━━━━┳━━━━━━━━┓
┃   ┃ date       ┃ open   ┃ high   ┃ low    ┃ close  ┃ adj_close ┃ volume    ┃ RSI_30 ┃
┡━━━╇━━━━━━━━━━━━╇━━━━━━━━╇━━━━━━━━╇━━━━━━━━╇━━━━━━━━╇━━━━━━━━━━━╇━━━━━━━━━━━╇━━━━━━━━┩
│ 0 │ 2020-01-02 │ 84.90  │ 86.14  │ 84.34  │ 86.05  │ 86.05     │ 47660500  │ nan    │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┼────────┤
│ 1 │ 2020-01-03 │ 88.10  │ 90.80  │ 87.38  │ 88.60  │ 88.60     │ 88892500  │ nan    │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┼────────┤
│ 2 │ 2020-01-06 │ 88.09  │ 90.31  │ 88.00  │ 90.31  │ 90.31     │ 50665000  │ nan    │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┼────────┤
│ 3 │ 2020-01-07 │ 92.28  │ 94.33  │ 90.67  │ 93.81  │ 93.81     │ 89410500  │ nan    │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┼────────┤
│ 4 │ 2020-01-08 │ 94.74  │ 99.70  │ 93.65  │ 98.43  │ 98.43     │ 155721500 │ nan    │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┼────────┤
│ 5 │ 2020-01-09 │ 99.42  │ 99.76  │ 94.57  │ 96.27  │ 96.27     │ 142202000 │ nan    │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┼────────┤
│ 6 │ 2020-01-10 │ 96.36  │ 96.99  │ 94.74  │ 95.63  │ 95.63     │ 64797500  │ nan    │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┼────────┤
│ 7 │ 2020-01-13 │ 98.70  │ 105.13 │ 98.40  │ 104.97 │ 104.97    │ 132588000 │ nan    │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┼────────┤
│ 8 │ 2020-01-14 │ 108.85 │ 109.48 │ 104.98 │ 107.58 │ 107.58    │ 144981000 │ nan    │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┼────────┤
│ 9 │ 2020-01-15 │ 105.95 │ 107.57 │ 103.36 │ 103.70 │ 103.70    │ 86844000  │ nan    │
└───┴────────────┴────────┴────────┴────────┴────────┴───────────┴───────────┴────────┘

(🦋) /forecast/ $ clean TSLA -f rfill
Namespace(drop='', fill='rfill', help=False, limit=5, target_dataset='TSLA')
Successfully cleaned 'TSLA' dataset

(🦋) /forecast/ $ show TSLA
2022 Jul 11, 14:20 (🦋) /forecast/ $ show TSLA
TSLA dataset has shape (row, column): (611, 8)

                         Dataset TSLA | Showing 10 of 611 rows
┏━━━┳━━━━━━━━━━━━┳━━━━━━━━┳━━━━━━━━┳━━━━━━━━┳━━━━━━━━┳━━━━━━━━━━━┳━━━━━━━━━━━┳━━━━━━━━┓
┃   ┃ date       ┃ open   ┃ high   ┃ low    ┃ close  ┃ adj_close ┃ volume    ┃ RSI_30 ┃
┡━━━╇━━━━━━━━━━━━╇━━━━━━━━╇━━━━━━━━╇━━━━━━━━╇━━━━━━━━╇━━━━━━━━━━━╇━━━━━━━━━━━╇━━━━━━━━┩
│ 0 │ 2020-01-02 │ 84.90  │ 86.14  │ 84.34  │ 86.05  │ 86.05     │ 47660500  │ 0.00   │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┼────────┤
│ 1 │ 2020-01-03 │ 88.10  │ 90.80  │ 87.38  │ 88.60  │ 88.60     │ 88892500  │ 0.00   │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┼────────┤
│ 2 │ 2020-01-06 │ 88.09  │ 90.31  │ 88.00  │ 90.31  │ 90.31     │ 50665000  │ 0.00   │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┼────────┤
│ 3 │ 2020-01-07 │ 92.28  │ 94.33  │ 90.67  │ 93.81  │ 93.81     │ 89410500  │ 0.00   │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┼────────┤
│ 4 │ 2020-01-08 │ 94.74  │ 99.70  │ 93.65  │ 98.43  │ 98.43     │ 155721500 │ 0.00   │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┼────────┤
│ 5 │ 2020-01-09 │ 99.42  │ 99.76  │ 94.57  │ 96.27  │ 96.27     │ 142202000 │ 0.00   │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┼────────┤
│ 6 │ 2020-01-10 │ 96.36  │ 96.99  │ 94.74  │ 95.63  │ 95.63     │ 64797500  │ 0.00   │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┼────────┤
│ 7 │ 2020-01-13 │ 98.70  │ 105.13 │ 98.40  │ 104.97 │ 104.97    │ 132588000 │ 0.00   │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┼────────┤
│ 8 │ 2020-01-14 │ 108.85 │ 109.48 │ 104.98 │ 107.58 │ 107.58    │ 144981000 │ 0.00   │
├───┼────────────┼────────┼────────┼────────┼────────┼───────────┼───────────┼────────┤
│ 9 │ 2020-01-15 │ 105.95 │ 107.57 │ 103.36 │ 103.70 │ 103.70    │ 86844000  │ 0.00   │
└───┴────────────┴────────┴────────┴────────┴────────┴───────────┴───────────┴────────┘

```