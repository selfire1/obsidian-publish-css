# Obsidian Publish CSS

The CSS for my Obsidian publish site: [joschuasgarden.com](https://joschuasgarden.com/).

![picture of my digital garden](https://github.com/selfire1/obsidian-publish-css/blob/main/site-overview.png?raw=true)

**Noteworthy inspirations:**
I like to [Steal from my heroes](https://joschuasgarden.com/Steal+from+your+heroes). I copied, changed and pasted a lot to come up with a style I cherish.
* Themes:
    * This theme is built on [Minimal Obsidian 2.5.4](https://github.com/kepano/obsidian-minimal) by @kepano: 
        * Sponsor his work on Patreon: https://www.patreon.com/kepano
    * [Chad Bennet's Publish CSS](https://github.com/chad-bennett/obsidian-publish-css/blob/main/publish.css)
    * [Eric Gregorich's Publish CSS](https://github.com/ericgregorich/Obsidian-Publish-CSS/blob/main/publish.css) 
* Tips:
    * Eric's [Publish CSS tips](https://ericgregorich.com/obsidian-publish-css/)
    * Importing custom fonts tip from [quantumgardener.blog](https://quantumgardener.blog/garden/Changing+the+look+of+your+Obsidian+site+using+fonts+and+CSS)
* Snippets / Inspiration:
    * Callout boxes from [Vileplume](https://github.com/hungsu/vileplume-obsidian)
    * Epistemic status from [devonzuegel](https://devonzuegel.com/post/epistemic-statuses-are-lazy-and-that-is-a-good-thing)
    * Icon from [iconmonstr](https://iconmonstr.com/)

## Special tweaks
### Callout Codeblocks
![picture of callouts](https://github.com/selfire1/obsidian-publish-css/blob/main/site-callout.png?raw=true)

Callouts help to make important things pop out.
Everything I put in three backticks followed by "co" gets formatted this way. ` ```co `

However, since I am using a codeblock, links won't work in here.


```css
pre.language-co {
border-radius: 10px;
border: 1px solid rgba(255,255,255,0.03);
padding: 10px 20px;
position: relative;
box-shadow: -10px -10px 30px rgba(255,255,255,0.05), 10px 10px 30px rgba(0,0,0,0.2);
background-color: var(--background-primary-alt) !important;
}

code.language-co.is-loaded {
  font-family: var(--text);
  white-space: normal;
}
```

### Annotation formatting
I want to include Levels of certainty and effort in some of my notes. Therefore I adapted the highlighting syntax `==…==`. Everything between these two equal signs will get formatted. Links still work.

![picture of annotations](https://github.com/selfire1/obsidian-publish-css/blob/main/annotations.png?raw=true)

```css
/* || Epistemological status styling via Highlighting */
.markdown-preview-view mark {
    background-color: var(--background-primary);
    color: var(--text-faint);
    font-size: var(--font-small);
    font-style: italic;
}

/* unresolved links */
.markdown-preview-view mark .internal-link.internal-link.is-unresolved {
  color: #a4a4a4
}

/* formatting internal links */
.markdown-preview-view mark .internal-link {
  color: var(--text-faint);
  font-style: normal;
}
 /* hover on internal links */
.markdown-preview-view mark .internal-link:hover {
  color: var(--text-faint);
  text-decoration: underline;
  text-decoration-thickness: 2px;
  text-decoration-color: var(--text-accent-hover-rgba);
}

/* Special formatting for "Level of Certainty" and "Level of Effort" */
.markdown-preview-view mark .internal-link[data-href^='Level of Certainty'] {
      font-weight: 500;
      font-style: normal;
      color: var(--text-muted);

}

.markdown-preview-view mark .internal-link[data-href^='Level of Effort'] {
      font-weight: 500;
      font-style: normal;
      color: var(--text-muted);

}
```

### Site logo

![picture of my digital garden](https://github.com/selfire1/obsidian-publish-css/blob/main/site-overview.png?raw=true)

Having a nice logo can make all the difference.

```css
.site-body-left-column-site-name {
  text-align: center;
  margin: 0 auto;
}
.site-body-left-column-site-name::before {
    background: none;
    display: block;
    content: url(path-to-your-logo.png);
    width: 60%;
    margin: 0 auto;
}
```


### Hiding files in navigation
I use this to simplify navigation for the user while keeping the search bar. Be aware that your notes are only *hidden* in the overview, they are still visible in search.

Here, you specify which items you do *not* want to be hidden. So swap these for which ones you want to be *visible*.

```css
.tree-item-self:not([data-path^='Bible Study Kit']):not([data-path^='Scripture (WEB)']):not([data-path^='+Welcome']):not([data-path^='Books MOC']):not([data-path^='Contact me']) {
  display: none;
}
```
***
If you find value for this and want to contribute, I'd love for you to sponsor my reading habit [on patreon](https://www.patreon.com/joschua).