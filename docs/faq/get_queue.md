# MA get_queue Action

This action allows you to retrieve the full details of a queue

![image](../assets/screenshots/service-call/get_queue.png)

The Queue ID can be found by inspecting the MA Player entity and finding the value for `active_queue`

The returned JSON is extensive and includes information about the current and next item in the queue. The [returned data can be used in templates](https://www.home-assistant.io/docs/scripts/perform-actions#use-templates-to-handle-response-data).

## Example

In this example `input_select.jukebox_player` holds the friendly name for a player and all MA player entity_id in the example begin with `ma_` (e.g. `media_player.ma_kitchen_speaker`)
```
script:
  get_now_playing:
    mode: queued
    alias: "Get Now Playing Track Name"
    sequence:
      - action: mass.get_queue
        data:
          queue_id: "{{ state_attr((expand(states.media_player) | selectattr('name' , 'search', states.input_select.jukebox_player.state, ignorecase=true ) | select('search', 'ma_') | map(attribute='entity_id') | join),'active_queue') }}"
        response_variable: queue_info
      - service: input_text.set_value
        data:
          entity_id: input_text.now_playing
          value: '{{ queue_info.current_item.name[:50] }}'
```
