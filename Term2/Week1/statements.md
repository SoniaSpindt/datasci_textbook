---
jupytext:
  formats: md:myst
  text_representation:
    extension: .md
    format_name: myst
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---

Statements
==========
<br>Before you start reading, please wait until it says <b><i>ready</i></b> above. :)

<hr>

```{epigraph}
To understand a program you must become both the machine and the program.

-- Alan Perlis
```
Like Dr. Perlis, I am convinced that you need to know a little bit about how your computer works in order to better understand how to control them with the programs you write. I hope that by explicitly naming some of the underlying components of your computer, you will be better able to explain and predict all of its observable behavior. This ability will not only help you do really well in this class, but it will give you an edge in future programming classes that you take. :)

Programming can dramatically improve our ability to collect and analyze information about the world, which in turn can lead to some pretty awesome discoveries. In data science, the purpose of writing a program is to instruct a computer to carry out the steps of data analysis. Computers cannot study the world on their own. People must describe precisely what steps the computer should take in order to collect and analyze data, and those steps are expressed through programs.

In this class, we will create these programs with a programming language called <b>Python</b>[^*], and we will begin our exploration of the machine by discussing the general life-cycle of a program. This life-cycle starts with you! How? Well, one day you will decide that you need a Python program in your life --- maybe that day is today! In order to write this program, you must first create a new file. Think of this like opening a new Google Doc for an essay you need to write. However, instead of writing English sentences in a <b>.doc</b> file, you will write lines of code in a <b>.py</b> file.

Now imagine that you were super productive and wrote a bit of Python code into your <b>.py</b> file. It looks like this:

```{code-cell} python3
 print("Hello, world!")    
```
Don't panic! It's normal to look at this code and think it makes no sense! We will talk about the specifics of this code over the next few weeks. For now, I want you to know that this line of code represents something we call a <b><i>statement</i></b> in Python. A statement is an action that we ask our computers to perform. Our Python programs will be riddled with statements because this is how we actually get our computers to do stuff. In this example, I am asking my computer to display the sentence "Hello, world!". That's an action. The computer must read this line of code and then DO something (i.e. display the sentence).

What would happen if we gave our computer the following program?

```{code-cell} python3

print("I'm a savage")  
print("Classy, bougie, ratchet")
print("Sassy, moody, nasty")
print("Acting stupid, what's happening?")

```
Go ahead! Click on the run button! :)

As you can see, your computer instantly spits out the chorus of Megan Thee Stallion's song Savage. This may feel like magic but it's not! In reality, some super awesome software is systematically working behind the scenes to display these lyrics for you. The details of how this works is outside the scope of this class, but you should  know that your computer starts at the top of your program and works its way down until it has read every line of code that you wrote in your program.

What other things do we find in our Python programs?

[^*]: Python is an incredibly versatile and powerful language. <a href="https://www.goskills.com/Development/Resources/Why-is-Python-so-popular">Check this article out if you want to know more about it.</a>
