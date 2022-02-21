# Get g-sheets document as json to lovelace markdown card
<br>

`Note: This tutorial assumes that you already have your document saved in google sheets and that you have your own api key.`

<br>

## Add this to your configuration.yaml

```yaml
sensor:
  - platform: rest
    name: {choose a name}
    resource: https://sheets.googleapis.com/v4/spreadsheets/{your-gsheets-file-url-link}/values/{sheet-name-and-range}?key={api-key}
    value_template: "Ok" #so that you don't get the "max length is 255 characters" error
    json_attributes:
      - values
    scan_interval: 60 #polling interval
```
<br>

Now that we have already data coming in, let's display it.
Keep in mind that your new "sensor" is receiving the full json as an attribute.
Eg.

<br>

<p align="center">
  <img src="https://github.com/mtippt/Images/blob/main/json_example.png?raw=true" alt="example_json_received" style="height: 350px; width:275px;"/>
</p>

<br>

Finally you have your variable and you can manipulate it as you normally do.

Eg.

<p align="center">
  <img src="https://github.com/mtippt/Images/blob/main/json_card_example.png?raw=true" alt="example_json_received" style="height: 250px; width:400px;"/>
</p>