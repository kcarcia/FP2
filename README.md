# Final Project Assignment 2: Explore One More! (FP2) 
DUE March 30, 2015 Monday (2015-03-30)

### My Library: net/url

#### Narrative, Code, and Output
GET and POST requests are so powerful. I just _had_ to play around with this library. So, let's bring you through my journey with net/url.

First, I begin by making a simple GET request to an online API called Dinopass. Dinopass generates a child-friendly password. (I've used this for a separate project.) I decide to start with this because it's very simple. The request looks something like this:
```
(define test-url (string->url "http://www.dinopass.com/password/simple"))
(display-pure-port (get-pure-port test-url))
```
When I run the program, a password returns like such:
```
> cuteant49
```
Easy peasy. Moving on...

Second, I decide to experiment with an API that's a bit more complicated. Google Maps API seems like that could be fun, so I go with that. I struggle to get this working. As it turns out, there are several ways to get a Google Map and figuring out which request to make is half the battle. Also, the documentation on getting an API key is outdated. I start with the following:
```
(define test-url2 (string->url "https://www.google.com/maps/embed/v1/place?key=AIzaSyB4AWESQh_0qzVuXIA2svATn0vam6A4y6E"))
(display-pure-port (get-pure-port test-url2))
```
But whenever I run the program, I get:
```
> The Google Maps API server rejected your request. Invalid request. Missing the 'q' parameter.
```
Something is clearly going wrong, I decide to play around with the different URLs listed on the Google website. This is when I'm finally successful.
```
(define test-url3 (string->url "https://www.google.com/maps/embed/v1/place?key=AIzaSyB4AWESQh_0qzVuXIA2svATn0vam6A4y6E&q=Fisht+Olympic+Stadium,Sochi+Russia"))
(display-pure-port (get-pure-port test-url3))
```
I choose the URL above because it has a q parameter. It also includes a parameter that gives a location. After miserably failing before, I think this is what I need. When I run the code, I find that I finally get it:
```
<!DOCTYPE html>
<html>
  <head>
    <style type="text/css">
      html, body, #mapDiv {
        height: 100%;
        margin: 0;
        padding: 0;
      }
    </style>
    <script src="https://maps.googleapis.com/maps/api/js?client=google-maps-embed&amp;libraries=geometry,search&amp;v=3.exp&amp;language=en_US"></script>
    <script src="https://maps.gstatic.com/intl/en_US/mapfiles/embed/20/6/init_embed.js"></script>
    <script>
      initEmbed([null,null,null,null,null,[[[2,"spotlight",null,null,null,null,null,[null,["0x40f5950ba45b45d7:0x9ec94ebaaff808cc","Fisht Olympic Stadium,Sochi Russia",null,[null,null,43.40201099999999,39.955709],0],null,null,null,null,null,null,null,"Fisht Olympic Stadium,Sochi Russia",null,null,[null,null,null,null,null,null,null,null,null,null,null,null,null,1],1,null,null,null,null,[4]]]],[[52]]],null,["en_US"],["/maps/api/ads/qle","/maps/api/js/ApplicationService.UpdateStarring","//accounts.google.com/ServiceLogin?continue=https://www.google.com/maps/api/js/ApplicationService.AuthSuccess","/maps/api/js/ApplicationService.GetEntityDetails","/maps/embed/upgrade204","//ad.doubleclick.net","/maps/embed/record204","/maps/api/js/ApplicationService.Search"],null,null,null,null,null,null,null,null,"NAcaVdygHYKeggTP_4HwBw",null,null,1,[[[2898.804628778489,39.95570899999999,43.40201099999999],null,null,13.10000038146973],null,0,[["0x40f5950ba45b45d7:0x9ec94ebaaff808cc","Олимпийский стадион Фишт, Olimpiyskiy prospekt, Adler, Krasnodar Krai",[43.40201099999999,39.955709],"11441762892034607308"],"Олимпийский стадион Фишт",["Olimpiyskiy prospekt","Adler","Krasnodar Krai, Russia"],4.700000286102295,"72 reviews","https://plus.google.com/101470115579731895850/about?hl=en\u0026authuser=0\u0026gl=us\u0026socpid=247\u0026socfid=maps_embed:placecard",null,null,null,null,null,null,"Stadium","Olimpiyskiy prospekt, Adler, Krasnodar Krai, Russia",null,null,[[[null,[2,"Mdnk2HRNdYlfBARNBgK2ag"]],[[3,39.95359353657923,43.40188345160524],[85.25614166259766,90,0],null,75],["//geo0.ggpht.com/cbk?cb_client=unknown_client\u0026output=thumbnail\u0026thumb=2\u0026panoid=Mdnk2HRNdYlfBARNBgK2ag\u0026w=223\u0026h=75\u0026yaw=85\u0026pitch=0\u0026thumbfov=120\u0026ll=43.401883,39.953594","Street View",null,[223,75]],5],[[null,[0,"109366472"]],[[2,39.955709,43.40201099999999],[0,90,0],[1024,683],90],["//storage.googleapis.com/static.panoramio.com/photos/small/109366472.jpg","36 Photos",[1024,683],[149,75]],10]],null,null,["https://plus.google.com/101470115579731895850/about?hl=en\u0026authuser=0\u0026gl=us\u0026socpid=247\u0026socfid=maps_embed:placecard","72 reviews",null,"Open-air stadium with 40,000 capacity, now used for training \u0026 matches for national soccer team."],null,null,null,1]],null,null,[null,null,[0],[0,0],[0],[0],[0],[0],[0],null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,null,[0]],0]);
    </script>
  </head>
  <body>
    <div id="mapDiv"></div>
  </body>
</html>
```
I'll have to figure out how to embded this on a web-server using Scheme, but I'll cross that bridge when I get to it.

Great, now moving on, I really want to get at the meat of what I probably want to do with my project. Working with iSENSE! Woohoo! (Well, if my partner agrees.) So since I've been working with GET requests, I want to try a POST request. I feel the perfect start would be to create a project on iSENSE. I start with this:
```
(define test-url5 (string->url "http://isenseproject.org//api/v1/projects?email=kaitlyn.carcia@hotmail.com&password=***&project_name=OPL+Project"))
(display-pure-port (post-pure-port test-url5))
```
However, something is going horribly wrong, and I'm at a loss.
```
> post-pure-port: aritiy mismatch...
```
I know these error messages typically mean I'm missing an argument. So I get back on the documentation and see that I need to send bytes (of data) with a post request. After doing some reading, it looks like my best option is to pass #f. At least I'm pretty sure it is...
```
(define test-url4 (string->url "http://isenseproject.org//api/v1/projects?email=kaitlyn.carcia@hotmail.com&password=***&project_name=OPL+Project"))
(display-pure-port (post-pure-port test-url4 #f))
```
But it seems to work because my new project is on iSENSE, and the following is returned:
```
> {"id":954,"featuredMediaId":null,"name":"OPL Project","url":"http://isenseproject.org/projects/954","path":"/projects/954","hidden":false,"featured":false,"likeCount":0,"content":"","timeAgoInWords":"less than a minute","createdAt":"March 31, 2015","ownerName":"Kaitlyn Carcia OPL","ownerUrl":"http://isenseproject.org/users/2978","dataSetCount":0,"fieldCount":0,"fields":[]}
```
So that's my story working with this API. I really, really want to use iSENSE now.
