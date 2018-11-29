# OSM JS
A collection of useful JavaScript bookmarklets for OpenStreetMap.

### What is a Bookmarklet?
A bookmarklet is a simple Javascript snippet added as a bookmark link, which can be used to do cool things with pages.  
Clicking the 'link' will run the JS, which can be useful in different situations.  
Code can also be imported from external sources, allowing for very complex things to happen.  
Common examples include sharing the page on a social media platform or changing all images to doges.

## Index
  - [Note Forward](#note-forward)
  - [Note Backward](#note-backward)
  - [Changeset Forward](#changeset-forward)
  - [Changeset Backward](#changeset-backward)
  - [This User on HDYC](#this-user-on-hdyc)

***

# The Bookmarklets

## Note Forward
For navigating through OSM.org notes in chronological order.

#### Process

  1. Extract current note number from `window.location.href`
    - `var re = /(?:\.org\/(?:note\/)?)(\d+)/;` does the job nicely, regardless of the URL
  2. Increment that by 1
  3. Redirect to `"https://osm.org/note/" + note`

#### What Should Work But Doesn't
```
window.location.replace(
  window.location.href.replace(
    /(?:\.org\/(?:note\/)?)(\d+)/,
    Number("$1") + 1
  )
);
```
<a href="javascript:(function(){var a=/(?:\.org\/(?:note\/)?)(\d+)/.match(window.location.href);window.location.replace(a[0],a[0]+1);})()'">Next Note</a>

## Note Backward
Indentical to [Note Forward](#note-forward), only subtracting from the note value.


## Changeset Forward
Similar to [Note Forward](#note-forward) but for cycling through changesets.


## Changeset Backward
See [Changeset Forward](#changeset-forward).


## This User on HDYC
For when on a user's profile on OSM.org. Will redirect to that user's hdyc.neis-one.org's page.

