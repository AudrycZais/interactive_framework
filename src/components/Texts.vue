<template>
  <div class="text">
    <hr />
    <div>
      <input type="checkbox" v-model="customization" />
      <div v-if="customization">
        <h2>Customization</h2>
        <div>
          <label for="font_primary"
            >Primary Font: {{ vars.font_primary }}
          </label>
          <input
            type="text"
            id="font_primary"
            v-model.lazy="vars.font_primary"
          />
          <span><a href="#">+</a></span>
        </div>
        <div>
          <label for="font_color">Font color: {{ vars.font_color }} </label>
          <input type="color" id="font_color" v-model="vars.font_color" />
        </div>
        <hr />
      </div>
    </div>
    <section>
      <h2>
        Text<span style="font-size: 0.5em">
          - {{ vars.font_primary }} | {{ vars.font_color }}</span
        >
      </h2>
      <p>
        This is <b>bold</b> and this is <strong>strong</strong>. This is
        <i>italic</i> and this is <em>emphasized</em>. This is
        <sup>superscript</sup> text and this is <sub>subscript</sub> text. This
        is <u>underlined</u> and this is code: <code>for (;;) { ... }</code>.
        Finally, this is a <a href="#">link</a>.
      </p>
      <p>
        Lorem, ipsum dolor sigt amet consectetur adipisicing elit. Non iusto
        minima molestiae mollitia neque praesentium, odit est velit nostrum nemo
        itaque consequuntur officia perspiciatis, veniam nam sunt aliquid
        asperiores natus?
      </p>
    </section>
    <hr />
  </div>
</template>

<script>
export default {
  data() {
    return {
      customization: false,
      vars: {
        font_primary: "Times, serif",
        font_color: "#000000",
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
