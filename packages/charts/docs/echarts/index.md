---
title: 基础图表组件
---

# ECharts

## 基础用例

```jsx
import React from 'react';
import ECharts from '@rsuite/charts';
import option from './option.json';

export default () => (
  <div style={{ height: 400 }}>
    <ECharts option={option} />
  </div>
);
```

## 加载中状态

```jsx
import React, { useState } from 'react';
import { LineChart } from '@rsuite/charts';
import data from './loading.json';

export default () => {
  const [loading, setLoading] = useState(true);
  const handleToggleLoading = (loading) => setLoading(loading);

  return (
    <div>
      <LineChart loading={loading} name="浏览量(PV)" data={data} />
      <div>
        <label>
          加载状态：
          <input type="checkbox" checked={loading} onChange={(e) => setLoading(e.target.checked)} />
          {loading ? '开启' : '关闭'}
        </label>
      </div>
    </div>
  );
};
```
