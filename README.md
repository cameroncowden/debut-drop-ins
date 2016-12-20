# debut-drop-ins
An open source respository for re-usable shopify sections.

## Usage
While the sections here are styled to match with the Debut theme out of the box, they can be added to any Shopify theme which supports sections (oh, wait, that's _all_ of them.)

## Requirements
Most sections are self-contained, i.e. the section file, in addition to the markup and schema, also contains any javascript and css which is required for its form or function. However, occassionally a section may require an additional file, line, or snippet added elsewhere in the theme. These will be noted accordingly.

## Developing / Understanding Sections
There are two distinct type of sections: homepage sections, and outside sections. A section can be a homepage section, and an outside section, but they will represent separate instances of the section. Homepage sections can be replicated, and have multiple instances of the same section (with unique data) to appear on the homepage. Each outside section is an individual instance of the same section, anywhere a section tag appears, as in: `{% section 'section-name' %}` 

In order for a section to be a homepage section, it just must have a preset block, like this one from the 'featured-blog' section: 

```
"presets": [
    {
      "name": "Blog posts",
      "category": "Blog",
      "settings": {
        "blog": "News",
        "post_limit": "3"
      }
    }
  ]
```
However, placing a {% section 'featured-blog' %} elsewhere in theme will create a section with separate data that is not replicable (even if it is the same section type as a homepage section!).

![Sections Separation Setup](http://drive.google.com/uc?export=view&id=0B8lNRC4OQBCWcm0wVXprX0VEejg)

![Sections Separation](http://drive.google.com/uc?export=view&id=0B8lNRC4OQBCWOW00YTJvNXhkOWM)

It should be noted that blocks are always replicatable, so admin accessible repeatable content models are still possible on interior pages, but at the block level, not the section level. 

As seen here:
![Repeatable Content Rows](https://github.com/cameroncowden/debut-drop-ins/raw/master/images/content-rows.png)




