---
layout: blog
title: Teaching Ruby to High School Girls
---
(Guest post by [Sarah Mei](http://sarahmei.com/blog))

For the last few years I've been volunteering one day each summer at the [GetSET](http://www.joyandshine.com/GetSET/) summer camp in Santa Clara. GetSET is pretty awesome, though their website is horrible. It's a week-long sleepaway summer camp for girls from under-represented minorities who live in the San Jose area. They first attend the summer before their freshman year of high school, and they return each year with the same group of cohorts.

During the week, they do a variety of half-day and whole-day workshops on different types of engineering - civil, mechanical, aerospace, and, of course, software. In addition, they tour a different college campus each year, and get help with college prep and applications. It's run by the Society of Women Engineers, and all the administrators, instructors, and TAs are volunteers. (And they always [need donations!](http://www.joyandshine.com/GetSET/?q=SupportGetSET))

Until this year I was just a TA for various programming classes, which basically meant all I had to do was show up. This year, though, they didn't have anyone to teach Intro to Java. I'd been working on [Ruby on Rails workshops for women](http://sfrubyworkshops.com), and I saw a chance to extend the work to kids.

"Well," I said, "I can't do Java, but if you want to make it Intro to Ruby, I'd totally do it." I wasn't expecting them to be too enthusiastic. SWE membership is mostly women who work in large companies, where Ruby doesn't have much of a foothold, and interpreted languages in general are regarded with some suspicion.

I got the affirmative response in less than 10 minutes. Go SWE!

It was half-day workshop, which means I had three hours with the girls. I quickly realized that wasn't going to be enough time for even a cursory overview of Rails. But I knew something visual would keep their interest better than cursor/command-line programs (particularly as this workshop was after lunch), plus I knew [Sarah Allen](http://ultrasaurus.com) had taught [Shoes](http://shoooes.net) with 4th and 5th graders. So I decided to build on her ideas.

**Introduction**

You can see [the slides I put together](http://sarahmei.github.com/getset/ruby_shoes.html#0) (they're HTML; use the arrow keys to move between them). They're pretty minimal - before we got started coding, we first did a quick welcome (slides 0-2), agenda and introductions (slides 3-7), and a little bit about "what is programming?" (slides 8-12). For the latter, I said that many people think programming is working in an endless cube farm (slide 9), with weird, possibly insane co-workers (slide 10), and doing a lot of math (slide 11). In fact, programming is more about language (slide 12) than math. I asked who in the class was bilingual; most of them raised their hands. I said programming is about learning to speak the language of the computer. I could see the lightbulbs lighting up! 

Then we talked about Ruby and Shoes (slides 13-17). I asked who had ever been a translator, going between someone who didn't speak English and someone who did - most raised their hands. I said the Ruby interpreter (slide 13) translates your Ruby code into something the computer can understand, just like a human interpreter translates from one language to another. Shoes (slide 14) translates your Shoes code into something Ruby can understand. Your program is on top of the stack (slide 16). 

Then I explained the workflow we'd use to program (slide 18). We had a folder on the desktop to hold the source file. To open the source file for editing, we dragged it to the Notepad shortcut. To run it, we dragged it to the Shoes shortcut. This worked really well - much more successful than the edit-compile-run cycle that we had done in the Java class in years prior.

That was the end of the slides. After that, it was all collaborative coding!

**Philosophy**

This is an introduction to programming, so I focused on getting them excited about programming and what it can do. This meant that they got away with some horrible style and, once in a while, some magic incantations. 

Ruby purists may protest that I didn't talk about objects, or classes, but for the ones who keep going with programming, they'll get that soon enough. In this class, I just wanted them to have fun and see what they could do with code.

Despite that focus, they formed an intuitive understanding of some pretty sophisticated programming concepts, as you'll see below.

**Setup**

I had them start with a blank file. Last year, I was a TA in [Akkana Peck's](http://shallowsky.com) Javascript class with this same group of girls when they were juniors. The Javascript class is their first programming class, and the girls start with an almost-working Javascript file and edit it to get it working. This time, I wanted to show them how in programming you really can start with nothing, and end up with something really cool.

Together we wrote an etch-a-sketch program in a series of small steps. I used the agile development philosophies of short iterations and frequent deployment to drive the project. Short iterations means that each step is a fairly minor change - we add one thing that the program didn't have before. Frequent deployment means that we ran the code constantly to get strong visual feedback that they were making progress. These in combination seemed to hold everyone's interest. 

For each step, I coded live on the projector with Notepad's font at 48pt. Then I ran the program to show them what the modified output would look like. Then I switched back to the code, got up, and walked around with the TAs to help the girls troubleshoot when they hit errors trying to make the change that was onscreen. There were 20 girls, 2 TAs, and me. One more TA - for one helper per five girls - would have been perfect.

**Step 0 - a blank application**

<div style="border: 1px dashed blue; padding-left: 7px;"><code><pre>
Shoes.app do
 
end
</pre></code></div>

Here we talked about do/end. I didn't explain blocks, exactly; I just said they'd be seeing the do/end combination in other places, and it just signifies the beginning and end of a section. Most of them typed `shoes` instead of `Shoes` at first, so we also talked about how computers are picky about spelling and capitalization of some words. 

When you run this, you get a blank window titled "Shoes," which I don't think is super exciting, but the girls thought it was pretty cool.

**Step 1 - add some text**

<div style="border: 1px dashed blue; padding-left: 7px;"><code><pre>
Shoes.app do
  <span class="changedcode">para "Hello, world"</span>
end
</pre></code></div>

Here we talked about strings. I said they could put whatever they wanted inside the quotes - the computer isn't picky about spelling and capitalization there. It's a sort of free zone for text. Also, I explained that `para` is short for "paragraph" the way `app` is short for "application," and that they'd be seeing a lot of abbreviations in programming. 

For several folks that was an a-ha moment; para is the Spanish word for "for," as in something "para usted" is "for you," and they'd been thinking Shoes spoke Spanish!

**Step 2 - add some attributes to the text**

<div style="border: 1px dashed blue; padding-left: 7px;"><code><pre>
Shoes.app do
  para "Hello, world"<span class="changedcode">, :align => 'center', :size => 'xx-large'</span>
end
</pre></code></div>

Here we talked about attributes as qualities that you attached to a particular object. In this case, we're attaching them to the paragraph object, so they're on the same line as `para`. 

The girls ran into a few issues here getting the punctuation right - commas after everything, colons before the attribute names, hashrockets (`=>`) between attributes and their values, and quotes around the values. I didn't explicitly talk about symbols, hashes, parameters, or implied hashes at the end of a method call. Instead I just pointed out that attributes always go at the end of a line, after the important stuff like what text you want.

**Step 3 - custom window title**

<div style="border: 1px dashed blue; padding-left: 7px;"><code><pre>
Shoes.app <span class="changedcode">:title => "My awesome application"</span> do
  para "Hello, world", :align => 'center', :size => 'xx-large'
end
</pre></code></div>

We went through this one pretty quickly because the girls were eager to get on to changing the background color. But I did point out that this time we're attaching an attribute to the entire program, instead of to a particular piece of it, so therefore it goes on the `Shoes.app` line.

**Step 4 - background color**

<div style="border: 1px dashed blue; padding-left: 7px;"><code><pre>
Shoes.app :title => "My awesome application" do
  <span class="changedcode">background tomato</span>
  para "Hello, world", :align => 'center', :size => 'xx-large'
end
</pre></code></div>

I encouraged the girls to try other named colors. When `fushia` didn't work but `fuschia` did, we talked again about the computer's pickiness. When `dark&nbsp;red` didn't work but `darkred` did, we talked about identifiers, and how they can't have spaces. 

One girl asked if we could add an attribute to the `para` object to change the text color. Aha, they were paying attention when we talked about the scope of attributes! I didn't know the attribute name, so I looked it up. As I did so, I talked about how you don't have to memorize how everything is done to be a good programmer. You just need to know where to find out.

**Step 5 - text color**

<div style="border: 1px dashed blue; padding-left: 7px;"><code><pre>
Shoes.app :title => "My awesome application" do
  background tomato
  para "Hello, world", :align => 'center', :size => 'xx-large'<span class="changedcode">,</span> 
                       <span class="changedcode">:stroke => saddlebrown</span>
end
</pre></code></div>

They played around with named colors some more. Once they found a few colors that bona fide didn't exist as named colors in Shoes, like "copper," we looked at <a href="images/shoes_colors.jpg">the color page in the Shoes manual</a>. Each color there has its equivalent `rgb` call underneath. I explained that you could say `tomato`, or you could equivalently say `rgb(255, 99, 71)`. The first number is red, the second color is green, and the third color is blue, and every color is a combination of those three colors. Since `tomato` is a reddish color, its first number, the red, is high relative to the other two. 

If the color you want isn't named, you can use its `rgb` equivalent. I asked for suggestions for a color to try to make, and we settled on periwinkle. I sat down at the projector and erased `tomato` and replaced it with `rgb(`. Then I asked: the first number is red, the second color is green, the third color is blue, so what three numbers should I try?

The shouted suggestion was 100, 0, 100. I put that in, saved it, dragged it onto Shoes, and we got a really deep purple. I went back to color page in the Shoes manual, and we looked at how the light colors like `antiquewhite` and `beige` have pretty high numbers for all three colors. On the other hand, `black` has all zeroes. So which direction should we take the numbers to get a lighter purple? They totally got it. Some girls tried really high numbers, like 500, and the color looked the same as lower numbers, like 300. So we talked about how the highest is 255, though I didn't touch on binary or why that's the limit.

At this point we took a break, and some of the girls continued experimenting with RGB values on their own. When we came back, a few girls had worked out pretty good versions of periwinkle, which is something like `rgb(180,170,205)`. But how do you add it to Shoes' list of colors?

This gave us the opportunity to talk about methods and objects a little bit. I pointed out that in our list of `para` attributes, they all had quotes around them except for `saddlebrown`. That's because `saddlebrown` is a method call, while the other two are strings. We need to add a `periwinkle` method, and then we call it like all the other ones.

**Step 6 - named color method**

<div style="border: 1px dashed blue; padding-left: 7px;"><code><pre>
Shoes.app :title => "My awesome application" do
  <span class="changedcode">def periwinkle</span>
    <span class="changedcode">rgb(180,170,205)</span>
  <span class="changedcode">end</span>
  background <span class="changedcode">periwinkle</span>
  para "Hello, world", :align => 'center', :size => 'xx-large', 
                       :stroke => saddlebrown
end
</pre></code></div>

I pointed out def/end as another set of section delimiters like do/end. In this case, we're saying that this method starts with `def`, short for "define" a method, and ends with `end`. I also talked about whitespace a little bit, because most of the girls weren't using any indentation in their code. I pointed out that indenting like I had done can help you keep track of your `end`s. This got more important later on!

**And now for something completely different**

We got a lot of mileage out of colors, which I wasn't expecting. I thought we'd run quickly through background colors and get into event loops before the break, but the girls were enjoying adding their own color combinations, and I did get to talk about RGB, which I hadn't been expecting to do.

Now though it was time to move on, so I announced that we were going to do something completely different - make the application interactive. 

**Step 7 - adding a button**

<div style="border: 1px dashed blue; padding-left: 7px;"><code><pre>
Shoes.app :title => "My awesome application" do
  def periwinkle
    rgb(180,170,205)
  end
  background periwinkle

  <span class="changedcode">button "Change the text" do</span>
    <span class="changedcode">@headline.text = "I'm changed!"</span>
  <span class="changedcode">end</span>

  <span class="changedcode">@headline = </span>para "Hello, world", :align => 'center', 
                                   :size => 'xx-large', 
                                   :stroke => saddlebrown
end
</pre></code></div>

We added two things: a `button` block, and an assignment. Here I talked about variables: stuff that you want to be able to get ahold of again later. In this case, we're assigning our `para` object to a variable called `@headline` and saving it, so that when someone presses the button, we can change its text.

I pointed out the do/end associated with the `button` block. At this point, a lot of girls were starting to have syntax errors because they forgot an `end` somewhere, and some got so annoyed that they actually started indenting. Success!

**Step 8 - coordinates**

<div style="border: 1px dashed blue; padding-left: 7px;"><code><pre>
Shoes.app :title => "My awesome application" do
  def periwinkle
    rgb(180,170,205)
  end
  background periwinkle

  <span class="changedcode">animate do</span> 
    <span class="changedcode">@button, @left, @top = self.mouse</span>
    @headline.text = <span class="changedcode">"#{@button} #{@left} #{@top}"</span>
  end

  @headline = para "Hello, world", :align => 'center', 
                                   :size => 'xx-large', 
                                   :stroke => saddlebrown
end
</pre></code></div>

In this step, we replaced the `button` block with an `animate` block that displays the current mouse coordinates in the `para` element. All window applications have an "event loop" that runs several times a second and checks for input. In this case, our `animate` block runs several times each second. Inside it, we call a built-in method in Shoes (like the color names are built-in methods) that gives us the current mouse coordinates. It gives us 3 numbers, which we store in 3 variables: `@button`, `@left`, and `@top`. 

The coordinates for the window start at 0, 0 in the top left corner. `@left` is how many pixels from the left-hand side of the window the mouse is, `@top` is how many pixels down from the top the mouse is, and `@button` tells us whether or not the mouse button is pressed. They didn't totally get it until they wrote the code and saw it working, and saw how it updated the numbers whenever they moved the mouse or clicked inside the window.

The string interpolation was the hardest part to explain, and to help them with. `@button`, `@left`, and `@top` are numbers, but they need to be strings if we want to display them in the `para` element. So we use `#{}` to turn them into strings. For most of the girls this was pretty much a magic line, I think, but since it was only there to demonstrate how the `animate` block works, I didn't worry about it too much.

I gave them some time to experiment with the coordinates - pushing the mouse all the way up into a corner, running it down along one of the edges, etc.

**Step 9 - drawing lines based on mouse coordinates**

<div style="border: 1px dashed blue; padding-left: 7px;"><code><pre>
Shoes.app :title => "My awesome application" do
  def periwinkle
    rgb(180,170,205)
  end
  background periwinkle

  animate do 
    @button, @left, @top = self.mouse
    <span class="changedcode">line 0, 0, @left, @top</span>
  end

  @headline = para "Draw!", :align => 'center', 
                            :size => 'xx-large', 
                            :stroke => saddlebrown
end
</pre></code></div>

In this step we replaced the `para` text replacement with a call to `line`, which draws a line between the first two coordinates and the second two coordinates. In this case, we're drawing a line from 0, 0 (the top left corner) to the current location of the mouse.

This went pretty quickly, and it really drove home that 0, 0 is the top left corner of the window. Some of the girls experimented with different origins so they could draw circular stars which I thought was a cool addition.

One thing we did during this step that didn't work so well was to change the names of `@left` and `@top` to the more descriptive `@mouse_column` and `@mouse_row`. I talked a little about how you need to give variables descriptive names, but they were too long to see effectively in 48-pt font on the projector, and it caused odd problems for the girls when they didn't replace all of the uses of `@left` and `@top`. 

I realize now, as I mentioned in the Philosophy section, that with beginners, you can't be too fussy about style. If they want to skip indentation altogether and give all their variables one-letter names, that's fine, as long as they're still excited about what they're doing. *I'm not trying to make good programmers at this point; I'm just showing them how much fun it is.*

If they keep going with it, they'll realize that there's a reason you indent and give your variables descriptive names, and they'll start doing it. But if I just tell them to, they won't. And nothing ensures that they drop it like a hot potato better than harping on them to write maintainable code.

Anyway! Moving on.

**Step 10 - only drawing a line when the button is down**

<div style="border: 1px dashed blue; padding-left: 7px;"><code><pre>
Shoes.app :title => "My awesome application" do
  def periwinkle
    rgb(180,170,205)
  end
  background periwinkle

  animate do 
    @button, @left, @top = self.mouse
    <span class="changedcode">unless @button == 0</span>
      <span class="changedcode">line 0, 0, @left, @top</span>
    <span class="changedcode">end</span>
  end

  @headline = para "Draw!", :align => 'center', 
                            :size => 'xx-large', 
                            :stroke => saddlebrown
end
</pre></code></div>

This was another fairly quick change - all we added was the `unless` block around the `line` call. Now it only draws a line when a mouse button is down, which allowed the girls to better control what the stars looked like.

We did talk a little bit about `=` (assignment) and `==` (comparison). Because they already knew that `@button` was 0 when no mouse buttons were down, this seemed to make sense.

**Step 11 - drawing from previous to current coordinates**

<div style="border: 1px dashed blue; padding-left: 7px;"><code><pre>
Shoes.app :title => "My awesome application" do
  def periwinkle
    rgb(180,170,205)
  end
  background periwinkle

  animate do 
    <span class="changedcode">previous_left = @left</span>
    <span class="changedcode">previous_top = @top</span>
    @button, @left, @top = self.mouse
    unless @button == 0
      line <span class="changedcode">previous_left, previous_top,</span> @left, @top
    end
  end

  @headline = para "Draw!", :align => 'center', 
                            :size => 'xx-large', 
                            :stroke => saddlebrown
end
</pre></code></div>

I thought this would take us a long time to get through, but to my surprise, the girls seemed to pick it up really quickly. We had already talked about variables and how you use them to store something you want to get ahold of later. So I asked them: each time you run through the loop, what's the value of `@left` and `@top` *before* you call `self.mouse`? 

They got it - at that point, those variables contain the values you set them to the *last* time you ran the loop. So we save them again before we replace them with the current values, and then we draw a line from the old values to the new values.

Ta-da, it's a drawing program! They played around with it for a while. One girl discovered she could change the `line` color by adding a `:stroke` attribute to the `line` call; that was a popular addition. Another girl dug into the documentation she had seen me use, and figured out how to use the color picker to let the user select a color for the line!

**Step 12 - a clear button**

<div style="border: 1px dashed blue; padding-left: 7px;"><code><pre>
Shoes.app :title => "My awesome application" do
  def periwinkle
    rgb(180,170,205)
  end
  background periwinkle

  animate do 
    previous_left = @left
    previous_top = @top
    @button, @left, @top = self.mouse
    unless @button == 0
      line previous_left, previous_top, @left, @top
    end
  end

  <span class="changedcode">button "Clear" do</span>
    <span class="changedcode">background periwinkle</span>
    <span class="changedcode">@headline.remove</span>
    <span class="changedcode">@headline = para "Draw!", :align => 'center', </span>
                              <span class="changedcode">:size => 'xx-large', </span>
                              <span class="changedcode">:stroke => saddlebrown</span>
  <span class="changedcode">end</span>

  @headline = para "Draw!", :align => 'center', 
                            :size => 'xx-large', 
                            :stroke => saddlebrown
end
</pre></code></div>

The last addition we had time for was a clear button, so that the girls didn't have to quit the program and start over to get a fresh drawing surface. It was pretty straightforward. You have a `button` block (which we'd seen before, when we changed the paragraph text), and then you `remove` the old text, which is now underneath the background, and redraw it on top of the background.

If you don't `remove` it, even though it's now underneath the background, it will get in the way of a new one being drawn, and your headline will slowly creep down the window. This gave us the opportunity to talk about the Z-axis, and how, conceptually, some things are on top of other things in the window. 

**Conclusions**

The girls rated the workshop quite highly, so I think it was a success. Next time I do this, though, I'll make a few changes:

* Arrange some extra curriculum steps in case everyone's going faster than I expect. The girls got a lot further with the application than I thought they would. I originally only planned out as far as the Clear button, figuring we'd be lucky to get through saving the previous coordinates. But we got through everything, including the RGB detour, including just enough time at the end to implement Clear.

* Prepare a handout with challenge goals for each step. Some girls got through everything really quickly and then looked for more to do. While most found the Shoes manual and started experimenting, a few started doing meebo and facebook. A little more direction would have helped channel their enthusiasm instead of letting it dissipate between steps.

* Prepare a handout with URLs to resources and directions for downloading and installing Shoes themselves.

* Buy some cheap USB keys so they can take home their .rb file, a Shoes installer, the reference code, and copies of the handouts in digital form.

Teaching this class was a fantastic experience, and having the two TAs - both experienced programmers, but new to Ruby and Shoes - was invaluable. Thanks to Alice Callen and SWE for letting me put this together. I hope I'll be able to do it again next year.

In the meantime, feel free to use my slides and code as the basis for your own Ruby workshop. Everything is available at [Github](http://sarahmei.github.com/getset). I've released my slides under the [Creative Commons Attribution license](http://creativecommons.org/licenses/by/3.0/us/), and the code under the [MIT license](http://www.opensource.org/licenses/mit-license.php). 

I'd love to get your ideas on how to improve this workshop. You can fork the project on Github, or [leave a comment on this post](http://www.sarahmei.com/blog/2009/08/15/teaching-ruby-to-high-school-girls/).

[Click here to leave a comment](http://www.sarahmei.com/blog/2009/08/15/teaching-ruby-to-high-school-girls/)