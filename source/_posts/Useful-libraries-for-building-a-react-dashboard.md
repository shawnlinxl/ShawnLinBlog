---
title: Useful libraries for building a react dashboard
date: 2018-11-18 21:31:20
tags: [react, notes]
---

# UI Framework

### Updated 2018-12-09

After making some real dashboards, Antd stood out to me as it offers many more components than Semantic UI and is a more complete ecosystem. However, it is not modulized and will be harder to integrate to your existing system since it's css file overwrites almost all the basic things (`h1`, `body`, ...) you can think of. Atlas Kit looks promising too, as it is highly modulized and components are beatiful. Material UI is better suited for mobile applications.

### Original

[Semantic UI React](https://react.semantic-ui.com/) offers a beautiful UI framework. You can build a decent website up and running in no time with it. It has a lot of elements built in, and it's also very well documented.

![Semantic UI Demo](/images/react-semantic-ui.png)

```sh
npm install --save semantic-ui-react semantic-ui-css
```
#### Alternatives

[Material UI](https://material-ui.com/)  (Google)
[React Bootstrap](https://react-bootstrap.github.io/)
[Ant Design](https://ant.design/) (Alibaba)
[Fabric](https://developer.microsoft.com/en-us/fabric) (Microsoft)
[Altas Kit](https://atlaskit.atlassian.com/) (Atlassian)
[React Toolbox](http://react-toolbox.io)
[Blueprint](https://blueprintjs.com/)

# Tables

After doing some research, I found [React Bootstrap Table 2](https://react-bootstrap-table.github.io/react-bootstrap-table2/docs/about.html). It's feature rich and very well documented. Note that at the current moment you'll need to import Bootstrap's CSS in your html file.

![React Bootstrap Table 2 Demo](/images/react-bootstrap-table2.png)

```sh
npm install --save react-bootstrap-table-next
```

# Date Picker

[React Datepicker](https://reactdatepicker.com/) is beautiful and easy to use.

![React Datepicker Demo](/images/react-datepicker.png)

```sh
npm install --save react-datepicker
```

#### Alternatives

[React Dates (Airbnb)](https://github.com/airbnb/react-dates)

# Date Converstion

[Moment.js](https://momentjs.com/) is pretty much the go-to library for any date time conversion in javascirpt.

```sh
npm install --save moment
```

# Select menu

[React Select](https://react-select.com/home)

```sh
npm install --save react-select
```
