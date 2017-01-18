---
layout: project
title: Everwealth
thumbnail-path: "../img/phone.png"
short-description: Everwealth is an AI-powered wealth management website that performs the same services as an individual investment advisor.
github-repository: orlando21/product-showcase
demo-url: http://gregbabb.com/product-showcase/index.html

---
This was a project for Bloc's [UX/UI fundamentals course](https://www.bloc.io/ux-design-bootcamp), and allowed me the opportunity to practice requirements gathering, competitive analysis, user research, site design, and development. The goal was to develop a simple and responsive page that sells (e.g., product showcase).


### Requirements and brand identity

I was given free reign to develop an idea for any product I wanted. Having an interest in fintech, I decided on a product that, for a token minimum starting balance, will invest your spare change for you according to your preferences and risk profile. The imaginary product competes with similarly positioned apps like [Wealthfront](https://www.wealthfront.com/) and [Betterment](https://www.betterment.com/).

After studying the app marketplace for a while, I proposed my own set of potential features (user stories) and wrote up a product brief. After discussion and approval from my Bloc mentor, I focused on the values and target audience of the product. I wrote up a S.W.O.T. of three other main competitors and developed a few personas of typical customers.

I wanted to target a younger crowd with little investing experience but wanting to save for the future. The product should feature easy onboarding comprising registration of users' investing preferences and assessment of risk. Users also don't have to worry about how to allocate their funds as a nice AI engine should come with the product ;-)

The idea of investment, simplicity, and growth appealed to me, and I found that the color green should figure in the website's logo and style. For the logo, I sketched out different versions of trees, but settled on a green leaf.

{:.center}
![]({{ site.baseurl }}/img/styleguide.jpg)

As well, it was necessary to find an appropriate color palette (above) comprising main and supporting (secondary and triadic) colors, which would appeal to the audience.

### Wireframing and testing

I had a couple of ideas for the landing page and sketched out a few versions in Balsamiq. Each version featured a different hero section, followed by varying sequences of sections for testimonials and product features.

{:.center}
![]({{ site.baseurl }}/img/low_fi.png)

Afterwards I chose one of the wireframes for mocking up in Sketch, my preferred design tool. Here I could put meat on the bones of the wireframe and design everything with the selected brand identity, including colors for all the page elements and calls to action. Sketch is intuitive and easy to use, and various plugins make life easier, such as a feature to show the dimensions and distances (in pixels) between elements.

Once a prototype of the landing page was designed, I uploaded PNGs of the artboards to [InVision](https://www.invisionapp.com/) for feedback from potential users. As a result, I changed some of the copy on both the landing and fees pages.

### Development

I developed the site with HTML5, CSS3, and jQuery. The challenge was a) coding a site that was as close as possible to the mockup, and b) making it responsive. Responsiveness was hard to achieve as I didn't start with a mobile first approach and had to put quite a lot of effort in media queries for small-screen phones (320px), tablets (768px), and laptops (992px).

I coded the HTML and CSS from scratch and use jQuery to both toggle the icon in mobile view and to dynamically change the color of the floating navbar when scrolling.

I'd been quite impressed with [CSS Grid](http://gridbyexample.com/what/) and decided to implement it. Therefore please make sure to enable CSS Grid in your browser for optimal viewing (also, I suspect it'll be best viewed in Chrome).

Although [the site](http://gregbabb.com/product-showcase/index.html) has many links and calls to action, currently only two pages are developed (landing and fees).

### Final thoughts

Most of my effort for this project went into the user requirements and branding. For the development phase, there were definitely some lessons learned on the wisdom of starting with a mobile first approach, as getting all your elements in order at different screen sizes can be challenging. My decision to go with CSS Grid Layout was probably overkill for such a simple page and didn't help me as much with responsiveness as I had hoped.

But definitely simple frameworks for responsive landing pages are the way to go.
