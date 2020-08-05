---
layout: post
title:  "Introducing Jupyter Ascending"
date:   2020-08-04 13:38:42 -0400
categories: python ipython ipynb jupyter_ascending

author: TJ DeVries
---

# Jupyter Ascending

When working with Jupyter Notebooks, I have often found it difficult to find
the best mix of editing and interactivity.

For example, I use [Neovim](https://github.com/neovim/neovim) as my primary
editor for working with code. Obviously, there is no fantasitc way to show
visualizations, plots and interactive widgets within the terminal (and neither
should there be!).

However, I do not like the Jupyter Notebook editor. It doesn't have my
shortcuts, I don't want to learn a bunchy of new navigation shortcuts (which I
realize is ironic, given that I use vim...), and I don't want to keep typing
`:wq!` to save, but accidentally sending it to the notebook.

Even if you're note using a terminal based text editor, I have found that the
Jupyter Notebook extensions for various editors often do not behave _exactly_
like the original web browser version. Not only that, but I have experienced
many crashes while using these extensions.

So, [untitled-ai](https://github.com/untitled-ai) decided to try and make
something that could be the best of both worlds. What we were aiming to do was
to create something that allowed:
1. The ability to use whatever editor you want to edit python files (and just
   python files, not `.ipynb` files.
2. The ability to see the current status of the synced notebook, and execute
cells.

And thus, [Jupyter Ascending](https://github.com/untitled-ai/jupyter_ascending)
was born.


## Example Usage

![Example](/assets/img/simple_jupyter_ascending.gif){: .large-gif }

## How does it work?

Jupyter Ascending contains three major parts.

### Part 1: Jupyter Server Plugin

While not as widely known or used (at least as far as I can tell) it is possible
to write plugins that run on the Jupyter Server -- NOT the Jupyter Notebook.
This allows us to run a http server that can accept requests and multiplex them
to the different Jupyter Notebook Plugins.

This allows us to connect to a Jupyter Server running on a _different computer_
and connect to it.

### Part 2: Jupyter Notebook Plugin

The Jupyter Notebook Plugin runs and listens for commands to execute. It listens
to the Jupyter Server plugin for valid commands and will execute them whenever
required.

### Part 3: Command Line Requests

The part that makes this usable from anywhere is the Command Line interface.
Each of the different requests are defined as an python file that can be
executed.

Each of the different commands are a separate command that can be run.

For example, to sync the state of a file:

```bash
$ python -m \
        jupyter_ascending.requests.sync \
        --filename ./path/to/my_notebook.synced.py
```

Or to execute the cell under your curosr:

```bash
$ python -m \
        jupyter_ascending.requests.execute \
        --filename ./path/to/my_notebook.synced.py \
        --linenumber 13
```

Since the interface is so simple, it is possible to create editor plugins in
almost any editor that supports plugins. For example, we have a vim plugin that
you can find at
[jupyter_ascening.vim](https://github.com/untitled-ai/jupyter_ascending.vim)
which takes less than 50 lines of code to implement (including configuration).





---

