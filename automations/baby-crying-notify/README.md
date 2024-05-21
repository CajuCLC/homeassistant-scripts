# Baby Crying Notify

This automation notifies and triggers actions when a baby crying sound is detected within five minutes from a specified camera.

## Usage

1. Browse the `baby_crying_notify.yaml` file to understand the automation.
2. Modify the code to fit your specific devices and setup requirements.
3. Create a new automation in Home Assistant using the modified YAML.

### Explanation

The condition checks if the baby crying sound was detected within the last 5 minutes. If you need to adjust this time frame, modify the `300` seconds value in the following code snippet:

```yaml
{{
  (as_timestamp(now()) - as_timestamp(states.binary_sensor.nursery_baby_cry_detected.last_changed) <= 300)
  and states('binary_sensor.nursery_baby_cry_detected') == 'on'
}}
```

## Author

- **CajuCLC**

## Creation Date

- **May 21, 2024**
