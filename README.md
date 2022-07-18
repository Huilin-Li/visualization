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
