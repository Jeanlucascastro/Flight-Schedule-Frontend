<template>
<div class="mx-auto" style="width: 100px;">

<v-footer
color="primary loghten-1"
padless
>

<v-row 
justify="center"
no-gutters
color="black"
>
<n-btn
v-for="link in links"
:key="link"
color="black"
text
rounded
class="my-2"
>
{{link}}
</n-btn>
<v-col
class="primary lighten-2 py-4 text-center black--text"
cols="12"
>

{{new Date().getFullYear()}} - <strong>Flight</strong>
</v-col>
</v-row> 
</v-footer>
</div>
</template>

<script>
export default {
  name: 'Footer'
}
</script>