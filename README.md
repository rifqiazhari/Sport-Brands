# Sport-Brands
![alt text](Screenshot(615).png)
![alt text](de3df82a-2d89-4215-9ed8-65094afa8b86.png)

# Code in R
`library(tidyverse) #read_csv`<br/>

`#read file`<br/>
`databola <- read_csv('databola.csv')`<br/>

`#reshaped to longer`<br/>
`databola_reshaped <- databola %>%`<br/>
&emsp;&emsp;`pivot_longer(!klub, names_to = 'media', values_to = 'k')`<br/>

`library(ggthemes) #themes`<br/>
`install.packages("hrbrthemes")`<br/>
`library(hrbrthemes)`<br/>

`databola_reshaped %>%`<br/>
&emsp;&emsp;`ggplot(aes(x=reorder(media,-k), y=k, fill=reorder(klub,-k))) +`<br/>
&emsp;&emsp;`geom_bar(stat="identity", position="dodge") +`<br/>
&emsp;&emsp;`xlab("Media") +`<br/>
&emsp;&emsp;`ylab("in k") +`<br/>
&emsp;&emsp;`ggtitle("Most Followed Sports Team in Indonesia") +`<br/>
&emsp;&emsp;`theme_ipsum_pub() +`<br/>
&emsp;&emsp;`theme(legend.position="bottom") #memindahkan legend ke bawah`<br/>
	
#export file
`write.csv(databola_reshaped, "databola_reshaped.csv")`<br/>
