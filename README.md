# visualization

```
        with open(path + html_name, 'w') as dashboard:
            dashboard.write("<html><head></head><body>" + "\n")
            for i in range(len(data_list)):
                file = data_list[i]
                PF = pd.read_excel(file)
                fig = px.histogram(PF, x='Chuck', opacity=0.5, log_y=True, marginal="rug", hover_data=PF.columns)
                inner_html = fig.to_html().split('<body>')[1].split('</body>')[0]
                dashboard.write(inner_html)
            dashboard.write("</body></html>" + "\n")
```


```

fig_test = go.Figure()
fig_test.add_trace(go.Scatter(x=test_plot_df['datetime'], y=test_plot_df['raw'],
                    mode='lines',
                    name='test raw data points'))
fig_test.add_trace(go.Scatter(x=test_plot_df['datetime'], y=test_plot_df['left'],
                    mode='lines',
                    name='test left data points'))
fig_test.show()
```

```

fig.update_layout(
    autosize=False,
    width=500,
    height=500,
    margin=dict(
        l=50,
        r=50,
        b=100,
        t=100,
        pad=4
    ),
    paper_bgcolor="LightSteelBlue",
)

fig.show()
```

```
data = pd.read_excel('./doc/UPW_temperature_instable/UPW_module_PF_XT_1900I_1950I_2022-04-01_2022-07-01.xlsx')
non_nan_data = data.dropna()

x_mean = non_nan_data['mean'].to_numpy()
x_sigma = non_nan_data['sigma'].to_numpy()
x_max = non_nan_data['max'].to_numpy()

# Group data together
hist_data = [x_mean]

group_labels = ['mean']

fig = ff.create_distplot(
    hist_data, group_labels, bin_size=[.001], show_rug=False)

fig.update_layout(
    xaxis_title="mean",
    autosize=False,
    width=450,
    height=450)
fig.update(layout_showlegend=False)
fig.show()

```
