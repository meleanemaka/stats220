```r
# square one
flag_tonga <- image_read("https://cdn.pixabay.com/photo/2012/04/11/15/44/flag-28596_1280.png") %>%
  image_scale(700)

# square two
tonga_text <- image_blank(width = 500,
                         height = 500,
                         color = "#000000") %>%
  image_annotate(text = "Tonga,",
                 color = "#FFFFFF",
                 size = 80,
                 font = "Impact",
                 gravity = "center")

# square three
boat_tonga <- image_read("https://cdn.pixabay.com/photo/2018/11/17/20/35/shipwreck-3821992_1280.jpg") %>%
  image_scale(700)

#square_four
ml_text <- image_blank(width = 500,
                       height = 500,
                       color = "#000000") %>%
  image_annotate(text = "my \n HOME",
                 color = "#FFFFFF",
                 size = 80,
                 font = "Impact",
                 gravity = "north")

# making each row

# first using one approach
tonga_vector <- c(flag_tonga, tonga_text)
top_row <- image_append(tonga_vector)

# second using a different approach
bottom_row <- image_append(c(boat_tonga, ml_text))

#making the whole thing!

# using another approach
meme <- c(top_row, bottom_row) %>%
  image_append(stack = TRUE) %>%
  image_scale(400)
```
