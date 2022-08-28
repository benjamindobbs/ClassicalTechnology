<template>
 <ClassInfo
 :sectionInfo="sectionInfo">
 </ClassInfo>  
</template>

<script>
    import section from "../static/json/robotics.json";
    import ClassInfo from '../components/classInfo.vue';;
  export default {
    name:"ECS",
    icons: {
    iconfont: 'mdi', 
  },
  data: () => ({
      sectionInfo: section,
  }),
  layout: "section",
  components: {
    ClassInfo,
}
  }
</script>

