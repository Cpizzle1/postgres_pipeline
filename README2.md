pip install kaggle
set up kaggle api 
    https://www.kaggle.com/docs/api

```bash
kaggle datasets download -d 'varunramesh1122/starwars-survey-in-usa'
```  

For St Louis Fred's Consumer Price Index dataset, run 


```bash
wget https://fred.stlouisfed.org/graph/fredgraph.csv?bgcolor=%23e1e9f0&chart_type=line&drp=0&fo=open%20sans&graph_bgcolor=%23ffffff&height=450&mode=fred&recession_bars=on&txtcolor=%23444444&ts=12&tts=12&width=1168&nt=0&thu=0&trc=0&show_legend=yes&show_axis_titles=yes&show_tooltip=yes&id=CUSR0000SS62031&scale=left&cosd=1999-01-01&coed=2020-04-01&line_color=%234572a7&link_values=false&line_style=solid&mark_type=none&mw=3&lw=2&ost=-99999&oet=99999&mma=0&fml=a&fq=Monthly&fam=avg&fgst=lin&fgsnd=2009-06-01&line_index=1&transformation=lin&vintage_date=2020-05-31&revision_date=2020-05-31&nd=1999-01-01
```

Next, copy the files downloaded from the EC2 instance to S3. Make sure that it has the aws-cli installed. Run aws configure and then aws s3 cp {FILE} s3://{S3_BUCKET}/{S3_FOLDER}/ to transfer the files to S3. Note that if the situation changes such that this becomes a daily job, we can write a shell script containing these commands, and add the command to run this shell script in our Airflow data pipeline