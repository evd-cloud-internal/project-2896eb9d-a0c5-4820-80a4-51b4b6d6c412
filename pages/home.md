---
name: Home
assetId: 956461b8-2daa-4062-9be8-d039495d49c0
type: page
---

# Kentucky mPing Reports

*Dashboard of mPing Reports*


{% row %}
    {% bar_chart
      data="mping"
      x="District_Name"
      y="count(District_Name) AS District"
      series="District_Name"
      order="District_Number"
      legend=false
      height=400
      x_axis_options={
        label_rotate = 45
      }
      chart_options={
        color_palette = ["#0072B2", "#E69F00", "#009E73", "#CC79A7", "#D55E00", "#56B4E9", "#F0E442", "#000000", "#8B4513", "#7B68EE", "#2E8B57", "#DC143C"]
      }
    /%}

    {% map title="mPing Reports by County" height=400 %}
        {% area_layer
            geography="us_counties"
            match_by="state-county"
            data="mping"
            area_id="'Kentucky' || '-' || County_Name"
            value="count(*)"
            color_palette=["#f7fbff", "#deebf7", "#c6dbef", "#9ecae1", "#6baed6", "#4292c6", "#2171b5", "#084594"]
            legend_label="Report Count"
            value_fmt="num0"
        /%}
    {% /map %}
{% /row %}



{% line_chart
    data="mping"
    x="obtime"
    y="count(*) AS Reports"
    date_grain="day"
    title="Daily mPing Reports"
    y_fmt="num0"
/%}

{% table
  data="mping"
%}
{% /table %}

{% download
  data="mping"
  label="Download Data"
  filename="kentucky_mping_reports"
/%}

{% dropdown
    id="county_filter"
    data="mping"
    value_column="County_Name"
    title="Filter by County"
    order="County_Name"
/%}

{% bubble_chart
  data="mping"
  x="District_Name"
  size="count(description)"
  y="description"
  series="description"
  filters=["county_filter"]
  height=1000
/%}
