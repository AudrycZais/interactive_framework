<template>
  <div>
    <hr />
    <div>
      <input type="checkbox" v-model="customization" />
      <div v-if="customization">
        <h2>Customization</h2>
        <div>
          <label for="form_input_width"
            >Form Input Width: {{ vars.form_input_width }}
          </label>
          <input
            type="range"
            id="form_input_width"
            v-model="vars.form_input_width"
          />
        </div>
        <hr />
      </div>
    </div>
    <form>
      <h2>Form inputs</h2>
      <div>
        <label for="input_1">Label 1</label>
        <input type="text" id="input_1" />
      </div>
    </form>
    <hr />
  </div>
</template>

<script>
export default {
  data() {
    return {
      customization: false,
      vars: {
        form_input_width: null,
      },
    };
  },
  watch: {
    vars: {
      handler(values) {
        for (const variable in values) {
          document.body.style.setProperty(`--${variable}`, values[variable]);
        }
      },
      deep: true,
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
</style>
