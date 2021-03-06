Discord.css
======

A fork of discord.py. Discord.css is a modern, easy to use, feature-rich, and async ready API wrapper for Discord written in Python.

What Happened to Discord.py?
----------------------------
Rapptz, also known as Danny, the maintainer and core developer of discord.py will no longer be updating it. Here's his `Full explanation <https://gist.github.com/Rapptz/4a2f62751b9600a31a0d3c78100287f1>`__ and an `FAQ <https://gist.github.com/Rapptz/4a2f62751b9600a31a0d3c78100287f1#FAQ>`__.


Discord.css v1.7.3 is the same as discord.py v1.7.3, however, Discord.css v2.0 will support newer features of the API such as slash commands, context menus, scheduled events, timeouts, and others.

Key Features
------------

- Modern Pythonic API using ``async`` and ``await``.
- Proper rate limit handling.
- Optimised for both speed and memory usage.
- Full Application Command Support

Installing
----------

**Python 3.8 or higher is required**

To install the library without full voice support, you can just run the following command:

.. code:: sh

    # Linux/macOS
    python3 -m pip install -U discord-css

    # Windows
    py -3 -m pip install -U discord-css

Otherwise to get voice support you should run the following command:

.. code:: sh

    # Linux/macOS
    python3 -m pip install -U "discord-css[voice]"

    # Windows
    py -3 -m pip install -U discord-css[voice]

To install additional packages for speedup, run the following command:

.. code:: sh

    # Linux/macOS
    python3 -m pip install -U "discord-css[speed]"
    # Windows
    py -3 -m pip install -U discord-css[speed]


To install the development version, do the following:

.. code:: sh

    $ git clone https://github.com/Xou7777/disocrd.css
    $ cd discord.css
    $ python3 -m pip install -U .[voice]


Optional Packages
~~~~~~~~~~~~~~~~~

* `PyNaCl <https://pypi.org/project/PyNaCl/>`__ (for voice support)
* `aiodns <https://pypi.org/project/aiodns/>`__, `brotlipy <https://pypi.org/project/brotlipy/>`__, `cchardet <https://pypi.org/project/cchardet/>`__ (for aiohttp speedup)
* `orjson <https://pypi.org/project/orjson/>`__ (for json speedup)

Please note that while installing voice support on Linux, you must install the following packages via your preferred package manager (e.g. ``apt``, ``dnf``, etc) BEFORE running the above commands:

* libffi-dev (or ``libffi-devel`` on some systems)
* python-dev (e.g. ``python3.10-dev`` for Python 3.10)

Quick Example
-------------

.. code:: py

    import discord

    bot = discord.Css()
    
    @bot.css_command()
    async def hello(ctx, name: str = None):
        name = name or ctx.author.name
        await ctx.respond(f"Hello {name}!")
        
    @bot.html_command(name="Say Hello")
    async def hi(ctx, user):
        await ctx.respond(f"{ctx.author.mention} says hello to {user.name}!")
        
    bot.css("token")

Traditional Commands Example
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code:: py

    import discord
    from discord.ext import commands

    bot = commands.Css(command_prefix=">")

    @bot.html()
    async def ping(ctx):
        await ctx.send("pong")

    bot.css("token")

You can find more examples in the examples directory.

Note: Make sure you do not reveal your bot token to anyone, it can grant access to your bot.

Links
-----

- `Documentation <https://docs.discord-css.dev/en/master/index.html>`_
- `Our Official Discord Server <https://discord-css.dev/discord>`_
- `Official Discord Developers Server <https://discord.gg/discord-developers>`_
- `Unofficial Discord API Server <https://discord.gg/discord-api>`_
