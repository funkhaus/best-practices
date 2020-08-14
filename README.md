# Funkhaus best practices
A running list of best practices. All our programmers should read this and understand each item.

This list formed the bais for a presentation at VueJS LA meetup on January 14, 2020 by Drew Baker. You can see the slides [here](https://docs.google.com/presentation/d/1xMqvylzoIwpEgwFEpXI8it_HGo7BUGrt8h65E0nvEQo/edit?usp=sharing).

## Basics
1.  No CSS resets
1.  Be semantic - call things what they are. Name your component what the filename is, and give it a class that matches.
1.  In Vue templates, use components like `<component-name/>` not like `<ComponentName>`.
1.  Avoid use of element name selectors in CSS. Don't use `h2`, give it a `.title` class instead.
1.  In general avoid use of CSS pseudo elements like `:content`, `:before`, `:after`. Except for list bullets or underlines.
1.  No use of floats
1.  Don’t use `#` ID’s unless using for JS selectors or actually need page anchors.
1.  Use a central z-index location for major structural components, increment by 100’s
1.  For component level z-index set top level to 0 and increment by 10
1.  Use positioning sparingly. In general most people over use `position:absolute`.
1.  If using useless markup to get a desired style, you’re doing it wrong. For example wrapping divs, centering divs.
1.  Define CSS for active and hover states at the end of component, followed by breakpoints at end of file please!
1.  When using SCSS if you’re going more than 2 levels deep, question yourself. Think of the top level element class as a namespace, so things in it don’t need namespaces too.
1.  Never use background-images, use object-fit with src-set instead.
1.  For class names use is-{state} and has-{feature} or not-{type}. Like is-active, is-opened, has-video, not-case-study, is-active.
1.  Common element class names: block, grid, panel, menu, overlay, meta, title, section, section-title.
1.  Margin top/bottom, padding left/right.
1.  Use lodash! You’re not getting points for using map() and filter() in inventive ways!
1.  Don’t fight the browser - scroll, events, URLs etc…
1.  With Nuxt-Link or Router-Link use relative paths from the root (start with a `/`).
1.  Use white spacing in your templates.
1.  Order your CSS in the same order your markup is in. Top to bottom as coded.
1.  A `switch` statement is better than a lot of if-else conditions
1.  [This is how you do forms in Vue.](https://alligator.io/vuejs/vue-form-handling/)
1.  100vh doesn't work great on mobile. [See this for how to do it right](https://stackoverflow.com/questions/58886797/how-to-access-the-real-100vh-on-ios-in-css).
1.  Don't use icon fonts, use SVGs. SVGO is a good tool for optimizing SVGs.
    1.  Be sure to include the `viewBox` attribute.
1.  This is [a good clean sample](https://github.com/funkhaus/factory/blob/master/src/components/WorkBlock/BlockWork.vue) component to study.

## Important Concepts
1.  We care about Chrome, Safari and Firefox in that order.
1.  You can write breakpoints without needing a media query generally. Often using width and max-width is enough. Good break points will really just be font-size and reducing columns perhaps.
1.  Understand collapsible margins!
1.  Understand intrinsic ratio sizing!
1.  Understand when to use wp-content, v-html, v-text
1.  Clean up after yourself, don’t leave behind old code!

## Be better at:
1.  Drew to show everyone how to build top-panel/bottom-panel style fixed sliding sites
1.  Really think hard about what can be a component. Makes a site so hard if you don’t use components.
1.  Know what components and tools.js we have in [fuxt](https://github.com/funkhaus/fuxt) and our [haus components](https://github.com/funkhaus/components)!
1.  Don’t do things rough with the expectation of coming back to it. Do it right the first time, think it through.
1.  Add head() data for SEO as you build each pages. Sucks to do this at the end.
1.  Learn how to spot red flags. Long file? Deep nested CSS? Watching a lot of things? Lots of specific break points? Committing to the store a lot?
1.  Organize your windows into panels or editor and browser and dev tools.
1.  Use Prettier along with the linting tools built into [fuxt](https://github.com/funkhaus/fuxt).

## Useful tools:
1.  [Demystifing Nth-Child in CSS](http://www.nealgrosskopf.com/tech/resources/80/)
1.  [Flexy Boxes Playground](https://the-echoplex.net/flexyboxes/)
1.  [CSS Grid Generator](https://cssgrid-generator.netlify.com/)
1.  [16:9 calculator](https://www.size43.com/16by9-aspect-ratio-calculator/)
1.  [Clippy](https://bennettfeely.com/clippy/)
1.  [Facebook OG debugger](https://developers.facebook.com/tools/debug/)

## Good reading:
1.  [The introduction to Reactive Programming you've been missing](https://gist.github.com/staltz/868e7e9bc2a7b8c1f754)
1.  [You (Might) Don't Need jQuery](https://github.com/nefe/You-Dont-Need-jQuery)
1.  [A Smashing Guide To The World Of Search Engine Optimization](https://www.smashingmagazine.com/smashing-guide-search-engine-optimization/)
