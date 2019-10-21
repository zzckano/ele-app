<template>
  <div class="formblock">
    <div class="label-wrap">{{label}}</div>
    <div class="input-group-wrap" @click="$emit('click')">
      <div class="input-wrap">
        <input
          v-if="!textarea"
          :type="type"
          :value="value"
          :placeholder="placeholder"
          @input="$emit('input',$event.target.value)"
        >

        <textarea
          v-else
          :type="type"
          :value="value"
          :placeholder="placeholder"
          @input="$emit('input',$event.target.value)"
          rows="2"
          maxlength="100"
        ></textarea>
        <i v-if="icon" :class="'fa fa-'+icon"></i>
      </div>
      <TabTag v-if="tags" :tags="tags" :selectTag="sex" @checkTag="checkTag"/>
    </div>
  </div>
</template>

<script>
import TabTag from "./TabTag";
export default {
  name: "FormBlock",
  props: {
    type: {
      type: String,
      default: "text"
    },
    label: String,
    value: String,
    placeholder: String,
    icon: String,
    textarea: String,
    tags: Array,
    sex: String
  },
  methods: {
    checkTag(item) {
      // console.log(item);
      this.$emit("checkSex", item);
    }
  },
  components: {
    TabTag
  }
};
</script>

<style scoped>
.formblock {
  /* border-top: 0.266667vw solid #eee; */
  background-color: #fff;
  border-bottom: 1px solid #eee;
  display: flex;
}
.formblock .label-wrap {
  flex-basis: 17.333333vw;
  padding: 3.733333vw 0;
  line-height: 4.8vw;
  color: #333;
  font-weight: 700;
}
.input-group-wrap {
  flex: 1;
}
.input-wrap {
  flex: 1 1 0;
  padding: 3.733333vw 0;
  display: flex;
  align-items: center;
}
.input-wrap input {
  outline: none;
  line-height: 4.8vw;
  color: #333;
  border: none;
  flex: 1;
  padding-right: 4vw;
  padding-left: 0;
  font-size: 0.9rem;
}

.input-wrap textarea {
  outline: none;
  font-size: 0.9rem;
  line-height: 4.8vw;
  color: #333;
  border: none;
  flex: 1;
  padding-right: 4vw;
  padding-left: 0;
}
.input-wrap i {
  margin-right: 3.2vw;
  color: rgb(102, 102, 102);
  font-size: 1.2rem;
}
</style>
