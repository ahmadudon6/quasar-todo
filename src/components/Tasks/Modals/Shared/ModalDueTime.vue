<template>
  <div 
       class="row q-mb-sm">
    <q-input outlined
             :value="dueTime"
             label="Due Time"
             @input="$emit('update:dueTime',$event)"
             class="col">
      <template v-slot:append>
        <q-icon v-if="dueTime"
                name="close"
                @click="$emit('clear')"
                class="cursor-pointer" />
        <q-icon name="access_time" class="cursor-pointer">
          <q-popup-proxy transition-show="scale" transition-hide="scale">
            <q-time :value="dueTime"
                    @input="$emit('update:dueTime',$event)"/>
          </q-popup-proxy>
        </q-icon>
      </template>
    </q-input>
  </div>
</template>

<script>
  export default {
    props: ['dueTime']
  }
</script>
