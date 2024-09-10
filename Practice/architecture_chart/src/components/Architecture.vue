<script setup lang="ts">
  import { ref } from 'vue';
  import mermaid from 'mermaid';
  import { icons } from '@iconify-json/logos';
  mermaid.initialize({startOnLoad: true});
  mermaid.registerIconPacks([
    {
      name: icons.prefix, // To use the prefix defined in the icon pack
      icons,
    },
  ]);

  const chartData = ref(`
  architecture-beta
    group api(logos:aws-lambda)[API]

    service db(logos:aws-aurora)[Database] in api
    service disk1(logos:aws-glacier)[Storage] in api
    service disk2(logos:aws-s3)[Storage] in api
    service server(logos:aws-ec2)[Server] in api

    db:L -- R:server
    disk1:T -- B:server
    disk2:T -- B:db
  `);
</script>

<template>
  <!-- Mermaidのチャートを描画 -->
  <div class="mermaid" v-html="chartData"></div>

</template>

