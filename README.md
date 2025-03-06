# sales-analysis of e-commerce business



sales_profit_by_segment = data.groupby('Segment').agg({'Sales':'sum', 'Profit':'sum'}).reset_index()
color_pallete = color.qualitative.Pastel

fig = go.Figure()
fig.add_trace(go.Bar(x=sales_profit_by_segment['Segment'],
                      y=sales_profit_by_segment['Sales'],
                      name='Sales',
                      marker_color=color_pallete[0]))

fig.add_trace(go.Bar(x=sales_profit_by_segment['Segment'],
                      y=sales_profit_by_segment['Profit'],
                      name='Profit',
                      marker_color=color_pallete[1]))
fig.update_layout(title='Sales and Profit Analysis by Customer Segment',
                  xaxis_title='Customer Segment', yaxis_title='Amount')
fig.show()
