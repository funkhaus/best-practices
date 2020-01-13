# Funkhaus best practices
A running list of best practices. All our programmers should read this and understand each item.

## Basics
1.  No resets
1.  Call things what they are, semantically.
1.  Name your component what the file name is, and give it a class that matches.
1.  Avoid use of element name selectors in CSS
1.  In general avoid use of CSS pseudo elements like content, before, after. Except for list bullets or underlines.
1.  No use of floats
1.  Don’t use # ID’s unless using for JS selectors or actually need page anchors.
1.  Use a central z-index location for major structural components, increment by 100’s
1.  For component level z-index set top level to 0 and increment by 10
1.  Use positioning sparingly. In general you over use position absolute.
1.  If using useless markup to get a desired style, you’re doing it wrong. For example wrapping divs, centering divs.
1.  Active, hover states at the end of component, followed by breakpoints at end of file please!
1.  When using scss if you’re going more than 2 levels deep, question yourself. Think of the top level element class as a namespace, so things in it don’t need namespaces too.
1.  Never use background-images, use object-fit with src-set instead.
1.  We care about Firefox, Chrome and Safari.
1.  For class names use is-{state} and has-{feature} or not-{type}. Like is-active, is-opened, has-video, not-case-study, is-active.
1.  Common element classes block, grid, panel, menu, overlay, meta, title, section, section-title
1.  Margin top/bottom, padding left/right.
1.  Use lodash! You’re not getting points for using map() and filter() in inventive ways!
1.  Don’t fight the browser - scroll, events, URLs etc…
1.  With Nuxt-Link or Router-Link use relative paths from the root (start with a /).
1.  Use white spacing in your templates
1.  Switch is better than a lot of if-else conditions 
1.  This is how you do forms: https://alligator.io/vuejs/vue-form-handling/
1.  100vh doesn't work great on mobile. See this for how to do it right: https://stackoverflow.com/questions/58886797/how-to-access-the-real-100vh-on-ios-in-css

## Important Concepts
1.  You can write breakpoints without needing a media query, generally just use width and max-width. Good break points will really just be font-size and reducing columns perhaps.
1.  Understand collapsable margins!
1.  Understand intrinsic ratio sizing!
1.  When to use wp-content, v-html, v-text
1.  Clean up after yourself, don’t leave behind old code

## Be better at:
1.  Drew to show everyone how to build top-panel/bottom-panel style fixed sliding sites
1.  Really think hard about what can be a component. Makes a site so hard if you don’t use components.
1.  Know what components we have in Haus Components!
1.  Don’t do things rough with the expectation of coming back to it. Do it right the first time, think it through.
1.  Add head() data for SEO as you build each pages. Sucks to do this at the end.
1.  Learn how to spot red flags. Long file? Deep nested CSS? Watching a lot of things? Lots of specific break points? Committing to the store a lot?
1.  Organize your windows into panels or editor and browser and dev tools.
1.  Use Prettier along with the linting tools built into Stackhaus.
