---
title: `top` - Pluto Planet Template Pack
---

## Screenshot - Preview

![](i/screenshot-top.png)


## Usage

### Try It Yourself - How To Use the Top Template Pack

If you want to try it yourself, install (fetch) the new template pack. Issue the command:

    $ pluto install top

Or as an alternative clone the template pack using `git`. Issue the commands:

    $ cd ~/.pluto
    $ git clone git://github.com/planet-templates/pluto.top.git

To check if the new template got installed, use the `list` command:

    $ pluto list

Listing something like:

    Installed templates include:
       top (~/.pluto/top/top.txt)

Showtime! Let's use the `-t/--template` switch to build a sample Planet Ruby. Example:

     $ pluto build ruby.yml --template top     or
     $ pluto b ruby -t top

Open up the generated planet page `ruby.html` in your browser. Voila. That's it.
