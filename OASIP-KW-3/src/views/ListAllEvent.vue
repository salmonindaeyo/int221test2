<script setup>

import EventList from '../components/EventListAllEmty.vue'
const getLinkAll = async () => {
  const res = await fetch(`http://ip21kw3.sit.kmutt.ac.th:8080/api/events`);
  if (res.status === 200) {
    eventLists.value = await res.json();
    console.log(eventLists.value);
    if (eventLists.value.length == 0) {
      check.value = false;
    }
  }
};
const eventLists = ref();


</script>
 
<template>
<div>
<EventList/>

</div>
</template>
 
<style>

</style>