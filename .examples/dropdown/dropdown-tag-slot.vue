<script setup>
const frameworks = [
  { label: 'React', value: 'react', asset: 'https://reactjs.org/logo-og.png' },
  {
    label: 'Vue',
    value: 'vue',
    asset:
      'https://brandlogos.net/wp-content/uploads/2022/01/vue.js-logo-brandlogo.net_.png',
  },
  {
    label: 'Angular',
    value: 'angular',
    asset: 'https://angular.io/assets/images/logos/angular/angular.png',
  },
  {
    label: 'Svelte',
    value: 'svelte',
    asset:
      'https://upload.wikimedia.org/wikipedia/commons/thumb/1/1b/Svelte_Logo.svg/1200px-Svelte_Logo.svg.png',
  },
]
</script>

<template>
  <FormKit type="form" #default="{ value }" :actions="false">
    <FormKit
      type="dropdown"
      name="framework"
      label="Choose a frontend framework"
      placeholder="Example placeholder"
      :options="frameworks"
      :value="vue"
      multiple
			selection-appearance="tags"
    >
      <!--TAG SLOT-->
      <template #tag="{ handlers, option }">
        <div class="formkit-tag">
          <img :src="option.asset" class="formkit-tag-image" />
          <span class="formkit-tag-label">
            {{ option.label }}
          </span>
          <button
            @click.prevent="handlers.removeSelection(option)"
            tabindex="-1"
            type="button"
            aria-controls="input_1"
            class="formkit-remove-selection"
          >
            <span class="formkit-close-icon formkit-icon"
              ><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 12 16">
                <path
                  d="M10,12.5c-.13,0-.26-.05-.35-.15L1.65,4.35c-.2-.2-.2-.51,0-.71,.2-.2,.51-.2,.71,0L10.35,11.65c.2,.2,.2,.51,0,.71-.1,.1-.23,.15-.35,.15Z"
                  fill="currentColor"
                ></path>
                <path
                  d="M2,12.5c-.13,0-.26-.05-.35-.15-.2-.2-.2-.51,0-.71L9.65,3.65c.2-.2,.51-.2,.71,0,.2,.2,.2,.51,0,.71L2.35,12.35c-.1,.1-.23,.15-.35,.15Z"
                  fill="currentColor"
                ></path></svg>
              </span>
          </button>
        </div>
      </template>
      <!--/TAG SLOT-->
		</FormKit>
    <pre wrap>{{ value }}</pre>
  </FormKit>
</template>

<style>

.formkit-tag {
  display: flex;
  align-items: center;
}
.formkit-tag img {
  width: 20px;
  height: 20px;
  margin-right: 10px;
}
</style>

