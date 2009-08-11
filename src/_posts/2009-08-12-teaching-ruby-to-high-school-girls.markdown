---
layout: blog
title: Teaching Ruby to High School Girls
---
(Guest post by [Sarah Mei](http://sarahmei.com/blog))

For the last few years I've been volunteering one day each summer at the [GetSET](http://getset.org) summer camp in Santa Clara. GetSET is pretty awesome, though their website is horrible. It's a week-long sleepaway summer camp for girls from under-represented minorities who live in the San Jose area. They first attend the summer before their freshman year of high school, and they return each year with the same group of cohorts.

During the week, they do a variety of half-day and whole-day workshops on different types of engineering - civil, mechanical, aerospace, and, of course, software. In addition, they tour a different college campus each year, and get help with college prep and applications. It's run by the Society of Women Engineers, and all the administrators, instructors, and TAs are volunteers.

For the last two years, I've been a TA in various programming classes, which basically meant all I had to do was show up. That suited me pretty well. But this year, when they sent out the big volunteer email in March, they said they were looking for someone to teach Intro to Java. I'd been working on [Ruby on Rails workshops for women](http://sfrubyworkshops.com), and I saw a chance to extend the work to kids.

"Well," I said, "I can't do Java, but if you want to make it Intro to Ruby, I'd totally do it." I wasn't expecting them to be too enthusiastic. SWE membership is mostly women who work in large companies, where Ruby doesn't have much of a foothold, and interpreted languages in general are regarded with some suspicion.

I got the affirmative response in less than 10 minutes. Go SWE!

It was half-day workshop, which means I had three hours with the girls. I quickly realized that wasn't going to be enough time for even a cursory overview of Rails. But I knew something visual would keep their interest better than cursor/command-line programs (particularly as this workshop was after lunch), plus I knew [Sarah Allen](http://ultrasaurus.com) had taught [Shoes](http://shoooes.net) with 4th and 5th graders. So I decided to build on her ideas.

You can see [the slides I put together](http://sarahmei.github.com/getset/ruby_shoes.html#0) (they're HTML; use the arrow keys to move between them). They're pretty minimal - before we got started coding, we first did a quick welcome (slides 0-2), agenda and introductions (slides 3-7), and a little bit about "what is programming?" (slides 8-12). For the latter, I said that many people think programming is working in an endless cube farm (slide 9), with weird, possibly insane co-workers (slide 10), and doing a lot of math (slide 11). In fact, programming is more about language (slide 12) than math. I asked who in the class was bilingual; most of them raised their hands. I said programming is about learning to speak the language of the computer, and I could almost see the lightbulbs lighting up. 

Then we talked about Ruby and Shoes (slides 13-17). I asked who had ever been a translator, going between someone who didn't speak English and someone who did - most raised their hands. I said the Ruby interpreter (slide 13) translates your Ruby code into something the computer can understand, just like a human interpreter translates from one language to another. Shoes (slide 14) translates your Shoes code into something Ruby can understand. Your program is on top of the stack (slide 16). They were really be getting it, which was exciting!

Then I explained the workflow we'd use to program (slide 18). We had a folder on the desktop to hold the source file. To open the source file for editing, we dragged it to the Notepad shortcut. To run it, we dragged it to the Shoes shortcut. This worked really well - much more successful than the edit-compile-run cycle that we had done in the Java class I was a TA for two years ago.

That was the end of the slides - we then launched into collaborative coding!

I had them start with a blank file. A year ago, I was a TA in the Javascript class with this same group of girls (they were then juniors). The Javascript class is their first programming class, and the girls start with an almost-working Javascript file and just edit it to get it working. This time, I wanted to show them how in programming you really can start with nothing, and end up with something really cool.

Together we wrote an etch-a-sketch program in a series of small steps. My philosophy is early and frequent visual feedback to keep interest, so each step was designed to be a fairly minor change. 

For each step, I coded live on the projector with Notepad's font at 48pt. Then I ran the program to show them how the modified output would look like. Then I switched back to the code, and walked around with my TAs to help the girls troubleshoot when they hit errors trying to make the change that was onscreen. There were 20 girls, 2 TAs, and me. We could have used one more TA - then we would have had one helper per 5 girls which, I think, would have made the steps go faster.

**Step 0 - a blank file**

<div style="border: 1px dashed blue; padding-left: 7px;"><code><pre>
Shoes.app do
 
end
</pre></code></div>

Here we talked about do/end. I didn't explain blocks, exactly; I just said they'd be seeing the do/end combination in other places, and it just signifies the beginning and end of a section. Most of them typed <code>shoes</code> instead of <code>Shoes</code> at first, so we also talked about how computers are picky about spelling and capitalization of some words. 

When you run this, you get a blank window titled "Shoes," which I don't think is super exciting, but the girls thought it was pretty cool.

**Step 1 - add some text**

<div style="border: 1px dashed blue; padding-left: 7px;"><code><pre>
Shoes.app do
  para "Hello, world"
end
</pre></code></div>

Here we talked about strings. I said they could put whatever they wanted inside the quotes - the computer isn't picky about spelling and capitalization there. It is a sort of "free zone" for text. Also, I explained that "para" is short for "paragraph" the way "app" is short for "application," and that they'd be seeing a lot of abbreviations in programming. 

For several folks that was an a-ha moment; para is the Spanish word for "for," as in something "para usted" is "for you," and they'd been thinking Shoes spoke Spanish!

**Step 2 - add some attributes to the text**

<div style="border: 1px dashed blue; padding-left: 7px;"><code><pre>
Shoes.app do
  para "Hello, world", :align => 'center', :size => 'xx-large'
end
</pre></code></div>