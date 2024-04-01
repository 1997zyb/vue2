

<template>
  <div class="mainclass">
    <count></count>
    <count></count>
    123
  </div>
</template>
  
<script>
import trees from '@/components/HelloWorld.vue'
import count from '@/components/count.vue'
export default {
  components: { trees, count },
  data() {
    return {
      treeData: [],
      treeExpandAll: true,
      treeNodeKey: 'id',
      content: '',
    }
  },
  mounted() {
    const jsonData = {
      "topic": "春节餐饮服务行业市场分析",
      "subheading": "行业现状与未来发展趋势",
      "sections": [
        {
          "topic": "行业概述",
          "subheading": "对春节餐饮服务行业的总体介绍",
          "pages": [
            {
              "title": "市场规模",
              "tags": "列表",
              "data": [
                {
                  "subtitle": "市场总体规模",
                  "content": "详细介绍春节期间餐饮服务行业的市场规模，包括总营业额、服务量等核心数据。"
                },
                {
                  "subtitle": "增长趋势",
                  "content": "分析过去几年春节餐饮服务行业的增长趋势，预测未来的发展方向。"
                },
                {
                  "subtitle": "市场份额",
                  "content": "介绍各大餐饮品牌在春节期间的市场份额及其变化情况。"
                }
              ]
            },
            {
              "title": "消费者分析",
              "tags": "层次结构",
              "master": "消费群体细分",
              "data": [
                {
                  "subtitle": "年龄分布",
                  "content": "根据年龄对春节餐饮服务的消费者进行分布分析，突出不同年龄段的消费特点。"
                },
                {
                  "subtitle": "消费偏好",
                  "content": "分析消费者在春节期间的餐饮服务消费偏好，包括菜品类别、消费场所等。"
                }
              ]
            },
            {
              "title": "竞争格局",
              "tags": "进度",
              "data": [
                {
                  "subtitle": "主要竞争者",
                  "content": "列举春节期间餐饮服务行业的主要竞争者，并分析其竞争优势。"
                },
                {
                  "subtitle": "市场份额变动",
                  "content": "探讨各大品牌在市场中的份额变化及其影响因素。"
                }
              ]
            },
            // {
            //   "title": "大大大大",
            //   "tags": "大大大",
            //   "data": [
            //     {
            //       "subtitle": "大去大",
            //       "content": "大去大"
            //     },
            //     {
            //       "subtitle": "地方干",
            //       "content": "士大夫"
            //     },
            //   ]
            // },
          ]
        },
        {
          "topic": "行业概述11",
          "subheading": "对春节餐饮服务行业的总体介绍11",
          "pages": [
            {
              "title": "市场规模11",
              "tags": "列表11",
              "data": [
                {
                  "subtitle": "市场总体规模11",
                  "content": "详细介绍春节期间餐饮服务行业的市场规模，包括总营业额、服务量等核心数据11。"
                },
                {
                  "subtitle": "增长趋势11",
                  "content": "分析过去几年春节餐饮服务行业的增长趋势，预测未来的发展方向11。"
                },
                {
                  "subtitle": "市场份额11",
                  "content": "介绍各大餐饮品牌在春节期间的市场份额及其变化情况11。"
                }
              ]
            },
            {
              "title": "消费者分析11",
              "tags": "层次结构11",
              "master": "消费群体细分11",
              "data": [
                {
                  "subtitle": "年龄分布11",
                  "content": "根据年龄对春节餐饮服务的消费者进行分布分析，突出不同年龄段的消费特点11。"
                },
                {
                  "subtitle": "消费偏好11",
                  "content": "分析消费者在春节期间的餐饮服务消费偏好，包括菜品类别、消费场所等11。"
                }
              ]
            },
            {
              "title": "竞争格局11",
              "tags": "进度11",
              "data": [
                {
                  "subtitle": "主要竞争者11",
                  "content": "列举春节期间餐饮服务行业的主要竞争者，并分析其竞争优势11。"
                },
                {
                  "subtitle": "市场份额变动11",
                  "content": "探讨各大品牌在市场中的份额变化及其影响因素11。"
                }
              ]
            }
          ]
        }

      ]
    }
    this.convertToChildrenFormat(jsonData);
    this.treeData = [jsonData]
    console.log('jsonData', this.treeData);
  },
  methods: {
    convertToChildrenFormat(data) {
      if (!data.sections) return;
      data.sections.forEach(section => {
        if (section.pages) {
          section.children = section.pages
          section.pages.forEach(page => {
            page.children = page.data;
            delete page.data;
          });
          delete section.pages;
        }
        if (section.children) {
          this.convertToChildrenFormat(section.children);
        }
      });
    }
  }
}
</script>
  
<style lang="scss" scoped>
.mainclass {
  margin: 1%;
  gap: 10px;
}
</style>
