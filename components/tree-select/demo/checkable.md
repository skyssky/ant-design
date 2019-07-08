---
order: 3
title:
  zh-CN: 可勾选
  en-US: Checkable
---

## zh-CN

使用勾选框实现多选功能。

## en-US

Multiple and checkable.

```jsx
import { TreeSelect } from 'antd';

const { SHOW_PARENT } = TreeSelect;

const treeData = [
  {
    title: 'NB',
    value: 'NB',
    key: '0-0',
    children: [
      {
        title: '全部',
        value: '全部',
        key: '0-0-0',
      },
      {
        title: '传统本',
        value: '传统本',
        key: '0-0-1',
      },
    ],
  },
  {
    title: 'DT',
    value: 'DT',
    key: '0-1',
    children: [
      {
        title: '全部',
        value: '全部',
        key: '0-1-0',
      },
      {
        title: 'AIO',
        value: 'AIO',
        key: '0-1-1',
      },
      {
        title: 'BOX',
        value: 'BOX',
        key: '0-1-2',
      },
    ],
  },
];

class Demo extends React.Component {
  state = {
    value: ['0-0-0'],
  };

  onChange = value => {
    console.log('onChange ', value);
    this.setState({ value });
  };

  render() {
    const tProps = {
      treeData,
      value: this.state.value,
      onChange: this.onChange,
      treeCheckable: true,
      showCheckedStrategy: SHOW_PARENT,
      searchPlaceholder: 'Please select',
      style: {
        width: 300,
      },
    };
    return <TreeSelect {...tProps} />;
  }
}

ReactDOM.render(<Demo />, mountNode);
```
