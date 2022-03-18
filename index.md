# My Meme

### The motivation and inspo

When we were asked to create an original meme, I knew mine would rotate around parenting and my life as a mom 👩‍🍼.
I just thought my parenting life would be an incredible source of ideas and inspiration (and hopefully a laugh or two) 😜 including but not limited to:

* the many unforgettable moments 🏆, 

* lots of big emotions at play 😆 😠 😢 , and

* a plethora of parenting fails 💩 to choose from.

How could I __NOT__ pay tribute to them at all? 


### True originality

My meme is a true story of my DS (dear son for those unfamiliar with [Mommy message board lingo](https://monicaandandy.com/blogs/ma-edit/mom-terms-to-know)).  It's a recurring story that happens when the planets don't align? IDK.  But I can assure you though that at times like these, he is not. Such. A dear.

### The creation

I found an image that perfectly portrays the deep frustration my DS experiences when he has these big feelings, and married it up with a recent reason for such frustration.

#momlife #bigfeelings #terribletwos #mommyslittlemonster #imnotcryingyourecrying #wheelsonthebus

![](my_meme.png)

```r
library(magick)

# Top text
mytoddlerwhen_text <- image_blank(width = 500,
                                  height = 150,
                                  color = "#f0f0f5") %>%
                         image_annotate(text = "My toddler when I sing\nWheels on the Bus",
                                   color = "#000000",
                                   size = 40,
                                   font = "Impact",
                                   gravity = "center")

# Middle picture 
url <- "https://www.houseofwellness.com.au/wp-content/uploads/2018/07/toddler-tantrums-displayplaybutton.jpg"

tantrum_pic <- image_read(url) %>%
                  image_scale(500)

# Bottom text
because_text <- image_blank(width = 500,
                            height = 150,
                            color = "#f0f0f5") %>%
                  image_annotate(text = "because he asked me to sing\n Wheels on the Bus",
                           color = "#000000",
                           size = 40,
                           font = "Impact",
                           gravity = "center")

# Putting the meme together
meme <- c(mytoddlerwhen_text, tantrum_pic, because_text) %>%
             image_append(stack = TRUE)

# Running the meme
meme
```
