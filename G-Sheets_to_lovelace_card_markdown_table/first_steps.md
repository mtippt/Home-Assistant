# Get g-sheets document as json to lovelace markdown card
<br>

`Note: This tutorial assumes that you already have your document saved in google sheets and that you have your own api key.`

<br>

## Add this to your configuration.yaml

```yaml
sensor:
  - platform: rest
    name: {choose a name}
    resource: https://sheets.googleapis.com/v4/spreadsheets/{your-gsheets-file-url-link}/values/{sheet-name}?key={api-key}
    value_template: "Ok" #so that you don't get the "max length is 255 characters" error
    json_attributes:
      - values
    scan_interval: 60 #polling interval
```

Now that we have already data coming in, let's display it.
Keep in mind that your new "sensor" is receiving the full json as an attribute.
Example:

![example_json_received](/Images/json_example.png "Json example")