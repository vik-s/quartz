---
title: About Writing Newsletters
tags:
  - misc_letters
project: substack
date_published: 2024-05-05
status: 🟢
final title:
---
Hey, I'm Vikram and thank you for reading.

It's been a week filled with work deadlines and I am traveling to Bangalore, India, at about the same time this edition goes live. Time has been short to write a deep technical article. I usually take my time to explain hard topics and draw figures to show ideas clearly. Instead of rushing an article with potential for error, I figured I'll write  about writing a newsletter. 

Pretty meta. Let's dig in.
## Newsletter as an educational medium

Much of RF engineering content is held within moats, and is accessible only through conventional mediums of education such as textbooks and universities. There are situations when these forms of media don't apply.
- You want to learn RF because you find it interesting and cannot justify the cost and commitment of an entire educational degree to learn it.
- You find the rigor of textbooks hard to comprehend and difficult to directly apply to engineering situations.
- You find the need to apply RF concepts at work due to a new project, but have not had a formal education in it.
- You would like to directly learn from somebody who has spent their career in it.
- You are about to interview, and need to review as many concepts as you can in a short span of time.

For all these cases, a weekly newsletter offers the option of delivering digestible pieces of technical content directly to the reader. Newsletter might imply actually writing about news, which I do not at the moment. 'Techletter' is probably a better term.

The downside is that you may not exactly find what you are looking for. For example, I've been writing articles on RF systems of late, but you might want to learn signal integrity or power electronics. Even the field of RF is vast, and I most certainly won't have the expertise to write about all of it. 

This is a problem in any domain. However, with sufficiently deep research I will be able to cover topics to at least to a fundamental level. At least, I think so. The other solution is to have more people write such newsletters to cover the space of technical topics available. In the rest of this short article, I'll cover what my process looks like - and hopefully inspire you to start your own.

## Content Workflow

Let us address the elephant in the room. How does one do this with other commitments like a job and family? Simple answer: it is hard to create good content. It often requires early mornings, late nights and writing/thinking about the newsletter at every possible moment. You should really enjoy putting thoughts into text if you were to do this long term and find ways not to burn out. If you can't deliver a technical article on time, that's okay. There are plenty of things to still write about - experiences, advice, things you found interesting, etc. 
### Topics
I don't overthink this. I just write whatever I am curious about that week, or have been thinking of. I write one off articles that are unconnected to anything. Or, I continue a thread of technical topics. I also discontinue threads, and pick them again later. The main idea is for me to stay interested and motivated. I don't want this to start feeling like a job. It should feel like fun for me to stay at it and not burnout.
### Tools
I love shiny software tools as much as the next guy. The right answer here is anything will do, but here is what I use.
- Text editor
	- I use Obsidian with the AnuPpucchin theme https://github.com/AnubisNekhet/anuppuccin . I like the ability to link to different articles I write. It is free to use, and all documents stay local. This means I can write anywhere even without internet. The whole editor is snappy, and I much prefer this to Notion. I use YAML frontmatter to put metadata into each document I write. I then use the Dataview plugin to automatically sort my articles based on topic and status.
- Images
	- I use the Excalidraw plugin in Obsidian. I simple love the ease of use of this tool and can create pretty complicated diagrams easily. I also like the informal look of the generated diagrams, which gives it a different feel than a technical blog or textbook. I use Canva (free version) to generate thumbnails for Substack and images for social media. In Canva, I have templates with the right image sizing for each platform. This makes it easy to duplicate it each time and create new images.
- Knowledge management
	- I use Zotero to store all the pdfs, and I read and highlight them in the same tool. It's fully featured and free to use. If your pdf collection grows, then Zotero offers paid cloud storage for a modest fee. But I store my collections on my own home server (yes, I am a nerd, I run my cloud infrastructure.) I also have a paid subscription to Readwise. I can quickly save webpages to it and use their reader to read and highlight those articles later. Both Zotero and Readwise have integration with Obsidian so that highlighted notes are directed imported into my writing tool.
- Writing style
	- I use Quillbot (free version) if I have time or feel that my writing is too verbose. It helps me rephrase my sentences to make it easier to read. I need to do this manually for each paragraph and re-read it after the tool finishes paraphrasing it to make sure the meaning did not change. I've tried hemingwayapp too, but it didn't appeal to me.
- ChatGPT
	- I use it to explain some concepts to me, or to list out concepts relevant to a particular topic. It helps me get a top level perspective of what I am writing about. I also use it to summarize my own writing so that I can generate some key takeaways. Sometimes I try to generate article titles but ultimately abandon it because it is too cheesy.

## The Writing

Once I know what I'm writing about, I spend about a day or two reading about it. Not everything I read is deep. I skim through a lot of stuff. Due to my prior experience in the field of RF, I can usually tell what the gist of anything is - even with equations. I'm only looking for the main takeaway at this point.

When I have sufficiently poked through textbooks, web articles, published papers and white papers, I write an outline. I specifically like to do this the night before I start writing an article - a trick I learned from Dickie Bush. I usually start writing at 5am, and at that moment, my only goal is to expand on the bullet point outline I made the night before. I dive right into writing without worrying about how to start.

When I write the article, I just go as fast and far as I can without stopping. I ignore spelling mistakes and grammatical issues, and just get the ideas on to the screen. It is much easier to edit content later than try to generate good writing from the get go. I dive deep into books, pdfs and articles that have content related to what I am writing about. I make sure that I understand it thoroughly, and express that in a simple and understandable way in my article.

I put a lot of emphasis on using short sentences and simple language. I admire the writing style of Paul Graham, and his essay 'on writing' is a favorite of mine. The goal is not to write as much as possible, but instead to deliver as much value in as few words as possible.

Ultimately, I do look at article length because one of the promises I made in this Substack is to keep articles short and readable. I've found that about 2000 words keeps the reading time under 10 mins. If my writing significantly exceeds that, then I just conclude the article in a reasonable way and use the rest for my next article.

The whole writing process takes about 2-3 days. Then I spend a day making figures for the article. I create one Excalidraw canvas per article and in it, I make all the necessary figures. I export each image out as it's own png file.

Finally, I copy everything I wrote in Obsidian and paste it into the substack editor. I spend about 30 minutes formatting everything to make look the way I want it to. At this point I insert the figures I created. I create a thumbnail for Substack and schedule it for publishing.

The whole process takes about 10-15 hours per week, depending on the complexity of the topic.
## Social Media

An often overlooked aspect of writing online is to spend a sizable amount of time delivering value on social media platforms. If no one knows you write content, then it just won't be found. So it is up to you to market it effectively on online platforms. For RF engineering content, I have found that LinkedIn is where most of my people engage. I got little attention on X, and decided it's not worth it.

On Sunday, I use a tool called Hypefury to write and schedule LinkedIn posts for the week. I try to write bite sized pieces (200 words) that deliver one key concept or idea. The writing style here is even more concise. The main idea is to grab attention to your content. Walls of text in social media just get scrolled past. Attractive images have done best for me. There's something scroll-stopping about a nice picture. Luckily, I have created quite a few when writing my article. So I repurpose most of it.

I include a link to the article I have written at the end of the post, if people want to read more. The main idea is to drive your LinkedIn audience to Substack so that it drives free subscriptions.

It does not end there. It is important to engage with your audience on social media. Online relationships are important and people provide different perspectives on your content. This sparks ideas that fuels future articles. Sometimes, people point out mistakes I have made and this gives me the chance to correct them. As a result, each Substack article is a living breathing document that evolves. The email you get is only a snapshot of the real thing.









