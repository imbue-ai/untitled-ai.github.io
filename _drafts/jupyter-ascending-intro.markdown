---
layout: post
title:  "Introducing Jupyter Ascending"
date:   2020-09-23 13:38:42 -0400
categories: python ipython ipynb jupyter_ascending

author: <a href="https://github.com/tjdevries">TJ DeVries</a>
---

# Jupyter Ascending

TL;DR: We're open-sourcing a tool that syncs your Jupyter notebooks to your favorite code editor so you can enjoy the best of both worlds!

![Jupyter Ascending](https://github.com/untitled-ai/jupyter_ascending/blob/main/media/demo.gif)

## Motivation

Jupyter notebooks are powerful tools for visualization and interactive code development, but they lack the full support (e.g. autocomplete, keybindings, refactoring tools) of your favorite code editor. We decided to build and open-source a tool that would combine the advantages of both, allowing the user to:
1. Use any code editor to work directly on Python files
2. Execute cells in a synced Jupyter notebook
3. Work locally as well as on remote servers

And thus [Jupyter Ascending](https://github.com/untitled-ai/jupyter_ascending) was born!

## How we use it

![Example](/assets/img/simple_jupyter_ascending.gif)

We like to use our editor side-by-side with our Jupyter notebook open in a browser (as shown in the GIF above). 

After creating `our_cool_script.sync.py`, we edit our code directly here, using `# %%` to indicate breaks between notebook cells. The code auto-syncs with its paired `our_cool_script.sync.ipynb` file. We can forward keyboard shortcuts from our editor for notebook commands like "run cell," "run all cells," etc. That way, we see the outputs in our notebook without ever leaving our editor.

Because of the client-server architecture, we can also sync our code to a remote Jupyter notebook. This lets us have all the power of a beefy dev-server with all the convenience of editing code locally.

We have example plugins or configuration instructions for using Jupyter Ascending in Visual Studio Code, PyCharm, and Vim. Adding other editor integrations is easy; since the interface is so simple, it is possible to create editor plugins in almost any editor that supports plugins. For example, [our Vim plugin](https://github.com/untitled-ai/jupyter_ascending.vim) takes less than 50 lines of code to implement (including configuration)!

## Your turn

We hope you [try it out](https://github.com/untitled-ai/jupyter_ascending)! We want this tool to be helpful for others, so please feel free to open issues on GitHub or reach out to us directly with questions and feedback. Have fun!

---

