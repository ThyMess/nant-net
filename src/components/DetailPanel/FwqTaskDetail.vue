<template>
    <div :data-clazz="model.clazz">
        <div class="panelTitle">{{i18n['fwqTask']}}</div>
        <div class="panelBody">
            <DefaultDetail :model="model" :onChange="onChange" :readOnly="readOnly" />
            <div class="panelRow">
                <div>{{i18n['fwqTask.fwqinfo']}}：</div>
                <el-input style="width:90%; font-size:12px"
                          :disabled="readOnly"
                          :value="model.fwqinfo"
                          @input="(value) => {onChange('fwqinfo', value)}" />
            </div>
        </div>
    </div>
</template>
<script>
  import DefaultDetail from "./DefaultDetail";
  export default {
    inject: ['i18n'],
    components: {
      DefaultDetail
    },
    props: {
      model: {
        type:Object,
        default: ()=>({}),
      },
      onChange: {
        type: Function,
        default: ()=>{}
      },
      readOnly:{
        type: Boolean,
        default: false,
      }
    },
  }
</script>
