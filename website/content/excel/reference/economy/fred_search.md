<!-- markdownlint-disable MD041 -->

Search for FRED series or economic releases by ID or string. This does not return the observation values, only the metadata. Use this function to find series IDs for `fred_series()`.

## Syntax

```excel wordwrap
=OBB.ECONOMY.FRED_SEARCH([query];[provider];[is_release];[release_id];[limit];[offset];[filter_variable];[filter_value];[tag_names];[exclude_tag_names])
```

### Example

```excel wordwrap
=OBB.ECONOMY.FRED_SEARCH()
```

---

## Parameters

| Name | Type | Description | Required |
| ---- | ---- | ----------- | -------- |
| query | Text | The search word(s). | False |
| provider | Text | Options: fred, defaults to fred. | False |
| is_release | Boolean | Is release?  If True, other search filter variables are ignored. If no query text or release_id is supplied, this defaults to True. (provider: fred) | False |
| release_id | Any | A specific release ID to target. (provider: fred) | False |
| limit | Number | The number of data entries to return. (1-1000) (provider: fred) | False |
| offset | Number | Offset the results in conjunction with limit. (provider: fred) | False |
| filter_variable | Any | Filter by an attribute. (provider: fred) | False |
| filter_value | Text | String value to filter the variable by.  Used in conjunction with filter_variable. (provider: fred) | False |
| tag_names | Text | A semicolon delimited list of tag names that series match all of.  Example: 'japan;imports' (provider: fred) | False |
| exclude_tag_names | Text | A semicolon delimited list of tag names that series match none of.  Example: 'imports;services'. Requires that variable tag_names also be set to limit the number of matching series. (provider: fred) | False |

---

## Return Data

| Name | Description |
| ---- | ----------- |
| release_id | The release ID for queries.  |
| series_id | The series ID for the item in the release.  |
| name | The name of the release.  |
| title | The title of the series.  |
| observation_start | The date of the first observation in the series.  |
| observation_end | The date of the last observation in the series.  |
| frequency | The frequency of the data.  |
| frequency_short | Short form of the data frequency.  |
| units | The units of the data.  |
| units_short | Short form of the data units.  |
| seasonal_adjustment | The seasonal adjustment of the data.  |
| seasonal_adjustment_short | Short form of the data seasonal adjustment.  |
| last_updated | The datetime of the last update to the data.  |
| notes | Description of the release.  |
| press_release | If the release is a press release.  |
| url | URL to the release.  |
| popularity | Popularity of the series (provider: fred) |
| group_popularity | Group popularity of the release (provider: fred) |