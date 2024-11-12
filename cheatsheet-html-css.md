## HTML/CSS cheatsheet



1. Hint: add background to `<div>` elements temporary, so you can see them on the page when working on layout. Remove background when finished with the layout.

2. `<div>` elements are "block" elements by default (`display: block;`). It means they take 100% width, and no elements will be added to the same row even if you limit div's width. 
- Add "width" property if you need to change the div's width.
- Add `display: inline-block;` if you need to display a div inline<br> ([w3](https://www.w3schools.com/css/css_display_visibility.asp) [mdn](https://developer.mozilla.org/en-US/docs/Web/CSS/display))


3. "top", "left", "right" and "bottom" CSS properties will only work when "position" is specified in the same class. The most common choices for "position" are "relative", "absolute" and "fixed"<br> ([w3](https://www.w3schools.com/css/css_positioning.asp) [mdn](https://developer.mozilla.org/en-US/docs/Web/CSS/position))

4. To center text horizontally in a `<div>`, use <mark>`text-align:center;`</mark>

5. To center div/block element horizontally inside another div:
- Add `margin: 0 auto;` to the child div
- Or add `text-align:center;` to the parent div, similar to the previous item.

6. <b>To center text vertically+horizontally in a div: </b>
- Using flexbox: add the following styles to the div<br> <mark>`display:flex; align-items:center; justify-content:center;`</mark><br> 'text-align' will not work in flexbox.
- Using "line-height" (when you need to center one line text): set line-height equal to the div's height<br>
<mark>`height:200px; line-height:200px; text-align:center;`</mark>

7. To center div/block element horizontally+vertically inside another div:
- If the child height is fixed, you can just calculate top position and add `margin: 0 auto;` to the child div.
- Or use methods from the item above, for centering text in a div.

8. <b>To display div/block elements inline:</b>
- Add `display:inline-block;` to child elements - they will float when there is enough space.
- Add `display:flex;` to the parent `<div>`. Then children will float to the left by default.
- Add `position:absolute;` to child elements and specify "top" and "left"  properties. <br> The parent element can end up with height=0 in this case, so you may need to set the height manually.

9. Different ways to display multiple elements stack to the right:
- add `float:right;` to each div, and adjust order as needed (they will reverse order by default).
- it may be easier to put child divs in another `<div>` and align the container to right.

10. To make image fit inside a div:
- add `width:100%; height:100%; object-fit:cover;` to the image element, if you need a fixed div height. 
- add `width:100%; height:auto;` if you want to allow the div stretch to image height.


11. <b>Different ways to display text over image:</b>
- Using "absolute" text position. <br>
Create a `<div>` with image and text. Use position:absolute and adjust "top"/"left" for the text. Adjust image display as needed - see other hints. 
```html
<div class="image-container">
  <img src="image.jpg" alt="Description">
  <div class="overlay-text">Overlay Text</div>
</div>
```
```css
.image-container {
  position: relative;
  width: 400px;
  height: 200px;
}
.image-container img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
.overlay-text {
  position: absolute;
  text-align: center;
  top: 0;
}
```
- Using "background-image" CSS property:<br>
Create a `<div>` with the text. Add "background-image" property in CSS. Center text if needed - see other hints. Adjust image display as needed - see other hints.
```html
<div class="image-container2">
  <div class="overlay-text2">Overlay Text</div>
</div>
```
```css
.image-container2 {
  background-image: url('image.jpg');
  background-size: cover;
  background-position: center;
  width: 400px;
  height: 200px;
}
```
<br>

12. Understand how to group elements in HTML. <br>
In many cases, the page can be divided into top bar and content section. Use `<div>` elements to create these groups and start building your html with highest level groups, then add details.<br>

13. Keep track of indentation in your HTML file.<br>
Indentation should reflect the hierarchical structure of the elements. 
