---
layout: post
title:  "Introducing Jupyter Ascending"
date:   2020-09-23 13:38:42 -0400
categories: python ipython ipynb jupyter_ascending

author: <a href="https://github.com/tjdevries">TJ DeVries</a>
---

# Jupyter Ascending

When working with Jupyter notebooks, I have often found it difficult to find
the best mix of editing utility and interactivity.

For example, I use [Neovim](https://github.com/neovim/neovim) as my primary
editor for working with code. Obviously, there is no fantastic way to show
visualizations, plots, and interactive widgets within the terminal (nor
should there be).

However, I do not like the Jupyter notebook editor; it doesn't have my
shortcuts. I don't want to learn a bunch of new navigation shortcuts,
and I don't want to keep typing `:wq!` to save while accidentally sending it to the notebook.

If you're using an IDE like PyCharm or VS Code,
you may be able to start a Jupyter notebook from within the IDE and access
all your normal editor features. But, at least in PyCharm, you can't readily work on Jupyter notebooks hosted on remote servers - which is our normal development workflow.

So, [Generally Intelligent](https://github.com/untitled-ai) decided to try and make
something that could be the best of both worlds. What we were aiming to do was
to create something that allowed:
1. The ability to use whatever editor you want to edit python files (and just
   python files, not `.ipynb` files).
2. The ability to see the current status of the synced notebook, and execute
cells.
3. The ability to work locally as well as on remote servers.

And thus, [Jupyter Ascending](https://github.com/untitled-ai/jupyter_ascending)
was born.

## What is it?

![Example](/assets/img/simple_jupyter_ascending.gif)

Jupyter Ascending is a tool that enables you to edit Jupyter notebooks from your favorite code editor. You edit a normal python file, and Jupyter Ascending syncs the code into a Jupyter notebook. This allows you to keep everything you like about your editor/IDE, like keybindings, autocomplete, etc. while also getting the interactivity and visualization that Jupyter provides.

We like to use an editor side-by-side with the Jupyter notebook open in a browser (as shown in the GIF above). You create a `my_cool_script.sync.py` file which is paired with `my_cool_script.sync.ipynb`. You edit your code in the `.sync.py` file, using `# %%` to indicate breaks between notebook cells. The code auto-syncs into the notebook using a hook/plugin in your editor that sends the code to a plugin in the Jupyter server. You can also forward keyboard shortcuts from your editor for notebook commands like "run cell," "run all cells," etc. That way, you never have to leave your editor, but can see all the outputs in the notebook as you run cells.

Because of the client-server architecture, you can also sync your code to a remote jupyter notebook. This lets you have all the power of a beefy dev-server with all the convenience of editing code locally.

We have example plugins or configuration instructions for using Jupyter Ascending in Visual Studio Code, PyCharm, and Vim. Adding other editor integrations is easy!

## How does it work?

Jupyter Ascending contains three major parts:

### Part 1: Jupyter Server Plugin

While this is not widely known or used (at least as far as I can tell), it is possible
to write plugins that run on the Jupyter server - NOT the Jupyter notebook.
This allows us to add a new HTTP request handler to take commands and multiplex them
to the different Jupyter notebook plugins. This also allows us to connect to a Jupyter server running on a _different computer_ and connect to it.

### Part 2: Jupyter Notebook Plugin

The Jupyter notebook plugin runs and listens for commands to execute. It listens
to the Jupyter server plugin for valid commands and will execute them whenever
required.

### Part 3: Command Line Requests

The part that makes this usable from anywhere is the Command Line Interface.
Each of the different requests are defined as an python file that can be
executed. Each of the different commands are a separate command that can be run.

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
almost any editor that supports plugins. For example, [our vim plugin](https://github.com/untitled-ai/jupyter_ascending.vim) takes less than 50 lines of code to implement (including configuration)!

## Try it out!

We hope this tool is useful for others. Please feel free to try it out and give us feedback!

---

