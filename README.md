# vue-time-ticker

This component provides functionality to display realtime second by second update
of the time difference between passed time and the current time. All mounted components will use the single scheduler, so all repaint will be smooth enough. The scheduler is lazy, so if you have no mounted components, you will have zero timeouts.

### Setup

```
yarn add vue-time-ticker
```

or using `npm`

```
npm install vue-time-ticker
```

### Usage

```
<template>
  <div>
    <vue-time-ticker :value="getValue" format="HOURS" />
  </div>
</template>

<script>
import VueTimeTicker from 'vue-time-ticker';

export default {
  name: 'Counter',
  components: { VueTimeTicker },
  computed: {
    getValue() {
      // any source of data for your component
      return this.value;
    },
  },
};
</script>

```

## Props descriptions

| Prop name |  Type  |           Example values            | Description                                                                                         |
| :-------- | :----: | :---------------------------------: | --------------------------------------------------------------------------------------------------- |
| value     | String |        2020-03-20T00:00:00z         | Should be valid format for default JavaScript `new Date()` constructor                              |
| format    | String | One of: `HOURS`,`MINUTES`,`SECONDS` | Represents format of displaying the result, `HOURS`: `00:00:00`, `MINUTES`: `00:00`,`SECONDS`: `00` |
