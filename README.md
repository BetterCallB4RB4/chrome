# Disclaimer
This repository has been cloned and is provided solely for archive purposes in relation to the Morro Linux guide. The contents of this repository are not officially supported by the Morro Linux project, and are intended to demonstrate or assist with the steps described in the accompanying guide. Use this repository at your own risk, and ensure you follow all instructions carefully to avoid issues with your system.
We do not guarantee the accuracy, completeness, or functionality of the files within this repository. Please exercise caution and refer to the official Morro Linux documentation and community resources for any official guidance or support.
Graphical aspect may vary depending on your choices in following the instructions below, but the end result should look something like this:

# Original Guide
https://gist.github.com/morrolinux/87aa37396432ea5d14a9220bc4892100
https://www.youtube.com/watch?v=po0ocIrTkHg

# Sync your firefox account
set up you default add-on bookmark and personalization 
## add-ons:
Vimium
Sideberry
Containers
Darkreader
AWS SSO container
Color Zilla


# Enable Firefox features

Go to `about:config` and set all of the following to `true`:
```
    toolkit.legacyUserProfileCustomizations.stylesheets
    layers.acceleration.force-enabled
    gfx.webrender.all
    gfx.webrender.enabled
    layout.css.backdrop-filter.enabled
    svg.context-properties.content.enabled
    
    # LINUX ONLY - WORKAROUND FOR BAR HIDING ON DRAG EVENT
    widget.gtk.ignore-bogus-leave-notify = 1
```

# clone this repository with the userChrome.css in the profileDirecotry 

1. Find your Firefox profile folder (`about:support` --> "Profile Directory") 
2. Create a folder named `chrome` inside it.
3. Create a file named `userChrome.css` inside the `chrome` folder you just created.
4. Paste in `userChrome.css` whatever you like from above
5. Restart Firefox for changes to take effect. **If nothing changes**, try going to `about:profiles` and click the "Restart Normally" button in the upper right portion of the screen. Thanks @kr1s7ian for pointing this out.

And then go to `Sidebery settings` > `General` > `Preface value`, enable it and set it to `XXX`.

Now You also need to remove indent when the bar is collapsed, or you won't be able to see all tabs

Go to `SideBery settings` --> `Styles editor` and add:

```
#root:not(:hover){
  --tabs-indent: 0;
}
```
