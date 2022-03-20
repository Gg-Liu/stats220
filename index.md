### **This is a meme created for an assignment:**
![alpaca_meme](https://raw.githubusercontent.com/Gg-Liu/stats220/gh-pages/alpaca_meme.png)

- This _meme_ features an alpaca, because alpacas are pretty darn cool.
- It also describes someone's (probably not mine) approach to assignments

* This is some meta-information about how this sentence is necessary.
* It is necessary because I have to be able to show my ability to write ordered lists in Markdown.
* So here it is.
* One more line just to be safe :)

### **Anyways, here is the code to generate this image:**
```R
library(magick)
top_r <- image_blank(width = 400,
                     height = 277,
                     color = "#6a9c80"
) %>%
  image_annotate(text = "It's the weekend",
                 color = "#FFFFFF", 
                 size = 40,
                 gravity = "center",
                 font = "impact")

bot_r <- image_blank(width = 400,
                                   height = 277,
                                   color = "#6a9c80"
) %>%
  image_annotate(text = "You have 3\nassignments due\nMonday and you\n haven't started on\nthem",
                 color = "#FFFFFF", 
                 size = 40,
                 gravity = "center",
                 font = "impact")

alpaca1 <- image_read("https://a4.pbase.com/o6/34/564334/1/115888523.vxu01GMk.20090807alpaca09comp.jpg") %>%
  image_scale(400) %>% image_border("#005050", "10x5")

top_row <- c(alpaca1, top_r) %>% image_append()
second_row <- c(alpaca1, bot_r) %>% image_append()
appended <- c(top_row, second_row) %>% image_append(stack = TRUE)

print(appended)

image_write(appended, "alpaca_meme.png")


```
