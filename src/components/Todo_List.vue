<template>
  <div>
    <ul>
        {{ todos }}
        <Todo_Item />
    </ul>

  </div>
</template>

<script>
import Todo_Item from '@/components/Todo_Item.vue'
export default {
  props: ['todos'],
  components: {
    Todo_Item
  }
}

</script>