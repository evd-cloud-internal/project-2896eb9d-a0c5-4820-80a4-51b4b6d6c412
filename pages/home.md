---
name: Home
assetId: 956461b8-2daa-4062-9be8-d039495d49c0
type: page
---

# Kentucky mPing Reports

Dashboard of mPing Reports


{% table
  data="mping"
%}
{% /table %}



{% bar_chart
  data="mping"
  x="District_Name"
  y="count(*)"
  series="District_Name"
  order="District_Number"
/%}



{% bubble_chart
  data="mping"
  x="District_Name"
  size="count(description)"
  y="description"
  series="description"
  height=800
/%}
