---
title: 2017 浙江大学程序设计竞赛
date: 2023-05-18
---

# 2017 浙江大学程序设计竞赛

## 基本信息

<table>
<tr>
<td><b>竞赛日期</b></td><td>2017/04/22</td>
</tr>
<tr>
<td><b>竞赛试题</b></td><td><a href="contest-en.pdf">English</a></a></td>
</tr>
<tr>
<td><b>竞赛榜单</b></td><td><a href="board">SUA Board</a></td>
</tr>
<tr>
<td><b>在线练习</b></td><td></td>
</tr>
</table>

## 统计数据

```vegalite
{
  "title": {
    "text": "题目通过数统计",
    "fontSize": 20
  },
  "data": {
    "values": [
      {"id": "A", "ac": 120, "type": "正式赛队"},
      {"id": "A", "ac": 28, "type": "非正式赛队"},
      {"id": "B", "ac": 4, "type": "正式赛队"},
      {"id": "B", "ac": 8, "type": "非正式赛队"},
      {"id": "C", "ac": 57, "type": "正式赛队"},
      {"id": "C", "ac": 22, "type": "非正式赛队"},
      {"id": "D", "ac": 1, "type": "正式赛队"},
      {"id": "D", "ac": 2, "type": "非正式赛队"},
      {"id": "E", "ac": 8, "type": "正式赛队"},
      {"id": "E", "ac": 1, "type": "非正式赛队"},
      {"id": "F", "ac": 17, "type": "正式赛队"},
      {"id": "F", "ac": 11, "type": "非正式赛队"},
      {"id": "G", "ac": 46, "type": "正式赛队"},
      {"id": "G", "ac": 17, "type": "非正式赛队"},
      {"id": "H", "ac": 14, "type": "正式赛队"},
      {"id": "H", "ac": 12, "type": "非正式赛队"},
      {"id": "I", "ac": 12, "type": "正式赛队"},
      {"id": "I", "ac": 13, "type": "非正式赛队"},
      {"id": "J", "ac": 129, "type": "正式赛队"},
      {"id": "J", "ac": 28, "type": "非正式赛队"}
    ]
  },
  "transform": [{
    "calculate": "if(datum.type === 'off', 0, 1)",
    "as": "typeOrder"
  }],
  "layer": [
    {
      "mark": {"type": "bar", "tooltip": true, "width": {"band": 0.5}},
      "encoding": {
        "x": {
          "field": "id",
          "type": "nominal",
          "axis": {"labelAngle": 0, "labelFontSize": 14, "title": "题目编号", "titleFontSize": 14},
          "sort": "-y"
        },
        "y": {
          "field": "ac",
          "aggregate": "sum",
          "type": "quantitative",
          "axis": {"labelAngle": 0, "labelFontSize": 14, "title": "通过数", "titleFontSize": 14}
        },
        "tooltip": [
          {
            "field": "type",
            "type": "nominal",
            "title": "队伍类型"
          },
          {
            "field": "ac",
            "aggregate": "sum",
            "type": "quantitative",
            "title": "通过数"
          }
        ],
        "color": {
          "field": "type",
          "type": "nominal",
          "scale": {
            "domain": ["正式赛队", "非正式赛队"],
            "range": ["#4c78a8", "#616166"]
          },
          "legend": null
        },
        "order": {"field": "typeOrder"}
      }
    },
    {
      "mark": {"type": "text", "style": "label", "fontSize": 14, "dy": -10},
      "encoding": {
        "x": {
          "field": "id",
          "type": "nominal",
          "sort": "-y"
        },
        "y": {
          "field": "ac",
          "aggregate": "sum",
          "type": "quantitative"
        },
        "text": {
          "field": "ac",
          "aggregate": "sum",
          "type": "quantitative"
        }
      }
    }
  ]
}
```

```vegalite
{
  "title": {
    "text": "队伍过题数统计",
    "fontSize": 20
  },
  "data": {
    "values": [
      {"ac": 0, "cnt": 4, "type": "正式赛队"},
      {"ac": 0, "cnt": 0, "type": "非正式赛队"},
      {"ac": 1, "cnt": 9, "type": "正式赛队"},
      {"ac": 1, "cnt": 2, "type": "非正式赛队"},
      {"ac": 2, "cnt": 55, "type": "正式赛队"},
      {"ac": 2, "cnt": 5, "type": "非正式赛队"},
      {"ac": 3, "cnt": 26, "type": "正式赛队"},
      {"ac": 3, "cnt": 3, "type": "非正式赛队"},
      {"ac": 4, "cnt": 21, "type": "正式赛队"},
      {"ac": 4, "cnt": 4, "type": "非正式赛队"},
      {"ac": 5, "cnt": 8, "type": "正式赛队"},
      {"ac": 5, "cnt": 3, "type": "非正式赛队"},
      {"ac": 6, "cnt": 4, "type": "正式赛队"},
      {"ac": 6, "cnt": 3, "type": "非正式赛队"},
      {"ac": 7, "cnt": 3, "type": "正式赛队"},
      {"ac": 7, "cnt": 2, "type": "非正式赛队"},
      {"ac": 8, "cnt": 3, "type": "正式赛队"},
      {"ac": 8, "cnt": 6, "type": "非正式赛队"},
      {"ac": 9, "cnt": 2, "type": "正式赛队"},
      {"ac": 9, "cnt": 0, "type": "非正式赛队"},
      {"ac": 10, "cnt": 0, "type": "正式赛队"},
      {"ac": 10, "cnt": 1, "type": "非正式赛队"}
    ]
  },
  "layer": [
    {
      "mark": {"type": "bar", "tooltip": true, "width": {"band": 0.5}},
      "encoding": {
        "x": {
          "field": "ac",
          "type": "nominal",
          "axis": {"labelAngle": 0, "labelFontSize": 14, "title": "过题数", "titleFontSize": 14}
        },
        "y": {
          "field": "cnt",
          "aggregate": "sum",
          "type": "quantitative",
          "axis": {"labelAngle": 0, "labelFontSize": 14, "title": "队伍数", "titleFontSize": 14}
        },
        "tooltip": [
          {
            "field": "type",
            "type": "nominal",
            "title": "类型"
          },
          {
            "field": "cnt",
            "aggregate": "sum",
            "type": "quantitative",
            "title": "队伍数"
          }
        ],
        "color": {
          "field": "type",
          "type": "nominal",
          "scale": {
            "domain": ["正式赛队", "非正式赛队"],
            "range": ["#4c78a8", "#616166"]
          },
          "legend": null
        },
        "order": {"field": "typeOrder"}
      }
    },
    {
      "mark": {"type": "text", "style": "label", "fontSize": 14, "dy": -10},
      "encoding": {
        "x": {
          "field": "ac",
          "type": "nominal"
        },
        "y": {
          "field": "cnt",
          "aggregate": "sum",
          "type": "quantitative"
        },
        "text": {
          "field": "cnt",
          "aggregate": "sum",
          "type": "quantitative"
        }
      }
    }
  ]
}
```

## 题解列表