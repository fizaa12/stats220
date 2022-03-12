# Hi!

## 🌸 Welcome to my website 🌸

I made this meme combining my coding skils with my love for ***Attack on Titan***. It depicts one of the character's most iconic faces and is an adaptation of an existing meme format. 

![](my_meme.png)

The two characters in this meme are

1. Yelena 
2. Armin




library(magick)
happy_yelena <- image_read("https://cdn.realsport101.com/images/ncavvykf/epicstream/97014c7e563ef6b21bf5512022e4168617db67a6-1920x1080.png?rect=0,0,1919,1080&w=686&h=386&auto=format&dpr=2") %>%
  image_scale(400) 

devastated_yelena <- image_read("https://shogi-pineapple.com/wp-content/uploads/2022/01/Attack-On-Titan-Season-4-Just-Jumpscared-Everyone-Including-Armin.png") %>%
  image_scale(400)



happy_text <- image_blank(width = 300,
                          height = 240,
                          color = "#000000") %>%
  image_annotate(text = "Omicron",
                 color = "#FFFFFF",
                 size = 50,
                 font = "Impact",
                 gravity = "center")

devastated_text <- image_blank(width = 300,
                               height = 200,
                               color = "#000000") %>%
  image_annotate(text = "My 2022 Travel Plans",
                 color = "#FFFFFF",
                 size = 30,
                 font = "Impact",
                 gravity = "center")


first_row <- c(happy_yelena, happy_text) %>%
  image_append()

second_row <- c(devastated_yelena, devastated_text) %>%
  image_append()

meme <- c(first_row, second_row) %>%
  image_append(stack = TRUE)

image_write(meme,"my_meme.png")
