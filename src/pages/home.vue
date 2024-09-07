<template>
  <div class="mb-body">
    <div class="card__wrapper" v-for="item in items" :key="item.id">
      <Card :name="`${item.lvl} LVL`" :title="item.title" :imgUrl="item.img">
        {{ item.descr }}
      </Card>
    </div>
</div>
</template>

<script>
import Card from '@/components/UI/Card'

import items from '@/seeders/items.js'

export default {
  components: { 
    Card 
  },
  data () {
    return {
      items: items
    }
  }
}
</script>