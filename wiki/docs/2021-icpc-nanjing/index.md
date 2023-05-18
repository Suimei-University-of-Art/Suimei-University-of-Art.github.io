---
title: 2021 ICPC 亚洲区域赛南京站
date: 2023-05-17
---

# 2021 ICPC 亚洲区域赛南京站

## 基本信息

<table>
<tr>
<td><b>竞赛日期</b></td><td>2021/12/04</td>
</tr>
<tr>
<td><b>竞赛试题</b></td><td><a href="contest-en.pdf">English</a></a></td>
</tr>
<tr>
<td><b>竞赛榜单</b></td><td><a href="https://board.xcpcio.com/icpc/46th/nanjing">XCPC Board</a> | <a href="board">SUA Board</a></td>
</tr>
<tr>
<td><b>在线练习</b></td><td><a href="https://codeforces.com/gym/103470">Codeforces Gym</a></td>
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
      {"id": "A", "ac": 637, "type": "正式赛队"},
      {"id": "A", "ac": 43, "type": "非正式赛队"},
      {"id": "B", "ac": 2, "type": "正式赛队"},
      {"id": "B", "ac": 1, "type": "非正式赛队"},
      {"id": "C", "ac": 427, "type": "正式赛队"},
      {"id": "C", "ac": 27, "type": "非正式赛队"},
      {"id": "D", "ac": 172, "type": "正式赛队"},
      {"id": "D", "ac": 8, "type": "非正式赛队"},
      {"id": "E", "ac": 28, "type": "正式赛队"},
      {"id": "E", "ac": 1, "type": "非正式赛队"},
      {"id": "F", "ac": 1, "type": "正式赛队"},
      {"id": "F", "ac": 0, "type": "非正式赛队"},
      {"id": "G", "ac": 14, "type": "正式赛队"},
      {"id": "G", "ac": 1, "type": "非正式赛队"},
      {"id": "H", "ac": 277, "type": "正式赛队"},
      {"id": "H", "ac": 13, "type": "非正式赛队"},
      {"id": "I", "ac": 29, "type": "正式赛队"},
      {"id": "I", "ac": 3, "type": "非正式赛队"},
      {"id": "J", "ac": 66, "type": "正式赛队"},
      {"id": "J", "ac": 3, "type": "非正式赛队"},
      {"id": "K", "ac": 2, "type": "正式赛队"},
      {"id": "K", "ac": 0, "type": "非正式赛队"},
      {"id": "L", "ac": 5, "type": "正式赛队"},
      {"id": "L", "ac": 1, "type": "非正式赛队"},
      {"id": "M", "ac": 605, "type": "正式赛队"},
      {"id": "M", "ac": 40, "type": "非正式赛队"}
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
      {"ac": 1, "cnt": 31, "type": "正式赛队"},
      {"ac": 1, "cnt": 3, "type": "非正式赛队"},
      {"ac": 2, "cnt": 173, "type": "正式赛队"},
      {"ac": 2, "cnt": 13, "type": "非正式赛队"},
      {"ac": 3, "cnt": 153, "type": "正式赛队"},
      {"ac": 3, "cnt": 13, "type": "非正式赛队"},
      {"ac": 4, "cnt": 112, "type": "正式赛队"},
      {"ac": 4, "cnt": 7, "type": "非正式赛队"},
      {"ac": 5, "cnt": 92, "type": "正式赛队"},
      {"ac": 5, "cnt": 3, "type": "非正式赛队"},
      {"ac": 6, "cnt": 44, "type": "正式赛队"},
      {"ac": 6, "cnt": 2, "type": "非正式赛队"},
      {"ac": 7, "cnt": 17, "type": "正式赛队"},
      {"ac": 7, "cnt": 1, "type": "非正式赛队"},
      {"ac": 8, "cnt": 6, "type": "正式赛队"},
      {"ac": 8, "cnt": 0, "type": "非正式赛队"},
      {"ac": 9, "cnt": 3, "type": "正式赛队"},
      {"ac": 9, "cnt": 0, "type": "非正式赛队"},
      {"ac": 10, "cnt": 4, "type": "正式赛队"},
      {"ac": 10, "cnt": 0, "type": "非正式赛队"},
      {"ac": 11, "cnt": 1, "type": "正式赛队"},
      {"ac": 11, "cnt": 1, "type": "非正式赛队"},
      {"ac": 12, "cnt": 1, "type": "正式赛队"},
      {"ac": 12, "cnt": 0, "type": "非正式赛队"},
      {"ac": 13, "cnt": 0, "type": "正式赛队"},
      {"ac": 13, "cnt": 0, "type": "非正式赛队"}
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