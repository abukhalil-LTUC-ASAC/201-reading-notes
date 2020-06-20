# Be consistent with your images, and be nice to the SEO

Following up from the [basic intro](https://abukhalil95.github.io/reading-notes/class-05), a familiar and easy to look at, of your website is your best bet for keeping attention. And there are multiple properties to keep in mind.

## Proper Imageries

* `width and height`: although images come predefined, its best practice to limit its size with one of the two properties to keep the aspect ratio but shrink the image as needed.
* Alignment: using the `float` property inside an `class=".alignleft"` or `class=".alignright"` to make life easier when assigning this property to images.
    * Centering the image I found best using `img.align-center { display: block; margin: 0px auto;}` since images are inline, and needs to be turned into blocks, then margining helps with 0px top and bottom, but of equal left and right margins since its automatically assigned.
* `background-image`: helps turn a whole `<div>` block into an image as a background.
    * repeat can be specified on x or y or automatically to repeat the image and fill the whole background.
    * fixed or scroll keeps the image in its place or scroll with the user
    * background-position specifies a no repeat image to a position.
    * the whole package can be specified using background shorthand in the following order: 
        1. background-color
        2. background-image
        3. background-repeat
        4. background-attachment
        5. background-position

* `sprites`: are defined as a single image used multiple times.

          ```
          a.button {
          height: 36px;
          background-image: url("images/button-sprite.jpg");
          text-indent: -9999px;
          display: inline-block;
          }
              a#add-to-basket {
              width: 174px;
              background-position: 0px 0px;
              }
              a#framing-options {
              width: 210px;
              background-position: -175px 0px;
              }
                  a#add-to-basket:hover 
                  {
                  background-position: 0px -40px;
                  }
                  a#framing-options:hover {
                  background-position: -175px -40px;
          }
                      a#add-to-basket:active {
                      background-position: 0px -80px;
                      }
                      a#framing-options:active {
                      background-position: -175px -80px;
          }
          ```

          The above represents 6 states using a single image for the basic, hover and click.

* `background-image` gradients: are a fun way to add aesthetic value without using images, it uses two or more colors to express the difference between them as linear color gradient, and the angle it makes or a [different radial gradient](https://cssgradient.io/), since browser support is limited for this part the following code helps make up for that part by specifying per browser settings and a fallback image if everything fails.

          ```
            gradient {
            /* fallback color */
            background-color: #66cccc;
            /* fallback image */
            background-image: url(images/fallback-image.png);
            /* Firefox 3.6+ */
            background-image: -moz-linear-gradient(#336666,
            #66cccc);
            /* Safari 4+, Chrome 1+ */
            background-image: -webkit-gradient(linear, 0% 0%,
            0% 100%, from(#66cccc), to(#336666));
            /* Safari 5.1+, Chrome 10+ */
            background-image: -webkit-linear-gradient(#336666,
            #66cccc);
            /* Opera 11.10+ */
            background-image: -o-linear-gradient(#336666,
            #66cccc);
            height: 150px;
            width: 300px;
          }
          ```
* Contrast is a major hurdle when dealing with images with overlay text, my way is to add a background padding that has a transparent and low contrast color that envelopes such texts nicely.

## Working with the SEO

Knowing beforehand that no matter what your website does, or how much work you had put in it. It won't matter at all if people cannot search for it. This comes in play in two parts:

* on-page techniques: Which describes the practice of using what people might look for inside you website, such as texts and alt images.

    The following is an ordered list of where keywords should exist.

      1. Page title.
      2. URL/Web Address.
      3. Headings `<h1..6>` tags.
      4. Text (2-3 times in body content).
      5. In between `<a>` tags with relevant (not click me!) content.
      6. Image `alt=""` text.
      7. [Page descriptions](https://yoast.com/meta-descriptions/) using `<meta>` tags.

* off-page techniques: Furthers your reachability by linking other websites to yours! It also considers content inside `<a>` tags.

So how would you identify what people would search for? This topic is totally new to me so I would simply list off from the book.

      1. Brain storm: list your products and services, and try to ask people what do they write when they try to reach you.
      2. Organize: Don't randomly throw keywords around, and instead make focused groups for each category and topic.
      3. Research: Basically use online tools such as [google's adwords](https://adwords.google.co.uk/select/KeywordToolExternal) 
      4. Compare: Something you might expect from overusing the same keywords over multiple site, as the legend said 
        > [When everyone's super, no one would be.](https://www.youtube.com/watch?v=fmSO2cz2ozQ)
        So don't be like the others!

      5. Refine: Add some relevant phrases in addition to the overused keywords, waffle stand would advertise locally at a much better chances if it adds the location and area next to the keyword.
      6. Map: as in divide keywords to their most used context, with each page having 3-5 keywords and don't repeat over other pages.

### Analytics, or as less famously known *stalking your visitor's behavior*.

Firstly, [sign up](http://www.google.com/analytics) to the don't be evil company. Then start doing some analytics. Most important features compile to the number of people, what do they look for and where do they come from.

#### * Numbers of people data include:
      - Number of visits total
      - Unique visits per address
      - Page views total
      - Pages per visit on average
      - Average time on site
      - Date selector to change data to match specific date
      - Exporting the data

#### * What are your visitors looking at?
      - Most visited pages
      - Landing pages where visitors first visit
      - Most exit pages
      - Bounce rate of those who leave from the landing page

#### * Source of entry!
      - Referrers as in most link pressed from another site to yours
      - Direct url typed in browser
      - Search terms from search engines such as google
      - Advanced features which include more in-depth and content dependant data

## So what does it take to get your website off?

Not an arm and leg, that is for sure! First step is about getting your domain name `mywebsite.com` many custom use of [top level domains](https://www.lifewire.com/what-does-com-mean-2483161) has emerged recently, giving unheard of countries more credit to its use such as Anguilla with its .ai which you could imagine as a domain name for many AI based services and products.

With the domain at hand, you would need some machine to launch the code with its domain from. Using web hosting services from third party servers are the most famous way to do so, even if you are paranoid about it's security, experience has shown how cheap and reliable they are. These hosting services vary in amount but they have similar cost dependant factors which are: 

    1. Disk Space
    2. Bandwidth which is basically the total upload and download traffic that comes and goes from your website
    3. Backups are additional spaces reserved for backing up your data. Mostly as a service and will offer swift relaunch in case of failure.
    4. Email accounts and inbox size might be part of the bundle, giving you custom @mywebsite.com email address.
    5. Server-side languages and databases is an important factor in checking if they can even host your website.

Some hosting services comes along with the full package, with you only need to use the domain name and point it towards their services such as wordpress and shopify.

## Some side notes

Transfers are mostly done through file transfer protocol (FTP), some are built in, others can be used by downloading a simple interface to do so. [FileZilla](filezilla-project.org) and [fireFTP](fireftp.mozdev.org) can be used on no matter what machine.

## HTML 5's new `<video><audio>` tags 

All while also providing a `HTMLMediaElement` API to make your own custom playbacks and different functionalities. If you ever need your own player and not a link to youtube and vimeo, take a [deep look into the website](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Client-side_web_APIs/Video_and_audio_APIs) and start customizing.