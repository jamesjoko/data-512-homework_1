# data512_hw1
HW 1 - Professionalism &amp; Reproducibility

This project aims to construct, analyze, and publish a dataset of monthly article traffic for a subset of Academy Award-winning film articles on English Wikipedia from July 1, 2015 through September 30, 2023. To reproduce the analysis, run all cells in the `jjoko_data512_hw1.ipynb` notebook from top to bottom.

The license of the source data is located here: https://en.wikipedia.org/wiki/Wikipedia:Text_of_the_Creative_Commons_Attribution-ShareAlike_3.0_Unported_License

This project uses the Wikimedia Foundation REST API. The terms of use are located here: https://www.mediawiki.org/wiki/REST_API#Terms_and_conditions

Link to the API documentation: https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews

The final output files created by my code are:
- academy_monthly_cumulative_201506-202309.json
- academy_monthly_desktop_201506-202309.json
- academy_monthly_mobile_201506-202309.json
- fewest_months_of_data.png
- max_and_min_average.png
- top10_peak_page_views.png

The fewest_months_of_data.png, max_and_min_average.png, and top10_peak_page_views.png outputs are time series visualizations to questions in Step 2: Analysis.

The structure of academy_monthly_cumulative_201506-202309.json, academy_monthly_desktop_201506-202309.json, academy_monthly_mobile_201506-202309.json is below. The number of views per access type are in the file name (mobile/desktop/cumulative(mobile+desktop))
```
{
article_title: [
    {
      "project": "string",
      "article": "string",
      "agent": "string",
      "granularity": "string",
      "timestamp": "string",
      "views": integer
    },
    {
      "project": "string",
      "article": "string",
      "agent": "string",
      "granularity": "string",
      "timestamp": "string",
      "views": integer
    },
    ...
  ]

}
```

One special consideration is that the URI encoding of the `urllib.parse.quote` function does not handle the "/" character by default. In response, I specified the safe='' parameter in the function.
