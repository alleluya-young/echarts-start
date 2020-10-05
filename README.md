基于 echarts 的 react 桥接层. (并不是一个完整的图表解决方案，仅仅桥接写法)

## Necessary

```
1. window对象注入echarts. 如：add <script type="text/javascript" src="//cdn.jsdelivr.net/npm/echarts@4.8.0/dist/echarts.min.js"></script> in html
2. 需要 "lodash": "^4.x", "react": "16.x", "uuid": "^8.x"
```

## Install

```
yarn add @echarts-start/react-bridge
```

## Usage

```
  import { Dataset, Legend, Series, Tooltip, XAxis, YAxis, Chart } from "@echarts-start/react-bridge";
  //data
  const datasetData = useMemo(
    () => [
      { product: "Matcha Latte", "2015": 43.3, "2016": 85.8, "2017": 93.7 },
      { product: "Milk Tea", "2015": 83.1, "2016": 73.4, "2017": 55.1 },
      { product: "Cheese Cocoa", "2015": 86.4, "2016": 65.2, "2017": 82.5 },
      { product: "Walnut Brownie", "2015": 72.4, "2016": 53.9, "2017": 39.1 },
    ],
    [],
  );
  const [loading, setLoading] = useState<boolean>(false);
    //element
      <Chart
        style={{ width: "100%", height: 400 }}
        resize
        loading={loading}
        onChartClick={(e) => {
          console.log("click events=", e);
        }}>
        <XAxis type={"category"} />
        <YAxis />
        <Tooltip trigger={"axis"} />
        <Legend />
        <Series type={"line"} />
        <Series type={"line"} />
        <Series type={"line"} />
        <Dataset dimensions={["product", "2015", "2016", "2017"]} source={datasetData} />
      </Chart>
```

[详细 demo](https://github.com/zxeryu/echarts-start/tree/master/%40echarts-start/react-bridge)

## Demo

```
$ git clone https://github.com/zxeryu/echarts-start
$ cd echarts-start
$ yarn install && yarn start
```
