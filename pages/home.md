---
name: Home
assetId: 956461b8-2daa-4062-9be8-d039495d49c0
type: page
---

# Welcome

This is your new project's homepage. Edit this file to get started.

```cnt_by_cnty
SELECT County_Name, Count(*) as Cnt
FROM mping
GROUP BY County_Name
ORDER BY County_Name
```

{% table
  data="mping"
%}
{% /table %}

{% table
  data="cnt_by_cnty"
%}
{% /table %}


{% bar_chart
  data="cnt_by_cnty"
  x="County_Name"
  y="Cnt"
/%}

{% bar_chart
  data="mping"
  x="County_Name"
  y="count(*)"
/%}