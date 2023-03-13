
  
  

# React Dot Matrix Chart

<a href="https://www.npmjs.com/package/react-dot-matrix-chart"><img src="https://badgen.net/npm/v/react-dot-matrix-chart?color=blue" alt="npm version"></a> <a href="https://www.npmjs.com/package/react-dot-matrix-chart" ><img src="https://img.shields.io/npm/dw/react-dot-matrix-chart?label=Downloads" /></a> <a href="https://github.com/KeyValueSoftwareSystems/react-dot-matrix-chart"><img src="https://github.com/KeyValueSoftwareSystems/react-dot-matrix-chart/actions/workflows/deploy.yml/badge.svg" alt="" /></a>

<div align="center">
<img src="./screenshot.png" alt="" width="573" height="199"/>
</div>

 
>A customizable ready to use Dot Matrix Chart Component for React

Try tweaking a dot matrix using this codesandbox link <a href="https://codesandbox.io/s/dot-matrix-chart-hqw9z0" >here</a>

## Installation

The easiest way to use react-dot-matrix-chart is to install it from npm and build it into your app with Webpack.

```
npm install react-dot-matrix-chart
```

You’ll need to install React separately since it isn't included in the package.

  

## Usage

  

React Dot Matrix Chart can run in a very basic mode by just providing the `dataPoints` like given below:

```

import DotMatrix from 'react-dot-matrix-chart';

<DotMatrix
  dataPoints={dataPointsArray}
/>

```

The datapoints is an array of objects with the following keys:

-  `name` - a string that represents each category
-  `count` - a number to specify the count of each category present(used to find the number of dots to be displayed)
-  `color` - a string to specify which colour to be used to represent the category in the dot matrix

  

An example for dataPoints array is shown below:

```

dataPointsArray = [
  {
    name: 'Category 1',
    count: 10,
    color: 'gray'
  },
  {
    name: 'Category 2',
    count: 10,
    color: 'black'
  },
  {
    name: 'Category 3',
    count: 10,
    color: 'green'
  }
];

```

You can use `title` prop to add a Title value to the dot matrix chart

```

<DotMatrix
  dataPoints={dataPointsArray}
  title="Dot Matrix"
/>

```

You can specify the number of rows or columns to be present in the chart as well using the dimensions prop.

```
<DotMatrix
  dataPoints={dataPointsArray}
  dimensions={
    rows: 5,
    columns: 10
  }
/>

```

If the count given in the dataPoints array results in a partial percentage (decimal value), a gradient dot will be displayed as shown below

  

## Props

  

Props that can be passed to the component are listed below:

<table>
  <thead>
    <tr>
      <th>Prop</th>
      <th>Description</th>
      <th>Default</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code><b>dataPoints:</b> object[]</code></td>
      <td>
      An array of category objects to specifying the count and name of each section
      </td>
      <td><code>undefined</code></td>
    </tr>
    <tr>
      <td><code><b>title?:</b> string</code></td>
      <td>
      The title of Dot Matrix chart rendered
      </td>
      <td><code>''</code></td>
    </tr>
    <tr>
      <td><code><b>dimensions?:</b> object</code></td>
      <td>
      To specify the number of rows and columns to be present in the chart
      </td>
      <td><code>{ rows: 5, columns: 12 }</code></td>
    </tr>
    <tr>
      <td><code><b>styles?:</b> object</code></td>
      <td>
      Provides you with a bunch of callback functions to override the default styles.
      </td>
      <td><code>undefined</code></td>
    </tr>
  </tbody>
</table>


## Style Customizations

All the default styles provided by this package are overridable using the `style` prop.
the below code shows all the overridable styles:

```
<DotMatrix
  dataPoints={dataPointsArray}
  styles={{
    Container: () => ({...styles}),
    DotsContainer: () => ({...styles}),
    Dot: () => ({...styles}),
    LegendContainer: () => ({...styles}),
    LegendName: () => ({...styles}),
    LegendDot: () => ({...styles})
  }}
/>

```

-  `Container` - overrides the dot matrix chart container style
-  `DotsContainer` - overrides the dot matrix chart dots container style
-  `Dot` - overrides the style of each dot in the chart
-  `LegendContainer` - overrides the legend (details) container style
-  `LegendName` - overrides the legend name style
-  `LegendDot` - overrides the legend dot style