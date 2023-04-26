# pollenprognos-card
A Lovelace card to display the sensor data from the integration [Home Assistant Pollenprognos integration](https://github.com/JohNan/homeassistant-pollenprognos).
![Screenshot 2022-08-05 at 22 37 45](https://user-images.githubusercontent.com/2181965/183159066-2cef1a6e-e59b-4bb3-832b-7bff781b471c.png)

## Requirement
- [Home Assistant Pollenprognos integration](https://github.com/JohNan/homeassistant-pollenprognos)

### Install with HACS
Add https://github.com/krissen/pollenprognos-card as a custom integration.
See more info: https://hacs.xyz/docs/faq/custom_repositories

## Credits
Small improvements to [pollen-card] by @nydayand , who in turn rewrote @isabellaalstrom [pollenprognos-card](https://github.com/isabellaalstrom/lovelace-pollenprognos-card).

## Options

| Name | Type | Default | Description
| ---- | ---- | ------- | -----------
| type | string | **Required** | `custom:pollen-card`
| city | string | **Required** | City from which you have sensors
| days_to_show | integer | **Optional** | How many days to show, 0 (only allergen) to 4.
| allergens | list | **Required** | List of allergens for which you have sensors
| title | boolean | **Optional** | Custom title if string, boolean value if generated or not to show. Default is generated text
| show_text | boolean | **Optional** | Set to `true` if you want to show the state text under the images

## Examples

<table>
<tr>
<td>0 days</td>
<td><img width="509" alt="card_0_days" src="https://user-images.githubusercontent.com/2943684/234618464-1d90b53a-61d7-4fe1-b5f8-10ae4cc17883.png"></td>
<td>

```yaml
cards:
  - type: 'custom:pollenprognos-card'
    city: Forshaga
    show_text: false
    days_to_show: 0
    allergens:
      - Al
      - Alm
      - Ambrosia
      - Björk
      - Ek
      - Gråbo
      - Gräs
      - Hassel
      - Sälg / vide
``` 
</td>
</tr>
<tr>
<td>2 days, no text</td>
<td><img width="510" alt="card_2_days_without_text" src="https://user-images.githubusercontent.com/2943684/234618818-0f5b4953-8604-48e9-b308-20a3887b45d8.png"></td>
<td>

```yaml
cards:
  - type: 'custom:pollenprognos-card'
    city: Forshaga
    show_text: false
    days_to_show: 2
    allergens:
      - Al
      - Alm
      - Ambrosia
      - Björk
      - Ek
      - Gråbo
      - Gräs
      - Hassel
      - Sälg / vide
```
</td>
</tr>
<tr>
<td>4 days, with text</td>
<td><img width="505" alt="card_4_days_with_text" src="https://user-images.githubusercontent.com/2943684/234618933-586749ed-04f2-4784-95ee-768265d2d14c.png"></td>
<td>

```yaml
cards:
  - type: 'custom:pollenprognos-card'
    city: Forshaga
    show_text: true
    days_to_show: 4
    allergens:
      - Al
      - Alm
      - Ambrosia
      - Björk
      - Ek
      - Gråbo
      - Gräs
      - Hassel
      - Sälg / vide
```
</td>
</tr>
</table>
