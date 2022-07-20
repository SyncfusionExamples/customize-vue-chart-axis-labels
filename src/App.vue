<template>
  <div id="app">
    <ejs-chart :primaryXAxis="chartPrimaryXAxis" :title="chartTitle"
    :primaryYAxis="chartPrimaryYAxis">
      <e-series-collection>
        <e-series type="Column" :dataSource="chartData" xName="name" yName="value"></e-series>
      </e-series-collection>   
    </ejs-chart>
  </div>
</template>

<script>
import Vue from "vue";
import { ChartPlugin, ColumnSeries, Category, MultiLevelLabel } from '@syncfusion/ej2-vue-charts';
Vue.use(ChartPlugin);

export default {
  provide : {chart : [ColumnSeries, Category, MultiLevelLabel ]},
  data() {
    return {
      chartPrimaryYAxis : { 
        title : 'Consumption Rate',
        labelStyle : { color: 'blue', fontWeight : 'bold'},
        titleStyle : { color : '#ed7d31', fontWeight : 'bold'}
     },
      chartTitle : 'Food Consumption Analysis',
      chartPrimaryXAxis : {
        valueType : 'Category',
        title : 'Food Items',
        labelIntersectAction : 'Rotate90',
        multiLevelLabels : [
          {
            textStyle : { color : 'red'},
            border : { type : 'Rectangle'},
            categories : [
              {start : -0.5,end : 5.5,text : 'In Season'},
              {start : 5.5,end : 10.5,text : 'Out of Season'},
              {start : 10.5,end : 16.5,text : 'In Season'},
              {start : 16.5,end : 21.5,text : 'Out of Season'}
            ]
          },
          {
            textStyle : { fontWeight : 'bold'},
            border : { type : 'Brace', color : 'Blue', width : 2 },
            categories : [
              {start : -0.5,end : 10.5, text : 'Vegetable'},
              {start : 10.5,end : 21.5, text : 'Fruits'} 
            ]
          }
        ],
        titleStyle : { color : '#ed7d31', fontWeight : 'bold'},
        labelPosition : 'Outside',
        labelStyle : { color : 'red', fontWeight : 'bold'},
        enableTrim : true,
        maximumLabelWidth : '38'
      },
      chartData : [
         { name : "Beetroot", value : 31 },
         { name : "Tomato" , value : 89 },
         { name : "Cucumber",  value : 62 },
         { name : "Cabbage",  value : 48 },
         { name : "Potato" , value : 96 },
         { name : "Turnip", value : 60 },
         { name : "Radish", value : 52 },
         { name : "Pumpkin", value : 20 },
         { name : "Peas", value : 40 },
         { name : "Onion", value : 79 },
         { name : "Carrot", value : 53 },
         { name : "Pine<br>apple", value : 28 },
         { name : "Jackfruit", value : 50 },
         { name : "Strawberry" , value : 12 },
         { name : "Pomogranate",  value : 43 },
         { name : "Watermelon", value : 35 },
         { name : "Lemon", value : 27 },
         { name : "Grape", value : 35 },
         { name : "Guava", value : 72 },
         { name : "Apple", value : 30 },
         { name : "Banana", value : 50 },
         { name : "Raspberries", value : 10 }
      ]
    };
  }
}
</script>





