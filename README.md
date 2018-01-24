# xmgrace-patch
patch to improve usability of xmgrace

## Additional software

* [libGD](https://libgd.github.io) is reqyuired for bounding boxes of raster image formats. It will be automatically detected.

## How to apply

go to the grace root directory: 

```bash
cd grace-<version>

patch -E -p1 < patch.instup.<version>
```

## Improved functionality

1. Instantaneous Updating

    This patch adds instantaneous updating to the major widgets. Only the
    feature changed gets updated. This means that, for example, the line 
    colour of a set is changed when you select the colour, NOT
    when you press apply. 

    Why is this so great?
    * Well, say I have a bunch of sets for which I selected all the line styles, 
      symbols and colours. Now I want to change the width of all of them
      Traditionally, this would have meant that I would have to go through and
      do every set individually. Now, I can select all the sets and ONLY the 
      line width wll get changed when I select a new line width.
      Imagine this with graphs, axes, etc.
    * I can see the result right away. I do not have to leave the widget and
       hit the apply button.
    * every modern program works like this

    There is a new X resource to control this. By default it is on, but if you want
    the old behavior, put the following line in your ~/.Xresources or ~/.Xdefaults file:
    ```
    XMgrace*InstantUpdate: false
    ```
    
2. Independent major and minor tic directions

3. A `Set Locator Fixed Point` button has been added to the locater menu.

4. PDFs, JPGs and PNGs can be cropped to the minimum bounding box: use the
"Tight BBox" device option from the GUI. The 3 devices now also have the
options to control this, like EPS:
bbox:tight
bbox:page

5. Set comments can be read from a file, one per line, from Edit/Data sets.../Edit/Read set comments

6. Offsets can be applied to Titles and Subtitles to finely control vertical placement

7. Project description added to the Plot window

8. autoscale added to the set menu

9. file with legend captions can now be added on command line


## Acknowledgements

Thanks to Rob Summers for catching some IU bugs.
