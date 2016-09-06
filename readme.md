# CSS Review

## Learning Objectives

- Describe what on a webpage can be modified with CSS, and what cannot
- Identify CSS methods that can replace bad habits in HTML
- Properly separate the concerns of semantics and style
- Identify the components of the box model
- Differentiate between border-box and content-box values for box-sizing

## Framing (5 minutes / 0:05)

### What Is CSS?

> Cascading Style Sheets are what make webpages look like more than just words on a page. HTML's only purpose is to say what purpose chunks of content serve; CSS's only purpose is to say what a chunk with a certain purpose should look like.

This lesson is going to be almost entirely you working through some exercises we have prepared for you. You will not turn in these exercises.

These exercises may use CSS properties with which you're unfamiliar. In fact, you may not be familiar with CSS at all.

## HTML / CSS Review (5 minutes / 0:10)

See the [slides](html_css_review.pdf).

### The Three Places CSS can go (5 minutes / 0:15)

#### Inline Styles (Bad)

```html
<section>
  <article style='border-bottom: 1px solid black;'>
     ...
  </article>
</section>
```

#### Internal Styles (Better)

```html
<!doctype html>
<html>
  <head>
    <style>
      article {
        border-bottom: 1px solid black;
      }
    </style>
  </head>
  <body>
    <section>
      <article>
	 ...
      </article>
    </section>
  </body>
</html>
```

#### External Styles (Best)

```html
<!doctype html>
<html>
  <head>
    <link rel='stylesheet' type='text/css' href='styles.css'>
  </head>
  <body>
    <section>
      <article>
	 ...
      </article>
    </section>
  </body>
</html>
```

```css
/* styles.css */

article {
  border-bottom: 1px solid black;
}
```

### Selecting Elements - Memorize (5 minutes / 0:20)

| Pattern   | Meaning                                             |
|:----------|:----------------------------------------------------|
| *         | any element                                         |
| E         | an element of type E                                |
| E, F      | any element of type E and any element with type F   |
| #myid     | any element with ID equal to "myid"                 |
| .myclass  | any element with class equal to "myclass"           |
| E#myid    | an E element with ID equal to "myid"                |
| E.myclass | an E element with class equal to "myclass"          |
| E F       | an F element child of an E element                  |
| E > F     | an F element that is a direct child of an E element |

> [And many more!](https://www.w3.org/TR/css3-selectors/#selectors)

Children vs. Descendants - [css tricks child & siblings](https://css-tricks.com/child-and-sibling-selectors/)

![children](https://css-tricks.com/wp-content/csstricks-uploads/child-combinator-selector-example.png)

## You Do: [CSS Diner](http://flukeout.github.io/) (10 minutes / 0:30)

### What Should You Do If Something Is Unfamiliar?

> 1. Read it like English. CSS is intended to be readable, although sometimes it's more successful than at other times.
> 2. Look it up. If you don't know what `box-sizing` means, Google `css box-sizing`.

The purpose of this class isn't for you to walk away being an expert in all things CSS. That takes months. Rather, it's for you to be exposed to all the things that can be accomplished with CSS. If they're on your radar, you can always look them up later.

## You Do: CSS Crash Course (30 minutes / 1:00)

Please count off from 1 to `[class size / 2]`. In pairs, please work to complete this exercise:

[CSS Review Exercise](https://github.com/ga-wdi-exercises/css-review)

Please complete them in this order...
1. Selectors  
2. Sizing  
3. Positioning  

### Questions (10 minutes / 1:10)

### Units

| Unit | Description                                                                                                                                                                                                                                            |
|:-----|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| px   | Relative to the viewing device. For screen display, typically one device pixel (dot) of the display. For printers and very high resolution screens one CSS pixel implies multiple device pixels, so that the number of pixel per inch stays around 96. |
| %    | Relative to the containing block                                                                                                                                                                                                                       |
| em   | Relative to the font-size of the element (2em means 2 times the size of the current font)                                                                                                                                                              |
| rem  | Relative to font-size of the root element                                                                                                                                                                                                              |
| vw   | Relative to 1% of the width of the viewport                                                                                                                                                                                                            |
| vh   | Relative to 1% of the height of the viewport                                                                                                                                                                                                           |

> [More Units](http://www.w3schools.com/cssref/css_units.asp)  
> [MDN Docs](https://developer.mozilla.org/en-US/docs/Web/CSS/length)  

### `box-sizing: border-box;`

![](https://dl.dropbox.com/s/d1fk9mu23q0byhh/Screenshot%202016-05-25%2009.08.53.png?dl=0)

The Box Model explains how CSS `width` is Calculated. By default, how wide an element is on the page is a combination of `width` + `padding` + `border` and the rendered `height` = `height` + `padding` + `border`. This can be problematic when trying to create a layout or position things logically on the page.

The [box-sizing: border-box;](http://codepen.io/team/css-tricks/pen/970f26f621cfa3ae3eec7e2a6b0e8c97) property incorporates the size of the border and padding into the rendered width.

> If I say the width is 200px, gosh darn it, it’s gonna be a 200px wide box even if I have 20px of padding. - Paul Irish on box-sizing

## Break (10 minutes / 1:20)

## You Do: Ghost CSS (30 minutes / 1:50)

Please count off again, and complete this exercise:

[CSS Ghost](https://github.com/ga-wdi-exercises/css-ghost)

### Questions (10 minutes / 2:00)

## You Do: Hyrule Potion Shop (20 minutes / 2:20)

<!-- AM: Need to replace this with some other exercise. -->

Please count off again, and complete this exercise:

[Hyrule Potion Shop](https://github.com/ga-wdi-exercises/hyrule_potion_shop)

### Closing / Questions (10 minutes / 2:30)

There are over 500 CSS properties. It's impossible to memorize them. The key is to just get an idea of what you can accomplish with CSS, and then know what to Google.

### Tools That Can Help

**[The CSS Validator](http://jigsaw.w3.org/css-validator/#validate_by_input)** is a tool into which you can copy and paste your CSS, and it'll tell you precisely what's wrong with it. We'll be expecting you to validate your CSS during this course.

**The Chrome element inspector** lets you look at a specific element on a page, see exactly which CSS rules are being applied to it, and turn those rules on and off and modify them. It doesn't change your file; refresh the page, and the changes are gone.

-----

## Quiz Questions

- What is the purpose of `flex-box`?
- What does `*` select?
- What does `box-sizing:border-box` do?
- What's the difference between `position:relative`, `position:absolute`, and `position:fixed`?
- What's the difference between borders, margins, and padding?
- What's the difference between an outline and a border?
- How would you apply styles only for screens narrower than 480 pixels?

## Further Reading

- [Shay Howe's HTML/CSS Guide](http://learn.shayhowe.com)
- [LearnLayout.com](http://learnlayout.com/)
  - An great interactive tutorial that details CSS' many properties and quirks.
- [W3Schools CSS Reference](http://www.w3schools.com/cssref/default.asp)
  - Almost every CSS property ever.
- [Mozilla Developer Network CSS Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference)
  - Like W3Schools, but in *much* more detail.
- [CanIUse.com](http://caniuse.com/)
  - Search for a CSS property (or HTML, or JS), and it'll tell you on which web browsers it functions.
- [CSS Validator](https://jigsaw.w3.org/css-validator/#validate_by_input)
  - Copy and paste your CSS in here and it tells you what's wrong with it.
- [CSS Tricks Almanac](https://css-tricks.com/almanac/)
  - A list of css selectors and properties
- [CSS Units - em vs px etc](http://kyleschaeffer.com/development/css-font-size-em-vs-px-vs-pt-vs/)

## Additional Resources

- [Codrops](http://tympanus.net/codrops/)
- [Codyhouse](https://codyhouse.co/library/)
