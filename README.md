# Penguin Frontend Application

This is the frontend for www.pengamous.org or pengamous.org


## Environment Variables

- `REFRESH_INTERVAL`: interval in milliseconds for page to refresh (default: 1000)
- `EXPIRE_INTERVAL`: how long a replica can go without being seen before we remove it from the display (default: 10s)
- `REMOVE_INTERVAL`: how long after `EXPIRE_INTERVAL` until we remove the icon (default: 20s)
- `SKIP_ERRORS`: set this to prevent errors from counting (useful on janky load balancers)
- `METADATA`: extra text at bottom of info area
- `CONTAINER_COLOR`: what color the container background should be (default: black). Valid options are any color from the CSS pallete, including:
  - red
  - orange
  - yellow
  - olive
  - green
  - teal
  - blue
  - violet
  - purple
  - pink
  - black
- `PETS`: The kind of pet shown in each container. Valid options are:
  - cows
  - chameleons
  - cowmeleons
  - penguins


## Paths

By default the loaded page will reach back to `/demo` every `REFRESH_INTERVAL` and use the returned information to update the display. Other paths are:

- `/info` - returns some additional information about the replica serving the request
- `/load` - adds a 2s delay to the response from `/info` - use this for putting artificial load on the system and watching the replicas scale

## Ports

The container will listen for traffic on port 8080.

