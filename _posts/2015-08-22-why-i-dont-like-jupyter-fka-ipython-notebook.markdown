---
layout: post
title: Why I Don't Like Jupyter (FKA IPython Notebook)
modified: 
categories: articles
excerpt: Especially for data science
tags: [R, Python, Data Science]
published: true
comments: true
author: kirill
image:
  feature:
  credit:
  creditlink:
share: true
date: 2015-08-22T16:30:21+02:00
---


<span class = "dropcap">D</span>on't get me wrong, it's certainly a great tool for presenting your code or even reporting, but everytime I use it for explorative, interactive data science, I keep switching to other tools quite quickly and wonder why I am still even trying to use it. I just mostly end up with messy, broken, "un*git*able" and unreadable analyses and I refuse to accept that this is my fault, but rather believe it is caused by the design of Jupyter/IPython.

#### It messes with your version control.

The Jupyter Notebook format is just a big json, which contains your code and the outputs of the code. Thus version control is difficult, because every time you make minimal changes to the code or rerun it with updated data, you will have to commit the code and all new results or outputs of it. This will unnecessarily blow up your repos used disk memory and make the diffs difficult to read (which would give a whole new meaning to the abbreviation *diff*). Yeah, I know, you also can export your code to a script (in my case .R script with the code), but then, why the overhead of using the code in two formats?
  
#### Code can only be run in chunks.
	
In Jupyter you can not run the code line by line. This means for testing or experimenting with your code or data, you either split your Notebook in one-liner chunks, which looks awful, or you make sure, that the lines you want to test are in a chunk, which has no lines, that take long to compute thing, you don't actually want to.

#### It's difficult to keep track

If you don't work your way down the notebook, but also work wih chunks in between other chunks, because you are still playing with the code, reviewing it or adapting it to new circumstances, you end up with a notebook, which has newer results above the older results. So to make sure you know the order or up-to-dateness of your results, you will have to check the execution numbers and can't rely on the order of the output anymore.

#### Code often ends up very fragmented

This is a logical consequence of my previous two points. People start splitting the chunks and forget to put them back together, lose track of the order of the analysis and it all ends up in a big mess. Good luck exporting it to .R or another native format, because then you will often find bugs, due to outdated code, wrong order, missing variables ...

#### The output is incomplete

This is maybe R specific, but I made an experience that the output is incomplete. Especially if you work with ggplot. Some warning messages don't appear in the notebook, but in the terminal, you started the notebook from. This is annoying, because actually that means that you should check your terminal and your output after every command you run to make sure not to miss warnings and error messages.

#### Potential security risks?

I ain't no security specialist, but the notebook opens a http port. Pray to lord it will not land on 0.0.0.0 host. In that case the whole universe has access to your notebook and thus to your system. I think I should write a crawler which checks for open Jupyter ports on random machines. That will teach you a lesson.

#### Limitation

Good luck writing shiny applications, or neat Rmarkdown presentations/websites/reports.

<hr>

This points are only the ones from the top of my head and I somehow have the feeling, that the list is not complete. What is your experience? I am excited about your comments. 


